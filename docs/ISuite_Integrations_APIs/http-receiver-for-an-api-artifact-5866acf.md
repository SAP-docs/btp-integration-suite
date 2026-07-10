<!-- loio5866acf4e216422d8edcdb99889d5836 -->

# HTTP Receiver for an API Artifact

The **HTTP Receiver Adapter** enables the API artifact and MCP Server to invoke backend services over HTTP/HTTPS. It acts as the outbound communication channel that connects your integration flow to external systems, whether they are cloud-based endpoints exposed via URLs or systems accessed through pre-configured destinations.



You can configure the HTTP Receiver Adapter in two ways depending on how the backend endpoint is defined:

-   *URL-based*: Directly specify the target endpoint URL. Best suited when the backend address is known and static, and no reusable destination configuration is required.
-   *Destination-based*: Reference a pre-configured API Provider destination. Best suited when connection details \(such as URL, proxy type, and authentication\) are centrally managed and reused across multiple artifacts.

    > ### Note:  
    > Destination-based connectivity is supported only for API artifacts deployed to the **Integration Cell** runtime. It is not supported for the **Edge Integration Cell** runtime.




## HTTP Receiver Adapter \(URL-based\)

Use this configuration when the API artifact endpoint is defined directly as a URL. This mode gives you inline control over the target address, authentication, and timeout settings without depending on an external destination configuration.

****


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

Name of the receiver adapter channel.

</td>
<td valign="top">

HTTP

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Optional description for the adapter.

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Adapter Type

</td>
<td valign="top">

Type of adapter used for backend communication.

</td>
<td valign="top">

HTTP

</td>
</tr>
<tr>
<td valign="top" rowspan="6">

Connection

</td>
<td valign="top">

Type

</td>
<td valign="top">

Specifies the backend endpoint configuration type.

</td>
<td valign="top">

URL

</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

Defines how the backend is reached.

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

Authentication mechanism used to invoke the backend service.

</td>
<td valign="top">

Defines how the tenant \(as the HTTP client\) authenticates itself against the receiver.

You can select one of the following authentication methods:

-   Basic

    The tenant authenticates itself against the receiver using user credentials \(user name and password\).

-   None

    When not to use any authentication can include, but not limited to, the following cases:

    -   If the target system that you want to communicate doesn't require any authentication.

    -   If you want to set an authorization header via a Content Modifier step before the adapter.

    -   If you want to set an authorization header via a Script step before the adapter.


-   OAuth2 Client Credentials

    Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user.

-   Client Certificate

    The tenant authenticates itself against the receiver using a client certificate.

    It's a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on the related tenant. The receiver side has to be configured appropriately.




</td>
</tr>
<tr>
<td valign="top">

Timeout \(in ms\)

</td>
<td valign="top">

Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

The default value is 60000 milliseconds \(1 minute\).

</td>
<td valign="top">

60000

</td>
</tr>
<tr>
<td valign="top">

Request Headers

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), that you want to send to the target system. By default, no custom headers are sent. Alternatively, use an `*` to send all custom headers to the target system. Alternatively, you can dynamically pass on the values by defining a property that includes a list of headers.

For adapter version 1.19 and above, ***traceparent*** is included by default in the Request Headers field.

**Remember**

Use an `*` separately. If you use an `*` and custom header together that are separated by a pipe \(|\), only the custom header is considered.

You must have defined the custom headers in the previous flow steps like content modifiers or scripts before you mention them in the HTTPReceiver Adapter.

The adapter doesn't support regular expressions like `SAP*`.

All Camel-specific headers \(that starts with ***camel*** or ***org.apache.camel***\) and the below listed HTTP protocol headers are excluded even if you specify them.

-   content-length

-   host

-   cache-control

-   connection

-   pragma

-   trailer

-   transfer-encoding

-   upgrade

-   via

-   warning




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

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an `*` to receive all the headers from the target system, which is also the default value.

</td>
<td valign="top">

User-defined

</td>
</tr>
</table>



## HTTP Receiver Adapter \(Destination-based\)

Use this configuration when the API artifact endpoint points to an destination.


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

Name of the receiver adapter channel.

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Channel Details:

Description

</td>
<td valign="top">

Optional description for the adapter.

</td>
<td valign="top">

User-defined

</td>
</tr>
<tr>
<td valign="top">

Adapter Details:

Adapter Type

</td>
<td valign="top">

Type of adapter used for backend communication.

</td>
<td valign="top">

HTTP

</td>
</tr>
<tr>
<td valign="top" rowspan="6">

Connection

</td>
<td valign="top">

Type

</td>
<td valign="top">

Specifies the backend endpoint configuration type.

</td>
<td valign="top">

API provider

</td>
</tr>
<tr>
<td valign="top">

Destination

</td>
<td valign="top">

The pre-configured API Provider destination used to reach the backend system.

</td>
<td valign="top">

Destination name

</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

Defines how the backend is reached.

</td>
<td valign="top">

The type of proxy that you are using to connect to the target system:

-   Select *Internet* if you are connecting to a cloud system.

-   Select *On-Premise* if you are connecting to an on-premise system.



</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

Authentication mechanism used to invoke the backend service.

</td>
<td valign="top">

Defines how the tenant \(as the HTTP client\) authenticates itself against the receiver.

You can select one of the following authentication methods:

-   Basic

    The tenant authenticates itself against the receiver using user credentials \(user name and password\).

-   None

    When not to use any authentication can include, but not limited to, the following cases:

    -   If the target system that you want to communicate doesn't require any authentication.

    -   If you want to set an authorization header via a Content Modifier step before the adapter.

    -   If you want to set an authorization header via a Script step before the adapter.


-   OAuth2 Client Credentials

    Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user.


Enabled only if you choose *Proxy Type* as *Internet*:

-   Client Certificate

    The tenant authenticates itself against the receiver using a client certificate.

    It's a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on the related tenant. The receiver side has to be configured appropriately.




</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

The endpoint URL resolved from the selected API Provider destination.

</td>
<td valign="top">

Auto-populated from destination

</td>
</tr>
<tr>
<td valign="top">

Timeout \(in ms\)

</td>
<td valign="top">

Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

The default value is 60000 milliseconds \(1 minute\).

</td>
<td valign="top">

60000

</td>
</tr>
</table>

