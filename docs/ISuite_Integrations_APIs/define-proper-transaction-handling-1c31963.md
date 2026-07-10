<!-- loio1c3196315d5a46a293d350b73dc2ccd5 -->

# Define Proper Transaction Handling

Define proper transaction handling while keeping limited resources in mind.

When modeling an integration flow, you can define transaction handling in the following ways:

-   Explicitly configure the transactional behavior within your integration flow for the whole integration process.

-   Explicitly configure the transactional behavior on the subprocesses level.


You usually enable transactional processing to ensure data consistency if your integration flow model contains persistence-related integration flow steps. However, transaction handling, has an impact on the resource consumption of the Cloud Integration runtime. Depending on your specific scenario, you disable transaction handling for the whole or parts of your integration flow to improve processing performance. However, you must not compromise on data consistency.

For more information on the transaction handling feature, see also [Define Transaction Handling](define-transaction-handling-2a5d4bc.md).



<a name="loio1c3196315d5a46a293d350b73dc2ccd5__section_bgx_1f5_w4b"/>

## What Is a Transaction?

A transaction is an atomic unit of commit. Every step that is processed within a transaction is either committed or all steps together are rolled-back.

For example, if you have multiple database write operations in your integration flow, a transaction spanning the whole integration flow guarantees that all write operations are consistently committed if the overall integration flow processing completes successfully. Otherwise, if an error occurs, even if one or more write operations have been carried out already, all operations are rolled back to avoid data inconsistencies. On the other hand, if no transaction handling is in place, and if, for example, the last write operation in the sequence of multiple write operations fails, then all other operations except for the last one have already been committed. In this case, the integration flow failed but you don't know for certain which data was already written, and which wasn't. This can lead to data inconsistency.



<a name="loio1c3196315d5a46a293d350b73dc2ccd5__section_ktq_kf5_w4b"/>

## Characteristics and Restrictions

Cloud Integration supports transaction handling for JDBC and JMS operations.

For more information, see [Transaction Handling Characteristics and Restrictions](transaction-handling-characteristics-and-restrictions-2388efb.md).



<a name="loio1c3196315d5a46a293d350b73dc2ccd5__section_qvr_n35_w4b"/>

## Transaction Handling Guidelines

Taking the restrictions and characteristics into consideration, the following guidelines apply: [Transaction Handling Guidelines](transaction-handling-guidelines-52e3f67.md).



<a name="loio1c3196315d5a46a293d350b73dc2ccd5__section_m1h_hj5_w4b"/>

## Scenarios

The following scenarios may or may not need transactional processing. Read about the different configuration options and which guidelines apply so that you can define the right transaction handler.:

-   Delta load with last modified time stamp

    In this scenario, we want to retrieve delta records using a time stamp as an indicator for an update of the data. Two variants are described in [Delta Synchronization](delta-synchronization-012be7e.md).

    Both variants use a time stamp that is stored in a data store at the very end of the integration process, so no transaction handler is required. If an exception occurs during the integration flow processing, the old time stamp isn't overwritten, and a subsequent integration flow execution fetches the same data again. This way, data consistency is guaranteed and this also prevents database transactions from being kept open for too long.

-   Control database connections

    In the [Control the Number of Simultaneously Opened Database Connections](control-the-number-of-simultaneously-opened-database-connections-90628e9.md) guideline, transaction handling is described in the context of limited database connections.

    The sample scenario consists of a main process with 2 subprocesses. The first subprocess contains 2 data store write operations. The second subprocess contains a select from data store operation with deletion on completion.

    The data store operations need to be carried out in a consistent way. Since the number of concurrent database connections is limited, you need to ensure that single database transactions are kept open for as short a time as possible. On the other hand, you need to set up your integration model in such a way that data consistency is kept end-to-end across your integration scenario. Therefore, ensure that all steps belonging together are executed in a single transaction. That way, data is either persisted or rolled back in all transactional resources. We recommend that you move the integration flow steps that need to be processed within a single transaction to a subprocess.

    In our case, for the first subprocess with the two write operations you need a JDBC transaction handler. For the second subprocess, a transaction isn't required because the delete on completion feature automatically ensures data consistency.

