<!-- loio641600ecbda44d9e8c16db02afe71b43 -->

# **Supported Adapters for External Callout in API Artifacts**

Overview of the receiver adapters supported when configuring additional Request-Reply steps in an API artifact to enable synchronous communication with external systems.



When designing an API artifact, you can add one or more Request-Reply policies as exit points to synchronously call external receiver systems and process their responses. Each Request-Reply step is connected to a receiver shape through a receiver channel, which uses a specific adapter to communicate with the target system. SAP Integration Suite supports a range of adapters that enable connectivity to diverse external systems — including cloud applications, on-premise backends, messaging systems, and databases — allowing you to extend the API artifact’s behavior with flexible, protocol-specific integrations.

After adding and configuring the required policies, configure the adapter that connects the API artifact to the target backend system.

1.  In the Policy Model, select the adapter channel between the request flow and the target endpoint.
2.  Configure the connection details based on the adapter type.
3.  Save the configuration.

The following communication channel adapters are supported


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

HTTP

Receiver adapter

</td>
<td valign="top">

Establishes an HTTP connection between SAP Integration Suite and a receiver system.

Receiver adapter:

-   Supports HTTP 1.1 only \(target system must support chunked transfer encoding and may not rely on the existence of the HTTP Content-Length header\)

-   Supports the following methods: DELETE, GET, HEAD, POST, PUT, TRACE


Method can also be determined dynamically by reading a value from a message header or property during runtime.

> ### Note:  
> Only destinations with the *Proxy Type* set to `Internet` is currently supported.
> 
> Supported authentication mechanism for `Internet`: Basic Authentication, No Authentication, OAuth2 Client Credentials, and Client Certificate



</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[HTTP Receiver Adapter](http-receiver-adapter-2da452e.md)

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




</td>
<td valign="top">

-   Integration Cell

-   Edge Integration Cell




</td>
<td valign="top">

[Configure the OData V2 Receiver Adapter](configure-the-odata-v2-receiver-adapter-c5c2e38.md)

[Configure the OData V4 Receiver Adapter](configure-the-odata-v4-receiver-adapter-cd66a12.md)

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

[Configure the SOAP \(SOAP 1.x\) Receiver Adapter](configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md)

</td>
</tr>
<tr>
<td valign="top">

Mail

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send e-mails to an e-mail server.

To authenticate against the e-mail server, you can send the user name and password in plain text or encrypted \(the latter only if the e-mail server supports this option\).

You can protect outbound e-mails at the transport layer with STARTTLS or SMTPS.

You can encrypt outbound e-mails using S/MIME \(supported content encryption algorithms: AES/CBC/PKCS5Padding, DESede/CBC/PKCS5Padding\).

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[Configure the Mail Receiver Adapter](configure-the-mail-receiver-adapter-f68d5e0.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to a JDBC \(Java Database Connectivity\) database and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC for DB2 \(On-Premise\)

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to DB2 \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC for DB2 \(On-Premise\)](jdbc-for-db2-on-premise-9515cf8.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC for Microsoft SQL Server \(Cloud\)

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Microsoft SQL Server \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC for Microsoft SQL Server \(Cloud\)](jdbc-for-microsoft-sql-server-cloud-4173d0a.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC for Microsoft SQL Server \(On-Premise\)

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Microsoft SQL Server \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC for Microsoft SQL Server \(On-Premise\)](jdbc-for-microsoft-sql-server-on-premise-9745e40.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC for Oracle \(Cloud\)

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Oracle \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC for Oracle \(Cloud\)](jdbc-for-oracle-cloud-f868182.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC for Oracle \(On-Premise\)

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Oracle \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC for Oracle \(On-Premise\)](jdbc-for-oracle-on-premise-e6db38a.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC for PostgreSQL \(Cloud\)

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to PostgreSQL \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC for PostgreSQL \(Cloud\)](jdbc-for-postgresql-cloud-4d5b488.md) 

</td>
</tr>
<tr>
<td valign="top">

JDBC for SAP HANA Cloud

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to SAP HANA Cloud using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[JDBC for SAP HANA \(Cloud\)](jdbc-for-sap-hana-cloud-187a8e8.md) 

</td>
</tr>
<tr>
<td valign="top">

RFC

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote receiver system using Remote Function Call \(RFC\).

RFC is the standard interface used for integrating on-premise ABAP systems to the systems hosted on the cloud using SAP Cloud Connector.

The adapter supports SAP NetWeaver, version 7.31 or higher.

</td>
<td valign="top">

-   Edge Integration Cell




</td>
<td valign="top">

[RFC Receiver Adapter](rfc-receiver-adapter-5c76048.md) 

</td>
</tr>
</table>

