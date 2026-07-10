<!-- loio2388efb12dfd4c6ca2473e8c7c730efc -->

# Transaction Handling Characteristics and Restrictions

Cloud Integration supports transaction handling for JDBC and JMS operations.

Transaction management allows an integration developer to define the boundaries of a transaction that don't just control database operations but also queue operations. It allows you to:

-   Manage a transaction at a process and subprocess level.

-   Have multiple individual transactions in an integration flow.

-   Disable transactions to commit every operation individually and immediately.


A database transaction is started whenever you perform any of the following database operations:

-   Data Store operation: Select, Write, Get, Delete

-   Write or Read Variable \(local or global\)

-   Use an Aggregator step


In addition, some adapters require a transaction to ensure transactional end-to-end processing:

-   A JMS transaction is initiated as soon as you try to read data from a JMS queue \(JMS sender channel\).

-   For a JMS receiver channel writing messages to a JMS queue, a JMS transaction is only initiated if transaction handling for JMS is set.

-   The XI sender and receiver adapters support quality of service Exactly Once \(EO\) based on temporary storage. This can be either a data store or a JMS queue.

-   The AS2 sender adapter uses JMS persistency.


A transaction is closed at the end of the process \(or subprocess\) where it's defined. You can also configure a timeout to avoid keeping the transaction open for an unlimited duration. Whichever happens first, closes the transaction.

> ### Note:  
> When the transaction timeout has been exceeded, the operation fails.

For a detailed description of the transaction handling configuration and options, see [Define Transaction Handling](define-transaction-handling-2a5d4bc.md).

When working with transactions, different configuration options are possible leading to different transactional behavior. Some integration flow steps do require a transaction. Some integration flow steps aren't supported with transactional resources. Different combinations of transaction settings are technically possible although not necessarily recommended or allowed. The following characteristics and limitations apply:

-   By default, when you create an integration flow, transaction handling is switched off for processing performance reasons. If required, you can switch on transaction handling to ensure data consistency. See: [Define Transaction Handling](define-transaction-handling-2a5d4bc.md). Even if you switch on transaction handling, a transaction is only opened if your integration flow contains a step that carries out a database operation that requires a transaction.

-   Data store operations and the writing of variables can benefit from a JDBC transaction handler to ensure data consistency across multiple data store operations. However, it can also be used without a JDBC transaction. In this case, the database operation is committed for the single integration flow step and no end-to-end transaction is hold.

-   There's an exception for the previous rule for the *Delete On Completion* option of the *Get* and *Select* data store operations. In this case, the deletion is always executed at the end of the processing. That way, the message is deleted after successful processing or not deleted if the message processing failed. This behavior is independent of the configured transaction handling. Therefore, data consistency is guaranteed even if no transaction handler is selected on the integration flow level.

-   If you use an *Aggregator* step, a JDBC transaction handler is mandatory to ensure data consistency. You get a check error if you configure an aggregator without a JDBC transaction switched on.

-   If you use only one single *JMS receiver channel* without, for example, a splitter or multicast, a JMS transaction handler isn't required. Instead, the JMS transaction is committed directly.

-   The same applies to the *XI adapter*. If you use only one single XI receiver channel without a splitter or multicast, you don't need a JMS/JDBC transaction handler \(depending on the temporary storage option chosen in the XI adapter\). Instead, the JMS/JDBC operation is committed directly.

-   Parallel processing of messages can't be transactional. Therefore, *General Splitter* and *Iterating Splitter* with parallel processing as well as *Parallel Multicast* don't support transaction handling. If you need a transaction, use sequential processing. Otherwise, deactivate transactional processing. This applies to both JDBC and JMS transaction handlers.

-   If there are multiple JMS receivers, for example, when using a *Sequential Multicast* or splitter followed by a *JMS receiver adapter*, a JMS transaction handler ensures that the data is consistently written/updated in all JMS queues. If no transaction handler is used for this kind of scenario, in an error situation some messages might have already been written to the JMS queue and so they aren't rolled back, leading to data inconsistency.

    The same applies to the *XI receiver adapter*. If you use multiple XI receiver adapters, for example, when using a *Sequential Multicast* or a splitter followed by an *XI receiver adapter*, a JMS/JDBC transaction handler ensures that the data is consistently updated.

-   If you use a *JMS receiver channel* in a *Send* step, a JMS transaction handler is needed to ensure that the data is consistently updated at the end of the processing. If an error happens after the *Send* step, the whole transaction will be rolled back.

    The same applies to the *XI receiver channel* in a send step. If you use an XI receiver channel in a Send step, a JMS/JDBC transaction handler is needed to ensure that the data is consistently updated at the end of the processing.

-   For the *XI receiver channel* we need to distinguish between the following kinds of errors:

    -   Processing errors within your integration flow: If you use a transaction handler, a rollback is carried out.

    -   Errors that occur during message delivery: When the error happens in the process of sending the message to the receiving backend system, no rollback is carried out even if a transaction handler is used. The reason is that at this point in time the message was already stored in temporary storage. A retry from temporary storage is done in a new transaction.


-   *JMS*, *XI*, and *AS2* sender adapters don't need a JMS transaction manager to be configured, because the retry handling works independently of the selected transaction handler. We recommend selecting the transaction manager as required by your scenario configured in the integration flow.


