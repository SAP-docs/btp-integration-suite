<!-- loio4857054e3f194ae6a7ed93a52002d556 -->

# JMS Resource Limits and Optimizing their Usage

The JMS messaging instance has limited resources. You can increase the capacity of these resources to a certain extend.



<a name="loio4857054e3f194ae6a7ed93a52002d556__section_b15_g2l_2yb"/>

## Default and Maximum JMS Resources

> ### Note:  
> The JMS messaging instance is used in asynchronous messaging scenarios with the JMS, AS2, AS4, and XI adapter.

For SAP Integration Suite \(all service plans\) and for existing SAP Cloud Integration \(Enterprise Edition\) licenses, there are the following default and maximum queue capacities.

> ### Note:  
> To learn more about JMS resources for Edge Integration Cell, see [JMS Resource Limits for Edge Integration Cell](jms-resource-limits-for-edge-integration-cell-17366b3.md).


<table>
<tr>
<th valign="top">

 

</th>
<th valign="top">

Default JMS resources

</th>
<th valign="top">

Maximum JMS resources to get by self-service

</th>
</tr>
<tr>
<td valign="top">

Number of JMS queues

</td>
<td valign="top">

30

</td>
<td valign="top">

100

</td>
</tr>
<tr>
<td valign="top">

Queue Capacity

</td>
<td valign="top">

9.3 GB

</td>
<td valign="top">

30 GB

</td>
</tr>
<tr>
<td valign="top">

Number of transactions

</td>
<td valign="top">

150

</td>
<td valign="top">

500

</td>
</tr>
<tr>
<td valign="top">

Number of consumers

</td>
<td valign="top">

150

</td>
<td valign="top">

500

</td>
</tr>
<tr>
<td valign="top">

Number of providers

</td>
<td valign="top">

159

</td>
<td valign="top">

500

</td>
</tr>
</table>

> ### Note:  
> Capacity of one JMS queue:
> 
> Resources such like number of transactions, message volume, and so forth, can be calculated from the resources associated with one single JMS queue.
> 
> One JMS queue comes with the following resources:
> 
> 
> <table>
> <tr>
> <td valign="top">
> 
> Queue capacity
> 
> </td>
> <td valign="top">
> 
> 300 MB
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Transactions
> 
> </td>
> <td valign="top">
> 
> 5
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Consumers
> 
> </td>
> <td valign="top">
> 
> 5
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Providers
> 
> </td>
> <td valign="top">
> 
> 5
> 
> </td>
> </tr>
> </table>

Independent of the allocated JMS resources, the following applies:

-   The maximum capacity for one queue is 95% of the total queue capacity.

-   256 messages can be processed in one transaction.

    This restriction is relevant when you have designed integration flows that split messages where multiple split messages are executed in the same transaction. If a message is bigger than 5 MB, before storing it in the JMS queue, Cloud Integration splits it internally into smaller chunks.

    This means: The maximum message size \(including attachments\) that can be stored in a JMS queue is 1280 MB \(256 \* 5 MB\). This limit is given by the fact that maximum 256 messages can be processed in one transaction \(see note above\).

    For more guidance and calculation examples, check out the following SAP Community blog: [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) \(section *Numbers of Messages in one Transaction*\).

-   Headers and exchange properties defined in the integration flow before the message is saved to the queue must not exceed 4 MB in total.




<a name="loio4857054e3f194ae6a7ed93a52002d556__section_oh5_g2l_2yb"/>

## How to Increase JMS Resources

You can increase the capacity up to 100 queues be self-service, as described in the table below.


<table>
<tr>
<th valign="top">

License

</th>
<th valign="top">

Increase up to 100 queues by self-service

</th>
<th valign="top">

Increase to \> 100 queues

</th>
</tr>
<tr>
<td valign="top">

SAP Integration Suite 

</td>
<td valign="top">

To get up to 100 queues, for the Cloud Integration capability, increase the JMS queues number.

See the following SAP Community blog: [Integration Suite – Simplified Onboarding and Provisioning](https://blogs.sap.com/2020/05/11/integration-suite-simplified-onboarding-and-provisioning) \(section *Increasing the JMS Message Broker resources*\)

</td>
<td valign="top">

Check out [2589823](https://me.sap.com/notes/2589823).

</td>
</tr>
</table>



<a name="loio4857054e3f194ae6a7ed93a52002d556__section_vsn_ffl_2yb"/>

## How Cloud Integration Manages Queues

The JMS sender or receiver adapter generates a message queue during deployment.

Unused message queues are not deleted automatically. Since queues are limited \(and paid\) resources, you should manually delete any queues which are not used by your integration flows any more.

Information on deleted message queues is available in the audit log.

> ### Caution:  
> There are certain limitations related to transactional behavior when using this adapter type together with *Data Store Operations* steps, *Aggregator* steps, or global variables. For more information, visit the following SAP Community blog: [Cloud Integration – How to configure Transaction Handling in Integration Flow](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fblogs.sap.com%2F2017%2F05%2F31%2Fcloud-integration-how-to-configure-transaction-handling-in-integration-flow).

> ### Note:  
> The JMS adapter stores only simple data type headers \(primitive data types or strings\).

Supported Headers: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)



<a name="loio4857054e3f194ae6a7ed93a52002d556__section_gvf_xt2_ykb"/>

## JMS Consumers and Providers

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

\(no. of runtime nodes\) x \(no. of JMS queues\)

</td>
<td valign="top">

\(no. of runtime nodes\) x \(no. of JMS queues\) x \(no. of concurrent processes\)

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

\(min. no. of consumers\) + \(no. of providers\)

</td>
<td valign="top">

\(max. no. of consumers\) + \(no. of providers\)

</td>
</tr>
</table>

> ### Note:  
> Runtime nodes are also referred to worker nodes.

> ### Note:  
> -   Number of JMS queues: Note that when the first integration flow that uses a JMS queue is deployed, a queue is created.
> 
> -   To find out the number of runtime nodes or the number of tenant management node \(only available when you operate SAP Cloud Integration in the Neo environment\), open the tile *Message Queues* \(in the *Monitor* section of the Web UI under *Manage Stores*\) and click *Details* in the information box below the header.
> 
> -   Transactions are distributed dynamically to providers and consumers.
> 
> -   To increase the number of queues, raise an incident \(component **BC-CP-EM-MES**\).

For more information, read the SAP Community blog: [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/).

**Related Information**  


[Managing Message Queues](managing-message-queues-cdcce24.md "You can monitor queues that are active for a tenant.")

