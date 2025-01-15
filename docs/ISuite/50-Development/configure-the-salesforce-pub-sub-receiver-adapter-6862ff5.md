<!-- loio6862ff5515ed44b2856e65a3d7c38a5d -->

# Configure the Salesforce Pub/Sub Receiver Adapter

Salesforce Pub/Sub Receiver adapter allows publishing of messages to Salesforce Pub/Sub.



<a name="loio6862ff5515ed44b2856e65a3d7c38a5d__section_receiver_copy_cl2_kgx_ydc"/>

## How the Salesforce Pub/Sub Receiver Adapter Works

If you have configured the Salesforce Pub/Sub Receiver Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Salesforce Pub/Sub \(this is a receiver system\), Salesforce Pub/Sub Receiver Adapter works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio6862ff5515ed44b2856e65a3d7c38a5d__section_receiver_copy_yst_12z_ydc"/>

## Configure the Salesforce Pub/Sub Receiver Adapter

Once you have created a receiver channel and selected the Salesforce Pub/Sub Receiver Adapter, you can configure its parameters as shown below:

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

Example: `https://login.salesforce.com` for Salesforce production environment, `https://test.salesforce.com` for Salesforce Sandbox environment and `https://{MyDomain}.my.salesforce.com`in case MyDomain is enabled on the org.

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

Specify the Security Token Alias that points to the secure parameter. It can be omitted if your IP has been whitelisted on Salesforce.

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

Specify the username alias that refers to a Secure Parameter.

</td>
</tr>
<tr>
<td valign="top">

*Issuer Alias*

</td>
<td valign="top">

Specify the OAuth client\_id of the connected app in Salesforce for which the certificate was registered.

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

*Operation*

</td>
<td valign="top">

Select the operation to be performed.

</td>
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
</table>

