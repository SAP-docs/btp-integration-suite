<!-- loioe67db827ba4f4197b88fac068de7a797 -->

# Azure Service Bus Receiver Adapter

Azure Service Bus Receiver Adapter allows reliable and convenient publishing of messages to Azure Service Bus.



## How the Azure Service Bus Receiver Adapter Works

If you have configured the Azure Service Bus Receiver Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Azure Service Bus \(this is a receiver system\), the adapter works on the request and sends the data back to the SAP Integration Suite tenant.



## Configure the Azure Service Bus Receiver Adapter

Once you have created a receiver channel and selected the Azure Service Bus Receiver Adapter, you can configure its parameters as shown below:

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

*Maximum Reconnect Attempts*

</td>
<td valign="top">

Specify the maximum number of retries to connect to Azure Service Bus.

Example: `3`

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting in milliseconds for the connection to be established. This is applicable to each retry, so the total connection timeout will also be dependent on the Maximum Reconnect Attempts.

Example: `60000`

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

Select the entity to write a message:

-   *Queue*
-   *Topic*



</td>
</tr>
<tr>
<td valign="top">

*Queue Name*

\(only available when *Entity* is selected as *Queue*\)

</td>
<td valign="top">

Specify the name of the Queue to which the message will be sent.

Example: `OrderProcessingQueue`

</td>
</tr>
<tr>
<td valign="top">

*Topic Name*

\(only available when *Entity* is selected as *Topic*\)

</td>
<td valign="top">

Specify the name of the Topic to which the message will be sent.

Example: `OrderApproval`

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

</td>
<td valign="top">

Select content type for message to be sent to Azure Service Bus:

-   *Application/JSON*
-   *Application/XML*
-   *Text/Plain*



</td>
</tr>
<tr>
<td valign="top">

*Broker Properties*

</td>
<td valign="top">

Enable to send Broker Properties to the message.

</td>
</tr>
<tr>
<td valign="top">

*Correlation ID*

</td>
<td valign="top">

Specify the Correlation Identifier for the message.

Example: `987f6543-a21c-34b5-d678-123456789abc`

</td>
</tr>
<tr>
<td valign="top">

*Message ID*

</td>
<td valign="top">

Specify the Message Identifier for the message.

Example: `b7f3a9d2-8c5e-4a1b-9e3d-2f6a7c8d9eOf`

</td>
</tr>
<tr>
<td valign="top">

*To*

</td>
<td valign="top">

Specify the address of the queue or topic to which message must be sent.

Example: `order-processing-service`

> ### Note:  
> This property is reserved for future use in routing scenarios and is currently ignored by the broker itself.



</td>
</tr>
<tr>
<td valign="top">

*Reply To*

</td>
<td valign="top">

Specify the address of the queue or topic for which a response must be sent.

Example: `response-queue`

</td>
</tr>
<tr>
<td valign="top">

*Time To Live \(in ms\)*

</td>
<td valign="top">

Specify a Time To Live \(TTL\) attribute \(in milliseconds\) for the message to be sent. Messages exceeding their TTL duration expire and are not retained by Azure Service Bus.

Example: `30000`

</td>
</tr>
<tr>
<td valign="top">

*Session ID*

</td>
<td valign="top">

Specify the session affiliation of the message for session aware entities.

Example: `session-xyz789`

</td>
</tr>
<tr>
<td valign="top">

*Reply To Session ID*

</td>
<td valign="top">

Specify the session identifier to reply to.

Example: `response-98765-session`

</td>
</tr>
<tr>
<td valign="top">

*Label/Subject*

</td>
<td valign="top">

Specify the label or subject for the message.

Example: `OrderProcessing`

</td>
</tr>
<tr>
<td valign="top">

*Partition Key*

</td>
<td valign="top">

Specify the partition key to the message.

Example: `order-98765`

</td>
</tr>
<tr>
<td valign="top">

*Key*

</td>
<td valign="top">

Specify the key to the property for the message.

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Select the type of property for the message:

-   *Date*
-   *Boolean*
-   *Number*
-   *String*



</td>
</tr>
<tr>
<td valign="top">

*Value*

</td>
<td valign="top">

Specify the value for the message.

</td>
</tr>
</table>

