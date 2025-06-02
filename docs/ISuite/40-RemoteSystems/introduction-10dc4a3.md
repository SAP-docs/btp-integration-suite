<!-- loio10dc4a3c52fc40eab7b6257a96bc75ab -->

# Introduction

You can connect various kinds of remote systems to the cloud-based integration platform using protocols such as HTTP/S, SSH and SMTP/S. Each communication protocol comes with certain options to protect the message exchange \(security options\).



## Kind of Systems to Connect to Cloud Integration

To give you an idea of which **kinds of remote systems** can be connected to the integration platform, here are some typical examples \(this is not a complete list\):

-   On-premise systems, for example, SAP systems based on SAP NetWeaver

-   SFTP servers

-   Cloud applications, for example, SAP SuccessFactors or SAP Cloud for Customer

-   Other systems such as e-mail servers or SOAP clients


Depending on the kind of system to connect, a certain communication **protocol** is to be considered, as will be explained in the next section.

To support dedicated kinds of systems \(through dedicated communication protocols\), the integration platform provides certain **adapters**. An adapter allows you to configure the details of the technical communication channel between the remote system and the integration platform.



## Supported Protocols

First task when setting up an integration scenario is to set up a secure transport channel between the remote system and Cloud Integration. The following protocols can be used: Hypertext Transfer Protocol Secure \(HTTPS\), SSH File Transfer Protocol \(SFTP\) and Simple Mail Transfer Protocol \(SMTP\), respectively SMTP secured with transport layer security \(SMTPS\).

> ### Note:  
> Note that HTTPS is based on the Transport Layer Security \(TLS\) protocol.

The following table provides more information on the different aspects to consider for each protocol.

**Protocols**


<table>
<tr>
<th valign="top">

Protocol

</th>
<th valign="top">

Call Direction

</th>
<th valign="top">

On Premise \(Mandatory\)

</th>
<th valign="top">

On Premise \(Recommended\)

</th>
<th valign="top">

Further Aspects to Consider

</th>
</tr>
<tr>
<td valign="top">

HTTP, HTTPS

</td>
<td valign="top">

Inbound

</td>
<td valign="top">

