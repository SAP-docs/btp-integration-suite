<!-- loio719d07cc6a1044efbfaeb9bcb9387238 -->

# Default Adapters for API Artifacts

Adapters define how API artifacts and MCP server artifacts connect to and communicate with target backend services.



When creating an API artifact, you can specify the backend endpoint either by providing a target URL directly or by selecting a destination created in your subaccount. This enables API artifacts to use centrally managed destinations to connect to internet-based or on-premise backend systems. This approach simplifies endpoint management and allows connection details to be maintained independently of the API artifact.

> ### Note:  
> Destination-based connectivity is supported only for API artifacts deployed to the **Integration Cell** runtime. It is not supported for the **Edge Integration Cell** runtime.

In addition to API proxification, API artifacts also support external callout scenarios, enabling communication with backend services without acting as a proxy. Depending on the adapter type, you can connect directly to an internet-accessible endpoint using a URL or use a destination to connect to internet-based or on-premise systems.

After adding and configuring the required policies, configure the adapter that connects the API artifact to the target backend system.

1.  In the Policy model, select the adapter channel between the request flow and the target endpoint.
2.  Configure the connection details based on the adapter type.
3.  Save the configuration.

The following communication channel adapters are supported:


<table>
<tr>
<th valign="top">

Adapter

</th>
<th valign="top">

Description

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Related Topic

</th>
</tr>
<tr>
<td valign="top">

HTTPS

Sender adapter

</td>
<td valign="top">

Establishes an HTTPS connection between SAP Integration Suite and a sender system.

You can connect to an internet-accessible endpoint using a URL or use a destination to access internet-based or on-premise systems.

</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[HTTPS Sender Adapter for API Artifact](https-sender-adapter-for-api-artifact-4a0ac44.md) 

</td>
</tr>
<tr>
<td valign="top">

HTTP

Receiver adapter

</td>
<td valign="top">

Establishes an HTTP connection between SAP Integration Suite and a receiver system.

Receiver adapter:

-   Supports HTTP 1.1 only \(target system must support chunked transfer encoding and may not rely on the existence of the HTTP Content-Length header\)

-   Supports the following methods: DELETE, GET, HEAD, POST, PUT, TRACE


Method can also be determined dynamically by reading a value from a message header or property during runtime.

</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[HTTP Receiver for an API Artifact](http-receiver-for-an-api-artifact-5866acf.md) 

</td>
</tr>
<tr>
<td valign="top">

OData

Sender adapter

</td>
<td valign="top">

Supports callouts to both OData V2 and OData V4 services.

Supports standard OData operations, including create, query, update, patch, and delete, and exchanges messages in ATOM or JSON format.

Connects SAP Integration Suite to systems using the Open Data \(OData\) protocol in either ATOM or JSON format \(only synchronous communication is supported\).

Supported versions: OData version 2.0

-   The adapter receives incoming requests in either ATOM or JSON format.

-   Supported operations: Create \(POST\), Delete \(DELETE\), Query \(GET\), Read \(GET\), Update \(PUT\)

-   Using the GET or POST method, the sender adapter can also invoke operations that are not covered by the standard CRUD \(Create, Retrieve, Update, and Delete\) methods \(function import\).




</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[OData Receiver Adapter for API Artifact](odata-receiver-adapter-for-api-artifact-c34c22f.md) 

</td>
</tr>
<tr>
<td valign="top">

OData

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to systems using the Open Data \(OData\) protocol.

Supported versions:

-   OData version 2.0: Supported operations: Create \(POST\), Delete \(DELETE\), Merge \(MERGE\), Query \(GET\), Read \(GET\), Update \(PUT\), Patch \(PATCH\)

-   OData version 4.0: Supported operations: Create \(POST\), Query \(GET\), Delete \(DELETE\), Update \(PUT\), and Patch \(PATCH\)

    > ### Note:  
    > The default adapter does not support OData V4.




</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[OData Sender Adapter for API Artifact](odata-sender-adapter-for-api-artifact-a636209.md)

</td>
</tr>
<tr>
<td valign="top">

SOAP SOAP 1.x

Sender Adapter

</td>
<td valign="top">

Exchanges messages with a sender system that supports Simple Object Access Protocol \(SOAP\) 1.1 or SOAP 1.2.

The message exchange patterns supported by the sender adapter are one-way messaging or request-reply.

The adapter supports Web services Security \(WS-Security\).

A size limit for the inbound message can be configured for the sender adapter.

</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[SOAP Receiver Adapter for API and MCP Server](soap-receiver-adapter-for-api-and-mcp-server-2a69e87.md) 

</td>
</tr>
<tr>
<td valign="top">

SOAP SOAP 1.x

Receiver adapter

</td>
<td valign="top">

Exchanges messages with a receiver system that supports Simple Object Access Protocol \(SOAP\) 1.1 or SOAP 1.2.

The adapter supports Web services Security \(WS-Security\).

</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[SOAP Sender Adapter for API and MCP Server](soap-sender-adapter-for-api-and-mcp-server-f0e2535.md) 

</td>
</tr>
</table>

