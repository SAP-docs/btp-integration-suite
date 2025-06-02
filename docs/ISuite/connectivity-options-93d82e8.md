<!-- loio93d82e8ff860450da10ad2c16bf5e971 -->

# Connectivity Options

SAP Integration Suite provides you with a comprehensive set of options to connect to SAP and non-SAP systems.

This set comprises:

-   80+ standard adapters

    Use a set of standard adapters out-of-the-box when modeling your integration flow. This set comprises:

    -   Technical adapters that enable you to connect SAP Integration Suite to remote systems through dedicated protocols such like HTTPS, FTP, SFTP, RFC, for example.

    -   Application-specific adapters that enable you to connect SAP Integration Suite to applications such like SAP SuccessFactors, Twitter, ELSTER, for example.


-   170+ non-SAP connectors

    Use a set of connectors that allow you to connect SAP Integration Suite to a number of SAP and non-SAP applications such like Citrix GoToWebinar, Dropbox Business, Evernote, Gmail, to name a few examples.

    Each connector is an application programming interface \(API\) that provides a set of API methods you can use to access the resources of the associated application.


Furthermore, SAP Integration Suite comes with an Adapter Development Kit that allows you to develop your own adapters and deploy them on your tenant.



<a name="loio93d82e8ff860450da10ad2c16bf5e971__section_hsl_nvq_5sb"/>

## Standard Adapters

SAP Integration Suite comes with a set of standard adapters that allow you to specify a certain connection type and to define, for example, which technical protocols should be used to connect a sender or a receiver system to the tenant and how this connection is protected. You can use these adapters out-of-the-box when designing integration flows.

> ### Note:  
> Note related to terminology:
> 
> A receiver adapter connects SAP Integration Suite to an external system. A sender adapter receives incoming messages \(sent from an external system\) or polls messages from an external system.

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

*AdvancedEventMesh* 

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to consume messages from queues or subscriptions in SAP Integration Suite, advanced event mesh.

See: [Configure the Advanced Event Mesh Sender Adapter](50-Development/configure-the-advanced-event-mesh-sender-adapter-abd2efc.md)

</td>
</tr>
<tr>
<td valign="top">

*AdvancedEventMesh* 

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to send messages to queues or topics in SAP Integration Suite, advanced event mesh.

See: [Configure the Advanced Event Mesh Receiver Adapter](50-Development/configure-the-advanced-event-mesh-receiver-adapter-881f656.md)

</td>
</tr>
<tr>
<td valign="top">

*Amazon DynamoDB* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Amazon DynamoDB.

See: [Amazon DynamoDB Receiver Adapter](50-Development/amazon-dynamodb-receiver-adapter-36620d5.md)

</td>
</tr>
<tr>
<td valign="top">

*Amazon EventBridge*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Amazon EventBridge.

See: [Amazon EventBridge Receiver Adapter](50-Development/amazon-eventbridge-receiver-adapter-ff3f9ed.md)

</td>
</tr>
<tr>
<td valign="top">

*AmazonWebServices* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Amazon Web Services.

The adapter supports the following protocols:

-   S3: Simple Cloud Storage

-   SQS: Simple Queue Service


See: [AmazonWebServices Sender Adapter](50-Development/amazonwebservices-sender-adapter-16772e3.md)

</td>
</tr>
<tr>
<td valign="top">

*AmazonWebServices* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Amazon Web Services.

The adapter supports the following protocols:

-   S3: Simple Cloud Storage

-   SQS: Simple Queue Service

-   SNS: Simple Notification Service

-   SWF: Simple Workflow Service