HTTP/S sender system \(for example, SAP ERP Central Component

</td>
<td valign="top">

HTTP/S proxy

</td>
<td valign="top">

Firewall to set up and configure

</td>
</tr>
<tr>
<td valign="top">

HTTP, HTTPS

</td>
<td valign="top">

Outbound

</td>
<td valign="top">

HTTP/S receiver system \(for example, SAP ERP Central Component

</td>
<td valign="top">

Web Dispatcher **OR** SAP Cloud Connector

</td>
<td valign="top">

Firewall to set up and configure

</td>
</tr>
<tr>
<td valign="top">

SSH

</td>
<td valign="top">

Outbound

</td>
<td valign="top">

SFTP server \(to store files\)

</td>
<td valign="top">

Tooling for ssh key managment

</td>
<td valign="top">

Virus scanner on inbound directory

</td>
</tr>
<tr>
<td valign="top">

SMTP, SMTPS

</td>
<td valign="top">

Outbound

</td>
<td valign="top">

Mail server

</td>
<td valign="top">

SMTPS \(SMTP over SSL/TLS\) support of mail server

</td>
<td valign="top">

Virus scanner on inbound mail boxes

</td>
</tr>
</table>

For each protocol, different authentication options are supported - ways how the connected systems prove their trustworthiness against each other during connection setup. Connection setup is performed differently, depending on whether inbound communication \(when a remote system as a sender calls Cloud Integration\) or outbound communication \(when Cloud Integration calls a remote system which, in turn, is then considered as the receiver\) is configured. The detailed procedure also depends on the chosen protocol and authentication option.

> ### Note:  
> Basic authentication is recommended for test purposes only. For productive scenarios, we recommend that you use *certificate-based authentication*.



## Adapters

The following figure illustrates some options for kinds of systems to connect to Cloud Integration. Both communication directions are considered: systems sending messages to Cloud Integration and systems that receive messages from Cloud Integration. The figure also shows which communication protocols and the Cloud Integration adapters that are to be configured in order to enable Cloud Integration to connect to the respective kind of system. Note that the figure only shows some typical use cases and is not complete.

> ### Note:  
> Adapters exchange data with remote components that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

The following table lists the available adapters:

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

See: [Configure the Advanced Event Mesh Sender Adapter](../50-Development/configure-the-advanced-event-mesh-sender-adapter-abd2efc.md)

</td>
</tr>
<tr>
<td valign="top">

*AdvancedEventMesh* 

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to send messages to queues or topics in SAP Integration Suite, advanced event mesh.

See: [Configure the Advanced Event Mesh Receiver Adapter](../50-Development/configure-the-advanced-event-mesh-receiver-adapter-881f656.md)

</td>
</tr>
<tr>
<td valign="top">

*Amazon DynamoDB* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Amazon DynamoDB.

See: [Amazon DynamoDB Receiver Adapter](../50-Development/amazon-dynamodb-receiver-adapter-36620d5.md)

</td>
</tr>
<tr>
<td valign="top">

*Amazon EventBridge*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Amazon EventBridge.

See: [Amazon EventBridge Receiver Adapter](../50-Development/amazon-eventbridge-receiver-adapter-ff3f9ed.md)

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


See: [AmazonWebServices Sender Adapter](../50-Development/amazonwebservices-sender-adapter-16772e3.md)

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


See: [AmazonWebServices Receiver Adapter](../50-Development/amazonwebservices-receiver-adapter-bc7d1aa.md)

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

See: [Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md)

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

See: [Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

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

See: [AMQP Sender for SAP Event Mesh](../50-Development/amqp-sender-for-sap-event-mesh-7d8a83f.md)

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

See: [AMQP Receiver for SAP Event Mesh](../50-Development/amqp-receiver-for-sap-event-mesh-0b7cc2f.md)

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

See: [AMQ Sender for SAP Integration Suite, advanced event mesh](../50-Development/amq-sender-for-sap-integration-suite-advanced-event-mesh-be1e496.md)

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

See: [AMQP Receiver for SAP Integration Suite, advanced event mesh](../50-Development/amqp-receiver-for-sap-integration-suite-advanced-event-mesh-5f229c0.md)

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

See: [Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md)

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

See: [Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

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

See: [Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md)

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

See: [Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

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

See: [Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md)

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

See: [Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

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

See: [Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md)

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

See: [Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

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

See: [Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md)

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

See: [Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md)

</td>
</tr>
<tr>
<td valign="top">

*Anaplan*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Anaplan.

See: [Anaplan Receiver Adapter](../50-Development/anaplan-receiver-adapter-364ab57.md)

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

See: [Configure the Ariba Sender Adapter](../50-Development/configure-the-ariba-sender-adapter-0629b58.md)

</td>
</tr>
<tr>
<td valign="top">

*Ariba*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to the Ariba network. Using this adapter, SAP and non-SAP cloud applications can send business-specific documents in commerce eXtensible Markup Language \(cXML\) format to the Ariba network.Receiver adapter

See: [Configure the Ariba Receiver Adapter](../50-Development/configure-the-ariba-receiver-adapter-49dffa3.md)

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

See: [Configure the AS2 Sender Adapter](../50-Development/configure-the-as2-sender-adapter-5d7ee17.md)

</td>
</tr>
<tr>
<td valign="top">

*AS2*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to exchange business-specific documents with a partner through the Applicability Statement 2 \(AS2\) protocol.

See: [Configure the AS2 Receiver Adapter](../50-Development/configure-the-as2-receiver-adapter-9db62be.md)

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


See: [AS4 Sender Adapter](../50-Development/as4-sender-adapter-a448605.md)

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


See: [AS4 Receiver Adapter](../50-Development/as4-receiver-adapter-3a2fde8.md)

</td>
</tr>
<tr>
<td valign="top">

*AzureStorage*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive files from Azure Storage.

See: [Configure the AzureStorage Sender Adapter](../50-Development/configure-the-azurestorage-sender-adapter-d42134a.md)

</td>
</tr>
<tr>
<td valign="top">

*AzureStorage*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to Azure Storage, to manage files, containers, folders, and messages, and to perform *create, read, update and delete* \(CRUD\) operations on objects stored there.

See: [Configure the AzureStorage Receiver Adapter](../50-Development/configure-the-azurestorage-receiver-adapter-30f59b0.md)

</td>
</tr>
<tr>
<td valign="top">

*Azure CosmosDB*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to exchange data with Microsoft Azure CosmosDB. Azure CosmosDB database is a platform as a service and a cloud-based NoSQL database by Azure.

See: [Azure Cosmos DB Receiver Adapter](../50-Development/azure-cosmos-db-receiver-adapter-aa8222e.md)

</td>
</tr>
<tr>
<td valign="top">

*Coupa*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to exchange data with Coupa. Coupa is a business spending management software.

See: [Coupa Receiver Adapter](../50-Development/coupa-receiver-adapter-648ac01.md)

</td>
</tr>
<tr>
<td valign="top">

*Data Store*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from a data store.

See: [Data Store Sender Adapter](../50-Development/data-store-sender-adapter-4f5ef3f.md)

</td>
</tr>
<tr>
<td valign="top">

*Dropbox*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive files from the Dropbox storage.

See: [Configure the Dropbox Sender Adapter](../50-Development/configure-the-dropbox-sender-adapter-de61991.md)

</td>
</tr>
<tr>
<td valign="top">

*Dropbox*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to write files and folders to the Dropbox storage.

See: [Configure the Dropbox Receiver Adapter](../50-Development/configure-the-dropbox-receiver-adapter-16ef7b4.md)

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

See: [ELSTER Receiver Adapter](../50-Development/elster-receiver-adapter-e374ef7.md)

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

See: [Facebook Receiver Adapter](../50-Development/facebook-receiver-adapter-3dcc408.md)

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

See: [Configure the FTP Sender Adapter](../50-Development/configure-the-ftp-sender-adapter-239042f.md)

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

See: [Configure the FTP Receiver Adapter](../50-Development/configure-the-ftp-receiver-adapter-c16d331.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Cloud Storage* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to read from different storage entities in Google Cloud Storage.

See: [Configure the Google Cloud Storage Sender Adapter](../50-Development/configure-the-google-cloud-storage-sender-adapter-ec213ce.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Cloud Storage* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to access and manage different storage entities in Google Cloud Storage.

See: [Configure the Google Cloud Storage Receiver Adapter](../50-Development/configure-the-google-cloud-storage-receiver-adapter-5a8ddef.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Pub/Sub* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Google Pub/Sub.

See: [Configure the Google Pub/Sub Sender Adapter](../50-Development/configure-the-google-pub-sub-sender-adapter-845ec21.md)

</td>
</tr>
<tr>
<td valign="top">

*Google Pub/Sub* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to publish messages to Google Pub/Sub.

See: [Configure the Google Pub/Sub Receiver Adapter](../50-Development/configure-the-google-pub-sub-receiver-adapter-30df22d.md)

</td>
</tr>
<tr>
<td valign="top">

*HTTPS*

Sender adapter

</td>
<td valign="top">

Establishes an HTTPS connection between SAP Integration Suite and a sender system.

See: [HTTPS Sender Adapter](../50-Development/https-sender-adapter-0ae4a78.md)

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


See: [HTTP Receiver Adapter](../50-Development/http-receiver-adapter-2da452e.md)

</td>
</tr>
<tr>
<td valign="top">

*HubSpot*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to HubSpot.

See: [HubSpot Receiver Adapter](../50-Development/hubspot-receiver-adapter-48cfaa8.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ \(REST\)*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to consume messages from IBM MQ using the REST message protocol.

See: [Configure the IBM MQ \(REST\) Sender Adapter](../50-Development/configure-the-ibm-mq-rest-sender-adapter-35cd02d.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ \(REST\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to publish messages to IBM MQ using the REST message protocol.

See: [Configure the IBM MQ \(REST\) Receiver Adapter](../50-Development/configure-the-ibm-mq-rest-receiver-adapter-45610e7.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ JMS*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to consume messages from IBM MQ via JMS message protocol.

See: [Configure the IBM MQ JMS Sender Adapter](../50-Development/configure-the-ibm-mq-jms-sender-adapter-d655ab4.md)

</td>
</tr>
<tr>
<td valign="top">

*IBM MQ JMS*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to publish messages to IBM MQ via JMS message protocol.

See: [Configure the IBM MQ JMS Receiver Adapter](../50-Development/configure-the-ibm-mq-jms-receiver-adapter-029bc1b.md)

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

See: [Configure the IDoc Sender Adapter](../50-Development/configure-the-idoc-sender-adapter-bf769d6.md)

</td>
</tr>
<tr>
<td valign="top">

*IDoc*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to exchange Intermediate Document \(IDoc\) messages with a receiver system that supports communication via SOAP Web services.

See: [Configure the IDoc Receiver Adapter](../50-Development/configure-the-idoc-receiver-adapter-018aa88.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to a JDBC \(Java Database Connectivity\) database and to execute SQL commands on the database.

See: [JDBC Receiver Adapter](../50-Development/jdbc-receiver-adapter-88be644.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for DB2 \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to DB2 \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for DB2 \(On-Premise\)](../50-Development/jdbc-for-db2-on-premise-9515cf8.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Microsoft SQL Server \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Microsoft SQL Server \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Microsoft SQL Server \(Cloud\)](../50-Development/jdbc-for-microsoft-sql-server-cloud-4173d0a.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Microsoft SQL Server \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Microsoft SQL Server \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Microsoft SQL Server \(On-Premise\)](../50-Development/jdbc-for-microsoft-sql-server-on-premise-9745e40.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Oracle \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Oracle \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Oracle \(Cloud\)](../50-Development/jdbc-for-oracle-cloud-f868182.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for Oracle \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to Oracle \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for Oracle \(On-Premise\)](../50-Development/jdbc-for-oracle-on-premise-e6db38a.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for PostgreSQL \(Cloud\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to PostgreSQL \(Cloud\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for PostgreSQL \(Cloud\)](../50-Development/jdbc-for-postgresql-cloud-4d5b488.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP HANA Cloud*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to SAP HANA Cloud using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP HANA \(Cloud\)](../50-Development/jdbc-for-sap-hana-cloud-187a8e8.md)

</td>
</tr>
<tr>
<td valign="top">

*JDBC for SAP HANA Platform \(On-Premise\)*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to SAP HANA Platform \(On-Premise\) using JDBC \(Java Database Connectivity\) and to execute SQL commands on the database.

See: [JDBC for SAP HANA Platform \(On-Premise\)](../50-Development/jdbc-for-sap-hana-platform-on-premise-ff29388.md)

</td>
</tr>
<tr>
<td valign="top">

*Jira*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to Jira.

See: [Jira Receiver Adapter](../50-Development/jira-receiver-adapter-d15b560.md)

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

See: [Configure the JMS Sender Adapter](../50-Development/configure-the-jms-sender-adapter-161791b.md)

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

See: [Configure the JMS Receiver Adapter](../50-Development/configure-the-jms-receiver-adapter-79edc04.md)

</td>
</tr>
<tr>
<td valign="top">

*Kafka*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to an external Kafka broker via Kafka protocol and to fetch Kafka records \(messages\).

See: [Configure the Kafka Sender Adapter](../50-Development/configure-the-kafka-sender-adapter-0d849e5.md)

</td>
</tr>
<tr>
<td valign="top">

*Kafka*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to connect to an external Kafka broker via Kafka protocol and to send Kafka records \(messages\).

See: [Configure the Kafka Receiver Adapter](../50-Development/configure-the-kafka-receiver-adapter-fc6ee1f.md)

</td>
</tr>
<tr>
<td valign="top">

*LeanIX*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to connect to SAP LeanIX.

See: [LeanIX Receiver Adapter](../50-Development/leanix-receiver-adapter-e49c1de.md)

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

See: [Mail Sender for IMAP](../50-Development/mail-sender-for-imap-5b94e42.md)

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

See: [Mail Sender for POP3](../50-Development/mail-sender-for-pop3-c52a4da.md)

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


See: [Configure the Mail Receiver Adapter](../50-Development/configure-the-mail-receiver-adapter-f68d5e0.md)

</td>
</tr>
<tr>
<td valign="top">

*MDI* 

Receiver adapter

</td>
<td valign="top">

The MDI \(SAP Master Data Integration\) adapter synchronizes your master data from SAP applications like SAP ECC and other third party applications with SAP MDI service.

See: [SAP Master Data Integration Receiver Adapter](../50-Development/sap-master-data-integration-receiver-adapter-e91e373.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Dynamics CRM* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Microsoft Dynamics Customer Relationship Management \(CRM\).

See: [Microsoft Dynamics CRM Receiver Adapter](../50-Development/microsoft-dynamics-crm-receiver-adapter-ee724c8.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft OneDrive* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using HTTP protocol.

See: [Configure the Microsoft OneDrive Sender Adapter](../50-Development/configure-the-microsoft-onedrive-sender-adapter-0724136.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft OneDrive* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using HTTP protocol.

See: [Configure the Microsoft OneDrive Receiver Adapter](../50-Development/configure-the-microsoft-onedrive-receiver-adapter-4158749.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft SharePoint* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using the HTTP/HTTPS protocol to read files from the system.

See: [Configure the Microsoft SharePoint Sender Adapter](../50-Development/configure-the-microsoft-sharepoint-sender-adapter-ce41e85.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft SharePoint* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote system using the HTTP protocol to write files to the system.

See: [Configure the Microsoft SharePoint Receiver Adapter](../50-Development/configure-the-microsoft-sharepoint-receiver-adapter-b12b33a.md)

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Teams* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Microsoft Teams.

See: [Microsoft Teams Receiver Adapter](../50-Development/microsoft-teams-receiver-adapter-1f333c3.md)

</td>
</tr>
<tr>
<td valign="top">

*NetSuite* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to NetSuite.

See: [NetSuite Receiver Adapter](../50-Development/netsuite-receiver-adapter-618127a.md)

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


See: [Configure the OData Sender Adapter](../50-Development/configure-the-odata-sender-adapter-de7aee5.md)

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

-   [Configure the OData V2 Receiver Adapter](../50-Development/configure-the-odata-v2-receiver-adapter-c5c2e38.md)

-   [Configure the OData V4 Receiver Adapter](../50-Development/configure-the-odata-v4-receiver-adapter-cd66a12.md)




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

See: [ODC Receiver Adapter](../50-Development/odc-receiver-adapter-3cdbc29.md)

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


See: [OpenConnectors Receiver Adapter](../50-Development/openconnectors-receiver-adapter-1a27cee.md)

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

See: [Configure the ProcessDirect Sender Adapter](../50-Development/configure-the-processdirect-sender-adapter-e340d4c.md)

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

See: [Configure the ProcessDirect Receiver Adapter](../50-Development/configure-the-processdirect-receiver-adapter-5b7327d.md)

</td>
</tr>
<tr>
<td valign="top">

*RabbitMQ*

Sender adapter

</td>
<td valign="top">

Allows SAP Integration Suite to consume messages from the RabbitMQ server. In addition, you use the adapter to send acknowledgements to the RabbitMQ server.

See: [Configure the RabbitMQ Sender Adapter](../50-Development/configure-the-rabbitmq-sender-adapter-4e3c554.md)

</td>
</tr>
<tr>
<td valign="top">

*RabbitMQ*

Receiver adapter

</td>
<td valign="top">

Allows SAP Integration Suite to send messages to the RabbitMQ server.

See: [Configure the RabbitMQ Receiver Adapter](../50-Development/configure-the-rabbitmq-receiver-adapter-e9dfc37.md)

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

See: [RFC Receiver Adapter](../50-Development/rfc-receiver-adapter-5c76048.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce* 

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Salesforce.

See: [Salesforce Sender Adapter](../50-Development/salesforce-sender-adapter-ba6420d.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Salesforce.

See: [Salesforce Receiver Adapter](../50-Development/salesforce-receiver-adapter-a548be9.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Pub/Sub* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to consume messages from Salesforce Pub/Sub API.

See: [Configure the Salesforce Pub/Sub Sender Adapter](../50-Development/configure-the-salesforce-pub-sub-sender-adapter-fdb114c.md)

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Pub/Sub* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to publish messages to Salesforce Pub/Sub API.

See: [Configure the Salesforce Pub/Sub Receiver Adapter](../50-Development/configure-the-salesforce-pub-sub-receiver-adapter-6862ff5.md)

</td>
</tr>
<tr>
<td valign="top">

*ServiceNow* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to ServiceNow. Supports basic authentication and OAuth.

See: [ServiceNow Receiver Adapter](../50-Development/servicenow-receiver-adapter-1e3bcf4.md)

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

See: [Configure the SFTP Sender Adapter](../50-Development/configure-the-sftp-sender-adapter-2de9ee5.md)

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

See: [Configure the SFTP Receiver Adapter](../50-Development/configure-the-sftp-receiver-adapter-4ef52cf.md)

</td>
</tr>
<tr>
<td valign="top">

*Slack*

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive search-related information from the Slack storage.

See: [Configure the Slack Sender Adapter](../50-Development/configure-the-slack-sender-adapter-1d93850.md)

</td>
</tr>
<tr>
<td valign="top">

*Slack*

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to get data from the Slack storage or to create, modify, or delete data on the Slack storage.

See: [Configure the Slack Receiver Adapter](../50-Development/configure-the-slack-receiver-adapter-7c2ea64.md)

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

See: [Configure the SMB Sender Adapter](../50-Development/configure-the-smb-sender-adapter-95bf6e9.md)

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

See: [Configure the SMB Receiver Adapter](../50-Development/configure-the-smb-receiver-adapter-ddd0d59.md)

</td>
</tr>
<tr>
<td valign="top">

*Snowflake* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Snowflake. Snowflake is a cloud computing-based data company that provides cloud-based data storage and analytics services.

See: [Snowflake Receiver Adapter](../50-Development/snowflake-receiver-adapter-1299e68.md)

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

See: [Configure the SOAP \(SOAP 1.x\) Sender Adapter](../50-Development/configure-the-soap-soap-1-x-sender-adapter-a178913.md)

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

See: [Configure the SOAP \(SOAP 1.x\) Receiver Adapter](../50-Development/configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md)

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

See: [Configure the SOAP \(SAP RM\) Sender Adapter](../50-Development/configure-the-soap-sap-rm-sender-adapter-6962234.md)

</td>
</tr>
<tr>
<td valign="top">

*SOAP SAP RM* 

Receiver adapter

</td>
<td valign="top">

Exchanges messages with a receiver system based on the SOAP communication protocol and SAP Reliable Messaging \(SAP RM\) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards.

See: [Configure the SOAP \(SAP RM\) Receiver Adapter](../50-Development/configure-the-soap-sap-rm-receiver-adapter-8366495.md)

</td>
</tr>
<tr>
<td valign="top">

*Splunk* 

Sender adapter

</td>
<td valign="top">

Enables SAP Integration Suite to receive search-related information from the Splunk storage.

See: [Configure the Splunk Sender Adapter](../50-Development/configure-the-splunk-sender-adapter-271ad20.md)

</td>
</tr>
<tr>
<td valign="top">

*Splunk* 

Receiver adapter

</td>
<td valign="top">

Enables SAP Integration Suite to get data from the Splunk storage or to create, modify, or delete data on the Splunk storage.

See: [Configure the Splunk Receiver Adapter](../50-Development/configure-the-splunk-receiver-adapter-e8e6ba6.md)

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

See: [Configure the SuccessFactors REST Sender Adapter](../50-Development/configure-the-successfactors-rest-sender-adapter-9f0646b.md)

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

See: [Configure the SuccessFactors REST Receiver Adapter](../50-Development/configure-the-successfactors-rest-receiver-adapter-9cff562.md)

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

See: [Configure the SuccessFactors \(SOAP\) Sender Adapter](../50-Development/configure-the-successfactors-soap-sender-adapter-874e4b1.md)

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

See: [Configure the SuccessFactors SOAP Receiver Adapter](../50-Development/configure-the-successfactors-soap-receiver-adapter-360ef42.md)

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

See: [Configure the SuccessFactors OData V2 Receiver Adapter](../50-Development/configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md)

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


See: [SuccessFactors OData V4 Receiver Adapter](../50-Development/successfactors-odata-v4-receiver-adapter-cd091fc.md)

</td>
</tr>
<tr>
<td valign="top">

*SugarCRM* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to SugarCRM.

See: [SugarCRM Receiver Adapter](../50-Development/sugarcrm-receiver-adapter-d96ddf7.md)

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

See: [Twitter Receiver Adapter](../50-Development/twitter-receiver-adapter-453c174.md)

</td>
</tr>
<tr>
<td valign="top">

*Workday* 

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to Workday. Supports Workday SOAP API with basic authentication.

See: [Workday Receiver Adapter](../50-Development/workday-receiver-adapter-0c6e670.md)

</td>
</tr>
<tr>
<td valign="top">

*XI*

Sender adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote sender system that can process the XI message protocol.

See: [Configure the XI Sender Adapter](../50-Development/configure-the-xi-sender-adapter-41a1a57.md)

</td>
</tr>
<tr>
<td valign="top">

*XI*

Receiver adapter

</td>
<td valign="top">

Connects SAP Integration Suite to a remote receiver system that can process the XI message protocol.

See: [Configure the XI Receiver Adapter](../50-Development/configure-the-xi-receiver-adapter-5d2670f.md)

</td>
</tr>
</table>

As well as the *transport-level security* options, you can also secure the communication at *message level*. This protects the content of the exchanged messages by means of digital encryption and signatures. Various security standards are available to do this: PKCS\#7, XML Digital Signature, OpenPGP, and WS-Security.

**Related Information**  


[Connectivity (Adapters)](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/55325f2a722c4f67bb7752b369b09ff8.html "You have the option to specify which technical protocols should be used to connect a sender or a receiver to the tenant.") :arrow_upper_right:

[Operating Model](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/72010e61b1d14d58a568b6475030a6ca.html "An operation model clearly defines the separation of tasks between SAP and the customer during all phases of an integration project.") :arrow_upper_right:

[Connecting to an On-Premise Landscape \(Example Setup\)](connecting-to-an-on-premise-landscape-example-setup-a15af84.md "")

