<!-- loio52e3f6760a4c46f7a423c43cf5656d75 -->

# Transaction Handling Guidelines

Taking the [Transaction Handling Characteristics and Restrictions](transaction-handling-characteristics-and-restrictions-2388efb.md) into consideration, the following guidelines apply.

-   To minimize resource consumption, configure transactions to be as short as possible . Since the transaction needs to be kept open during the entire process that it's configured for, transactions consume resources that are limited. When you configure a transaction in the main process, the transaction is already opened at the beginning of the overall process and is kept open until the whole process ends. Long-running scenarios can cause transaction lock issues on the database or can exceed the number of available connections.

-   On the other hand, make sure that you configure the transaction to be as long as needed for consistent runtime execution. For end-to-end transactional behavior, you need to make sure that all steps belonging together are executed in a single transaction so that data is either persisted or rolled back in all transactional resources.

-   Whenever possible, move related tasks into a subprocess so that the transaction can be limited to the subprocess and the main process can be kept nontransactional. This measure ensures that the transactions aren't kept open for long or for the entire duration of message execution.

-   If possible, place the data store operation or JMS send step at the end of your integration flow assuming that your integration flow doesn't need any other transactional flow steps. This way you avoid the need to define a transaction. The data store operation or JMS send step is committed directly, or if there's an error, no other operations need to be rolled back.

-   Configure only one transaction if multiple JMS components are used to reduce the number of transactions concurrently opened: If a JMS, XI, or AS2 Sender Channel, and one or more JMS receiver adapters are used in a single integration flow, you can optimize the number of transactions used in the JMS instance by using a JMS transaction handler. In this case, only one transaction is opened for the whole process.

-   Avoid mixing JDBC and JMS transactions. Cloud Integration doesn't support distributed transactions, so you can't execute JMS and JDBC transactions together in a single transaction. If there's an error, the JDBC transaction can already be committed and if the JMS transaction can't be committed afterwards, the message remains in the JMS inbound queue or isn't committed into the JMS outbound queue. In such cases, the message is retried from inbound queue, sender system, or sender adapter and can cause duplicate messages.


