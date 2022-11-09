<!-- loio4f5ef3f724c2480da421daa7880bb040 -->

# Data Store Sender Adapter

This adapter enables Cloud Integration to consume messages from a data store. This feature helps you to enable asynchronous decoupling of inbound and outbound processing by using the data store as temporary storage.

To understand the concept of asynchronous decoupling, assume that a sender sends a message to Cloud Integration \(inbound processing\). If there's an error in outbound processing \(for example, a receiver can't be reached temporarily\), the middleware \(Cloud Integration\) retries message processing independently. There's no need that the sender triggers a reprocessing of the message as soon as the error situation is fixed. The sender relies on the middleware to do that. To support this scenario, Cloud Integration stores the message received from the sender in the data store. To implement this step, you can design a dedicated integration flow that receives the sender's message and uses a *Data Store Write* step to store it in the data store \(see [Define Data Store Write Operations](define-data-store-write-operations-46260ee.md)\).

Furthermore, you model outbound processing in an integration flow that initially consumes the message from the data store \(using the *Data Store* sender adapter\). The outbound integration flow retries the message from the data store as long as the error situation lasts.

The following figure depicts the described example setup.

 ![](images/Data_Store_Sender_Adapter_96edd76.png) 

You can model the steps that write into the data store and those that consume message from it also in the same integration flow.

If multiple worker nodes are set up, there's no parallel processing of the same data store entry by these multiple worker nodes.

> ### Tip:  
> You can use this feature to implement scenarios with quality of service Exactly Once for cases when the sender hasn't any mechanism in place to retry messages.
> 
> See: [Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md)
> 
> For more information on the data store, see:
> 
> -   [Define Data Store Operations](define-data-store-operations-79f63a4.md)
> 
> -   [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md)

> ### Note:  
> Availability of this feature:
> 
> -   Cloud Foundry environment: Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).
> 
> -   Neo environment: This feature is available for all editions.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a product profile other than the one expected \(see [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md)\).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow \(see [Product Profiles](product-profiles-8007daa.md)\). To use the latest version of a flow step or adapter, edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integraion flow.

To use this adapter type in an integration flow, connect a *Sender* with a *Start Message* shape and select adapter type *Data Store*.

Once you've created a *Data Store* sender channel, you can configure the following attributes.

Go to the *General* tab to configure the following adapter parameters.

**General**


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Name*



</td>
<td valign="top">

Enter the name of the channel.



</td>
</tr>
</table>

Go to the *Connection* tab to configure the following adapter parameters.

**Connection**


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Data Store Name*



</td>
<td valign="top">

Specifies the name of the data store \(no white spaces\).

The maximum length allowed for the data store name is 40 characters. If you enter a longer string, a validation error is raised. Note that this length restriction applies to the value that is used for this parameter at runtime.



</td>
</tr>
<tr>
<td valign="top">

*Visibility*



</td>
<td valign="top">

Defines whether the data store is shared by all integration flows \(deployed on the tenant\) or only by one specific integration flow.

-   *Global*: Data store is shared across all integration flows deployed on the tenant.

-   *Integration Flow* \(default setting\): Only a single integration flow uses the data store. A data store configured with this setting is also referred to as local data store.


For more information and guidelines how to use this parameter, see [Anticipate Message Throughput When Choosing a Storage Option](anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md).



</td>
</tr>
<tr>
<td valign="top">

*Poll Interval \(in s\)*



</td>
<td valign="top">

Specify the poll interval in seconds to wait before consuming messages from the data store. The default is set to 10 s. The minimum is set to 1 s. The maximum is set to 300 s.

The adapter continuously consumes messages from the data store if the data store contains entries that are ready to be processed.

The poll interval only becomes effective as soon as the data store doesn't contain such entries anymore. From that point in time, the adapter waits for the time specified by the *Poll Interval* parameter and then again tries to consume messages from the data store.

> ### Note:  
> The smaller the poll interval \(for example, 1 s or less\), the more load is put on the data store.



</td>
</tr>
<tr>
<td valign="top">

*Retry Interval \(in min\)*



</td>
<td valign="top">

Enter a value for the amount of time to wait before retrying message delivery. The default is set to 1 min. The minimum is set to 1 min. The maximum is set to 1440 min \(24 hours\).



</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff*



</td>
<td valign="top">

Select this option to double the retry interval after each unsuccessful retry. By default, this option is deselected.



</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in min\)*



</td>
<td valign="top">

You can set an upper limit on that value to avoid an endless increase of the retry interval. The default value is 60 minutes. The minimum value is 10 minutes. The maximum is set to 1440 min \(24 hours\).



</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in min\):*



</td>
<td valign="top">

Enter a value for the timeout of the in-progress repository. After this time, a message is retried in case of a cluster outage. The default value is 10 minutes. The minimum value is 1 minute. The maximum is set to 300 min \(5 hours\).



</td>
</tr>
</table>

