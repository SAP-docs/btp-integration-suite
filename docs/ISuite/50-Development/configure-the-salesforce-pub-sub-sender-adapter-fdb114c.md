<!-- loiofdb114ce369a4f0da1f67d07bbce5bbe -->

# Configure the Salesforce Pub/Sub Sender Adapter

Salesforce Pub/Sub Sender adapter provides the ability to consume messages seamlessly from Salesforce Pub/Sub.



<a name="loiofdb114ce369a4f0da1f67d07bbce5bbe__section_cl2_kgx_ydc"/>

## How the Salesforce Pub/Sub Sender Adapter Works

If you have configured the Salesforce Pub/Sub Sender Adapter, data exchange is performed as follows at runtime: Salesforce Pub/Sub sends the operation request to SAP Integration Suite tenant, Salesforce Pub/Sub Sender Adapter works on the request and sends the data to SAP Integration Suite tenant.



<a name="loiofdb114ce369a4f0da1f67d07bbce5bbe__section_yst_12z_ydc"/>

## Configure the Salesforce Pub/Sub Sender Adapter

Once you have created a sender channel and selected the Salesforce Pub/Sub Sender Adapter, you can configure its parameters as shown below:

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

*Host*

</td>
<td valign="top">

Specify the host to which the proxy requests are sent for the gRPC API \(towards the gRPC host\). The proxy requests to the gRPC host will go through the proxy.

Example: `api.pubsub.salesforce.com`

</td>
</tr>
<tr>
<td valign="top">

*Port*

</td>
<td valign="top">

Specify the port to which the proxy requests are sent for the gRPC API \(towards the gRPC port\). The proxy requests to the gRPC port will go through the proxy.

Example: `7443`

</td>
</tr>
<tr>
<td valign="top">

*Tenant ID*

</td>
<td valign="top">

Specify the Salesforce Organization ID.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the authentication type to be used for the connection to Salesforce:

-   *OAuth 2.0 Username-Password*
-   *OAuth 2.0 JWT Bearer*



</td>
</tr>
<tr>
<td valign="top" colspan="2">

> ### Note:  
> The following fields are available when *Authentication* is set to *OAuth 2.0 Username-Password*.



</td>
</tr>
<tr>
<td valign="top">

*Token URL*

</td>
<td valign="top">

Specify the login endpoint to your Salesforce instance url.

Example: `https://login.salesforce.com` for Salesforce production environment, `https://test.salesforce.com` for Salesforce Sandbox environment and `https://{MyDomain}.my.salesforce.com` in case MyDomain is enabled on the org.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the User Credentials storing the username-password details.

</td>
</tr>
<tr>
<td valign="top">

*Security Token Alias*

</td>
<td valign="top">

Specify the Security Token Alias that points to the Secure Parameter. It can be omitted if your IP has been whitelisted on Salesforce.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Credential Name*

</td>
<td valign="top">

Specify the OAuth Credential Name that refers to the user credentials \(Consumer key-Client secret pair\).

</td>
</tr>
<tr>
<td valign="top" colspan="2">

> ### Note:  
> The following fields are available when *Authentication* is set to *OAuth 2.0 JWT Bearer*.



</td>
</tr>
<tr>
<td valign="top">

*Audience*

</td>
<td valign="top">

Specify the login endpoint to your Salesforce instance URL.

Example:`https://login.salesforce.com` for Salesforce production environment, `https://test.salesforce.com` for Salesforce Sandbox environment and `https://site.force.com/customers` if implementing for an Experience Cloud site

</td>
</tr>
<tr>
<td valign="top">

*Subject Alias*

</td>
<td valign="top">

Specify the Secure Parameter that stores the username of the Salesforce user.

</td>
</tr>
<tr>
<td valign="top">

*Issuer Alias*

</td>
<td valign="top">

Specify the Secure Parameter which indicates the OAuth client\_id of the connected app in Salesforce for which the certificate was registered.

</td>
</tr>
<tr>
<td valign="top">

*Keystore Alias*

</td>
<td valign="top">

Specify the alias name of the added JKS file in Keystore as a Key Pair. It consists of key and certificate to sign the JWT.

</td>
</tr>
<tr>
<td valign="top">

*Expiration \(in ms\)*

</td>
<td valign="top">

Specifies the validity of the assertion in milliseconds.

</td>
</tr>
<tr>
<td valign="top">

*Connection Check Interval \(in ms\)*

</td>
<td valign="top">

Specify the interval in milliseconds to verify the connection validity of the gRPC.

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

*Channel Name*

</td>
<td valign="top">

Specify the Salesforce channel name to perform the subscription.

> ### Note:  
> The channel name is case-sensitive.



</td>
</tr>
<tr>
<td valign="top">

*Replay ID Approach*

</td>
<td valign="top">

Select the replay option in the first FetchRequest:

-   *Events from a specific position \(Custom\)*
-   *Events from a earliest position \(Earliest\)*
-   *Events from latest position \(Latest\)*

    > ### Note:  
    > The default value is *Events from latest position \(Latest\)* allows subscription only to new event messages and does not retrieve earlier event messages stored in the event bus.




</td>
</tr>
<tr>
<td valign="top">

*Replay ID*

</td>
<td valign="top">

Specify the Replay ID value. The Replay ID is populated by Salesforce and refers to the position of the event in the event stream.

Example: `8381402`

</td>
</tr>
<tr>
<td valign="top">

*Request Batch size*

</td>
<td valign="top">

Specify the number of events to be requested in the Salesforce fetchRequest. The default value is `100`.

</td>
</tr>
<tr>
<td valign="top">

*Replay Preset for Invalid Replay ID*

</td>
<td valign="top">

Select the replay option in case `sfdc.platform.eventbus.grpc.subscription.fetch.replayid.corrupted` error occurs:

-   *Events from latest position \(Latest\)*
-   *Events from earliest position \(Earliest\)*

    > ### Note:  
    > The default value is *Events from earliest position \(Earliest\)* indicating the earlier \(existing\) event messages stored in the event bus.




</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check Expiration \(in ms\)*

</td>
<td valign="top">

Specify the expiry time in milliseconds while handling the Duplicate check. The default value is `300000`.

</td>
</tr>
<tr>
<td valign="top">

*Process Errors as an Event*

</td>
<td valign="top">

Enable to write error events in the exchange. If disabled, issues connecting to event streams will only be written to the logs.

</td>
</tr>
</table>