See: [AmazonWebServices Receiver Adapter](50-Development/amazonwebservices-receiver-adapter-bc7d1aa.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from queues or topic subscriptions in an external messaging system.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocols: TCP, WebSocket

See: [Configure the AMQP Sender Adapter](50-Development/configure-the-amqp-sender-adapter-99ce674.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to queues or topics in an external messaging system.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocols: TCP, WebSocket

See: [Configure the AMQP Receiver Adapter](50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for SAP Event Mesh*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from SAP Event Mesh.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: WebSocket

See: [AMQP Sender for SAP Event Mesh](50-Development/amqp-sender-for-sap-event-mesh-7d8a83f.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for SAP Event Mesh*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to SAP Event Mesh.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: WebSocket

See: [AMQP Receiver for SAP Event Mesh](50-Development/amqp-receiver-for-sap-event-mesh-0b7cc2f.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for SAP Integration Suite, advanced event mesh*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from SAP Integration Suite, advanced event mesh.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQ Sender for SAP Integration Suite, advanced event mesh](50-Development/amq-sender-for-sap-integration-suite-advanced-event-mesh-be1e496.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for SAP Integration Suite, advanced event mesh*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to SAP Integration Suite, advanced event mesh.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [AMQP Receiver for SAP Integration Suite, advanced event mesh](50-Development/amqp-receiver-for-sap-integration-suite-advanced-event-mesh-5f229c0.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Microsoft Azure Service Bus*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Microsoft Azure Service Bus.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Sender Adapter](50-Development/configure-the-amqp-sender-adapter-99ce674.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Microsoft Azure Service Bus*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to Microsoft Azure Service Bus.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Receiver Adapter](50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Solace PubSub+*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Solace PubSub+.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Sender Adapter](50-Development/configure-the-amqp-sender-adapter-99ce674.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Solace PubSub+*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to Solace PubSub+.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Receiver Adapter](50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache Qpid Broker-J*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Apache Qpid Broker-J.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP, WebSocket

See: [Configure the AMQP Sender Adapter](50-Development/configure-the-amqp-sender-adapter-99ce674.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache Qpid Broker-J*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to Apache Qpid Broker-J.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP, WebSocket

See: [Configure the AMQP Receiver Adapter](50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache ActiveMQ 5 / Apache ActiveMQ Artemis*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Apache ActiveMQ 5 / Apache ActiveMQ Artemis.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Sender Adapter](50-Development/configure-the-amqp-sender-adapter-99ce674.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for Apache ActiveMQ 5 / Apache ActiveMQ Artemis*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to Apache ActiveMQ 5 / Apache ActiveMQ Artemis.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Receiver Adapter](50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for IBM MQ*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from IBM MQ.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Sender Adapter](50-Development/configure-the-amqp-sender-adapter-99ce674.md)

</td>
</tr>
<tr>
<td valign="top">

*AMQP for IBM MQ*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send messages to IBM MQ.

Supported message protocol: AMQP \(Advanced Message Queuing Protocol\) 1.0

Supported transport protocol: TCP

See: [Configure the AMQP Receiver Adapter](50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*Anaplan*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Anaplan.

See: [Anaplan Receiver Adapter](50-Development/anaplan-receiver-adapter-364ab57.md)

</td>
</tr>
<tr>
<td valign="top">

*Ariba*

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to the Ariba Network. Using this adapter, SAP and non-SAP cloud applications can receive business-specific documents in commerce eXtensible Markup Language \(cXML\) format from the Ariba network.

The sender adapter allows you to define a schedule for polling data from Ariba.

See: [Configure the Ariba Sender Adapter](50-Development/configure-the-ariba-sender-adapter-0629b58.md)

</td>
</tr>
<tr>
<td valign="top">

*Ariba*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to the Ariba network. Using this adapter, SAP and non-SAP cloud applications can send business-specific documents in commerce eXtensible Markup Language \(cXML\) format to the Ariba network.Receiver adapter

See: [Configure the Ariba Receiver Adapter](50-Development/configure-the-ariba-receiver-adapter-49dffa3.md)

</td>
</tr>
<tr>
<td valign="top">

*AS2*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to exchange business-specific documents with a partner through the Applicability Statement 2 \(AS2\) protocol.

Sender adapter: Can return an electronic receipt to the sender of the AS2 message \(in the form of a Message Disposition Notification \(MDN\)\)

See: [Configure the AS2 Sender Adapter](50-Development/configure-the-as2-sender-adapter-5d7ee17.md)

</td>
</tr>
<tr>
<td valign="top">

*AS2*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to exchange business-specific documents with a partner through the Applicability Statement 2 \(AS2\) protocol.

See: [Configure the AS2 Receiver Adapter](50-Development/configure-the-as2-receiver-adapter-9db62be.md)

</td>
</tr>
<tr>
<td valign="top">

*AS4*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to securely process incoming AS4 messages using Web Services. The AS4 sender adapter is based on the ebMS 3.0 specification that supports the ebMS handler conformance profile.

-   Supports one-way/ebMS3 push message exchange pattern \(MEP\).

-   Support on-way/ebMS3 pull that allows the message party to pick the corresponding message from the partner.

-   Supports signature verification and decryption of the message.

-   Generates receipts after processing the incoming AS4 message.

-   Allows you to set a size limit for the body and attachment of an incoming message.


See: [AS4 Sender Adapter](50-Development/as4-sender-adapter-a448605.md)

</td>
</tr>
<tr>
<td valign="top">

*AS4*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to establish a connection between any two message service handlers \(MSHs\) for exchanging business documents. The AS4 receiver adapter uses the Light Client conformance policy and supports only message pushing for the sending MSH and selective message pulling for the receiving MSH.

Receiver adapter:

-   Supports one-way/push message exchange pattern \(MEP\) that involves the transfer of business documents from a sending MSH to a receiving MSH.

-   Supports one-way/selective-pull message exchange pattern \(MEP\) that involves the receiving MSH initiating a selective pull request to the sending MSH. The sending MSH responds by sending the specific user message.

-   Supports storing and verification of receipts.


See: [AS4 Receiver Adapter](50-Development/as4-receiver-adapter-3a2fde8.md)

</td>
</tr>
<tr>
<td valign="top">

*AzureStorage*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive files from Azure Storage.

See: [Configure the AzureStorage Sender Adapter](50-Development/configure-the-azurestorage-sender-adapter-d42134a.md)

</td>
</tr>
<tr>
<td valign="top">

*AzureStorage*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to Azure Storage, to manage files, containers, folders, and messages, and to perform *create, read, update and delete* \(CRUD\) operations on objects stored there.

See: [Configure the AzureStorage Receiver Adapter](50-Development/configure-the-azurestorage-receiver-adapter-30f59b0.md)

</td>
</tr>
<tr>
<td valign="top">

*Azure CosmosDB*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to exchange data with Microsoft Azure CosmosDB. Azure CosmosDB database is a platform as a service and a cloud-based NoSQL database by Azure.

See: [Azure Cosmos DB Receiver Adapter](50-Development/azure-cosmos-db-receiver-adapter-aa8222e.md)

</td>
</tr>
<tr>
<td valign="top">

*Coupa*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to exchange data with Coupa. Coupa is a business spending management software.

See: [Coupa Receiver Adapter](50-Development/coupa-receiver-adapter-648ac01.md)

</td>
</tr>
<tr>
<td valign="top">

*Data Store*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from a data store.

See: [Data Store Sender Adapter](50-Development/data-store-sender-adapter-4f5ef3f.md)

</td>
</tr>
<tr>
<td valign="top">

*Dropbox*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive files from the Dropbox storage.

See: [Configure the Dropbox Sender Adapter](50-Development/configure-the-dropbox-sender-adapter-de61991.md)

</td>
</tr>
<tr>
<td valign="top">

*Dropbox*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to write files and folders to the Dropbox storage.

See: [Configure the Dropbox Receiver Adapter](50-Development/configure-the-dropbox-receiver-adapter-16ef7b4.md)

</td>
</tr>
<tr>
<td valign="top">

*ELSTER*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send a tax document to the ELSTER server.

ELSTER \(acronym for the German term *Elektronische Steuererklärung*\) is used in German fiscal management to process tax declarations exchanged over the Internet.

The adapter supports the following operations: Getting the version of the ERiC \(ELSTER Rich Client\) library, validating a tax document, and sending a tax document.

See: [ELSTER Receiver Adapter](50-Development/elster-receiver-adapter-e374ef7.md)

</td>
</tr>
<tr>
<td valign="top">

*Facebook*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to access and extract information from Facebook based on certain criteria such as keywords or user data.

Using OAuth, the SAP BTP tenant can access resources on Facebook on behalf of a Facebook user.

See: [Facebook Receiver Adapter](50-Development/facebook-receiver-adapter-3dcc408.md)

</td>
</tr>
<tr>
<td valign="top">

*FTP*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to a remote system using TCP \(Transmission Control Protocol\) to receive files from the system.

FTP stands for File Transfer Protocol.

The sender adapter allows you to define a schedule for polling data from the connected system.

See: [Configure the FTP Sender Adapter](50-Development/configure-the-ftp-sender-adapter-239042f.md)

</td>
</tr>
<tr>
<td valign="top">

*FTP*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to a remote system using TCP \(Transmission Control Protocol\) to write files to the system.

FTP stands for File Transfer Protocol.

See: [Configure the FTP Receiver Adapter](50-Development/configure-the-ftp-receiver-adapter-c16d331.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Cloud Storage* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to read from different storage entities in Google Cloud Storage.

See: [Configure the Google Cloud Storage Sender Adapter](50-Development/configure-the-google-cloud-storage-sender-adapter-ec213ce.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Cloud Storage* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to access and manage different storage entities in Google Cloud Storage.

See: [Configure the Google Cloud Storage Receiver Adapter](50-Development/configure-the-google-cloud-storage-receiver-adapter-5a8ddef.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Pub/Sub* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Google Pub/Sub.

See: [Configure the Google Pub/Sub Sender Adapter](50-Development/configure-the-google-pub-sub-sender-adapter-845ec21.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Pub/Sub* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to publish messages to Google Pub/Sub.

See: [Configure the Google Pub/Sub Receiver Adapter](50-Development/configure-the-google-pub-sub-receiver-adapter-30df22d.md)

</td>
</tr>
<tr>
<td valign="top">

*HTTPS*

Sender adapter

</td>
<td valign="top">

Establishes an HTTPS connection between SAP Integration Suite and a sender system.

See: [HTTPS Sender Adapter](50-Development/https-sender-adapter-0ae4a78.md)

</td>
</tr>
<tr>
<td valign="top">

*HTTP*

Receiver adapter

</td>
<td valign="top">

Establishes an HTTP connection between SAP Integration Suite and a receiver system.

Receiver adapter:

-   Supports HTTP 1.1 only \(target system must support chunked transfer encoding and may not rely on the existence of the HTTP Content-Length header\)

-   Supports the following methods: DELETE, GET, HEAD, POST, PUT, TRACE

    Method can also be determined dynamically by reading a value from a message header or property during runtime.


See: [HTTP Receiver Adapter](50-Development/http-receiver-adapter-2da452e.md)

</td>
</tr>
<tr>
<td valign="top">

*HubSpot*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to HubSpot.

See: [HubSpot Receiver Adapter](50-Development/hubspot-receiver-adapter-48cfaa8.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ \(REST\)*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to consume messages from IBM MQ using the REST message protocol.

See: [Configure the IBM MQ \(REST\) Sender Adapter](50-Development/configure-the-ibm-mq-rest-sender-adapter-35cd02d.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ \(REST\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to publish messages to IBM MQ using the REST message protocol.

See: [Configure the IBM MQ \(REST\) Receiver Adapter](50-Development/configure-the-ibm-mq-rest-receiver-adapter-45610e7.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ JMS*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to consume messages from IBM MQ via JMS message protocol.

See: [Configure the IBM MQ JMS Sender Adapter](50-Development/configure-the-ibm-mq-jms-sender-adapter-d655ab4.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ JMS*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to publish messages to IBM MQ via JMS message protocol.

See: [Configure the IBM MQ JMS Receiver Adapter](50-Development/configure-the-ibm-mq-jms-receiver-adapter-029bc1b.md)

</td>
</tr>
<tr>
<td valign="top">

*IDoc*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to exchange Intermediate Document \(IDoc\) messages with a sender system that supports communication via SOAP Web services.

A size limit for the inbound message can be configured for the sender adapter.

See: [Configure the IDoc Sender Adapter](50-Development/configure-the-idoc-sender-adapter-bf769d6.md)

</td>
</tr>
<tr>
<td valign="top">

*IDoc*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to exchange Intermediate Document \(IDoc\) messages with a receiver system that supports communication via SOAP Web services.

See: [Configure the IDoc Receiver Adapter](50-Development/configure-the-idoc-receiver-adapter-018aa88.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to a JDBC \(Java Database Connectivity\) database and to execute SQL commands on the database.

See: [JDBC Receiver Adapter](50-Development/jdbc-receiver-adapter-88be644.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for DB2 \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to DB2 \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for DB2 \(On-Premise\)](50-Development/jdbc-for-db2-on-premise-9515cf8.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Microsoft SQL Server \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Microsoft SQL Server \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Microsoft SQL Server \(Cloud\)](50-Development/jdbc-for-microsoft-sql-server-cloud-4173d0a.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Microsoft SQL Server \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Microsoft SQL Server \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Microsoft SQL Server \(On-Premise\)](50-Development/jdbc-for-microsoft-sql-server-on-premise-9745e40.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Oracle \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Oracle \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Oracle \(Cloud\)](50-Development/jdbc-for-oracle-cloud-f868182.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Oracle \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Oracle \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Oracle \(On-Premise\)](50-Development/jdbc-for-oracle-on-premise-e6db38a.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for PostgreSQL \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to PostgreSQL \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for PostgreSQL \(Cloud\)](50-Development/jdbc-for-postgresql-cloud-4d5b488.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP HANA Cloud*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to SAP HANA Cloud using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP HANA \(Cloud\)](50-Development/jdbc-for-sap-hana-cloud-187a8e8.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP HANA Platform \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to SAP HANA Platform \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP HANA Platform \(On-Premise\)](50-Development/jdbc-for-sap-hana-platform-on-premise-ff29388.md)

</td>
</tr>
<tr>
<td valign="top">

*Jira*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to Jira.

See: [Jira Receiver Adapter](50-Development/jira-receiver-adapter-d15b560.md)

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

See: [Configure the JMS Sender Adapter](50-Development/configure-the-jms-sender-adapter-161791b.md)

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

See: [Configure the JMS Receiver Adapter](50-Development/configure-the-jms-receiver-adapter-79edc04.md)

</td>
</tr>
<tr>
<td valign="top">

*Kafka*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to an external Kafka broker via Kafka protocol and to fetch Kafka records \(messages\).

See: [Configure the Kafka Sender Adapter](50-Development/configure-the-kafka-sender-adapter-0d849e5.md)

</td>
</tr>
<tr>
<td valign="top">

*Kafka*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to an external Kafka broker via Kafka protocol and to send Kafka records \(messages\).

See: [Configure the Kafka Receiver Adapter](50-Development/configure-the-kafka-receiver-adapter-fc6ee1f.md)

</td>
</tr>
<tr>
<td valign="top">

*LeanIX*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to SAP LeanIX.

See: [LeanIX Receiver Adapter](50-Development/leanix-receiver-adapter-e49c1de.md)

</td>
</tr>
<tr>
<td valign="top">

*Mail Sender for IMAP*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to read e-mails from an e-mail server using the Internet Message Access Protocol \(IMAP\) protocol.

To authenticate against the e-mail server, you can send the user name and password in plain text or encrypted \(the latter only if the e-mail server supports this option\).

You can protect inbound e-mails at the transport layer with IMAPS and STARTTLS.

The sender adapter allows you to define a schedule for polling data from the connected system.

For more information on possible threats when processing e-mail content with the Mail adapter, see the product documentation.

See: [Mail Sender for IMAP](50-Development/mail-sender-for-imap-5b94e42.md)

</td>
</tr>
<tr>
<td valign="top">

*Mail Sender for POP3*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to read e-mails from an e-mail server using the Post Office Protocol \(POP3\) protocol.

To authenticate against the e-mail server, you can send the user name and password in plain text or encrypted \(the latter only if the e-mail server supports this option\).

You can protect inbound e-mails at the transport layer with POP3S and STARTTLS.

The sender adapter allows you to define a schedule for polling data from the connected system.

For more information on possible threats when processing e-mail content with the Mail adapter, see the product documentation.

See: [Mail Sender for POP3](50-Development/mail-sender-for-pop3-c52a4da.md)

</td>
</tr>
<tr>
<td valign="top">

*Mail*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to send e-mails to an e-mail server.

To authenticate against the e-mail server, you can send the user name and password in plain text or encrypted \(the latter only if the e-mail server supports this option\).

-   You can protect outbound e-mails at the transport layer with STARTTLS or SMTPS.

-   You can encrypt outbound e-mails using S/MIME \(supported content encryption algorithms: AES/CBC/PKCS5Padding, DESede/CBC/PKCS5Padding\).


See: [Configure the Mail Receiver Adapter](50-Development/configure-the-mail-receiver-adapter-f68d5e0.md)

</td>
</tr>
<tr>
<td valign="top">

*MDI* 

Receiver adapter

</td>
<td valign="top">

The MDI \(SAP Master Data Integration\) adapter synchronizes your master data from SAP applications like SAP ECC and other third party applications with SAP MDI service.

See: [SAP Master Data Integration Receiver Adapter](50-Development/sap-master-data-integration-receiver-adapter-e91e373.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics CRM* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Microsoft Dynamics Customer Relationship Management \(CRM\).

See: [Microsoft Dynamics CRM Receiver Adapter](50-Development/microsoft-dynamics-crm-receiver-adapter-ee724c8.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft OneDrive* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using HTTP protocol.

See: [Configure the Microsoft OneDrive Sender Adapter](50-Development/configure-the-microsoft-onedrive-sender-adapter-0724136.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft OneDrive* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using HTTP protocol.

See: [Configure the Microsoft OneDrive Receiver Adapter](50-Development/configure-the-microsoft-onedrive-receiver-adapter-4158749.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft SharePoint* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using the HTTP/HTTPS protocol to read files from the system.

See: [Configure the Microsoft SharePoint Sender Adapter](50-Development/configure-the-microsoft-sharepoint-sender-adapter-ce41e85.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft SharePoint* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using the HTTP protocol to write files to the system.

See: [Configure the Microsoft SharePoint Receiver Adapter](50-Development/configure-the-microsoft-sharepoint-receiver-adapter-b12b33a.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Teams* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Microsoft Teams.

See: [Microsoft Teams Receiver Adapter](50-Development/microsoft-teams-receiver-adapter-1f333c3.md)

</td>
</tr>
<tr>
<td valign="top">

*NetSuite* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to NetSuite.

See: [NetSuite Receiver Adapter](50-Development/netsuite-receiver-adapter-618127a.md)

</td>
</tr>
<tr>
<td valign="top">

*OData* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to systems using the Open Data \(OData\) protocol in either ATOM or JSON format \(only synchronous communication is supported\).

Supported versions: OData version 2.0

-   The adapter receives incoming requests in either ATOM or JSON format.

-   Supported operations: Create \(POST\), Delete \(DELETE\), Query \(GET\), Read \(GET\), Update \(PUT\)

    Using the GET or POST method, the sender adapter can also invoke operations that are not covered by the standard CRUD \(Create, Retrieve, Update, and Delete\) methods \(function import\).


See: [Configure the OData Sender Adapter](50-Development/configure-the-odata-sender-adapter-de7aee5.md)

</td>
</tr>
<tr>
<td valign="top">

*OData*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to systems using the Open Data \(OData\) protocol.

Supported versions:

-   OData version 2.0

    Supported operations: Create \(POST\), Delete \(DELETE\), Merge \(MERGE\), Query \(GET\), Read \(GET\), Update \(PUT\), Patch \(PATCH\)

-   OData version 4.0

    Supported operations: Create \(POST\), Query \(GET\), Delete \(DELETE\), Update \(PUT\), and Patch \(PATCH\)

-   The outgoing request payload must be in XML format.


See:

-   [Configure the OData V2 Receiver Adapter](50-Development/configure-the-odata-v2-receiver-adapter-c5c2e38.md)

-   [Configure the OData V4 Receiver Adapter](50-Development/configure-the-odata-v4-receiver-adapter-cd66a12.md)




</td>
</tr>
<tr>
<td valign="top">

*ODC*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to SAP Gateway OData Channel \(through transport protocol HTTPS\).

Supported operations: Create \(POST\), Delete \(DELETE\), Merge \(MERGE\), Query \(GET\), Read \(GET\), Update \(PUT\)

See: [ODC Receiver Adapter](50-Development/odc-receiver-adapter-3cdbc29.md)

</td>
</tr>
<tr>
<td valign="top">

*OpenConnectors*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to more than 150 non-SAP Cloud applications that are supported by SAP Open Connectors.

-   Uses APIs to fetch data from specific third-party applications.

-   Is designed to handle large volumes of incoming data.

-   Supports messages in both JSON and XML format, for request and response calls.

-   Allows you to define specific values for variables.


See: [OpenConnectors Receiver Adapter](50-Development/openconnectors-receiver-adapter-1a27cee.md)

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

See: [Configure the ProcessDirect Sender Adapter](50-Development/configure-the-processdirect-sender-adapter-e340d4c.md)

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

See: [Configure the ProcessDirect Receiver Adapter](50-Development/configure-the-processdirect-receiver-adapter-5b7327d.md)

</td>
</tr>
<tr>
<td valign="top">

*RabbitMQ*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to consume messages from the RabbitMQ server. In addition, you use the adapter to send acknowledgements to the RabbitMQ server.

See: [Configure the RabbitMQ Sender Adapter](50-Development/configure-the-rabbitmq-sender-adapter-4e3c554.md)

</td>
</tr>
<tr>
<td valign="top">

*RabbitMQ*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to send messages to the RabbitMQ server.

See: [Configure the RabbitMQ Receiver Adapter](50-Development/configure-the-rabbitmq-receiver-adapter-e9dfc37.md)

</td>
</tr>
<tr>
<td valign="top">

*RFC*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote receiver system using Remote Function Call \(RFC\).

RFC is the standard interface used for integrating on-premise ABAP systems to the systems hosted on the cloud using SAP Cloud Connector.

The adapter supports SAP NetWeaver, version 7.31 or higher.

See: [RFC Receiver Adapter](50-Development/rfc-receiver-adapter-5c76048.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Salesforce.

See: [Salesforce Sender Adapter](50-Development/salesforce-sender-adapter-ba6420d.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Salesforce.

See: [Salesforce Receiver Adapter](50-Development/salesforce-receiver-adapter-a548be9.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Pub/Sub* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Salesforce Pub/Sub API.

See: [Configure the Salesforce Pub/Sub Sender Adapter](50-Development/configure-the-salesforce-pub-sub-sender-adapter-fdb114c.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Pub/Sub* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to publish messages to Salesforce Pub/Sub API.

See: [Configure the Salesforce Pub/Sub Receiver Adapter](50-Development/configure-the-salesforce-pub-sub-receiver-adapter-6862ff5.md)

</td>
</tr>
<tr>
<td valign="top">

*ServiceNow* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to ServiceNow. Supports basic authentication and OAuth.

See: [ServiceNow Receiver Adapter](50-Development/servicenow-receiver-adapter-1e3bcf4.md)

</td>
</tr>
<tr>
<td valign="top">

*SFTP* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using the SSH File Transfer protocol to read files from the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol \(or SFTP\).

Supported versions:

SSH version 2 \(as specified at [The Secure Shell \(SSH\) Protocol Architecture](http://tools.ietf.org/html/rfc4251)\), SSH File Transfer Protocol \(SFTP\) version 3 or higher

The sender adapter allows you to define a schedule for polling data from the connected system.

See: [Configure the SFTP Sender Adapter](50-Development/configure-the-sftp-sender-adapter-2de9ee5.md)

</td>
</tr>
<tr>
<td valign="top">

*SFTP*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using the SSH File Transfer protocol to write files to the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol \(or SFTP\).

Supported versions:

SSH version 2 \(as specified at [The Secure Shell \(SSH\) Protocol Architecture](http://tools.ietf.org/html/rfc4251)\), SSH File Transfer Protocol \(SFTP\) version 3 or higher

See: [Configure the SFTP Receiver Adapter](50-Development/configure-the-sftp-receiver-adapter-4ef52cf.md)

</td>
</tr>
<tr>
<td valign="top">

*Slack*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive search-related information from the Slack storage.

See: [Configure the Slack Sender Adapter](50-Development/configure-the-slack-sender-adapter-1d93850.md)

</td>
</tr>
<tr>
<td valign="top">

*Slack*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to get data from the Slack storage or to create, modify, or delete data on the Slack storage.

See: [Configure the Slack Receiver Adapter](50-Development/configure-the-slack-receiver-adapter-7c2ea64.md)

</td>
</tr>
<tr>
<td valign="top">

*SMB*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to a remote SMB Server using TCP \(Transmission Control Protocol\) to perform a read operation on the system. SMB stands for Server Message Block.

Supported Versions:

-   SMB 2.0.2
-   SMB 2.1
-   SMB 3.0
-   SMB 3.0.2
-   SMB 3.1.1

See: [Configure the SMB Sender Adapter](50-Development/configure-the-smb-sender-adapter-95bf6e9.md)

</td>
</tr>
<tr>
<td valign="top">

*SMB*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote SMB Server using TCP \(Transmission Control Protocol\) to perform a file or folder operation on the system. SMB stands for Server Message Block.

Supported Versions:

-   SMB 2.0.2
-   SMB 2.1
-   SMB 3.0
-   SMB 3.0.2
-   SMB 3.1.1

See: [Configure the SMB Receiver Adapter](50-Development/configure-the-smb-receiver-adapter-ddd0d59.md)

</td>
</tr>
<tr>
<td valign="top">

*Snowflake* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Snowflake. Snowflake is a cloud computing-based data company that provides cloud-based data storage and analytics services.

See: [Snowflake Receiver Adapter](50-Development/snowflake-receiver-adapter-1299e68.md)

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

See: [Configure the SOAP \(SOAP 1.x\) Sender Adapter](50-Development/configure-the-soap-soap-1-x-sender-adapter-a178913.md)

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

See: [Configure the SOAP \(SOAP 1.x\) Receiver Adapter](50-Development/configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md)

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

See: [Configure the SOAP \(SAP RM\) Sender Adapter](50-Development/configure-the-soap-sap-rm-sender-adapter-6962234.md)

</td>
</tr>
<tr>
<td valign="top">

*SOAP SAP RM* 

Receiver adapter

</td>
<td valign="top">

Exchanges messages with a receiver system based on the SOAP communication protocol and SAP Reliable Messaging \(SAP RM\) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards.

See: [Configure the SOAP \(SAP RM\) Receiver Adapter](50-Development/configure-the-soap-sap-rm-receiver-adapter-8366495.md)

</td>
</tr>
<tr>
<td valign="top">

*Splunk* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive search-related information from the Splunk storage.

See: [Configure the Splunk Sender Adapter](50-Development/configure-the-splunk-sender-adapter-271ad20.md)

</td>
</tr>
<tr>
<td valign="top">

*Splunk* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to get data from the Splunk storage or to create, modify, or delete data on the Splunk storage.

See: [Configure the Splunk Receiver Adapter](50-Development/configure-the-splunk-receiver-adapter-e8e6ba6.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors REST*

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a SuccessFactors sender system using the REST message protocol.

The adapter supports the following operations: GET

See: [Configure the SuccessFactors REST Sender Adapter](50-Development/configure-the-successfactors-rest-sender-adapter-9f0646b.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors REST*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a SuccessFactors receiver system using the REST message protocol.

The adapter supports the following operations: GET, POST

See: [Configure the SuccessFactors REST Receiver Adapter](50-Development/configure-the-successfactors-rest-receiver-adapter-9cff562.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors SOAP*

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to SOAP-based Web services of a SuccessFactors sender system \(synchronous or asynchronous communication\).

The adapter supports the following operations: Query

See: [Configure the SuccessFactors \(SOAP\) Sender Adapter](50-Development/configure-the-successfactors-soap-sender-adapter-874e4b1.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors SOAP*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to SOAP-based Web services of a SuccessFactors receiver system \(synchronous or asynchronous communication\).

The adapter supports the following operations: Insert, Query, Update, Upsert

See: [Configure the SuccessFactors SOAP Receiver Adapter](50-Development/configure-the-successfactors-soap-receiver-adapter-360ef42.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors OData V2*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a SuccessFactors system using OData V2.

Features of OData version 2.0 supported by the adapter:

-   Operations: GET \(get single entity as an entry document\), PUT \(update existing entry with an entry document\), POST \(create new entry from an entry document\), DELETE \(Delete an entry from an entry document\), UPSERT \(combination of Update OR Insert\)

-   Query options: $expand, $skip,and $top

-   Server-side pagination

-   Client-side pagination

-   Pagination enhancement: Data retrieved in chunks and sent to Cloud Integration

-   Deep insert: Creates a structure of related entities in one request

-   Authentication options: Basic authentication

-   Reference links: Link two entities using the <link\> tag

See: [Configure the SuccessFactors OData V2 Receiver Adapter](50-Development/configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md)

</td>
</tr>
<tr>
<td valign="top">

*SuccessFactors OData V4*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a SuccessFactors system using OData V4.

Features of OData version 4.0 supported by the adapter:

-   Operations: GET, POST, PUT, DELETE

-   Navigation

-   Primitive types supported according to OData V4 specification

-   Structural types supported for create/update operations:

    Edm.ComplexType, Edm:EnumType, Collection\(Edm.PrimitiveType\) and Collection\(Edm.ComplexType\)


See: [SuccessFactors OData V4 Receiver Adapter](50-Development/successfactors-odata-v4-receiver-adapter-cd091fc.md)

</td>
</tr>
<tr>
<td valign="top">

*SugarCRM* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to SugarCRM.

See: [SugarCRM Receiver Adapter](50-Development/sugarcrm-receiver-adapter-d96ddf7.md)

</td>
</tr>
<tr>
<td valign="top">

*Twitter* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to access Twitter and read or post tweets.

Using OAuth, SAP Integration Suite can access resources on Twitter on behalf of a Twitter user.

See: [Twitter Receiver Adapter](50-Development/twitter-receiver-adapter-453c174.md)

</td>
</tr>
<tr>
<td valign="top">

*Workday* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Workday. Supports Workday SOAP API with basic authentication.

See: [Workday Receiver Adapter](50-Development/workday-receiver-adapter-0c6e670.md)

</td>
</tr>
<tr>
<td valign="top">

*XI*

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote sender system that can process the XI message protocol.

See: [Configure the XI Sender Adapter](50-Development/configure-the-xi-sender-adapter-41a1a57.md)

</td>
</tr>
<tr>
<td valign="top">

*XI*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote receiver system that can process the XI message protocol.

See: [Configure the XI Receiver Adapter](50-Development/configure-the-xi-receiver-adapter-5d2670f.md)

</td>
</tr>
</table>



<a name="loio93d82e8ff860450da10ad2c16bf5e971__section_fs4_qvq_5sb"/>

## Connectors

Connect SAP Integration Suite to a number of SAP and non-SAP applications such like Citrix GoToWebinar, Dropbox Business, Evernote, Gmail, to name a few examples. Each connector is an application programming interface \(API\) that provides a set of API resources and methods you can use to access the resources of the associated application.

Open Connectors provides you with a catalog of 170+ non-SAP connectors. You can use the *OpenConnectors* adapter to connect SAP Integration Suite tenant with such a connector \(see: [OpenConnectors Receiver Adapter](50-Development/openconnectors-receiver-adapter-1a27cee.md)\).

**Connectors**


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

*Act! 365* 

</td>
<td valign="top">

Sales pipeline and marketing application designed to help businesses close more deals

See: [Act! 365](https://help.openconnectors.ext.hana.ondemand.com/home/actessentials)

</td>
</tr>
<tr>
<td valign="top">

*Act! Premium* 

</td>
<td valign="top">

Keep track of client and prospect details in a single database that can be shared by multiple users

See: [Act! Premium](https://help.openconnectors.ext.hana.ondemand.com/home/actpremiumcrm)

</td>
</tr>
<tr>
<td valign="top">

*Act-On* 

</td>
<td valign="top">

Marketing automation software to help sales and marketing teams convert leads

See: [Act-On](https://help.openconnectors.ext.hana.ondemand.com/home/acton)

</td>
</tr>
<tr>
<td valign="top">

*Acuity Scheduling* 

</td>
<td valign="top">

Appointment scheduling software for appointments, payments, and intake forms

See: [Acuity Scheduling](https://help.openconnectors.ext.hana.ondemand.com/home/acuityscheduling)

</td>
</tr>
<tr>
<td valign="top">

*Adobe Sign* 

</td>
<td valign="top">

An eSignature application to easily prepare and send documents for e-sign

See: [Adobe Sign](https://help.openconnectors.ext.hana.ondemand.com/home/adobe-esign)

</td>
</tr>
<tr>
<td valign="top">

*ADP Lifion* 

</td>
<td valign="top">

Building sophisticated, consumer-grade solutions that can meet all of their needs while allowing companies to grow and win in the market.

See: [ADP Lifion](https://help.openconnectors.ext.hana.ondemand.com/home/catalog) 

</td>
</tr>
<tr>
<td valign="top">

*ADP WorkForce Now* 

</td>
<td valign="top">

Human capital management solution for companies with more than 50 employees

See: [ADP WorkForce Now](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*Amazon S3* 

</td>
<td valign="top">

File storage and web based content on Amazon.co, S3 Buckets

See: [Amazon S3](https://help.openconnectors.ext.hana.ondemand.com/home/amazons3)

</td>
</tr>
<tr>
<td valign="top">

*Amazon SQS* 

</td>
<td valign="top">

A distributed message queuing service introduced by Amazon.com.

See: [Amazon SQS](https://help.openconnectors.ext.hana.ondemand.com/home/amazonsqs)

</td>
</tr>
<tr>
<td valign="top">

*Autotask CRM* 

</td>
<td valign="top">

Allows you to manage contacts, leads, accounts, opportunities, etc

See: [Autotask CRM](https://help.openconnectors.ext.hana.ondemand.com/home/autotaskcrm)

</td>
</tr>
<tr>
<td valign="top">

*Autotask Helpdesk* 

</td>
<td valign="top">

Unified service and support issue tracking software

See: [Autotask Helpdesk](https://help.openconnectors.ext.hana.ondemand.com/home/autotaskhelpdesk)

</td>
</tr>
<tr>
<td valign="top">

*Azure Blob* 

</td>
<td valign="top">

Helps you to create data lakes for your analytics needs, provides storage to build powerful cloud-native and mobile applications

See: [Azure Blob](https://help.openconnectors.ext.hana.ondemand.com/home/azureblob)

</td>
</tr>
<tr>
<td valign="top">

*Bamboo HR* 

</td>
<td valign="top">

Human resoures application for applicant tracking and employee goals

See: [Bamboo HR](https://help.openconnectors.ext.hana.ondemand.com/home/bamboohr)

</td>
</tr>
<tr>
<td valign="top">

*BigCommerce* 

</td>
<td valign="top">

Enterprise eCommerce platform to manage shipping and payments, listings and products

See: [BigCommerce](https://help.openconnectors.ext.hana.ondemand.com/home/bigcommerce)

</td>
</tr>
<tr>
<td valign="top">

*BigQuery* 

</td>
<td valign="top">

A fully-managed, serverless data warehouse that enables scalable analysis over petabytes of data

See: [BigQuery](https://help.openconnectors.ext.hana.ondemand.com/home/bigquery)

</td>
</tr>
<tr>
<td valign="top">

*boxv2* 

</td>
<td valign="top">

Cloud content management, collaboration, and file sharing service

See: [boxv2](https://help.openconnectors.ext.hana.ondemand.com/home/box)

</td>
</tr>
<tr>
<td valign="top">

*BrightTALK* 

</td>
<td valign="top">

Technology media providing webinar and video solutions

See: [BrightTALK](https://help.openconnectors.ext.hana.ondemand.com/home/brighttalk)

</td>
</tr>
<tr>
<td valign="top">

*Bullhorn* 

</td>
<td valign="top">

Applicant tracking system and CRM for staffing firms

See: [Bullhorn](https://help.openconnectors.ext.hana.ondemand.com/home/bullhorn)

</td>
</tr>
<tr>
<td valign="top">

*Campaign Monitor* 

</td>
<td valign="top">

Email Marketing and Automation for your Business

See: [Campaign Monitor](https://help.openconnectors.ext.hana.ondemand.com/home/campaignmonitor)

</td>
</tr>
<tr>
<td valign="top">

*Chargebee* 

</td>
<td valign="top">

Recurring billing for subscription businesses

See: [Chargebee](https://help.openconnectors.ext.hana.ondemand.com/home/chargebee)

</td>
</tr>
<tr>
<td valign="top">

*Chargebee V2* 

</td>
<td valign="top">

A recurring billing and subscription management tool

See: [Chargebee](https://help.openconnectors.ext.hana.ondemand.com/home/chargebee)

</td>
</tr>
<tr>
<td valign="top">

*Chargify* 

</td>
<td valign="top">

Recurring billing for subscription businesses

See: [Chargify](https://help.openconnectors.ext.hana.ondemand.com/home/chargify)

</td>
</tr>
<tr>
<td valign="top">

*Cisco Webex Teams* 

</td>
<td valign="top">

Team collaboration service brings together messaging, file sharing, video meeting, whiteboarding, and calling

See: [Cisco Webex Teams](https://help.openconnectors.ext.hana.ondemand.com/home/cisco-webex-teams)

</td>
</tr>
<tr>
<td valign="top">

*Citrix ShareFile* 

</td>
<td valign="top">

The secure file sharing and transfer service that's built for business

See: [Citrix ShareFile](https://help.openconnectors.ext.hana.ondemand.com/home/sharefile)

</td>
</tr>
<tr>
<td valign="top">

*Click Field Service Edge* 

</td>
<td valign="top">

Innovative, market-leading field service management software solution, offered in a modular fashion

See: [Click Field Service Edge](https://help.openconnectors.ext.hana.ondemand.com/home/fieldserviceedge)

</td>
</tr>
<tr>
<td valign="top">

*Close.io* 

</td>
<td valign="top">

Predictive CRM focused on automation services for sales teams

See: [Close.io](https://help.openconnectors.ext.hana.ondemand.com/home/closeio)

</td>
</tr>
<tr>
<td valign="top">

*Clover* 

</td>
<td valign="top">

Small and Medium-sized Businesses Point of Sale System for Merchants

See: [Clover](https://help.openconnectors.ext.hana.ondemand.com/home/clover)

</td>
</tr>
<tr>
<td valign="top">

*Connector for Stripe* 

</td>
<td valign="top">

API Driven credit card processing with token based identity

See:[https://help.openconnectors.ext.hana.ondemand.com/home/stripe](https://help.openconnectors.ext.hana.ondemand.com/home/stripe) 

</td>
</tr>
<tr>
<td valign="top">

*ConnectWise CRM REST* 

</td>
<td valign="top">

Online software with sales and marketing capability

See: [ConnectWise CRM Rest](https://help.openconnectors.ext.hana.ondemand.com/home/connectwisecrmrest)

</td>
</tr>
<tr>
<td valign="top">

*Constant Contact* 

</td>
<td valign="top">

Email marketing automation platform to create marketing campaigns

See: [Constant Contact](https://help.openconnectors.ext.hana.ondemand.com/home/constantcontact)

</td>
</tr>
<tr>
<td valign="top">

*Coupa* 

</td>
<td valign="top">

Cloud platform for visibility and control of your business spend

See: [Coupa](https://help.openconnectors.ext.hana.ondemand.com/home/coupa)

</td>
</tr>
<tr>
<td valign="top">

*Dayforce HCM* 

</td>
<td valign="top">

An always-on people platform that is built as a single system with powerful data at its core.

See: [Dayforce HCM](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*DocuShare Flex* 

</td>
<td valign="top">

Document management focused on integrated user cases

See: [DocuShare Flex](https://help.openconnectors.ext.hana.ondemand.com/home/docushareflex)

</td>
</tr>
<tr>
<td valign="top">

*DocuSign* 

</td>
<td valign="top">

Offers eSignature, a way to sign electronically on practically any device, from almost anywhere, at any time

See: [DocuSign](https://help.openconnectors.ext.hana.ondemand.com/home/docusign)

</td>
</tr>
<tr>
<td valign="top">

*Dropbox* 

</td>
<td valign="top">

Document management application for secure file sharing and storage

See: [Dropbox](https://help.openconnectors.ext.hana.ondemand.com/home/dropbox)

</td>
</tr>
<tr>
<td valign="top">

*Dropbox Business* 

</td>
<td valign="top">

Document management application featuring entreprise security

See: [Dropbox Business](https://help.openconnectors.ext.hana.ondemand.com/home/dropboxbusiness)

</td>
</tr>
<tr>
<td valign="top">

*E-conomic* 

</td>
<td valign="top">

Accounting and ERP system focused in the Nordics

See: [E-conomic](https://help.openconnectors.ext.hana.ondemand.com/home/economic)

</td>
</tr>
<tr>
<td valign="top">

*Ecwid* 

</td>
<td valign="top">

eCommerce Shopping Cart solution with Wordpress Plugins

See: [Ecwid](https://help.openconnectors.ext.hana.ondemand.com/home/ecwid)

</td>
</tr>
<tr>
<td valign="top">

*Egnyte* 

</td>
<td valign="top">

Cloud storage platform featuring Secure Enterprise File Sharing and Content Governance

See: [Egnyte](https://help.openconnectors.ext.hana.ondemand.com/home/egnyte)

</td>
</tr>
<tr>
<td valign="top">

*Etsy* 

</td>
<td valign="top">

Platform for hand crafted goods featuring invididual merchants

See: [Etsy](https://help.openconnectors.ext.hana.ondemand.com/home/etsy)

</td>
</tr>
<tr>
<td valign="top">

*Evernote* 

</td>
<td valign="top">

Cloud based notetaking application designed for note taking, organizing, task lists, and archiving

See: [Evernote](https://help.openconnectors.ext.hana.ondemand.com/home/evernote)

</td>
</tr>
<tr>
<td valign="top">

*Expensify* 

</td>
<td valign="top">

Travel, Expense, and Invoice management

See: [Expensify](https://help.openconnectors.ext.hana.ondemand.com/home/expensify)

</td>
</tr>
<tr>
<td valign="top">

*Facebook* 

</td>
<td valign="top">

Provides social media and social networking service

See: [Facebook](https://help.openconnectors.ext.hana.ondemand.com/home/facebooksocial)

</td>
</tr>
<tr>
<td valign="top">

*Facebook Lead Ads* 

</td>
<td valign="top">

Advertising service to run lead generation campaigns

See: [Facebook Lead Ads](https://help.openconnectors.ext.hana.ondemand.com/home/facebookleadads)

</td>
</tr>
<tr>
<td valign="top">

*Facebook Workplace* 

</td>
<td valign="top">

An entreprise connectivity platform featuring tools like groups, instant messaging and News Feed

See: [Facebook Workplace](https://help.openconnectors.ext.hana.ondemand.com/home/facebookworkplace)

</td>
</tr>
<tr>
<td valign="top">

*Files* 

</td>
<td valign="top">

Customer can upload a file as a resource

See: [Files](https://help.openconnectors.ext.hana.ondemand.com/home/files)

</td>
</tr>
<tr>
<td valign="top">

*First Advantage* 

</td>
<td valign="top">

Delivers comprehensive background check solutions and insights

See: [First Advantage](https://help.openconnectors.ext.hana.ondemand.com/home/firstadvantage)

</td>
</tr>
<tr>
<td valign="top">

*Fortnox* 

</td>
<td valign="top">

Comprehensive accounting software that covers invoicing, suppliers, taxes, focuses on the Nordics

See: [Fortnox](https://help.openconnectors.ext.hana.ondemand.com/home/fortnox)

</td>
</tr>
<tr>
<td valign="top">

*Freshbooks Classic* 

</td>
<td valign="top">

Financial and accounting software for small and medium sized businesses

See: [FreshBooks Classic](https://help.openconnectors.ext.hana.ondemand.com/home/freshbooks)

</td>
</tr>
<tr>
<td valign="top">

*Freshbooks Cloud Accounting* 

</td>
<td valign="top">

Cloud based financial and accounting software for small businesses

See: [Freshbooks Cloud Accounting](https://help.openconnectors.ext.hana.ondemand.com/home/freshbooks)

</td>
</tr>
<tr>
<td valign="top">

*Freshdesk V2* 

</td>
<td valign="top">

Cloud-based customer service software \(version 2\)

See: [Freshdesk V2](https://help.openconnectors.ext.hana.ondemand.com/home/freshdeskv2)

</td>
</tr>
<tr>
<td valign="top">

*Freshservice* 

</td>
<td valign="top">

Cloud based ITSM software for your service desk to manage incidents, assets and more

See: [Freshservice](https://help.openconnectors.ext.hana.ondemand.com/home/freshservice)

</td>
</tr>
<tr>
<td valign="top">

*GitHub* 

</td>
<td valign="top">

Git based version control repositories for developers

See: [GitHub](https://help.openconnectors.ext.hana.ondemand.com/home/github)

</td>
</tr>
<tr>
<td valign="top">

*GlobalMeet Webinar* 

</td>
<td valign="top">

Cloud-based SaaS webcast platform for live webcasting and video streaming for entreprise

See: [GlobalMeet Webinar](https://help.openconnectors.ext.hana.ondemand.com/home/globalmeet)

</td>
</tr>
<tr>
<td valign="top">

*Gmail* 

</td>
<td valign="top">

A free email service developed by Google

See: [Gmail](https://help.openconnectors.ext.hana.ondemand.com/home/gmail)

</td>
</tr>
<tr>
<td valign="top">

*GoodData* 

</td>
<td valign="top">

Business intelligence and big data analytics software for cloud computing

See: [GoodData](https://help.openconnectors.ext.hana.ondemand.com/home/gooddata)

</td>
</tr>
<tr>
<td valign="top">

*Google Ads* 

</td>
<td valign="top">

An online advertising platform developed by Google

See: [Google Ads](https://help.openconnectors.ext.hana.ondemand.com/home/google-ads)

</td>
</tr>
<tr>
<td valign="top">

*Google AdWords* 

</td>
<td valign="top">

Online advertisement platform from Google

See: [Google AdWords](https://help.openconnectors.ext.hana.ondemand.com/home/googleadwords)

</td>
</tr>
<tr>
<td valign="top">

*Google Analytics* 

</td>
<td valign="top">

Measures your advertising ROI as well as tracks your Flash, video, and social networking sites and applications

See: [Google Analytics](https://help.openconnectors.ext.hana.ondemand.com/home/googleanalytics)

</td>
</tr>
<tr>
<td valign="top">

*Google Calendar* 

</td>
<td valign="top">

Scheduling calendar service from Google, integrated online calendars designed for teams

See: [Google Calendar](https://help.openconnectors.ext.hana.ondemand.com/home/googlecalendar)

</td>
</tr>
<tr>
<td valign="top">

*Google Cloud Storage* 

</td>
<td valign="top">

A Restful online file storage web service for storing and accessing data on Google Cloud Platform infrastructure

See: [Google Cloud Storage](https://help.openconnectors.ext.hana.ondemand.com/home/googlecloudstorage)

</td>
</tr>
<tr>
<td valign="top">

*Google Drive* 

</td>
<td valign="top">

File storage and synchronization service available on all devices from Google

See: [Google Drive](https://help.openconnectors.ext.hana.ondemand.com/home/googledrive)

</td>
</tr>
<tr>
<td valign="top">

*Google Sheets V4* 

</td>
<td valign="top">

Spreadsheet program from Google \(version 4\)

See: [Google Sheets V4](https://help.openconnectors.ext.hana.ondemand.com/home/googlesheets)

</td>
</tr>
<tr>
<td valign="top">

*Google Suite* 

</td>
<td valign="top">

Integrated suite of cloud computing, productivity, and collaboration apps

See: [Google Suite](https://help.openconnectors.ext.hana.ondemand.com/home/googlesuite)

</td>
</tr>
<tr>
<td valign="top">

*GoToWebinar* 

</td>
<td valign="top">

A simple, self-service webinar tool to host large-scale online events

See: [GoToWebinar](https://help.openconnectors.ext.hana.ondemand.com/home/gotowebinar)

</td>
</tr>
<tr>
<td valign="top">

*Greenhouse* 

</td>
<td valign="top">

Applicant tracking system and recruiting software

See: [Greenhouse](https://help.openconnectors.ext.hana.ondemand.com/home/greenhouse)

</td>
</tr>
<tr>
<td valign="top">

*HireRight* 

</td>
<td valign="top">

A leading provider of on-demand employment background checks and pre-employment screening solutions

See: [HireRight](https://help.openconnectors.ext.hana.ondemand.com/home/hireright)

</td>
</tr>
<tr>
<td valign="top">

*Hootsuite* 

</td>
<td valign="top">

Social media management platform to manage multiple networks and profiles

See: [Hootsuite](https://help.openconnectors.ext.hana.ondemand.com/home/hootsuite)

</td>
</tr>
<tr>
<td valign="top">

*HubSpot CRM* 

</td>
<td valign="top">

Allows the sales team to easily organize, track, and grow pipeline

See: [HubSpot CRM](https://help.openconnectors.ext.hana.ondemand.com/home/hubspotcrm)

</td>
</tr>
<tr>
<td valign="top">

*HubSpot Marketing* 

</td>
<td valign="top">

Advanced marketing platform that integrates all of your current software, services, support systems

See: [HubSpot Marketing](https://help.openconnectors.ext.hana.ondemand.com/home/hubspot)

</td>
</tr>
<tr>
<td valign="top">

*iContact* 

</td>
<td valign="top">

Email marketing software application for small businesses

See: [iContact](https://help.openconnectors.ext.hana.ondemand.com/home/icontact)

</td>
</tr>
<tr>
<td valign="top">

*Infobip* 

</td>
<td valign="top">

Seamless mobile interactions and messaging between business and people

See: [Infobip](https://help.openconnectors.ext.hana.ondemand.com/home/infobip)

</td>
</tr>
<tr>
<td valign="top">

*Infusionsoft CRM by Keap* 

</td>
<td valign="top">

The Infusionsoft suite for account,contact,opportunity and contact management

See: [Infusionsoft CRM by Keap](https://help.openconnectors.ext.hana.ondemand.com/home/infusionsoftcrm)

</td>
</tr>
<tr>
<td valign="top">

*Infusionsoft ERP by Keap* 

</td>
<td valign="top">

Enterprise resource planning suite that manages the business process

See: [Infusionsoft ERP by Keap](https://help.openconnectors.ext.hana.ondemand.com/home/infusionsofterp)

</td>
</tr>
<tr>
<td valign="top">

*Infusionsoft Marketing Automation by Keap* 

</td>
<td valign="top">

Automates and simplifies tasks within the Infusionsoft suite

See: [Infusionsoft Marketing Automation by Keap](https://help.openconnectors.ext.hana.ondemand.com/home/infusionsoftmarketing)

</td>
</tr>
<tr>
<td valign="top">

*Infusionsoft Online Sales by Keap* 

</td>
<td valign="top">

Customize sales within the Infusionsoft suite

See: [Infusionsoft Online Sales by Keap](https://help.openconnectors.ext.hana.ondemand.com/home/infusionsoftecommerce)

</td>
</tr>
<tr>
<td valign="top">

*Infusionsoft REST by Keap* 

</td>
<td valign="top">

E-mail marketing and sales platform for small businesses for appointments, campaigns, emails, opportunities management

See: [Infusionsoft REST by Keap](https://help.openconnectors.ext.hana.ondemand.com/home/infusionsoftrest)

</td>
</tr>
<tr>
<td valign="top">

*Insightly* 

</td>
<td valign="top">

Cloud-based CRM platform for Gmail, G Suite, and Outlook

See: [Insightly](https://help.openconnectors.ext.hana.ondemand.com/home/insightly)

</td>
</tr>
<tr>
<td valign="top">

*Intercom* 

</td>
<td valign="top">

A marketing platform lets businesses track and filter customer data

See: [Intercom](https://help.openconnectors.ext.hana.ondemand.com/home/intercom)

</td>
</tr>
<tr>
<td valign="top">

*Intercom V2* 

</td>
<td valign="top">

A software that specializes in business messaging, providing businesses with a way to chat with their customers

See: [Intercom V2](https://help.openconnectors.ext.hana.ondemand.com/home/intercom)

</td>
</tr>
<tr>
<td valign="top">

*JIRA* 

</td>
<td valign="top">

Plan, track, and manage your agile and software development projects

See: [JIRA](https://help.openconnectors.ext.hana.ondemand.com/home/jira)

</td>
</tr>
<tr>
<td valign="top">

*Jira On Prem* 

</td>
<td valign="top">

Flexible, collaborative ITSM solution built for rapid service delivery

See:[Jira On Prem](https://help.openconnectors.ext.hana.ondemand.com/home/jiraonprem)

</td>
</tr>
<tr>
<td valign="top">

*Lithium Response* 

</td>
<td valign="top">

Manage multiple networks and profiles with this social media management

See: [Lithium Response](https://help.openconnectors.ext.hana.ondemand.com/home/lithiumlsw)

</td>
</tr>
<tr>
<td valign="top">

*Magento v2.0* 

</td>
<td valign="top">

Open-source e-commerce platform for retailers and brands \(version 2.0\)

See: [Magento v2.0](https://help.openconnectors.ext.hana.ondemand.com/home/magentov20)

</td>
</tr>
<tr>
<td valign="top">

*MailChimp v3.0* 

</td>
<td valign="top">

Email marketing, ads, landing pages, and automation tools \(version 3\)

See: [MailChimp v3.0](https://help.openconnectors.ext.hana.ondemand.com/home/mailchimpv3)

</td>
</tr>
<tr>
<td valign="top">

*MailJet* 

</td>
<td valign="top">

Email delivery service for marketing and developer teams

See: [MailJet](https://help.openconnectors.ext.hana.ondemand.com/home/mailjet)

</td>
</tr>
<tr>
<td valign="top">

*MailJet Marketing* 

</td>
<td valign="top">

Build, send, and monitor your email marketing campaigns

See: [MailJet Marketing](https://help.openconnectors.ext.hana.ondemand.com/home/mailjetmarketing)

</td>
</tr>
<tr>
<td valign="top">

*Marketo* 

</td>
<td valign="top">

Marketing automation software focused on account-based marketing

See: [Marketo](https://help.openconnectors.ext.hana.ondemand.com/home/marketo)

</td>
</tr>
<tr>
<td valign="top">

*Maximizer* 

</td>
<td valign="top">

All-inclusive CRM software for sales, marketing, and customer service

See: [Maximizer](https://help.openconnectors.ext.hana.ondemand.com/home/maximizer)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics 365 Finance and Operations* 

</td>
<td valign="top">

Enterprise resource planning system for medium to large organizations

See: [Microsoft Dynamics 365 Finance and Operations](https://help.openconnectors.ext.hana.ondemand.com/home/dynamics365fo)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics 365 HR* 

</td>
<td valign="top">

Optimising HR programmes, transform employee experiences, and discover workforce insights

See: [Microsoft Dynamics 365 HR](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics Business Central Cloud* 

</td>
<td valign="top">

A cloud solution that connects operations across your small or medium-sized business

See: [Microsoft Dynamics Business Central Cloud](https://help.openconnectors.ext.hana.ondemand.com/home/msbusinesscentral)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics CRM* 

</td>
<td valign="top">

CRM package that focuses on sales, marketing, and service sectors

See: [Microsoft Dynamics CRM](https://help.openconnectors.ext.hana.ondemand.com/home/dynamicscrmadfs)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics CRM Rest* 

</td>
<td valign="top">

Built on the latest Web API of Microsoft for Microsoft Dynamics CRM package that focuses on sales, marketing, and service sectors

See: [Microsoft Dynamics CRM Rest](https://help.openconnectors.ext.hana.ondemand.com/home/dynamicscrmrest)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics GP* 

</td>
<td valign="top">

ERP solution for financials, inventory, and operations for small and medium businesses

See: [Microsoft Dynamics GP](https://help.openconnectors.ext.hana.ondemand.com/home/greatplains)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics Navision* 

</td>
<td valign="top">

An easily adaptable enterprise resource planning \(ERP\) solution, part of the Microsoft Dynamics family

See: [Microsoft Dynamics Navision](https://help.openconnectors.ext.hana.ondemand.com/home/dynamicsnavisionerp)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Graph* 

</td>
<td valign="top">

Developer platform to connects Microsoft services and devices

See: [Microsoft Graph](https://help.openconnectors.ext.hana.ondemand.com/home/microsoftgraph)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Office 365* 

</td>
<td valign="top">

A line of subscription services offered by Microsoft as part of the Microsoft Office product line

See: [Microsoft Office 365](https://help.openconnectors.ext.hana.ondemand.com/home/office365)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft OneDrive and Sharepoint Graph* 

</td>
<td valign="top">

The OneDrive REST API is a portion of the Microsoft Graph API which allows your app to connect to content stored in OneDrive and SharePoint

See: [Microsoft OneDrive and Sharepoint Graph](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft OneDrive for Business* 

</td>
<td valign="top">

Managed by the organisation to store, sync, and share work files in the cloud

See: [Microsoft OneDrive for Business](https://help.openconnectors.ext.hana.ondemand.com/home/onedrivebusiness)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft SQL Server* 

</td>
<td valign="top">

Relational database management system developed by Microsoft

See: [Microsoft SQL Server](https://help.openconnectors.ext.hana.ondemand.com/home/sqlserver)

</td>
</tr>
<tr>
<td valign="top">

*MySQL* 

</td>
<td valign="top">

Open source relational database management system

See: [MySQL](https://help.openconnectors.ext.hana.ondemand.com/home/mysql)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite CRM* 

</td>
<td valign="top">

Customer relationship management solution with 360 view of customers \(2018 Release 1\)

See: [Netsuite CRM](https://help.openconnectors.ext.hana.ondemand.com/home/netsuitecrmv2)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite CRM 2022* 

</td>
<td valign="top">

Customer relationship management solution with 360 view of customers

See: [Netsuite CRM 2022](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite ERP* 

</td>
<td valign="top">

Scalable cloud ERP for mid-sized businesses and large enterprises

See: [Netsuite ERP](https://help.openconnectors.ext.hana.ondemand.com/home/netsuiteerpv2)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite ERP 2022* 

</td>
<td valign="top">

Scalable cloud ERP for mid-sized businesses and large enterprises

See: [Netsuite ERP 2022](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite Finance* 

</td>
<td valign="top">

Expedites daily transactions, accelerates close and ensures compliance

See: [Netsuite Finance](https://help.openconnectors.ext.hana.ondemand.com/home/netsuitefinancev2)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite Finance 2022* 

</td>
<td valign="top">

Expedites daily transactions, accelerates close and ensures compliance

See: [Netsuite Finance 2022](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite ERP 2018 Release 1* 

</td>
<td valign="top">

Scalable cloud ERP for mid-sized businesses and large enterprises\(2018 Release 1\)

See: [Netsuite ERP 2018 Release 1](https://help.openconnectors.ext.hana.ondemand.com/home/netsuiteerpv2)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite Finance 2018 Release 1* 

</td>
<td valign="top">

Expedites daily transactions, accelerates close and ensures compliance

See: [Netsuite Finance 2018 Release 1](https://help.openconnectors.ext.hana.ondemand.com/home/netsuitefinancev2)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite HC* 

</td>
<td valign="top">

Integrates people data to allows control over HR processes \(2018 Release 1\)

See: [Netsuite HC](https://help.openconnectors.ext.hana.ondemand.com/home/netsuitehcv2)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite HC 2022* 

</td>
<td valign="top">

Integrates people data to allows control over HR processes

See: [Netsuite HC 2022](https://help.openconnectors.ext.hana.ondemand.com/home/catalog)

</td>
</tr>
<tr>
<td valign="top">

*Netsuite Restlets* 

</td>
<td valign="top">

Allows to build custom REST-based endpoints into NetSuite

See: [Netsuite Restlets](https://help.openconnectors.ext.hana.ondemand.com/home/netsuiterestlets)

</td>
</tr>
<tr>
<td valign="top">

*OneDrive* 

</td>
<td valign="top">

File hosting service and synchronization service from Microsoft

See: [OneDrive](https://help.openconnectors.ext.hana.ondemand.com/home/onedrivev2)

</td>
</tr>
<tr>
<td valign="top">

*OneNote* 

</td>
<td valign="top">

Digital notebook and allows free-form information gathering and multi-user collaboration

See: [OneNote](https://help.openconnectors.ext.hana.ondemand.com/home/onenote)

</td>
</tr>
<tr>
<td valign="top">

*Oracle DB* 

</td>
<td valign="top">

A proprietary multi-model database management system

See: [Oracle DB](https://help.openconnectors.ext.hana.ondemand.com/home/oracledb)

</td>
</tr>
<tr>
<td valign="top">

*Oracle Eloqua* 

</td>
<td valign="top">

Software as a Service for marketing automation

See: [Oracle Eloqua](https://help.openconnectors.ext.hana.ondemand.com/home/eloqua)

</td>
</tr>
<tr>
<td valign="top">

*Oracle HCM Cloud* 

</td>
<td valign="top">

Cloud-based software application suite for global HR, talent, and workforce management

See: [Oracle HCM Cloud](https://help.openconnectors.ext.hana.ondemand.com/home/oraclehcmcloud)

</td>
</tr>
<tr>
<td valign="top">

*Oracle Sales Cloud* 

</td>
<td valign="top">

Enhance sales engagement and strengthen customer relationships,featuring account, opportunity and lead management

See: [Oracle Sales Cloud](https://help.openconnectors.ext.hana.ondemand.com/home/oraclesalescloud)

</td>
</tr>
<tr>
<td valign="top">

*Oracle Service Cloud* 

</td>
<td valign="top">

Unified web, social, and contact center experiences

See: [Oracle Service Cloud](https://help.openconnectors.ext.hana.ondemand.com/home/servicecloud)

</td>
</tr>
<tr>
<td valign="top">

*Orderful* 

</td>
<td valign="top">

Enable suppliers to immediately trade data with buyers

See: [Orderful](https://help.openconnectors.ext.hana.ondemand.com/home/orderful)

</td>
</tr>
<tr>
<td valign="top">

*Outlook Email* 

</td>
<td valign="top">

Combines email, calendar events, and files in one place from Microsoft

See: [Outlook Email](https://help.openconnectors.ext.hana.ondemand.com/home/outlookemail)

</td>
</tr>
<tr>
<td valign="top">

*Pardot by Salesforce* 

</td>
<td valign="top">

Business to business marketing automation from Salesforce

See: [Pardot by Salesforce](https://help.openconnectors.ext.hana.ondemand.com/home/pardot)

</td>
</tr>
<tr>
<td valign="top">

*Paypal v2* 

</td>
<td valign="top">

Send Money, Pay Online or Set Up a Merchant Account \(version 2\)

See: [Paypal v2](https://help.openconnectors.ext.hana.ondemand.com/home/paypalv2)

</td>
</tr>
<tr>
<td valign="top">

*Pipedrive* 

</td>
<td valign="top">

Sales customer relationship management tool with little input,enables teams of all sizes to manage sales pipeline

See: [Pipedrive](https://help.openconnectors.ext.hana.ondemand.com/home/pipedrive)

</td>
</tr>
<tr>
<td valign="top">

*Plaid* 

</td>
<td valign="top">

Enables applications to connect with users bank accounts

See: [Plaid](https://help.openconnectors.ext.hana.ondemand.com/home/plaid)

</td>
</tr>
<tr>
<td valign="top">

*Platform API* 

</td>
<td valign="top">

Facilitate your integrations to be fully customizable

See: [Platform API](https://help.openconnectors.ext.hana.ondemand.com/home/platform-reference)

</td>
</tr>
<tr>
<td valign="top">

*PostgreSQL* 

</td>
<td valign="top">

Open source object-relational database system that uses and extends the structured query language

See: [PostgreSQL](https://help.openconnectors.ext.hana.ondemand.com/home/postgresql)

</td>
</tr>
<tr>
<td valign="top">

*QuickBooks Online* 

</td>
<td valign="top">

Cloud-based financial management software with payments, pay bills, and payroll functions

See: [QuickBooks Online](https://help.openconnectors.ext.hana.ondemand.com/home/quickbooks)

</td>
</tr>
<tr>
<td valign="top">

*QuickBooks Online Rest* 

</td>
<td valign="top">

Rest API for QuickBooks Online which is a Cloud-based financial management software with payments, pay bills, and payroll functions

</td>
</tr>
<tr>
<td valign="top">

*Rally \(Formerly CA Agile Central\)* 

</td>
<td valign="top">

An enterprise-class platform that's purpose-built for scaling agile development practices

See: [Rally \(Formerly CA Agile Central\)](https://help.openconnectors.ext.hana.ondemand.com/home/caagilecentral)

</td>
</tr>
<tr>
<td valign="top">

*Recurly* 

</td>
<td valign="top">

A cloud-based company providing recurring billing management as an outsourced service

See: [Recurly](https://help.openconnectors.ext.hana.ondemand.com/home/recurly)

</td>
</tr>
<tr>
<td valign="top">

*Sage 200 Accounting* 

</td>
<td valign="top">

Finance and management software to manage accounts and customers

See: [Sage 200 Accounting](https://help.openconnectors.ext.hana.ondemand.com/home/sage200)

</td>
</tr>
<tr>
<td valign="top">

*Sage 50 US* 

</td>
<td valign="top">

US edition of Sage 50 allowing you to manage customers, invoices, purchase orders, etc. across multiple Finance Element

</td>
</tr>
<tr>
<td valign="top">

*Sage Accounting* 

</td>
<td valign="top">

Business management software subscription-based product

See: [Sage Accounting](https://help.openconnectors.ext.hana.ondemand.com/home/sageone)

</td>
</tr>
<tr>
<td valign="top">

*Sage CRM* 

</td>
<td valign="top">

Manage customers, leads, marketing, sales opportunities and customer service

See: [Sage CRM](https://help.openconnectors.ext.hana.ondemand.com/home/sagecrm)

</td>
</tr>
<tr>
<td valign="top">

*Sage Intacct V3* 

</td>
<td valign="top">

Provides generic or open functions that can operate on multiple types of accounting objects

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Files* 

</td>
<td valign="top">

Manage, share, store, and collaborate on files,connect to external file systems

See: [Salesforce Files](https://help.openconnectors.ext.hana.ondemand.com/home/sfdcdocuments)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Libraries* 

</td>
<td valign="top">

Store, share, and manage your files with content libraries

See: [Salesforce Libraries](https://help.openconnectors.ext.hana.ondemand.com/home/sfdclibraries)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Marketing Cloud* 

</td>
<td valign="top">

Digital marketing automation and analytics software and services

See: [Salesforce Marketing Cloud](https://help.openconnectors.ext.hana.ondemand.com/home/salesforcemarketingcloud)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Sales Cloud* 

</td>
<td valign="top">

Sales module to improve business growth by connecting data across sales, service, marketing, and B2B commerce

See: [Salesforce Sales Cloud](https://help.openconnectors.ext.hana.ondemand.com/home/sfdc)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Service Cloud* 

</td>
<td valign="top">

Customer service module to improve customer success

See: [Salesforce Service Cloud](https://help.openconnectors.ext.hana.ondemand.com/home/sfdcservicecloud)

</td>
</tr>
<tr>
<td valign="top">

*SalesLoft* 

</td>
<td valign="top">

Sales engagement platform to build stronger relationships, have better insight into customer needs

See: [SalesLoft](https://help.openconnectors.ext.hana.ondemand.com/home/salesloft)

</td>
</tr>
<tr>
<td valign="top">

*SendGrid* 

</td>
<td valign="top">

Cloud-based email delivery service

See: [SendGrid](https://help.openconnectors.ext.hana.ondemand.com/home/sendgrid)

</td>
</tr>
<tr>
<td valign="top">

*Sendoso* 

</td>
<td valign="top">

The leading Sending Platform for sourcing, storing, shipping, and measuring ROI

See: [Sendoso](https://help.openconnectors.ext.hana.ondemand.com/home/sendoso)

</td>
</tr>
<tr>
<td valign="top">

*ServiceMax* 

</td>
<td valign="top">

Leading provider of mobile, cloud-based Service Execution solutions, a new software category that includes Field Service Management

See: [ServiceMax](https://help.openconnectors.ext.hana.ondemand.com/home/servicemax)

</td>
</tr>
<tr>
<td valign="top">

*ServiceNow* 

</td>
<td valign="top">

Digital workflows for enterprise businesses

See: [ServiceNow](https://help.openconnectors.ext.hana.ondemand.com/home/servicenow)

</td>
</tr>
<tr>
<td valign="top">

*ServiceNow OAuth* 

</td>
<td valign="top">

Digital workflows for enterprise businesses

See: [ServiceNow OAuth](https://help.openconnectors.ext.hana.ondemand.com/home/servicenowoauth)

</td>
</tr>
<tr>
<td valign="top">

*SFTP Element* 

</td>
<td valign="top">

Provides file access, file transfer, and file management from your cloud service

See: [SFTP Element](https://help.openconnectors.ext.hana.ondemand.com/home/sftp)

</td>
</tr>
<tr>
<td valign="top">

*Sharepoint* 

</td>
<td valign="top">

Web-based collaborative platform that integrates with Microsoft Office

See: [Sharepoint](https://help.openconnectors.ext.hana.ondemand.com/home/sharepoint)

</td>
</tr>
<tr>
<td valign="top">

*Shopify* 

</td>
<td valign="top">

Complete eCommerce platform to simplify the process of running an online store

See: [Shopify](https://help.openconnectors.ext.hana.ondemand.com/home/shopify)

</td>
</tr>
<tr>
<td valign="top">

*Slack* 

</td>
<td valign="top">

Real time messaging, file sharing and powerful search

See: [Slack](https://help.openconnectors.ext.hana.ondemand.com/home/slack)

</td>
</tr>
<tr>
<td valign="top">

*SmartRecruiters* 

</td>
<td valign="top">

Recruitment software and applicant tracking system

See: [SmartRecruiters](https://help.openconnectors.ext.hana.ondemand.com/home/smartrecruiters)

</td>
</tr>
<tr>
<td valign="top">

*Snowflake* 

</td>
<td valign="top">

Data warehouse built for the cloud for all your data and all your users

See: [Snowflake](https://help.openconnectors.ext.hana.ondemand.com/home/snowflake)

</td>
</tr>
<tr>
<td valign="top">

*Square* 

</td>
<td valign="top">

Credit card processing system and Point of Sale system

See: [Square](https://help.openconnectors.ext.hana.ondemand.com/home/square)

</td>
</tr>
<tr>
<td valign="top">

*Stripe* 

</td>
<td valign="top">

API Driven credit card processing with token based identity

See: [Stripe](https://help.openconnectors.ext.hana.ondemand.com/home/stripe)

</td>
</tr>
<tr>
<td valign="top">

*Sugar Enterprise* 

</td>
<td valign="top">

The industry’s most flexible option for highly-tailored, on-premise Customer Experience applications

See: [Sugar Enterprise](https://help.openconnectors.ext.hana.ondemand.com/home/sugarenterprise)

</td>
</tr>
<tr>
<td valign="top">

*Sugar Market* 

</td>
<td valign="top">

A flagship marketing automation solution from SugarCRM

See: [Sugar Market](https://help.openconnectors.ext.hana.ondemand.com/home/sugarmarket)

</td>
</tr>
<tr>
<td valign="top">

*Sugar Professional* 

</td>
<td valign="top">

On-premise Customer Experience solution designed to meet the needs of fast-growing small businesses

See: [Sugar Professional](https://help.openconnectors.ext.hana.ondemand.com/home/sugarprofessional)

</td>
</tr>
<tr>
<td valign="top">

*Sugar Sell* 

</td>
<td valign="top">

Create more meaningful experiences and build lasting relationships

See: [Sugar Sell](https://help.openconnectors.ext.hana.ondemand.com/home/sugarsell)

</td>
</tr>
<tr>
<td valign="top">

*Sugar Serve* 

</td>
<td valign="top">

Add a Sugar serve Instance to connect your existing Sugar serve account

See: [Sugar Serve](https://help.openconnectors.ext.hana.ondemand.com/home/sugarserve)

</td>
</tr>
<tr>
<td valign="top">

*SugarCRM* 

</td>
<td valign="top">

CRM software with a simple user interface, industry-leading customer experience

See: [SugarCRM](https://help.openconnectors.ext.hana.ondemand.com/home/sugarcrmv2)

</td>
</tr>
<tr>
<td valign="top">

*Syncplicity* 

</td>
<td valign="top">

Enterprise file sharing and content collaboration that helps companies build a digital workplace

See: [Syncplicity](https://help.openconnectors.ext.hana.ondemand.com/home/syncplicity)

</td>
</tr>
<tr>
<td valign="top">

*Taleo Business Edition* 

</td>
<td valign="top">

Human capital cloud service software

See: [Taleo Business Edition](https://help.openconnectors.ext.hana.ondemand.com/home/taleobusiness)

</td>
</tr>
<tr>
<td valign="top">

*Tango Card* 

</td>
<td valign="top">

Rewards provider with E-Gift card rewards and incentives for the global enterprise

See: [Tango Card](https://help.openconnectors.ext.hana.ondemand.com/home/tangocard)

</td>
</tr>
<tr>
<td valign="top">

*Terminus* 

</td>
<td valign="top">

Business to business account-based marketing platform

See: [Terminus](https://help.openconnectors.ext.hana.ondemand.com/home/terminus)

</td>
</tr>
<tr>
<td valign="top">

*Twilio* 

</td>
<td valign="top">

Communication APIs for SMS, Voice, Video and Authentication

See: [Twilio](https://help.openconnectors.ext.hana.ondemand.com/home/twiliov2)

</td>
</tr>
<tr>
<td valign="top">

*Twilio SMS* 

</td>
<td valign="top">

Messaging API for SMS for communication

See: [Twilio SMS](https://help.openconnectors.ext.hana.ondemand.com/home/twilio)

</td>
</tr>
<tr>
<td valign="top">

*Twitter* 

</td>
<td valign="top">

Microblogging and social networking service on which users post and interact with messages

See: [Twitter](https://help.openconnectors.ext.hana.ondemand.com/home/twitter)

</td>
</tr>
<tr>
<td valign="top">

*Ultimate Ultipro* 

</td>
<td valign="top">

One comprehensive cloud solution that delivers business benefits for your organization

</td>
</tr>
<tr>
<td valign="top">

*Volusion* 

</td>
<td valign="top">

Ecommerce website store and shopping cart software

See: [Volusion](https://help.openconnectors.ext.hana.ondemand.com/home/volusion)

</td>
</tr>
<tr>
<td valign="top">

*Weebly* 

</td>
<td valign="top">

Website builder and eCommerce tools from Square

See: [Weebly](https://help.openconnectors.ext.hana.ondemand.com/home/weebly)

</td>
</tr>
<tr>
<td valign="top">

*WooCommerce* 

</td>
<td valign="top">

An eCommerce plugin to sell products and services in WordPress

See: [WooCommerce](https://help.openconnectors.ext.hana.ondemand.com/home/woocommercerest)

</td>
</tr>
<tr>
<td valign="top">

*Workday* 

</td>
<td valign="top">

Cloud ERP system for finance, HR, and planning

See: [Workday](https://help.openconnectors.ext.hana.ondemand.com/home/workday)

</td>
</tr>
<tr>
<td valign="top">

*Wufoo* 

</td>
<td valign="top">

Online form builder with cloud storage database

See: [Wufoo](https://help.openconnectors.ext.hana.ondemand.com/home/wufoo)

</td>
</tr>
<tr>
<td valign="top">

*Zendesk* 

</td>
<td valign="top">

Customer service software and support ticket system

See: [Zendesk](https://help.openconnectors.ext.hana.ondemand.com/home/zendesk)

</td>
</tr>
<tr>
<td valign="top">

*Zoho Crm* 

</td>
<td valign="top">

On-demand SaaS-based customer relationship management \(version 2\)

See: [Zoho Crm](https://help.openconnectors.ext.hana.ondemand.com/home/zohocrmv2)

</td>
</tr>
<tr>
<td valign="top">

*Zuora v2* 

</td>
<td valign="top">

Launch, manage, and transform a cloud-based subscription business \(version 2\)

See: [Zuora v2](https://help.openconnectors.ext.hana.ondemand.com/home/zuorav2)

</td>
</tr>
</table>



<a name="loio93d82e8ff860450da10ad2c16bf5e971__section_z2k_rvq_5sb"/>

## Adapter Development Kit

The Adapter Development Kit \(ADK\) enables you to develop your own custom adapters.

You can use custom adapters when designing integration flows using the Cloud Integration *Design* application.

More information: [Developing Custom Adapters](50-Development/developing-custom-adapters-7392cc4.md)

