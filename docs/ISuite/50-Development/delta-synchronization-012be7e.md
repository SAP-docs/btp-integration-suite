<!-- loio012be7e9eb114a528ac58a93bce73de4 -->

# Delta Synchronization

Learn how to retrieve only delta data from the source system using the current date or the latest date in the payload.

Assume that you need to implement a process that runs at regular intervals. You don't want to retrieve all records during every run to avoid that the resulting data set increases. Note that the relevant part of the data set is the data that has changed \(added or updated\) since the last run. This is referred to as delta content.

There are different indicators for an update. This guideline comes with 2 variants, each of which uses a timestamp as an indicator for an update.

Using a timestamp, you can define your query of data retrieval in such a way that only the data that has changed since the last run is pulled from the source. To implement such a use case, the timestamp of the last execution is stored in a local variable.

Variables are stored in the database of the Cloud Integration tenant for 400 days after the last update. There are 2 types of variables. Choose the type according to your use case:

-   A local variable is accessible only by the integration flow that creates it.

-   A global variable is accessible by all integration flows on the tenant.


More information: [Define Write Variables](define-write-variables-de04b75.md) 

For demo purposes, the Cloud Integration OData API is used to retrieve the message processing log \(MPL\) of the messages processed on the tenant. Only the logs since the last delta run are retrieved.

> ### Note:  
> Make sure that API clients are authorized to access the Cloud Integration OData API for your tenant.
> 
> More information:
> 
> -   [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md)
> 
> -   [Setting Up Inbound HTTP Connections (for API Clients), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/fbae09c89d9246f88149c5293c96ab5f.html "") :arrow_upper_right:

The following variants are provided:

-   Delta Synchronization with timestamp based on Date Now Expression

    More information: [Delta Synchronization Via Date Now XPath](delta-synchronization-via-date-now-xpath-698307a.md)

-   Delta Synchronization with timestamp received from the last delta payload

    More information: [Delta Synchronization Via Timestamp in Payload](delta-synchronization-via-timestamp-in-payload-28a6006.md)




<a name="loio012be7e9eb114a528ac58a93bce73de4__section_syz_f5z_q4b"/>

## Prerequisites

For both variants, the same prerequisites apply.

To illustrate a use case, the integration flow retrieves the log entries of the messages processed on a tenant. The MPL stores data about the messages processed on a tenant, and for each processed message it stores information about the individual processing steps.

For both variants the following processing details are selected:

-   MessageGuid

-   Status

-   LogStart


To access the MPL, you use the OData API. The `MessageProcessingLog` OData API entity allows you to get all message processing logs \(see: [Message Processing Logs](message-processing-logs-827a2d7.md)\).

To access the OData API to retrieve the MPL, configure and deploy a *User Credentials* artifact that contains the credentials of a user that is authorized to access the API. The name of the *User Credentials* artifact must correspond to the name that you configure in the integration flow. By default, we used the name `iFlowDesignGuidelineUser`.

Before the first run, the following externalized parameters must be set:

****


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Default Value

</th>
</tr>
<tr>
<td valign="top">

address

</td>
<td valign="top">

URL to access the `Message Processing Logs` OData API for your tenant. For example, <code>https://&lt;Cloud Integration host address&gt;/api/v1/</code> 

> ### Note:  
> To find out the host address, note the following: The URL of your customer-specific Cloud Integration user interface is:
> 
> <code>https://&lt;Cloud Integration host address&gt;/itspaces</code>



</td>
</tr>
<tr>
<td valign="top">

credentialName

</td>
<td valign="top">

Credential Name to access the Cloud Integration OData API for your tenant. By default, the name `iFlowDesignGuidelineUser` is preset.

</td>
</tr>
<tr>
<td valign="top">

defaultDate

</td>
<td valign="top">

Date for the first run of the process in following format `yyyy-MM-ddT00:00:00`. For example: date now – 1 day

</td>
</tr>
</table>



<a name="loio012be7e9eb114a528ac58a93bce73de4__section_uxh_4b1_r4b"/>

## More Information

[Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md)

[Message Processing Logs](https://api.sap.com/api/MessageProcessingLogs/overview) \(OData API on SAP Business Accelerator Hub\)

[Define Transaction Handling](define-transaction-handling-2a5d4bc.md)

[Define Write Variables](define-write-variables-de04b75.md)

