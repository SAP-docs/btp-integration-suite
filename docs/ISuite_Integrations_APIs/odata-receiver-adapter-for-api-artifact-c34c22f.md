<!-- loioc34c22f3335641fe991166c8c2a0b27a -->

# OData Receiver Adapter for API Artifact

The OData receiver adapter forwards requests from an API artifact to an OData service. It acts as the outbound communication endpoint of the policy model and enables the API artifact to invoke OData services hosted on cloud or on-premise systems.



The OData receiver adapter is automatically added when you create an API artifact with the **OData** service type. After requests are processed by the configured policies, the adapter forwards them to the target OData service using either a direct URL or an SAP BTP destination.

The adapter supports two connection types:

-   **URL-based** – Connects directly to an OData service by specifying its endpoint URL.
-   **Destination-based** – Connects to an OData service through a configured SAP BTP destination.

    > ### Note:  
    > Destination-based connectivity is supported only for API artifacts deployed to the **Integration Cell** runtime. It is not supported for the **Edge Integration Cell** runtime.


The adapter configuration defines how the API artifact connects to the target OData service, including the connection type, authentication method, proxy configuration, and request processing options.



**OData Receiver \(URL-based\)**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
<th valign="top">

Value/Options

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

General

</td>
<td valign="top">

Name

</td>
<td valign="top">

Specifies a unique name for the OData receiver adapter.

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Specifies an optional description for the adapter configuration.

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **OData** and cannot be changed.

</td>
<td valign="top">

OData \(Read-only\)

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Connection

</td>
<td valign="top">

Type

</td>
<td valign="top">

Specifies that the adapter connects directly to an OData service using its service URL.

</td>
<td valign="top">

URL \(Read-only\)

</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

Specifies the network through which the adapter connects to the target OData service. Currently, only **Internet** is supported for URL-based connections.

</td>
<td valign="top">

Internet

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

Specifies the authentication method used to connect to the target OData service. The available options depend on the target service requirements.

</td>
<td valign="top">

You can select one of the following authentication methods:

-   Basic: The tenant authenticates itself against the receiver using user credentials \(user name and password\).

-   None: When not to use any authentication can include, but not limited to, the following cases:

    -   If the target system that you want to communicate doesn't require any authentication.

    -   If you want to set an authorization header via a Content Modifier step before the adapter.

    -   If you want to set an authorization header via a Script step before the adapter.


-   OAuth2 Client Credentials: Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user.

-   Client Certificate: The tenant authenticates itself against the receiver using a client certificate.




</td>
</tr>
<tr>
<td valign="top">

CSRF Protected

</td>
<td valign="top">

Keep this option selected \(default setting\) to ensure that your integration artifact is protected against Cross-Site-Request-Forgery, a kind of attack where a malicious party can perform harmful actions by masquerading as the logged in user.

</td>
<td valign="top">

Enabled

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Processing

</td>
<td valign="top">

Operation Details

</td>
<td valign="top">

Specifies how the adapter determines the OData operation during runtime. The operation is resolved dynamically based on the incoming request.

</td>
<td valign="top">

Dynamic

</td>
</tr>
<tr>
<td valign="top">

Attach Error Details on Failure

</td>
<td valign="top">

Specifies whether request and response details are included in the generated error attachment when message processing fails.

</td>
<td valign="top">

Enabled

</td>
</tr>
<tr>
<td valign="top">

Request Headers

</td>
<td valign="top">

Specifies the HTTP request headers that are forwarded to the target OData service. You can specify individual headers or use wildcard patterns \(for example, `*`\).

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Response Headers

</td>
<td valign="top">

Specifies the HTTP response headers returned by the OData service that are propagated back to the API artifact. You can specify individual headers or use wildcard patterns \(for example, `*`\).

</td>
<td valign="top">

User-defined

</td>
</tr>
</table>

**OData Receiver \(Destination-based\)**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
<th valign="top">

Value/Options

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

General

</td>
<td valign="top">

Name

</td>
<td valign="top">

Specifies a unique name for the OData receiver adapter.

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Specifies an optional description for the adapter configuration.

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **OData** and cannot be changed.

</td>
<td valign="top">

OData \(Read-only\)

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Connection

</td>
<td valign="top">

Type

</td>
<td valign="top">

Specifies that the adapter connects directly to an OData service using its service URL.

</td>
<td valign="top">

URL \(Read-only\)

</td>
</tr>
<tr>
<td valign="top">

Destination

</td>
<td valign="top">

Specifies the SAP BTP destination that defines the endpoint and connectivity settings for the target OData service.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

Specifies the connectivity type used to access the target OData service. Select **Internet** for cloud-based services or **On-Premise** to connect through SAP Cloud Connector.

</td>
<td valign="top">

Internet, On-Premise

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

Specifies the authentication method used to connect to the target OData service. The available options depend on the target service requirements.

</td>
<td valign="top">

You can select one of the following authentication methods:

-   Basic: The tenant authenticates itself against the receiver using user credentials \(user name and password\).

-   None: When not to use any authentication can include, but not limited to, the following cases:

    -   If the target system that you want to communicate doesn't require any authentication.

    -   If you want to set an authorization header via a Content Modifier step before the adapter.

    -   If you want to set an authorization header via a Script step before the adapter.


-   OAuth2 Client Credentials: Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user.

-   Client Certificate: The tenant authenticates itself against the receiver using a client certificate.




</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

Displays the endpoint URL resolved from the selected destination. This value is read-only and is automatically populated after a destination is selected.

</td>
<td valign="top">

System-generated

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Processing

</td>
<td valign="top">

Operation Details

</td>
<td valign="top">

Specifies how the adapter determines the OData operation during runtime. The operation is resolved dynamically based on the incoming request.

</td>
<td valign="top">

Dynamic

</td>
</tr>
<tr>
<td valign="top">

Attach Error Details on Failure

</td>
<td valign="top">

Specifies whether request and response details are included in the generated error attachment when message processing fails.

</td>
<td valign="top">

Enabled

</td>
</tr>
<tr>
<td valign="top">

Request Headers

</td>
<td valign="top">

Specifies the HTTP request headers that are forwarded to the target OData service. You can specify individual headers or use wildcard patterns \(for example, `*`\).

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Response Headers

</td>
<td valign="top">

Specifies the HTTP response headers returned by the OData service that are propagated back to the API artifact. You can specify individual headers or use wildcard patterns \(for example, `*`\).

</td>
<td valign="top">

User-defined

</td>
</tr>
</table>

