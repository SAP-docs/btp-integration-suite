<!-- loioe80310f99d064f649245a389d4e9939d -->

# Azure Service Bus Sender Adapter

Azure Service Bus Sender adapter provides the ability to consume messages seamlessly from Azure Service Bus.



## How the Azure Service Bus Sender Adapter works

If you have configured the Azure Service Bus Sender Adapter, data exchange is performed as follows at runtime: Azure Service Bus sends the operation request to SAP Integration Suite tenant, Azure Service Bus Sender Adapter works on the request and sends the data to SAP Integration Suite tenant. Polling actively checks for new messages at a defined interval.



## Configure the Azure Service Bus Sender Adapter

Once you have created a sender channel and selected the Azure Service Bus Sender Adapter, you can configure its parameters as shown below:

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

*Hostname*

</td>
<td valign="top">

Specify the hostname for the namespace in use.

Example: `myservice.servicebus.windows.net`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select authentication mechanism to connect to Azure Service Bus.

-   *Microsoft Entra ID*
-   *Shared Access Signature*



</td>
</tr>
<tr>
<td valign="top" colspan="2">

> ### Note:  
> Values to create security artifacts can be found in the Azure Portal.



</td>
</tr>
<tr>
<td valign="top">

*Directory \(tenant\) ID Alias*

\(Only available when *Microsoft Entra ID* is selected\)

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the Directory ID needed to connect to Azure Service Bus.

</td>
</tr>
<tr>
<td valign="top">

*Application \(client\) ID Alias*

\(Only available when *Microsoft Entra ID* is selected\)

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the Application ID needed to connect to Azure Service Bus.

</td>
</tr>
<tr>
<td valign="top">

*Client Secret Value Alias*

\(Only available when *Microsoft Entra ID* is selected\)

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the Client Secret Value ID needed to connect to Azure Service Bus.

</td>
</tr>
<tr>
<td valign="top">

*Shared Access Policy Name*

\(Only available when *Shared Access Signature* is selected\)

</td>
<td valign="top">

Specify the Shared Access Policy Name that defines the authorization rule.

</td>
</tr>
<tr>
<td valign="top">

*Access Key Alias*

\(Only available when *Shared Access Signature* is selected\)

</td>
<td valign="top">

Specify the Access Key alias to authorize access to the Azure Service Bus.

> ### Note:  
> This can be created as a Secure Parameter using the Primary Key for your Shared Access Policies available under Settings in Azure Portal.



</td>
</tr>
<tr>
<td valign="top">

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specify the polling interval in milliseconds to retrieve the messages.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Maximum Reconnect Attempts*

</td>
<td valign="top">

Specify the maximum nymber of retries to connect to Azure Service Bus.

Example: `3`

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time in milliseconds for the connection to be established. This is applicable to each retry, so the total connection timeout will also be dependent on the Maximum Reconnect Attempts.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Error Handling*

</td>
<td valign="top">

Select the process action for the error in the adapter:

-   *Add to System Trace Logs*
-   *Changes iFlow Status to Error*
-   *Create Error MPL*



</td>
</tr>
</table>

**Processing**


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

*Entity*

</td>
<td valign="top">

Select the entity for receiving messages.

-   *Queue*
-   *Topic*



</td>
</tr>
<tr>
<td valign="top">

*Queue Name*

\(Only available when Entity as *Queue* is selected\)

</td>
<td valign="top">

Specify the Queue name for receive message.

Example: `OrderProcessingQueue`

</td>
</tr>
<tr>
<td valign="top">

*Topic Name*

\(Only available when Entity as *Topic* is selected\)

</td>
<td valign="top">

Specify the Topic name from which message will be read.

Example: `OrderApproval`

</td>
</tr>
<tr>
<td valign="top">

*Subscription Name*

\(Only available when Entity as *Topic* is selected\)

</td>
<td valign="top">

Specify the subscription name to receive a message.

Example: `OrderSubscription`

</td>
</tr>
<tr>
<td valign="top">

*Max Messages Per Node*

</td>
<td valign="top">

Specify maximum number of messages to be retrieved per node. Recommended: Less than `5000`.

Example: `10`

</td>
</tr>
<tr>
<td valign="top">

*Max Wait Time \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting interval in milliseconds for receiving the messages.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check*

</td>
<td valign="top">

Enable to check duplicate in receiving messages.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check Interval*

</td>
<td valign="top">

Select the action to be performed in case of transaction failure.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Failure Message Handling*

</td>
<td valign="top">

Select the action to be performed in case of transaction failure.

-   *Acknowledge*
-   *Defer*
-   *Keep and Process Again*
-   *Move to Dead Letter Queue*



</td>
</tr>
</table>