-   Splitter with multiple JMS receivers

    This scenario contains a sequential splitter step with a subsequent JMS receiver. Parallel processing in combination with a transaction handler isn't supported. Therefore, you need to ensure that the *Parallel Processing* flag is deselected for your splitter. To ensure data consistency across all JMS write operations, you need a JMS transaction handler.

    See: [Splitter with Multiple Receivers \(JMS Adapter Type\)](splitter-with-multiple-receivers-jms-adapter-type-fc2755c.md)

    > ### Note:  
    > Another option is to have a sequential multicast with multiple JMS receivers. You would still need a JMS transaction handler to ensure data consistency.

-   JMS send step in a local integration process

    In this scenario, multiple messages are sent to a JMS queue whereas the data is updated consistently across all JMS write operations. For reasons of reusability, the JMS send step is defined in a local integration process that is called multiple times from within the main integration process.

    A transaction handler is required for the main integration process. For the subprocesses, the transaction is set to *From Calling Process*. Therefore, the transactions are merged into a single transaction across the whole end-to-end process. This measure reduces the number of required transactions to a minimum.

    See: [JMS Send Step in Local Integration Process](jms-send-step-in-local-integration-process-a5644c8.md)

-   Master data update with XI send steps

    In this scenario, you want to update product master data by calling the backend system via the XI 3.0 protocol. Multiple master data tables are to be updated consistently. Therefore, you need a transaction handler to ensure data consistency. To keep the transaction as short as possible, the actual exchange of messages is done in a local subprocess that is called right at the end of the main process. Therefore, the transaction can be limited to the subprocess and the main process can be kept nontransactional.

    See: [Master Data Update with XI Send Steps](master-data-update-with-xi-send-steps-5fb0541.md)

-   Master data update with JMS send steps

    Similar to [Master Data Update with XI Send Steps](master-data-update-with-xi-send-steps-5fb0541.md), you want to consistently update product master data. However, in this case we use JMS instead of the XI 3.0 protocol, and, therefore, we need a JMS transaction handler to ensure data consistency. To keep the transaction as short as possible, the actual exchange of messages is done in a local subprocess that is called right at the end of the main process. Therefore, the transaction can be limited to the subprocess and the main process can be kept nontransactional.

    See: [Master Data Update with JMS Send Steps](master-data-update-with-jms-send-steps-1c3e583.md)


The scenarios and their settings are summarized in the table:


<table>
<tr>
<th valign="top">

Scenario

</th>
<th valign="top">

Transaction required in main process

</th>
<th valign="top">

Transaction required in subprocess

</th>
<th valign="top">

Transaction type

</th>
</tr>
<tr>
<td valign="top">

Delta load with last modified time stamp

</td>
<td valign="top">

No

</td>
<td valign="top">

n/a

</td>
<td valign="top">

n/a

</td>
</tr>
<tr>
<td valign="top">

Control database connections: subprocess with two write operations

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Required for JDBC

</td>
</tr>
<tr>
<td valign="top">

Control database connections: subprocess with select and delete on completion

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
<td valign="top">

n/a

</td>
</tr>
<tr>
<td valign="top">

Splitter with JMS receivers

</td>
<td valign="top">

Yes

</td>
<td valign="top">

n/a

</td>
<td valign="top">

Required for JMS

</td>
</tr>
<tr>
<td valign="top">

JMS send step in reusable subprocess

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Required for JMS

</td>
</tr>
<tr>
<td valign="top">

Master data update with XI send steps

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Required for JDBC

</td>
</tr>
<tr>
<td valign="top">

Master data update with JMS send steps

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Required for JMS

</td>
</tr>
</table>

