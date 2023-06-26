<!-- loio4857054e3f194ae6a7ed93a52002d556 -->

# JMS Resource Limits and Optimizing their Usage

The JMS messaging instance that is used in asynchronous messaging scenarios with the JMS, AS2, AS4, or XI adapter has limited resources. SAP Integration Suite Standard Edition sets a limit on the queues, storage, and connections that you can use in the messaging instance.



Resource Limits for SAP Integration Suite Standard Edition:

-   Maximum number of queues: 30

-   Total queue capacity: 9.3 GB

-   Maximum capacity for one queue: 95% of the total queue capacity

-   150 transactions

-   150 consumers

-   150 providers

-   150 GB of data per month can be processed by JMS messaging

-   256 messages can be processed in one transaction


For more information about JMS resource and size limits, visit the following blog: [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/).



In case you want to increase the JMS resources, you can assign more Enterprise Messaging units that contain one queue and a dedicated set of JMS resources.

Resource limits for 5 Enterprise Messaging units:

-   Number of JMS queues in Cloud Integration: 1

-   Queue capacity: 300 MB

-   5 transactions

-   5 consumers

-   5 providers

-   5 GB of data per month can be processed by JMS messaging


You can find a step-by-step guide on how to activate Enterprise Messaging here: [Activating Enterprise Messaging](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/a74cddceacb34abb958e817c1f6782d2.html "You can activate Enterprise Messaging on all licensed versions of Cloud Integration.") :arrow_upper_right:



There are also technical restrictions on the size of the headers and exchange properties that can be stored in the JMS queue.

The following size limits apply when saving messages to JMS queues:

-   There are no size limits for the payload. The message is split internally when it is put into the queue.

-   There are no size limits for attachments. The message and the attachment are split internally when put into the queue.

-   Headers and exchange properties defined in the integration flow before the message is saved to the queue must not exceed 4 MB in total.


> ### Note:  
> The JMS sender or receiver adapter generates a message queue during deployment.
> 
> Unused message queues are not deleted automatically. Since queues are limited \(and paid\) resources, you should manually delete any queues which are not used by your integration flows any more.
> 
> Information on deleted message queues is available in the audit log.

> ### Caution:  
> There are certain limitations related to transactional behavior when using this adapter type together with *Data Store Operations* steps, *Aggregator* steps, or global variables. For more information, visit the following blog: [Cloud Integration – How to configure Transaction Handling in Integration Flow](https://blogs.sap.com/2017/05/31/cloud-integration-how-to-configure-transaction-handling-in-integration-flow/?preview_id=494608).

> ### Note:  
> The JMS adapter stores only simple data type headers \(primitive data types or strings\).

Supported Headers: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)



Processing JMS messages always requires a consumer \(JMS sender adapter\) or provider \(JMS receiver adapter\) and a transaction. In critical resource situations \(as analyzed by the *Manage Queues* monitor\), you can optimize the usage of transactions based on the following calculations.

****


<table>
<tr>
<th valign="top">



</th>
<th valign="top">

Min. No. of ...



</th>
<th valign="top">

Max. No. of ...



</th>
</tr>
<tr>
<td valign="top">

Consumers



</td>
<td valign="top">

No. of runtime nodes \* No. of JMS queues



</td>
<td valign="top">

No. of runtime nodes \* No. of JMS queues \* No. of concurrent processes

\(where the value of the latter argument is derived from the sender channel parameter *Number of Concurrent Processes*\)



</td>
</tr>
<tr>
<td valign="top">

Providers



</td>
<td valign="top" colspan="2">

Number of providers for a tenant cannot be calculated \(depends on the sender system\).

The no. of providers is equal to the no. of parallel sender calls.



</td>
</tr>
<tr>
<td valign="top">

Transactions



</td>
<td valign="top">

Min. no. of consumers + No. of providers



</td>
<td valign="top">

Max. no. of consumers + No. of providers



</td>
</tr>
</table>

> ### Note:  
> -   No. of JMS queues: Note that when the first integration flow that uses a JMS queue is deployed, a queue is created.
> 
> -   To find out the number of runtime nodes or the number of tenant management node \(only available when you operate SAP Cloud Integration in the Neo environment\), open the tile *Message Queues* \(in the *Monitor* section of the Web UI under *Manage Stores*\) and click *Details* in the information box below the header.
> 
> -   Note that transactions are distributed dynamically to providers and consumers.
> 
> -   For increasing the number of queues use **BC-CP-EM-MES** to raise an incident.

For more information, read the SAP Community blog: [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/).

**Related Information**  


[Managing Message Queues](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/cdcce24f484a41c08ab46d12ab666451.html "Certain adapters allow you to store messages in queues. Using the Web UI, you can monitor queues that are active for a tenant.") :arrow_upper_right:

