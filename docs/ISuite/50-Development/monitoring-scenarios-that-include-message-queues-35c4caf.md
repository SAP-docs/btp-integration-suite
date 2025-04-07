<!-- loio35c4caf989f942c6959bc5ac27b45033 -->

# Monitoring Scenarios that Include Message Queues

Learn more about how to monitor scenarios that include message queues and possible error situations.



<a name="loio35c4caf989f942c6959bc5ac27b45033__section_hnm_qqm_jyb"/>

## Quality of Service

When monitoring message processing of integration flows that contain JMS message queues \(in the *Monitor Message Processing* area\), you notice that in most cases every message is processed exactly once. However, in rare cases a message processing log suggests that there’s an inconsistency indicating that a message has been processed more than once from a message queue. If Cloud Integration sends this message to a receiver system \(for example, using a SOAP channel\) and the receiver system isn't prepared for this, it can lead to problems.

The JMS broker doesn't provide exactly once processing. For non-exclusive queues, there are cases when a message is processed more than once and even in parallel by different consumers. This can happen, for example, when during processing from the JMS message queue the connection to the JMS broker gets lost. The reason for this is that when the connection is interrupted also the lock on the JMS broker for that message gets lost.

For exclusive queues, retry and inconsistencies are handled differently, and exactly once in order processing can be achieved if the connection remains healthy.

> ### Note:  
> There are two different queue types that affect how messages are processed.
> 
> -   Non-Exclusive Queues: Allow multiple consumers to process messages in parallel, which can lead to messages being processed more than once if connections are lost or interrupted.
> -   Exclusive Queues: Restrict message processing to a single consumer at a time, ensuring ordered processing.

> ### Tip:  
> If a message is processed by one consumer \(an integration flow deployed on a Cloud Integration worker node\), the JMS broker writes a lock entry that makes sure that no other consumer starts processing the same message. For non-exclusive queues, when the connection between consumer \(Cloud Integration\) and JMS broker is interrupted, the locks are deleted. Exclusive queues inherently handle this with ordered processing.

For an example, consider the following scenario: Consumer 1 starts processing a message from the message queue and during this step the connection to the JMS broker gets lost. Consumer 1 does not have any information that the connection was lost and still tries to process the message. During this period, it is possible that another consumer \(consumer 2\) starts to process the same message.

If the receiver adapter used to send the final message to another system does not support exactly once message processing, the described behavior can lead to inconsistencies.

In particular, the problem is that in such situations the system is processing the message more than once but adapter used to send the message to the receiver system isn't supporting exactly once processing. If the receiver adapter supports exactly once processing, the JMS broker can send the message more than once and data consistency of the application logic isn't broken. Exactly once processing for the JMS adapter doesn't solve the adapter problem.

Furthermore, the functionality to reprocess a message builds on the assumption that JMS processes a message exactly once. If in rare cases this assumption is incorrect, the retry at runtime is not working as configured. In such a case, based on the JMS processing Cloud Integration *can assume* that it detects a breakdown of the worker node \(which can happen, for example, caused by an out-of-memory situation\). In that case, the retry interval is set to 18 minutes.

> ### Note:  
> For exclusive queues, the retry is managed by the JMS broker and does not utilize separate error queues as in non-exclusive queues.

To mitigate such problems, if possible, use an adapter that supports exactly once processing \(for example, the XI adapter\).

More information on the different options to design integration scenarios with exactly once processing: [Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md)



<a name="loio35c4caf989f942c6959bc5ac27b45033__section_uxf_qqm_jyb"/>

## Reprocessing of Messages

If messages fail during processing from a queue, a retry of the message is triggered. The JMS sender adapter allows you to configure message retry, for example, to set a specific retry interval \(see [Configure the JMS Sender Adapter](configure-the-jms-sender-adapter-161791b.md)\).

However, in specific cases, the message is processed differently than expected from the retry configuration.

Note the following aspects related to retry processing for non-exclusive queues:

-   In general, JMS transactions are used to process messages. A retry from the JMS broker is executed when a rollback occurred.

    The JMS transaction is finished after the message processing log \(MPL\) status is set. If an error occurs in the commit or rollback phase of the JMS session, the MPL status is adapted in most cases. However, some cases are not covered. In those cases, message status is set to *Completed*. That means that there can be retries happening although the message was already set to *Completed*.

-   The JMS broker immediately retries the message. This behavior can’t be changed. Since this retry is too fast for almost all applications in non-exclusive setups, it is not used directly in Cloud Integration.

    If the retry that moves messages to the error queue fails, the JMS broker starts to retry the message with a very high frequency. This can occur if a transacted session is not available due to a JMS resource shortage. Usually, this resource shortage occurs only for a very short time because sessions are continuously released during message processing. Therefore, this occurs only for a short period.

-   The property `JMSRedelivered` indicates that a retry was performed by the JMS broker. If the `JMSRedelivered` property is set, the message is stored in a separate error queue \(see [Managing Queues](managing-queues-f116962.md)\). For the sending of messages into the error queue, a separate message processing log is written.

    The setting of property `JMSRedelivered` by the JMS broker isn't accurate. The JMS specification contains a paragraph that says:

    *If a client receives a message with the JMSRedelivered indicator set, it is likely, but not guaranteed, that this message was delivered but not acknowledged in the past.*

    If the JMS broker sends a message to the JMS client and receives an error, it isn’t sure that the message did not reach the client. There's a specific degree of freedom for the broker about when to set this property and when not. Therefore, it is possible that a message is flagged as redelivered and moved to the error queue although it hasn't reached the JMS client before. There are also cases of early message delivery to the client application although it has not started to process this message. If this client is in a shutdown phase \(for example, downscaling, integration flow un-deployment or re-deployment, software update\) it can happen that it ignores this message entirely and not acknowledges its retrieval. The broker has to resend this message to the next consumer, but it flags it as a redelivery \(which is the correct state from the broker’s perspective\).

-   An automatic job runs every minute to move the message from the error queue back to the processing queue according to the configured redelivery configuration in the adapter. In this case, the message is added to the end of the queue. If the processing queue contains many messages, the added message is not processed immediately.

    By default, the retry job sequentially accesses all error queues. The timeout is set to 5 seconds. That means: If a queue is empty, it takes 5 seconds until the next queue is scanned. If there are many queues, it can take long. Therefore, this process can be parallelized which requires some additional JMS resources. To avoid a possible resource shortage, this setting isn't enabled by default. You can find more details under [3280895](https://me.sap.com/notes/3280895).


To summarize, the following situations can occur for non-exclusive queues:

-   In rare cases, the MPL doesn't reflect all details of how the message has been processed during JMS retries.

-   The retry times can deviate from the configured values, depending on the situation.

-   There can be retries although no errors are visible in the MPL.

-   If using many queues, additional configurations can be necessary to make sure that the retry intervals are realized as configured in the channel.


There can also be combinations of issues with the reprocessing of messages and issues related to the quality of service.

