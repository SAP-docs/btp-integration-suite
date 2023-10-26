<!-- loio55325f2a722c4f67bb7752b369b09ff8 -->

# Connectivity \(Adapters\)

You have the option to specify which technical protocols should be used to connect a sender or a receiver to the tenant.

> ### Remember:  
> There are currently certain limitations when working in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

The following **adapters** are available.



<a name="loio55325f2a722c4f67bb7752b369b09ff8__section_gv3_zlx_ztb"/>

## Adapters Provided by SAP

When designing an integration flow, you can choose among the following adapters predefined by SAP.

**Adapter**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*AmazonWebServices* 

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to Amazon Web Services.

The adapter supports the following protocols:

-   S3: Simple Cloud Storage

-   SQS: Simple Queue Service


See: [AmazonWebServices Sender Adapter](../Development/amazonwebservices-sender-adapter-16772e3.md)

</td>
</tr>
<tr>
<td valign="top">

*AmazonWebServices* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to Amazon Web Services.

The adapter supports the following protocols:

-   S3: Simple Cloud Storage

-   SQS: Simple Queue Service

-   SNS: Simple Notification Service

-   SWF: Simple Workflow Service


See: [AmazonWebServices Receiver Adapter](../Development/amazonwebservices-receiver-adapter-bc7d1aa.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from queues or topic subscriptions in an external messaging system.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocols: TCP, WebSocket

See: [Configure the AMQP Sender Adapter](../Development/configure-the-amqp-sender-adapter-99ce674.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send messages to queues or topics in an external messaging system.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocols: TCP, WebSocket

See: [Configure the AMQP Receiver Adapter](../Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for SAP Event Mesh*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from SAP Event Mesh.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: WebSocket

See: [AMQP Sender for SAP Event Mesh](../Development/amqp-sender-for-sap-event-mesh-7d8a83f.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for SAP Event Mesh*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send messages to SAP Event Mesh.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: WebSocket

See: [AMQP Receiver for SAP Event Mesh](../Development/amqp-receiver-for-sap-event-mesh-0b7cc2f.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Microsoft Azure Service Bus*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from Microsoft Azure Service Bus.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Sender for Microsoft Azure Service Bus](../Development/amqp-sender-for-microsoft-azure-service-bus-7384ac3.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Microsoft Azure Service Bus*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send messages to Microsoft Azure Service Bus.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Receiver for Microsoft Azure Service Bus](../Development/amqp-receiver-for-microsoft-azure-service-bus-9c64d80.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Solace PubSub+*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from Solace PubSub+.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Sender for Solace PubSub+](../Development/amqp-sender-for-solace-pubsub-c9ab47d.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Solace PubSub+*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send messages to Solace PubSub+.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Receiver for Solace PubSub+](../Development/amqp-receiver-for-solace-pubsub-19f18d8.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache Qpid Broker-J*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from Apache Qpid Broker-J.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP, WebSocket

See: [AMQP Sender for Apache Qpid Broker-J](../Development/amqp-sender-for-apache-qpid-broker-j-b4983f7.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache Qpid Broker-J*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send messages to Apache Qpid Broker-J.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP, WebSocket

See: [AMQP Receiver for Apache Qpid Broker-J](../Development/amqp-receiver-for-apache-qpid-broker-j-622aa1d.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache ActiveMQ 5 / Apache ActiveMQ Artemis*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from Apache ActiveMQ 5 / Apache ActiveMQ Artemis.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Sender for Apache ActiveMQ 5 and Apache ActiveMQ Artemis](../Development/amqp-sender-for-apache-activemq-5-and-apache-activemq-artemis-dc4c564.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache ActiveMQ 5 / Apache ActiveMQ Artemis*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send messages to Apache ActiveMQ 5 / Apache ActiveMQ Artemis.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Receiver for Apache ActiveMQ 5 and Apache ActiveMQ Artemis](../Development/amqp-receiver-for-apache-activemq-5-and-apache-activemq-artemis-76c4dd3.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for IBM MQ*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from IBM MQ.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Sender for IBM MQ](../Development/amqp-sender-for-ibm-mq-f6cc0e4.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for IBM MQ*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send messages to IBM MQ.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Receiver for IBM MQ](../Development/amqp-receiver-for-ibm-mq-990fa99.md)

</td>
</tr>
<tr>
<td valign="top">

*Ariba*

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to the Ariba Network. Using this adapter, SAP and non-SAP cloud applications can receive business-specific documents in commerce eXtensible Markup Language \(cXML\) format from the Ariba network.

The sender adapter allows you to define a schedule for polling data from Ariba.

See: [Configure the Ariba Sender Adapter](../Development/configure-the-ariba-sender-adapter-0629b58.md)

</td>
</tr>
<tr>
<td valign="top">

*Ariba*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to the Ariba network. Using this adapter, SAP and non-SAP cloud applications can send business-specific documents in commerce eXtensible Markup Language \(cXML\) format to the Ariba network.Receiver adapter

See: [Configure the Ariba Receiver Adapter](../Development/configure-the-ariba-receiver-adapter-49dffa3.md)

</td>
</tr>
<tr>
<td valign="top">

*AS2*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to exchange business-specific documents with a partner through the Applicability Statement 2 \(AS2\) protocol.

Sender adapter: Can return an electronic receipt to the sender of the AS2 message \(in the form of a Message Disposition Notification \(MDN\)\)

See: [Configure the AS2 Sender Adapter](../Development/configure-the-as2-sender-adapter-5d7ee17.md)

</td>
</tr>
<tr>
<td valign="top">

*AS2*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to exchange business-specific documents with a partner through the Applicability Statement 2 \(AS2\) protocol.

See: [Configure the AS2 Receiver Adapter](../Development/configure-the-as2-receiver-adapter-9db62be.md)

</td>
</tr>
<tr>
<td valign="top">

*AS4*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to securely process incoming AS4 messages using Web Services. The AS4 sender adapter is based on the ebMS 3.0 specification that supports the ebMS handler conformance profile.

-   Supports one-way/ebMS3 push message exchange pattern \(MEP\).

-   Support on-way/ebMS3 pull that allows the message party to pick the corresponding message from the partner.

-   Supports signature verification and decryption of the message.

-   Generates receipts after processing the incoming AS4 message.

-   Allows you to set a size limit for the body and attachment of an incoming message.


See: [AS4 Sender Adapter](../Development/as4-sender-adapter-a448605.md)

</td>
</tr>
<tr>
<td valign="top">

*AS4*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to establish a connection between any two message service handlers \(MSHs\) for exchanging business documents. The AS4 receiver adapter uses the Light Client conformance policy and supports only message pushing for the sending MSH and selective message pulling for the receiving MSH.

Receiver adapter:

-   Supports one-way/push message exchange pattern \(MEP\) that involves the transfer of business documents from a sending MSH to a receiving MSH.

-   Supports one-way/selective-pull message exchange pattern \(MEP\) that involves the receiving MSH initiating a selective pull request to the sending MSH. The sending MSH responds by sending the specific user message.

-   Supports storing and verification of receipts.


See: [AS4 Receiver Adapter](../Development/as4-receiver-adapter-3a2fde8.md)

</td>
</tr>
<tr>
<td valign="top">

*Data Store*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to consume messages from a data store.

See: [Data Store Sender Adapter](../Development/data-store-sender-adapter-4f5ef3f.md)

</td>
</tr>
<tr>
<td valign="top">

*ELSTER*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send a tax document to the ELSTER server.

ELSTER \(acronym for the German term *Elektronische Steuererklärung*\) is used in German fiscal management to process tax declarations exchanged over the Internet.

The adapter supports the following operations: Getting the version of the ERiC \(ELSTER Rich Client\) library, validating a tax document, and sending a tax document.

See: [ELSTER Receiver Adapter](../Development/elster-receiver-adapter-e374ef7.md)

</td>
</tr>
<tr>
<td valign="top">

*Facebook*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to access and extract information from Facebook based on certain criteria such as keywords or user data.

Using OAuth, the SAP BTP tenant can access resources on Facebook on behalf of a Facebook user.

See: [Facebook Receiver Adapter](../Development/facebook-receiver-adapter-3dcc408.md)

</td>
</tr>
<tr>
<td valign="top">

*FTP*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to connect to a remote system using TCP \(Transmission Control Protocol\) to receive files from the system.

FTP stands for File Transfer Protocol.

The sender adapter allows you to define a schedule for polling data from the connected system.

See: [Configure the FTP Sender Adapter](../Development/configure-the-ftp-sender-adapter-239042f.md)

</td>
</tr>
<tr>
<td valign="top">

*FTP*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to connect to a remote system using TCP \(Transmission Control Protocol\) to write files to the system.

FTP stands for File Transfer Protocol.

See: [Configure the FTP Receiver Adapter](../Development/configure-the-ftp-receiver-adapter-c16d331.md)

</td>
</tr>
<tr>
<td valign="top">

*HTTPS*

Sender adapter

</td>
<td valign="top">

Establishes an HTTPS connection between SAP Cloud Integration and a sender system.

See: [HTTPS Sender Adapter](../Development/https-sender-adapter-0ae4a78.md)

</td>
</tr>
<tr>
<td valign="top">

*HTTP*

Receiver adapter

</td>
<td valign="top">

Establishes an HTTP connection between SAP Cloud Integration and a receiver system.

Receiver adapter:

-   Supports HTTP 1.1 only \(target system must support chunked transfer encoding and may not rely on the existence of the HTTP Content-Length header\)

-   Supports the following methods: DELETE, GET, HEAD, POST, PUT, TRACE

    Method can also be determined dynamically by reading a value from a message header or property during runtime.


See: [HTTP Receiver Adapter](../Development/http-receiver-adapter-2da452e.md)

</td>
</tr>
<tr>
<td valign="top">

*IDoc*

Sender adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to exchange Intermediate Document \(IDoc\) messages with a sender system that supports communication via SOAP Web services.

A size limit for the inbound message can be configured for the sender adapter.

See: [Configure the IDoc Sender Adapter](../Development/configure-the-idoc-sender-adapter-bf769d6.md)

</td>
</tr>
<tr>
<td valign="top">

*IDoc*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to exchange Intermediate Document \(IDoc\) messages with a receiver system that supports communication via SOAP Web services.

See: [Configure the IDoc Receiver Adapter](../Development/configure-the-idoc-receiver-adapter-018aa88.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to a JDBC \(Java Database Connectivity\) database and to execute SQL commands on the database.

See: [JDBC Receiver Adapter](../Development/jdbc-receiver-adapter-88be644.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for DB2 \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to DB2 \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for DB2 \(On-Premise\)](../Development/jdbc-for-db2-on-premise-9515cf8.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Microsoft SQL Server \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to Microsoft SQL Server \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Microsoft SQL Server \(Cloud\)](../Development/jdbc-for-microsoft-sql-server-cloud-4173d0a.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Microsoft SQL Server \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to Microsoft SQL Server \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Microsoft SQL Server \(On-Premise\)](../Development/jdbc-for-microsoft-sql-server-on-premise-9745e40.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Oracle \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to Oracle \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Oracle \(Cloud\)](../Development/jdbc-for-oracle-cloud-f868182.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Oracle \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to Oracle \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Oracle \(On-Premise\)](../Development/jdbc-for-oracle-on-premise-e6db38a.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for PostgreSQL \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to PostgreSQL \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for PostgreSQL \(Cloud\)](../Development/jdbc-for-postgresql-cloud-4d5b488.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP ASE Service \(Neo\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to SAP ASE Service \(Neo\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP ASE Service \(Neo\)](../Development/jdbc-for-sap-ase-service-neo-a6271cc.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP HANA Cloud*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to SAP HANA Cloud using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP HANA \(Cloud\)](../Development/jdbc-for-sap-hana-cloud-187a8e8.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP HANA Platform \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to SAP HANA Platform \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP HANA Platform \(On-Premise\)](../Development/jdbc-for-sap-hana-platform-on-premise-ff29388.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP HANA Service \(Neo\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to SAP HANA Service \(Neo\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP HANA Service \(Neo\)](../Development/jdbc-for-sap-hana-service-neo-030e47e.md)

</td>
</tr>
<tr>
<td valign="top">

*JMS* 

Sender adapter

</td>
<td valign="top">

Enables asynchronous messaging by using message queues.

The sender adapter consumes messages from a queue. The messages are processed concurrently.

To prevent situations where the JMS adapter tries again and again to process a failed \(large\) message, you can store messages \(where the processing stopped unexpectedly\) in a dead-letter queue after two retries.

Certain constraints apply with regard to the number and capacity of involved queues, as well as for the headers and exchange properties defined in the integration flow before the message is saved to the queue \(as described in the product documentation\).

See: [Configure the JMS Sender Adapter](../Development/configure-the-jms-sender-adapter-161791b.md)

</td>
</tr>
<tr>
<td valign="top">

*JMS*

Receiver adapter

</td>
<td valign="top">

Enables asynchronous messaging by using message queues.

The receiver adapter stores messages and schedules them for processing in a queue. The messages are processed concurrently.

See: [Configure the JMS Receiver Adapter](../Development/configure-the-jms-receiver-adapter-79edc04.md)

</td>
</tr>
<tr>
<td valign="top">

*Kafka*

Sender adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to an external Kafka broker via Kafka protocol and to fetch Kafka records \(messages\).

See: [Configure the Kafka Sender Adapter](../Development/configure-the-kafka-sender-adapter-0d849e5.md)

</td>
</tr>
<tr>
<td valign="top">

*Kafka*

Receiver adapter

</td>
<td valign="top">

Allows SAP Cloud Integration to connect to an external Kafka broker via Kafka protocol and to send Kafka records \(messages\).

See: [Configure the Kafka Receiver Adapter](../Development/configure-the-kafka-receiver-adapter-fc6ee1f.md)

</td>
</tr>
<tr>
<td valign="top">

*Mail Sender for IMAP*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to read e-mails from an e-mail server using the Internet Message Access Protocol \(IMAP\) protocol.

To authenticate against the e-mail server, you can send the user name and password in plain text or encrypted \(the latter only if the e-mail server supports this option\).

You can protect inbound e-mails at the transport layer with IMAPS and STARTTLS.

The sender adapter allows you to define a schedule for polling data from the connected system.

For more information on possible threats when processing e-mail content with the Mail adapter, see the product documentation.

See: [Mail Sender for IMAP](../Development/mail-sender-for-imap-5b94e42.md)

</td>
</tr>
<tr>
<td valign="top">

*Mail Sender for POP3*

Sender adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to read e-mails from an e-mail server using the Post Office Protocol \(POP3\) protocol.

To authenticate against the e-mail server, you can send the user name and password in plain text or encrypted \(the latter only if the e-mail server supports this option\).

You can protect inbound e-mails at the transport layer with POP3S and STARTTLS.

The sender adapter allows you to define a schedule for polling data from the connected system.

For more information on possible threats when processing e-mail content with the Mail adapter, see the product documentation.

See: [Mail Sender for POP3](../Development/mail-sender-for-pop3-c52a4da.md)

</td>
</tr>
<tr>
<td valign="top">

*Mail*

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to send e-mails to an e-mail server.

To authenticate against the e-mail server, you can send the user name and password in plain text or encrypted \(the latter only if the e-mail server supports this option\).

-   You can protect outbound e-mails at the transport layer with STARTTLS or SMTPS.

-   You can encrypt outbound e-mails using S/MIME \(supported content encryption algorithms: AES/CBC/PKCS5Padding, DESede/CBC/PKCS5Padding\).


See: [Configure the Mail Receiver Adapter](../Development/configure-the-mail-receiver-adapter-f68d5e0.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics CRM* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to Microsoft Dynamics Customer Relationship Management \(CRM\).

See: [Microsoft Dynamics CRM Receiver Adapter](../Development/microsoft-dynamics-crm-receiver-adapter-ee724c8.md)

</td>
</tr>
<tr>
<td valign="top">

*OData* 

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to systems using the Open Data \(OData\) protocol in either ATOM or JSON format \(only synchronous communication is supported\).

Supported versions: OData version 2.0

-   The adapter receives incoming requests in either ATOM or JSON format.

-   Supported operations: Create \(POST\), Delete \(DELETE\), Query \(GET\), Read \(GET\), Update \(PUT\)

    Using the GET or POST method, the sender adapter can also invoke operations that are not covered by the standard CRUD \(Create, Retrieve, Update, and Delete\) methods \(function import\).


See: [Configure the OData Sender Adapter](../Development/configure-the-odata-sender-adapter-de7aee5.md)

</td>
</tr>
<tr>
<td valign="top">

*OData*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to systems using the Open Data \(OData\) protocol.

Supported versions:

-   OData version 2.0

    Supported operations: Create \(POST\), Delete \(DELETE\), Merge \(MERGE\), Query \(GET\), Read \(GET\), Update \(PUT\), Patch \(PATCH\)

-   OData version 4.0

    Supported operations: Create \(POST\), Query \(GET\), Update \(PUT\)

-   The outgoing request payload must be in XML format.


See:

-   [Configure the OData V2 Receiver Adapter](../Development/configure-the-odata-v2-receiver-adapter-c5c2e38.md)

-   [Configure the OData V4 Receiver Adapter](../Development/configure-the-odata-v4-receiver-adapter-cd66a12.md)




</td>
</tr>
<tr>
<td valign="top">

*ODC*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to SAP Gateway OData Channel \(through transport protocol HTTPS\).

Supported operations: Create \(POST\), Delete \(DELETE\), Merge \(MERGE\), Query \(GET\), Read \(GET\), Update \(PUT\)

See: [ODC Receiver Adapter](../Development/odc-receiver-adapter-3cdbc29.md)

</td>
</tr>
<tr>
<td valign="top">

*OpenConnectors*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to more than 150 non-SAP Cloud applications that are supported by SAP Open Connectors.

-   Uses APIs to fetch data from specific third-party applications.

-   Is designed to handle large volumes of incoming data.

-   Supports messages in both JSON and XML format, for request and response calls.

-   Allows you to define specific values for variables.


See: [OpenConnectors Receiver Adapter](../Development/openconnectors-receiver-adapter-1a27cee.md)

</td>
</tr>
<tr>
<td valign="top">

*ProcessDirect*

Sender adapter

</td>
<td valign="top">

Connects an integration flow with another integration flow deployed on the same tenant.

An integration flow with a ProcessDirect sender adapter \(as consumer\) consumes data from another integration flow.

N:1 cardinality of producer and consumer integration flows is supported.

See: [Configure the ProcessDirect Sender Adapter](../Development/configure-the-processdirect-sender-adapter-e340d4c.md)

</td>
</tr>
<tr>
<td valign="top">

*ProcessDirect*

Receiver adapter

</td>
<td valign="top">

Connects an integration flow with another integration flow deployed on the same tenant.

An integration flow with a ProcessDirect receiver adapter \(as producer\) sends data to another integration flow.

N:1 cardinality of producer and consumer integration flows is supported.

See: [Configure the ProcessDirect Receiver Adapter](../Development/configure-the-processdirect-receiver-adapter-5b7327d.md)

</td>
</tr>
<tr>
<td valign="top">

*RFC*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a remote receiver system using Remote Function Call \(RFC\).

RFC is the standard interface used for integrating on-premise ABAP systems to the systems hosted on the cloud using SAP Cloud Connector.

The adapter supports SAP NetWeaver, version 7.31 or higher.

See: [RFC Receiver Adapter](../Development/rfc-receiver-adapter-5c76048.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce* 

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to Salesforce.

See: [Salesforce Sender Adapter](../Development/salesforce-sender-adapter-ba6420d.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to Salesforce.

See: [Salesforce Receiver Adapter](../Development/salesforce-receiver-adapter-a548be9.md)

</td>
</tr>
<tr>
<td valign="top">

*SFTP* 

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a remote system using the SSH File Transfer protocol to read files from the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol \(or SFTP\).

Supported versions:

SSH version 2 \(as specified at [The Secure Shell \(SSH\) Protocol Architecture](http://tools.ietf.org/html/rfc4251)\), SSH File Transfer Protocol \(SFTP\) version 3 or higher

The sender adapter allows you to define a schedule for polling data from the connected system.

See: [Configure the SFTP Sender Adapter](../Development/configure-the-sftp-sender-adapter-2de9ee5.md)

</td>
</tr>
<tr>
<td valign="top">

*SFTP*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a remote system using the SSH File Transfer protocol to write files to the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol \(or SFTP\).

Supported versions:

SSH version 2 \(as specified at [The Secure Shell \(SSH\) Protocol Architecture](http://tools.ietf.org/html/rfc4251)\), SSH File Transfer Protocol \(SFTP\) version 3 or higher

See: [Configure the SFTP Receiver Adapter](../Development/configure-the-sftp-receiver-adapter-4ef52cf.md)

</td>
</tr>
<tr>
<td valign="top">

*SOAP SOAP 1.x* 

Sender adapter

</td>
<td valign="top">

Exchanges messages with a sender system that supports Simple Object Access Protocol \(SOAP\) 1.1 or SOAP 1.2.

The message exchange patterns supported by the sender adapter are one-way messaging or request-reply.

The adapter supports Web services Security \(WS-Security\).

A size limit for the inbound message can be configured for the sender adapter.

See: [Configure the SOAP \(SOAP 1.x\) Sender Adapter](../Development/configure-the-soap-soap-1-x-sender-adapter-a178913.md)

</td>
</tr>
<tr>
<td valign="top">

*SOAP SOAP 1.x*

Receiver adapter

</td>
<td valign="top">

Exchanges messages with a receiver system that supports Simple Object Access Protocol \(SOAP\) 1.1 or SOAP 1.2.

The adapter supports Web services Security \(WS-Security\).

See: [Configure the SOAP \(SOAP 1.x\) Receiver Adapter](../Development/configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md)

</td>
</tr>
<tr>
<td valign="top">

*SOAP SAP RM* 

Sender adapter

</td>
<td valign="top">

Exchanges messages with a sender system based on the SOAP communication protocol and SAP Reliable Messaging \(SAP RM\) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards.

A size limit for the inbound message can be configured for the sender adapter.

See: [Configure the SOAP \(SAP RM\) Sender Adapter](../Development/configure-the-soap-sap-rm-sender-adapter-6962234.md)

</td>
</tr>
<tr>
<td valign="top">

*SOAP SAP RM* 

Receiver adapter

</td>
<td valign="top">

Exchanges messages with a receiver system based on the SOAP communication protocol and SAP Reliable Messaging \(SAP RM\) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards.

See: [Configure the SOAP \(SAP RM\) Receiver Adapter](../Development/configure-the-soap-sap-rm-receiver-adapter-8366495.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors REST*

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a SuccessFactors sender system using the REST message protocol.

The adapter supports the following operations: GET

See: [Configure the SuccessFactors REST Sender Adapter](../Development/configure-the-successfactors-rest-sender-adapter-9f0646b.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors REST*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a SuccessFactors receiver system using the REST message protocol.

The adapter supports the following operations: GET, POST

See: [Configure the SuccessFactors REST Receiver Adapter](../Development/configure-the-successfactors-rest-receiver-adapter-9cff562.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors SOAP*

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to SOAP-based Web services of a SuccessFactors sender system \(synchronous or asynchronous communication\).

The adapter supports the following operations: Query

See: [Configure the SuccessFactors \(SOAP\) Sender Adapter](../Development/configure-the-successfactors-soap-sender-adapter-874e4b1.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors SOAP*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to SOAP-based Web services of a SuccessFactors receiver system \(synchronous or asynchronous communication\).

The adapter supports the following operations: Insert, Query, Update, Upsert

See: [Configure the SuccessFactors SOAP Receiver Adapter](../Development/configure-the-successfactors-soap-receiver-adapter-360ef42.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors OData V2*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a SuccessFactors system using OData V2.

Features of OData version 2.0 supported by the adapter:

-   Operations: GET \(get single entity as an entry document\), PUT \(update existing entry with an entry document\), POST \(create new entry from an entry document\), DELETE \(Delete an entry from an entry document\), UPSERT \(combination of Update OR Insert\)

-   Query options: $expand, $skip,and $top

-   Server-side pagination

-   Client-side pagination

-   Pagination enhancement: Data retrieved in chunks and sent to Cloud Integration

-   Deep insert: Creates a structure of related entities in one request

-   Authentication options: Basic authentication

-   Reference links: Link two entities using the <link\> tag

See: [Configure the SuccessFactors OData V2 Receiver Adapter](../Development/configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors OData V4*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a SuccessFactors system using OData V4.

Features of OData version 4.0 supported by the adapter:

-   Operations: GET, POST, PUT, DELETE

-   Navigation

-   Primitive types supported according to OData V4 specification

-   Structural types supported for create/update operations:

    Edm.ComplexType, Edm:EnumType, Collection\(Edm.PrimitiveType\) and Collection\(Edm.ComplexType\)


See: [SuccessFactors OData V4 Receiver Adapter](../Development/successfactors-odata-v4-receiver-adapter-cd091fc.md)

</td>
</tr>
<tr>
<td valign="top">

*SugarCRM* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to SugarCRM.

See: [SugarCRM Receiver Adapter](../Development/sugarcrm-receiver-adapter-d96ddf7.md)

</td>
</tr>
<tr>
<td valign="top">

*Twitter* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Cloud Integration to access Twitter and read or post tweets.

Using OAuth, SAP Cloud Integration can access resources on Twitter on behalf of a Twitter user.

See: [Twitter Receiver Adapter](../Development/twitter-receiver-adapter-453c174.md)

</td>
</tr>
<tr>
<td valign="top">

*XI*

Sender adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a remote sender system that can process the XI message protocol.

See: [Configure the XI Sender Adapter](../Development/configure-the-xi-sender-adapter-41a1a57.md)

</td>
</tr>
<tr>
<td valign="top">

*XI*

Receiver adapter

</td>
<td valign="top">

Connects SAP Cloud Integration to a remote receiver system that can process the XI message protocol.

See: [Configure the XI Receiver Adapter](../Development/configure-the-xi-receiver-adapter-5d2670f.md)

</td>
</tr>
</table>

