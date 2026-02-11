<!-- loio35c4caf989f942c6959bc5ac27b45033 -->

# Monitoring Scenarios that Include Message Queues

Learn more about monitoring scenarios that include message queues and possible error situations.



<a name="loio35c4caf989f942c6959bc5ac27b45033__section_hnm_qqm_jyb"/>

## JMS Message Processing and Quality of Service

When monitoring message processing of integration flows that contain JMS message queues \(in the *Monitor Message Processing* area\), you notice that in most cases each message is processed exactly once. However, in rare cases a message processing log suggests that there’s an inconsistency indicating that a message has been processed more than once from a message queue. If Cloud Integration sends this message to a receiver system \(for example, using a SOAP channel\) and the receiver system isn't prepared for this, it can lead to problems.

The JMS broker doesn't provide exactly once processing. For non-exclusive queues, there are cases when a message is processed more than once and even in parallel by different consumers. This can happen, for example, when during processing from the JMS message queue the connection to the JMS broker gets lost. The reason for this is that when the connection is interrupted, the lock on the message held by the broker is released \(so the message becomes available for redelivery\).

For exclusive queues, retry and inconsistencies are handled differently, and exactly once in order processing can be achieved if the connection remains healthy.

> ### Note:  
> There are two different queue types that affect how messages are processed.
> 
> -   Non-Exclusive Queues: Allow multiple consumers to process messages in parallel, which can lead to messages being processed more than once if connections are lost or interrupted.
> -   Exclusive Queues: Restrict message processing to a single consumer at a time, ensuring ordered processing.



## Duplicate Processing and Receiver Impact

When a message is processed by one consumer \(an integration flow deployed on a Cloud Integration worker node\), the JMS broker writes a lock entry that makes sure that no other consumer starts processing the same message. Exclusive queues inherently handle this with ordered processing, but for non-exclusive queues, if the connection between the consumer \(Cloud Integration\) and the JMS broker is interrupted, the lock is released. In this case, another consumer can begin processing the same message.

For example, consider the following scenario:

-   Consumer 1 starts processing a message from the message queue. During this step, the connection to the JMS broker gets lost.
-   Because Consumer 1 never acknowledges the message after the connection is lost, the JMS broker can redeliver it to another consumer.
-   Consumer 1 doesn't have any information that the connection was lost and still tries to process the message.
-   During this period, another consumer \(Consumer 2\) starts to process the same message.

If the receiver adapter used to send the final message to another system does not support exactly once message processing, such behavior can lead to inconsistencies.

If the receiver adapter does support exactly once processing, the JMS broker may still deliver the message more than once, but the receiver ensures that each message is processed only once. This means that, from the receiver's perspective, the application data remains consistent even if duplicates are sent.

However, configuring exactly once processing on the JMS adapter alone does not guarantee end‑to‑end exactly‑once delivery — broker redelivery and receiver‑side semantics \(for example, deduplication or idempotent processing\) also matter.

Furthermore, the functionality to reprocess a message builds on the assumption that JMS processes a message exactly once. If, in rare cases, this assumption is incorrect, runtime retries may not behave as configured. In such a case, based on the JMS processing Cloud Integration *can assume* a worker-node failure \(which can happen, for example, caused by an out-of-memory situation\) and apply its platform retry logic. In that case, the retry interval is set to 18 minutes.

> ### Note:  
> For exclusive queues, the retry is managed by the JMS broker and doesn't utilize separate error queues as in non-exclusive queues.

To mitigate such problems, use an adapter that supports exactly once processing where possible \(for example, the XI adapter\). For more information on the different options to design integration scenarios with exactly once processing, see:[Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md)



<a name="loio35c4caf989f942c6959bc5ac27b45033__section_uxf_qqm_jyb"/>

## Retry Process

If messages fail during processing from a queue, a retry of the message is triggered. The JMS sender adapter allows you to configure message retry, for example, to set a specific retry interval \(see [Configure the JMS Sender Adapter](configure-the-jms-sender-adapter-161791b.md)\).

However, in specific cases, the message is processed differently than expected from the retry configuration.

Note the following aspects related to retry processing for non-exclusive queues:

-   **Normal retry**

    In general, JMS transactions are used to process messages. A retry from the JMS broker is performed when a rollback occurs.

    The JMS transaction is finished after the message processing log \(MPL\) status is set. If an error occurs in the commit or rollback phase of the JMS session, the MPL status is adapted in most cases. However, some cases aren't covered. In these cases, the message status is set to *Completed*. That means that retries can occur even if the log shows success.

-   **Broker retries**

    The JMS broker immediately retries the message. This behavior can’t be changed. Since this retry is too fast for almost all applications in non-exclusive setups, it isn't used directly in Cloud Integration.

    If the retry that moves messages to the error queue fails, the JMS broker starts to retry the message with a very high frequency. This can occur if a transacted session isn't available due to a JMS resource shortage. Usually, this resource shortage occurs only for a very short time because sessions are continuously released during message processing.

-   **Re-delivery / error queue**

    The property `JMSRedelivered` indicates that a retry was performed by the JMS broker. If the `JMSRedelivered` property is set, the message is stored in a separate error queue \(see [Managing Queues](managing-queues-f116962.md)\). For the sending of messages into the error queue, a separate message processing log is written.

    The setting of property `JMSRedelivered` by the JMS broker isn't accurate. The JMS specification contains a paragraph that says: *If a client receives a message with the JMSRedelivered indicator set, it is likely, but not guaranteed, that this message was delivered but not acknowledged in the past.*

    If the JMS broker sends a message to the JMS client and receives an error, it isn’t sure that the message did not reach the client. There's a specific degree of freedom for the broker about when to set this property and when not. Therefore, it's possible that a message is flagged as redelivered and moved to the error queue even though it hasn't reached the JMS client before.

    There are also cases of early message delivery to the client application although it hasn't started to process this message. If this client is in a shutdown phase \(for example, downscaling, integration flow un-deployment or re-deployment, software update\) it can happen that it ignores this message entirely and not acknowledges its retrieval. The broker has to resend this message to the next consumer, but it flags it as a redelivery \(which is the correct state from the broker’s perspective\).

-   **Cloud Integration retry job**

    An automatic job runs every minute and sequentially goes through all non-empty error queues to move their messages back to the processing queue according to the configured redelivery configuration in the adapter. In this case, the messages are added to the end of the queue. If the processing queue contains many messages, an added message isn't processed immediately.

    The timeout is set to 5 seconds. This means that, after the last message in a non-empty queue, it takes 5 seconds until the next queue is scanned.




To summarize, the following situations can occur for non-exclusive queues:

-   In rare cases, the MPL doesn't reflect all details of how the message has been processed during JMS retries.

-   The retry times can deviate from the configured values, depending on the situation.

-   There can be retries although no errors are visible in the MPL.

-   If using many queues, additional configurations can be necessary to make sure that the retry intervals are realized as configured in the channel.


There can also be combinations of issues with the reprocessing of messages and issues related to the quality of service, which may be mitigated by using the relevant adapter.

