<!-- loiobc177b404e11407f8c77204db97261d2 -->

# Connection Setup for Inbound Communication - for API Clients

The Cloud Integration OData API allows you to access Cloud Integration resources \(for example, integration content, Partner Directory content, or message processing logs\) through an API. Using API-based access, you can write programs that process Cloud Integration resources. When configuring secure inbound HTTP connections, different authentication options can be used to authenticate API clients against the Cloud Integration OData API.

For more information on the OData API, see [OData API](../Development/odata-api-a617d6f.md).



<a name="loiobc177b404e11407f8c77204db97261d2__section_fxd_dff_fpb"/>

## Cloud Foundry Environment

The following table provides an overview of the available authentication options and a summary of the configuration steps in the Cloud Foundry environment \(for the connection to API resources\). The table provides a brief summary to indicate the key aspects. Note that the most secure/recommended options are on top, the less secure ones further below in the table.


<table>
<tr>
<th valign="top">

Authentication Option

</th>
<th valign="top">

Configuration \(Summary\)

</th>
<th valign="top">

How it Works

</th>
</tr>
<tr>
<td valign="top">

OAuth

</td>
<td valign="top">

Go to SAP BTP cockpit and define a service key for the *Process Integration* service and *api* plan. Specify the role that is to be used to grant access to the Cloud Integration resource. For example, if you like to access message processing logs through the OData API, you need to specify role template `MonitoringDataRead`.

The generated service key contains the following properties: `clientid`, `clientsecret`, and `tokenurl`.

See: [OAuth with Client Credentials Grant for API Clients](../ConnectionSetup/oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

</td>
<td valign="top">

For the client credentials grant variant of OAuth, authentication at runtime comprises two HTTP requests:

1.  In a first request \(addressed to the token service reachable by the `tokenurl`\), the API client provides `clientid` and `clientsecret` and gets back from the token service an access token.

2.  In a second request \(addressed to the Cloud Integration resource\), the API client provides the access token and gets access to the Cloud Integration resource.

    For modifying calls, an CSRF-Token is required.




</td>
</tr>
<tr>
<td valign="top">

Basic authentication of a user registered at an identity provider \(IdP\)

\(this option isn't considered to be secure enough for productive scenarios\)

</td>
<td valign="top">

Register a user at an identity provider \(for example, SAP's default identity provider SAP ID Service\). Using SAP BTP cockpit, you assign to the user a role template to be used to grant permission to access to the Cloud Integration resource \(for example, `MonitoringDataRead` when you like to access message processing logs\).

See: [Basic Authentication of an IdP User for API Clients](../ConnectionSetup/basic-authentication-of-an-idp-user-for-api-clients-57f104d.md)

</td>
<td valign="top">

With username and password \(known to the identity provider\), the API client can access the Cloud Integration resource.

For modifying calls, an CSRF-Token is required.

</td>
</tr>
</table>



<a name="loiobc177b404e11407f8c77204db97261d2__section_m4g_2ff_fpb"/>

## Neo Environment

The following table provides an overview of the available authentication options and a summary of the configuration steps in the Neo environment \(for the connection to API resources\). The table provides a brief summary to indicate the key aspects. Note that the most secure/recommended options are on top, the less secure ones further below in the table.


<table>
<tr>
<th valign="top">

Authentication Option

</th>
<th valign="top">

Configuration \(Summary\)

</th>
<th valign="top">

How it Works

</th>
</tr>
<tr>
<td valign="top">

OAuth

</td>
<td valign="top">

Go to SAP BTP cockpit and define an OAuth client. For *Authorization Grant* select the option *Client Credentials*. On saving, a client ID and secret is generated. Assign to user `oauth_client_<client ID>` a role that grants access to the Cloud Integration resource.

See: [Setting Up OAuth Inbound Authentication with Client Credentials Grant for API Clients](../ConnectionSetup/setting-up-oauth-inbound-authentication-with-client-credentials-grant-for-api-clients-040d811.md)

</td>
<td valign="top">

For the client credentials grant variant of OAuth, authentication at runtime comprises two HTTP requests:

1.  In a first request \(addressed to a service with an URL as described at [Setting Up OAuth Inbound Authentication with Client Credentials Grant for API Clients](../ConnectionSetup/setting-up-oauth-inbound-authentication-with-client-credentials-grant-for-api-clients-040d811.md)\), the API client provides ID and Secret from the OAuth client and gets back an access token.

2.  In a second request \(addressed to the Cloud Integration resource\), the sender provides the access token and gets access to the Cloud Integration resource.

    For modifying calls, an CSRF-Token is required.




</td>
</tr>
<tr>
<td valign="top">

Basic authentication of a user registered at an identity provider \(IdP\)

\(this option isn't considered to be secure enough for productive scenarios\)

</td>
<td valign="top">

Register a user at an identity provider \(for example, SAP's default identity provider SAP ID Service\). Using SAP BTP cockpit, you assign to the user a role template to be used to grant permission to access to the Cloud Integration resource.

See: [Setting Up Inbound Authentication of an IdP User for API Clients](../ConnectionSetup/setting-up-inbound-authentication-of-an-idp-user-for-api-clients-1656c91.md) 

</td>
<td valign="top">

With username and password \(known to the identity provider\), the API client can access the Cloud Integration resource. For modifying calls, an CSRF-Token is required.

</td>
</tr>
</table>

