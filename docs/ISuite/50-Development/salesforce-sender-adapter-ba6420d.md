<!-- loioba6420dc38dc4bcc96df1a28ab80af5e -->

# Salesforce Sender Adapter

Once you have created a sender channel and selected the *Salesforce* adapter, you can configure its attributes.

The *General* tab shows general information such as the adapter type, its direction \(sender\), the transport protocol, and the message protocol.

Select the *Connection* tab and provide the sender information.

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

*Authentication*

</td>
<td valign="top">

Specify the type of Authentication to be used when connecting to Salesforce.

Select one of the following types:

-   *OAuth Client Credentials*

-   *OAuth JWT Bearer*




</td>
</tr>
<tr>
<td valign="top">

*Address*

\(if *Authentication* is *OAuth Client Credentials*\)

</td>
<td valign="top">

Specifies the recipient's endpoint URL, the Salesforce login base URL, for user authentication.

</td>
</tr>
<tr>
<td valign="top">

*Basic Credential Name*

\(if *Authentication* is *OAuth Client Credentials*\)

</td>
<td valign="top">

Specifies the name of the *User Credentials* artifact that contains the credentials for basic authentication. This refers to the username-password pair used in authentication to Salesforce. This property enables the system to fetch the *User Credentials* security material deployed on SAP Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

*Security Token Alias*

\(if *Authentication* is *OAuth Client Credentials*\)

</td>
<td valign="top">

Specifies the name of the *Secure Parameter* artifact that contains the security token needed to connect to Salesforce. This property enables the system to fetch the Security Token from the security material deployed on SAP Cloud Integration. This field can be omitted if your IP has been whitelisted on Salesforce

</td>
</tr>
<tr>
<td valign="top">

*OAuth Credential Name*

\(if *Authentication* is *OAuth Client Credentials*\)

</td>
<td valign="top">

​

Specifies the name of the *OAuth Client Credentials* artifact that contains the Salesforce’s OAuth consumer key-client secret pair. This property enables the system to retrieve the OAuth security material deployed on SAP Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

*Audience*

\(if *Authentication* is *OAuth JWT Bearer*\)

</td>
<td valign="top">

Specifies the recipient's endpoint URL.

By default, the URL `https://login.salesforce.com` is used. Based on your scenario, you can change this setting:

-   For Salesforce production environments: `https://login.salesforce.com`.

-   For Sandbox environments: `https://test.salesforce.com`

-   If `MyDomain` is enabled on the org, you can use `https://<MyDomain>.my.salesforce.com`.




</td>
</tr>
<tr>
<td valign="top">

*Subject Alias*

\(if *Authentication* is *OAuth JWT Bearer*\)

</td>
<td valign="top">

The alias name of the deployed *Secure Parameter* artifact. It specifies the Salesforce username.

</td>
</tr>
<tr>
<td valign="top">

*Issuer Alias*

\(if *Authentication* is *OAuth JWT Bearer*\)

</td>
<td valign="top">

The alias name of the deployed *Secure Parameter* artifact. It specifies the OAuth Consumer Key of the connected app for which the certificate was registered.

</td>
</tr>
<tr>
<td valign="top">

*Keystore Alias*

\(if *Authentication* is *OAuth JWT Bearer*\)

</td>
<td valign="top">

The alias name of the added JKS file in the keystore as a key pair. It consists of a key and certificate to sign the JWT.

</td>
</tr>
<tr>
<td valign="top">

*Expiration*

\(if *Authentication* is *OAuth JWT Bearer*\)

</td>
<td valign="top">

Specifies the validity of the assertion in seconds.

</td>
</tr>
<tr>
<td valign="top">

*Polling Interval \(in ms\)* 

</td>
<td valign="top">

Specifies the polling interval expressed in milliseconds. The polling interval allows you to control the waiting time before checking if the existing connection is still active or needs to be reestablished.

</td>
</tr>
<tr>
<td valign="top">

*Process Errors as an Event* 

</td>
<td valign="top">

Select this option to treat errors while connecting to Salesforce as events.

*Process Errors as an Event* creates message exceptions in SAP Cloud Integration for each connection error during Salesforce Streaming. Errors that prevent Cloud Integration from picking up events via streaming are raised as a message exception in Cloud Integration. An example exception message during streaming is `Organization concurrent user limit exceeded`.

</td>
</tr>
</table>

Select the *Processing* tab and provide the recipient information.

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

*Event Type*

</td>
<td valign="top">

Specifies the event type to be retrieved from Salesforce.

Select one of the following types:

-   *PushTopic Events*

-   *Generic Events*

-   *Platform Events*

-   *Change Data Capture Events* 




</td>
</tr>
<tr>
<td valign="top">

*Replay Id Approach*

</td>
<td valign="top">

Every event or message retrieved from Salesforce Stream is assigned a `Replay ID` value. This field refers to the position of the event in the event stream.

There are 3 possible settings:

-   *Events from latest position \(-1\)* 

    Enables SAP Cloud Integration to receive any new events. It represents `Replay ID` value `-1`. Note that the integration flow needs to be deployed and running for any new event to be received. Any event generated while the integration flow is not available will be missed.

-   *Events from earliest position \(-2\)*

    Enables SAP Cloud Integration to receive all events that have not yet expired. It represents `Replay ID` value `-2`.

-   *Events from a specific position*

    This option gives the possibility to specify any `Replay ID`. If chosen, SAP Cloud Integration receives all events that were created after the specified Replay ID. If the `Replay ID` is `5`, a message containing Replay Id 6, 7, 8, and so forth, is retrieved.




</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specifies the operation to perform towards Salesforce by choosing one of the provided operation options. Currently, the *Subscribe* option is available.

</td>
</tr>
<tr>
<td valign="top">

*Channel Name*

</td>
<td valign="top">

Made of a Topic name preceded with a prefix. For instance, a PushTopic can be prefixed with `/topic/`. Example: `/topic/MyPushTopic`. Note that in general the names are case-sensitive.

</td>
</tr>
<tr>
<td valign="top">

*Replay Id*

</td>
<td valign="top">

Refers to the position of the event in the event stream. The *Replay Id* is populated by Salesforce and refers to the position of the event in the event stream. Note that the *Replay Id* values are not guaranteed to be continuous for consecutive events. By specifying the value of the *Replay Id*, the integration flow retrieves events that are within the retention window and that have followed the specified *Replay Id*. Example: If *Replay Id* 6 is specified, the integration flow receives all messages with a *Replay Id* greater than 6.

</td>
</tr>
<tr>
<td valign="top">

*API Version*

</td>
<td valign="top">

Specifies the version of the API to be used for retrieving data from Salesforce. The default version is 51.0.

</td>
</tr>
<tr>
<td valign="top">

*Payload Format*

</td>
<td valign="top">

Specifies the format of the request message to be sent to and the response to be returned from Salesforce. Possible values include *Application/XML* and *Application/JSON*. Note that the default value is *Application/XML*.

</td>
</tr>
<tr>
<td valign="top">

*Pretty Print*

</td>
<td valign="top">

Select the *Pretty Print* option to have the XML payload nicely formatted and its readability improved.

</td>
</tr>
</table>

