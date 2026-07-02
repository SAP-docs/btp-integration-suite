<!-- loio9f7cf82866dc43e7a3991582f4ae0ae8 -->

# Adapters Authentication Methods

The following tables provide an overview of sender and receiver adapters along with their authentication methods.

> ### Tip:  
> -   *Availability of Options*
> 
>     Not all authentication options are always available. The available options depend on the authentication methods supported by the server side.
> 
> -   *Transport Level Security \(TLS\)*
> 
>     Regardless of the authentication mechanism, always try to use transport level security \(TLS\) where possible. Some authentication methods must only be used in combination with TLS.
> 
> -   *Client Certificate-Based Authentication*
> 
>     Client certificate-based authentication usually offers the highest level of security but can be more complex to configure. Additionally, certificates have an expiration date and will need to be periodically rotated.
> 
> -   *Recommendations for Production Scenarios*
> 
>     It is highly recommended to configure one of the secure authentication methods. Specifically, avoid using less secure methods like *Basic* or *None* in production environments.

**Sender Adapters**


<table>
<tr>
<th valign="top">

Sender Adapter

</th>
<th valign="top">

Authentication Method

</th>
<th valign="top">

Configuration and More Information

</th>
</tr>
<tr>
<td valign="top">

AdvancedEventMesh

</td>
<td valign="top">

-   Client Certificate
-   OAuth2
-   Basic



</td>
<td valign="top">

[Configure the Advanced Event Mesh Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/abd2efcc810442edaf17a750904d1d3a.html "The AdvancedEventMesh sender adapter allows SAP Integration Suite to consume messages from queues or subscriptions in SAP Integration Suite, advanced event mesh.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AMQP - TCP

</td>
<td valign="top">

-   Client Certificate \(recommended\)
-   SASL\(use only in combination with TLS – Flag “Connect with TLS”\)
-   None



</td>
<td valign="top">

[Configure the AMQP Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/99ce6748400b4dbfbadf633aeb111067.html "You use the Advanced Message Queuing Protocol (AMQP) sender adapter to consume messages in SAP Integration Suite from queues in an external message broker or from the SAP Event Mesh.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AMQP - WebSocket

</td>
<td valign="top">

-   SASL
-   OAuth2 Client Credentials\(use only in combination with TLS – Flag “Connect with TLS”\)
-   None



</td>
<td valign="top">

[Configure the AMQP Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/99ce6748400b4dbfbadf633aeb111067.html "You use the Advanced Message Queuing Protocol (AMQP) sender adapter to consume messages in SAP Integration Suite from queues in an external message broker or from the SAP Event Mesh.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Ariba

</td>
<td valign="top">

-   Client Certificate
-   Shared Key



</td>
<td valign="top">

[Configure the Ariba Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/0629b58d4a764a0b8bcf9aa884503e78.html "The Ariba sender adapter connects SAP Integration Suite to the Ariba Network. Using this adapter, SAP and non-SAP cloud applications can receive business-specific documents in commerce eXtensible Markup Language (cXML) format from the Ariba network. The sender adapter allows you to define a schedule for polling data from Ariba.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AS2

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the AS2 Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/5d7ee17e554841df8ef355413b88e056.html "") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

AS2 MDN

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the AS2 MDN Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/c54effed7f1643979326e6a461899904.html "") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

AS4

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [AS4 Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/a448605c3c5545a9970704778cf4236a.html "You use AS4 message exchange protocol to securely process incoming business documents using Web services.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

AmazonWebServices

</td>
<td valign="top">

AWS access key and secret key

</td>
<td valign="top">

[AmazonWebServices Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/16772e3bd410433b9bb47d9361b03e3c.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AzureStorage

</td>
<td valign="top">

-   SAS Token
-   Shared Access Key



</td>
<td valign="top">

[Configure the AzureStorage Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d42134adf89d47d2a731704d203981e0.html "The AzureStorage sender adapter enables SAP Integration Suite to receive files from Azure Storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Data Store

</td>
<td valign="top">

N.A. as no connection with a remote component

</td>
<td valign="top">

[Data Store Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/4f5ef3f724c2480da421daa7880bb040.html "This adapter enables Cloud Integration to consume messages from a data store. This feature helps you to enable asynchronous decoupling of inbound and outbound processing by using the data store as temporary storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Dropbox

</td>
<td valign="top">

-   OAuth Credentials



</td>
<td valign="top">

[Configure the Dropbox Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/de619914e2a24c53a1253d90b79b814f.html "The Dropbox sender adapter enables SAP Integration Suite to receive files from the Dropbox storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

FTP

</td>
<td valign="top">

-   Explicit FTPS

-   Implicit FTPS

-   Plain FTP \(no encryption\)




</td>
<td valign="top">

[Configure the FTP Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/239042f2328a406a8647b93b937921a3.html "The FTP (File Transfer Protocol) sender adapter connects SAP Integration Suite to a remote system using TCP (Transmission Control Protocol) to receive files from the system.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

HTTPS

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)




</td>
</tr>
<tr>
<td valign="top">

IDoc

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the IDoc Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/bf769d68d95b458d87290dd2d37024b3.html "The IDoc sender adapter enables SAP Integration Suite to receive Intermediate Document (IDoc) messages from a sender.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

JMS

</td>
<td valign="top">

N.A. as no connection with a remote component

</td>
<td valign="top">

[Configure the JMS Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/161791b8cb98485ba00d81efa4197a49.html "The JMS (Java Message Service) sender adapter enables asynchronous decoupling of inbound and outbound processing by using message queues. The sender adapter consumes messages from a JMS queue.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Kafka

</td>
<td valign="top">

-   Client Certificate
-   SASL with SASL Mechanism SCRAM-SHA-256 or -512 \(use only in combination with TLS – Flag “Connect with TLS”\)
-   SASL with SASL Mechanism”PLAIN” \(use only in combination with TLS – Flag “Connect with TLS”\)



</td>
<td valign="top">

[Configure the Kafka Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/0d849e5b2ea749ff890d7e78db2f3a0b.html "You use the Kafka Sender adapter to connect to an external Kafka broker via Kafka protocol and to fetch messages.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Mail - IMAP4

</td>
<td valign="top">

-   Encrypted User/Password \(use only in combination with TLS – “IMAPS” or “STARTTLS mandatory”\)
-   Plain User/Password \(use only in combination with TLS – “IMAPS” or “STARTTLS mandatory”\)
-   OAuth2 Authorization Code \(recommended\)



</td>
<td valign="top">

[Mail Sender for IMAP](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/5b94e4298d70447f92a5ce728d7e25e3.html "You use the mail sender adapter to download e-mails from mailboxes using the Internet Message Access Protocol (IMAP) protocol, to access the content of the e-mail body, and to access e-mail attachments.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Mail - POP3

</td>
<td valign="top">

-   Encrypted User/Password \(use only in combination with TLS – “POP3S” or “STARTTLS mandatory”\)
-   Plain User/Password \(use only in combination with TLS – “POP3S” or “STARTTLS mandatory”\)



</td>
<td valign="top">

[Mail Sender for POP3](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/c52a4da2877f4827b2a2f6bfeb90c670.html "You use the mail sender adapter to download e-mails from mailboxes using the Post Office Protocol (POP3) protocol, to access the content of the e-mail body, and to access e-mail attachments.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Mail - SMTP

</td>
<td valign="top">

-   Mail / SMTP - OAuth2 Authorization Code \(recommended\)
-   Encrypted User/Password \(use only in combination with TLS – “SMTPS” or “STARTTLS mandatory”\)
-   Plain User/Password \(use only in combination with TLS – “SMTPS” or “STARTTLS mandatory”\)



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Microsoft SharePoint

</td>
<td valign="top">

-   OAuth2 Authorization Code

-   OAuth2 Client Credentials




</td>
<td valign="top">

[Configure the Microsoft SharePoint Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ce41e85abcc140dca0b6f638ff5d0cd4.html "The Microsoft SharePoint sender adapter connects an SAP Integration Suite tenant to a remote system using the HTTP/HTTPS protocol to read files from the system.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

OData

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the OData Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/de7aee5160134b74a949ac2b84cb7412.html "") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

ProcessDirect

</td>
<td valign="top">

N.A. as no connection with a remote component

</td>
<td valign="top">

[Configure the ProcessDirect Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e340d4c4bce948d4ba6cc5b4fc24ad45.html "You use the ProcessDirect sender adapter to establish fast and direct communication between integration flows by reducing latency and network overhead provided both of them are available within a same tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

RabbitMQ

</td>
<td valign="top">

-   Client Certificate
-   SASL



</td>
<td valign="top">

[Configure the RabbitMQ Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/4e3c55458ee542d28408ce041ab74831.html "The RabbitMQ sender adapter allows you to consume messages in SAP Integration Suite from queues on the RabbitMQ server. In addition, you use the adapter to send acknowledgements to the RabbitMQ server.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Salesforce

</td>
<td valign="top">

-   OAuth Client Credentials
-   OAuth JWT Bearer



</td>
<td valign="top">

[Salesforce Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ba6420dc38dc4bcc96df1a28ab80af5e.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SFTP

</td>
<td valign="top">

-   Public Key
-   User Name/Password
-   Dual



</td>
<td valign="top">

[Configure the SFTP Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/2de9ee58737247969eb7dc9e68b1b121.html "The SFTP sender adapter connects an SAP Integration Suite tenant to a remote system using the SSH File Transfer protocol to read files from the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol (or SFTP).") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Slack

</td>
<td valign="top">

-   Token



</td>
<td valign="top">

[Configure the Slack Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1d93850b43504c50b87c6c62ef0ffc5a.html "Enables SAP Integration Suite to receive search-related information from the Slack storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SMB

</td>
<td valign="top">

Basic

</td>
<td valign="top">

[Configure the SMB Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/95bf6e9d2f084543a4431e26c075ab76.html "The SMB (Server Message Block) sender adapter connects SAP Integration Suite to a remote share drive using TCP (Transmission Control Protocol) to read files from the server.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SOAP - SAP RM

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the SOAP (SAP RM) Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/69622346a10c4d5086a9b3e4f052337a.html "The SOAP (SAP RM) Sender Adapter exchanges messages with a sender system based on the SOAP communication protocol (1.1. and 1.2) and SAP Reliable Messaging (SAP RM) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards. A size limit for the inbound message can be configured for the sender adapter.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

SOAP - SOAP 1.x

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the SOAP (SOAP 1.x) Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/a178913a4d3245ab9bff2a0edcc331d5.html "The SOAP (SOAP 1.x) sender adapter enables a SAP BTP tenant to exchange messages with a sender system that supports Simple Object Access Protocol (SOAP) 1.1 and 1.2.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Splunk

</td>
<td valign="top">

-   Basic Authentication
-   Splunk Token



</td>
<td valign="top">

[Configure the Splunk Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/271ad20bef0b4bb5a4e0977b1f6a3a11.html "Enables SAP Integration Suite to receive search-related information from the Splunk storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SuccessFactors - REST

</td>
<td valign="top">

-   OAuth2 Client Credentials



</td>
<td valign="top">

[Configure the SuccessFactors REST Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/9f0646b481764b4b890a342c3e14a002.html "The SuccessFactors (REST) sender adapter connects an SAP Cloud Integration tenant to a SuccessFactors sender system using the REST message protocol.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SuccessFactors - SOAP

</td>
<td valign="top">

-   Basic
-   OAuth2 SAML Bearer Assertion



</td>
<td valign="top">

[Configure the SuccessFactors (SOAP) Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/874e4b1e7d754b08a0b9e0b606e18a7f.html "The SuccessFactors (SOAP) sender adapter connects an SAP Cloud Integration tenant to SOAP-based Web Services of a SuccessFactors sender system (synchronous or asynchronous communication).") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Xl

</td>
<td valign="top">

-   Client Certificate \(recommended\)

-   OAuth with Client Credentials Grant \(recommended\)

-   Basic




</td>
<td valign="top">

Sender adapter: Select the *User Role* option for the *Authorization* parameter. SAP Business Technology Platform cockpit: Create a service instance and an associated service key as described at:

-   [Client Certificate Authentication for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7f84d16aa42741efb08dc9875743e47c.html "The sender authenticates itself with a client certificate when calling the integration flow deployed on the worker node. At runtime, the system checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.") :arrow_upper_right:

-   [OAuth with Client Credentials Grant for Integration Flow Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/6c052ce62b27449385d3e75aeeb08f05.html "You can configure OAuth authentication, in particular the Client Credentials Grant variant, for inbound calls from sender systems to the integration platform. That way, the sender (client) application is granted access to the associated worker node through OAuth authentication.") :arrow_upper_right:

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the XI Sender Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/41a1a57bf54644d1bd351ca689cf531d.html "The XI sender adapter allows you to connect a tenant to a local Integration Engine in a sender system.") :arrow_upper_right:

</td>
</tr>
</table>

**Receiver Adapters**


<table>
<tr>
<th valign="top">

Receiver Adapter

</th>
<th valign="top">

Authentication Method

</th>
<th valign="top">

Configuration and More Information

</th>
</tr>
<tr>
<td valign="top">

AdvancedEventMesh

</td>
<td valign="top">

-   Client Certificate
-   OAuth2
-   Basic



</td>
<td valign="top">

[Configure the Advanced Event Mesh Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/881f65686e874cd0a72902c0a937f996.html "The AdvancedEventMesh receiver adapter allows SAP Integration Suite to send messages to queues or topics in SAP Integration Suite, advanced event mesh.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Amazon DynamoDB

</td>
<td valign="top">

Access Key and Secret Key

</td>
<td valign="top">

[Amazon DynamoDB Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/36620d58456d4d409ddc09e8c6722694.html "The Amazon DynamoDB receiver adapter enables you to connect SAP Integration Suite to Amazon DynamoDB.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AmazonEventBridge

</td>
<td valign="top">

Access Key and Secret Key

</td>
<td valign="top">

[Amazon EventBridge Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ff3f9edc07344fa8a497dc4445ef7820.html "The Amazon EventBridge Receiver Adapter connects SAP Integration Suite to Amazon EventBridge. Amazon EventBridge is a serverless service that uses events to connect application components together.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AMQP - TCP

</td>
<td valign="top">

-   Client Certificate
-   SASL
-   None



</td>
<td valign="top">

[Configure the AMQP Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d5660c146a93483692335e9d79a8c58f.html "You use the Advanced Message Queuing Protocol (AMQP) receiver adapter to send messages from SAP Integration Suite to queues or topics in an external message broker.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AMQP - WebSocket

</td>
<td valign="top">

-   SASL
-   None
-   OAuth2 Client Credentials



</td>
<td valign="top">

[Configure the AMQP Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d5660c146a93483692335e9d79a8c58f.html "You use the Advanced Message Queuing Protocol (AMQP) receiver adapter to send messages from SAP Integration Suite to queues or topics in an external message broker.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Anaplan

</td>
<td valign="top">

User Credentials

</td>
<td valign="top">

[Anaplan Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/364ab5763690404babc3be42123d4838.html "The Anaplan receiver adapter connects SAP Integration Suite to Anaplan. Anaplan is a cloud-based platform for business planning and performance management. The Anaplan adapter helps you exchange data between the two systems.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Ariba

</td>
<td valign="top">

-   Client Certificate
-   Shared Key



</td>
<td valign="top">

[Configure the Ariba Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/49dffa3da5784b7bb5dd6d8bf975939c.html "The Ariva receiver adapter connects SAP Integration Suite to the Ariba network. Using this adapter, SAP and non-SAP cloud applications can send business-specific documents in commerce eXtensible Markup Language (cXML) format to the Ariba network.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AS2

</td>
<td valign="top">

-   Client Certificate
-   Dynamic

-   Basic Authentication
-   None



</td>
<td valign="top">

[Configure the AS2 Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/9db62be7f6024c45b36ded818b75e6c8.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AS4

</td>
<td valign="top">

-   Client Certificate
-   SAML Authentication
-   Basic Authentication
-   None



</td>
<td valign="top">

[AS4 Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/3a2fde8f52cf4ac38770eb843d3b3943.html "Provides basic insights on how the AS4 messaging protocol enables message exchange between message service handlers (MSHs).") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AmazonWebServices

</td>
<td valign="top">

Access Key and Secret Key

</td>
<td valign="top">

[AmazonWebServices Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/bc7d1aac1c494af591f8edd5c52bea0f.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

AzureStorage

</td>
<td valign="top">

-   SAS token
-   Shared Access Key



</td>
<td valign="top">

[Configure the AzureStorage Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/30f59b05319e45cf8b2b10c3ca28ca39.html "The AzureStorage receiver adapter enables SAP Integration Suite to write files and folders to Azure Storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Coupa

</td>
<td valign="top">

-   OAuth Client Credentials



</td>
<td valign="top">

[Coupa Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/648ac016b9bc49288c7a86ee7a4a1972.html "The Coupa receiver adapter connects SAP Integration Suite to Coupa. Coupa is a business spending management software. The Coupa adapter helps you exchange data between the two systems.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Dropbox

</td>
<td valign="top">

-   OAuth Credential Name



</td>
<td valign="top">

[Configure the Dropbox Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/16ef7b42f5084db28fd2644a0825ec87.html "The Dropbox receiver adapter enables SAP Integration Suite to write files and folders to the Dropbox storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Elster

</td>
<td valign="top">

Message Signing and Encryption

</td>
<td valign="top">

[ELSTER Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e374ef7fb342413caf55ad6fd50384bb.html "This adapter enables an SAP BTP tenant to send a tax document to the ELSTER server.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Facebook

</td>
<td valign="top">

-   OAuth Access Token



</td>
<td valign="top">

[Facebook Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/3dcc4080897c4bd4bf55bb8bf1bcac0d.html "You use the Facetbook receiver adapter to extract information from Facebook (which is the receiver platform) based on certain criteria such as keywords, user data, for example. As one example, you can use this feature in social marketing activities to do social media data analysis based on Facebook content.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

FTP

</td>
<td valign="top">

-   Explicit FTPS

-   Implicit FTPS

-   Plain FTP \(no encryption\)




</td>
<td valign="top">

[Configure the FTP Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/c16d331e8ebb4a0e8c58af96bf519561.html "The FTP (File Transfer Protocol) receiver adapter connects SAP Integration Suite to a remote system using TCP (Transmission Control Protocol) to write files to the system.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

HTTP

</td>
<td valign="top">

-   Client Certificate
-   OAuth2 Client Credentials
-   OAuth2 SAML Bearer Assertion
-   Principal Propagation
-   Basic
-   None



</td>
<td valign="top">

[HTTP Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/2da452effb764b3bb28f8e0a2f5bd480.html "Use the HTTP receiver adapter to communicate with target systems using HTTP message protocol.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

HubSpot

</td>
<td valign="top">

-   OAuth2 Authorization Code

-   Private App




</td>
<td valign="top">

[HubSpot Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/48cfaa8e109d46489c620c8125e8a1a9.html "The HubSpot Receiver adapter connects SAP Integration Suite to HubSpot. HubSpot is a dynamic platform enabling seamless integration across departments such as marketing, sales, and customer service. The HubSpot adapter helps you exchange data between the two systems.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

IDoc

</td>
<td valign="top">

-   Client Certificate
-   Principal Propagation
-   Basic
-   None



</td>
<td valign="top">

[Configure the IDoc Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/018aa88b6d284ca2b8476b6e6053cfeb.html "The IDoc receiver adapter enables SAP Integration Suite to send Intermediate Document (IDoc) messages to a receiver.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

JDBC

</td>
<td valign="top">

Database User, Password and Access Token

</td>
<td valign="top">

[JDBC Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/88be64412f1b46d684dfba11f2767c5b.html "The JDBC (Java Database Connectivity) adapter enables you to connect SAP Integration Suite to cloud or on-premise databases.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Jira

</td>
<td valign="top">

Basic

</td>
<td valign="top">

[Jira Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d15b560938c9446fbd9eb0ce84282fb0.html "The Jira receiver adapter connects SAP Integration Suite to Jira. The Jira adapter helps you exchange data between the two systems. Jira is a versatile software with multiple offerings like issue tracking, bug management, and agile project management.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

JMS

</td>
<td valign="top">

N.A. as no connection with a remote component

</td>
<td valign="top">

[Configure the JMS Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/79edc04c91574a6bb8c15ae3e1a27b03.html "The JMS (Java Message Service) receiver adapter enables asynchronous decoupling of inbound and outbound processing by using message queues. The receiver adapter stores messages and schedules them for processing in a queue.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Kafka

</td>
<td valign="top">

-   Client Certificate
-   SASL



</td>
<td valign="top">

[Configure the Kafka Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/fc6ee1fb1c1843c195f3cc8cdbfd4b15.html "You use the Kafka Receiver adapter to connect to an external Kafka broker via Kafka protocol.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

LDAP

</td>
<td valign="top">

-   Simple



</td>
<td valign="top">

[LDAP Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/06a753f90fd64272af1692603cdd3b9e.html "The Lightweight Directory Access Protocol (LDAP) Receiver Adapter enables you to communicate with systems that expose data through LDAP service.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Mail

</td>
<td valign="top">

-   Encrypted User/Password
-   Plain User/Password
-   OAuth2 Authorization Code
-   None



</td>
<td valign="top">

[Configure the Mail Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/f68d5e03fd574f509f89474f6a6e272a.html "You use the mail receiver adapter to send encrypted messages by e-mail.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Microsoft Dynamics CRM

</td>
<td valign="top">

-   OAuth - Password Credentials
-   OAuth – Client Credentials Secret



</td>
<td valign="top">

[Microsoft Dynamics CRM Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ee724c8672834041a26413d94dfdb042.html "The Microsoft Dynamics CRM receiver adapter enables SAP Integration Suite to accelerate the implementation time and reduce the complexity of connecting to Microsoft Dynamics CRM.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Microsoft SharePoint

</td>
<td valign="top">

-   OAuth2 Client Credentials

-   OAuth2 Authorization Code

-   Dynamic




</td>
<td valign="top">

[Configure the Microsoft SharePoint Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b12b33a903ac4e388d1892a2febdc732.html "The Microsoft SharePoint receiver adapter connects an SAP Integration Suite tenant to a remote system using HTTP protocol to write files to the system.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

NetSuite

</td>
<td valign="top">

Token-Based Authentication \(TBA\)

</td>
<td valign="top">

[NetSuite Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/618127afc04e43179a34452d28780e50.html "The NetSuite receiver adapter connects SAP Integration Suite to NetSuite.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

OData - V2

</td>
<td valign="top">

-   Client Certificate
-   OAuth2 Client Credentials
-   OAuth2 SAML Bearer Assertion
-   Principal Propagation
-   Basic
-   None



</td>
<td valign="top">

[Configure the OData V2 Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/c5c2e38e0c87472e996dfda04920bfc4.html "Configure the OData receiver adapter by understanding the adapter parameters.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

OData - V4

</td>
<td valign="top">

-   Client Certificate
-   OAuth2 Client Credentials
-   Basic
-   None



</td>
<td valign="top">

[Configure the OData V4 Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cd66a12cc2054e36a5dfa6b93d56c7bb.html "You configure the ODataV4 receiver adapter by understanding the adapter parameters.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

ODC

</td>
<td valign="top">

-   Principal Propagation
-   Basic



</td>
<td valign="top">

[ODC Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/3cdbc29ca2b641738513ab8665bab9fd.html "The ODC adapter enables you to communicate with systems that expose data through the OData Channel for SAP Gateway.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

OpenConnectors

</td>
<td valign="top">

-   Client ID
-   Secret from Open Connectors



</td>
<td valign="top">

[OpenConnectors Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1a27cee87cd14ef69ca56fb50b1e3983.html "You use the OpenConnectors receiver adapter in integration flows to communicate with more than 170 non-SAP cloud applications that are supported by Open Connectors.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

ProcessDirect

</td>
<td valign="top">

N.A. as no connection with a remote component

</td>
<td valign="top">

[Configure the ProcessDirect Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/5b7327df4f874e4986e4e397e5aab3b8.html "You use the ProcessDirect receiver adapter to establish fast and direct communication between integration flows by reducing latency and network overhead provided both of them are available within a same tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

RabbitMQ

</td>
<td valign="top">

-   Client Certificate
-   SASL



</td>
<td valign="top">

[Configure the RabbitMQ Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e9dfc37fb5b349d5ad1d6e43e194e69e.html "You use the RabbitMQ receiver adapter to send messages from SAP Integration Suite to exchanges or queues on the RabbitMQ server.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

RFC

</td>
<td valign="top">

Via Remote Function Call

</td>
<td valign="top">

[RFC Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/5c76048b04594888a47e74d35a91c08a.html "Connects an SAP Cloud Integration tenant to a remote receiver system using Remote Function Call (RFC).") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Salesforce

</td>
<td valign="top">

-   OAuth Client Credentials
-   OAuth JWT Bearer



</td>
<td valign="top">

[Salesforce Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/a548be9518704e4aad7d02963f3f7dec.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SAP Master Data Integration

</td>
<td valign="top">

OAuth2 Client Credentialsis

</td>
<td valign="top">

[SAP Master Data Integration Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e91e373bbb5b49ccbc2977152def61a2.html "Use SAP Master Data Integration (MDI) receiver adapter to synchronize your master data from SAP applications like SAP ECC and other third-party applications with SAP MDI service.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

ServiceNow

</td>
<td valign="top">

-   OAuth2 Client Credentials
-   Basic



</td>
<td valign="top">

[ServiceNow Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1e3bcf40403441d4898e6badd53c2b79.html "ServiceNow receiver adapter enables SAP Cloud Integration and SAP Integration Suite to accelerate the implementation time and reduce the complexity of connecting to ServiceNow.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SFTP

</td>
<td valign="top">

-   Public Key
-   User Name/Password
-   Dual



</td>
<td valign="top">

[Configure the SFTP Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/4ef52cf6c89b44219ab7c23ef8a1df31.html "The SFTP receiver adapter connects an SAP Integration Suite tenant to a remote system using the SSH File Transfer protocol to write files to the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol (or SFTP).") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Slack

</td>
<td valign="top">

-   User Token
-   Bot Token
-   None



</td>
<td valign="top">

[Configure the Slack Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7c2ea64f931640afb01c6a9d82abdfa1.html "Enables SAP Integration Suite to get data from the Slack storage or to create, modify, or delete data on the Slack storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SMB

</td>
<td valign="top">

Basic

</td>
<td valign="top">

[Configure the SMB Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ddd0d599610a421e9670f08cfe624fcb.html "The SMB (Server Message Block) receiver adapter connects SAP Integration Suite to a remote share drive using TCP (Transmission Control Protocol) to perform read and write operations including create, delete, rename etc.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Snowflake

</td>
<td valign="top">

-   Database Account
-   Key-Pair



</td>
<td valign="top">

[Snowflake Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1299e684c3464a0b82626c8ebee79e25.html "The Snowflake receiver adapter connects SAP Integration Suite to Snowflake.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SOAP - SAP RM

</td>
<td valign="top">

-   Client Certificate
-   Principal Propagation
-   Basic
-   None



</td>
<td valign="top">

[Configure the SOAP (SAP RM) Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/8366495128624ec895f239888ef1e3ec.html "Exchanges messages with a receiver system based on the SOAP communication protocol and SAP Reliable Messaging (SAP RM) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SOAP - SOAP 1.x

</td>
<td valign="top">

-   Client Certificate
-   Principal Propagation
-   OAuth2 SAML Bearer Assertion
-   Basic
-   None



</td>
<td valign="top">

[Configure the SOAP (SOAP 1.x) Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/57f7b34b9b86438d9cb760c5c541f88c.html "The SOAP (SOAP 1.x) receiver adapter enables a SAP BTP tenant to exchange messages with a receiver system that supports Simple Object Access Protocol (SOAP) 1.1.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Splunk

</td>
<td valign="top">

-   Basic Authentication
-   Splunk Token
-   None



</td>
<td valign="top">

[Configure the Splunk Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e8e6ba6a38a14041bdd630d3386a5d3e.html "Enables SAP Integration Suite to get data from the Splunk storage or to create, modify, or delete data on the Splunk storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SuccessFactors - OData V2

</td>
<td valign="top">

-   OAuth2 SAML Bearer Assertion
-   Basic



</td>
<td valign="top">

[Configure the SuccessFactors OData V2 Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d16dd12c5c5649e99c8939879a77f9c0.html "Configure the SuccessFactors OData V2 receiver adapter by understanding the adapter parameters.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SuccessFactors - OData V4

</td>
<td valign="top">

-   OAuth2 SAML Bearer Assertion
-   OAuth2 Client Credentials



</td>
<td valign="top">

[SuccessFactors OData V4 Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cd091fc8051d42ee95eda2858ca2a2f0.html "The SuccessFactors receiver adapter enables you to communicate with the SuccessFactors system. You use the OData V4 message protocol to connect to the OData V4-based Web services of the SuccessFactors system.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SuccessFactors - REST

</td>
<td valign="top">

-   OAuth2 Client Credentials



</td>
<td valign="top">

[Configure the SuccessFactors REST Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/9cff562cd220458db0aca97ac24887a0.html "The SuccessFactors (REST) receiver adapter connects an SAP Cloud Integration tenant to a SuccessFactors receiver system using the REST message protocol.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SuccessFactors - SOAP

</td>
<td valign="top">

-   OAuth2 SAML Bearer Assertion
-   Basic



</td>
<td valign="top">

[Configure the SuccessFactors SOAP Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/360ef42b1d4e4b86a6867b6f0adce4ce.html "The SuccessFactors SOAP receiver adapter connects a tenantSAP Cloud Integration to SOAP-based Web services of a SuccessFactors receiver system (synchronous or asynchronous communication).") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

SugarCRM

</td>
<td valign="top">

-   Basic



</td>
<td valign="top">

[SugarCRM Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d96ddf70caaf488ba87233f54f79ede6.html "The SugarCRM receiver adapter enables an SAP Cloud Integration tenant to accelerate the implementation time and reduce the complexity of connecting to SugarCRM.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Twitter

</td>
<td valign="top">

-   OAuth



</td>
<td valign="top">

[Twitter Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/453c174be6ca4098a8c99dc4c1262d25.html "You use the Twitter receiver adapter to extract information from the Twitter platform based on certain criteria such as keywords, user data, for example. As one example, you can use this feature to send, search for and receive Twitter feeds.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Workday

</td>
<td valign="top">

-   Basic



</td>
<td valign="top">

[Workday Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/0c6e67020af9433cb09a56736d73ca76.html "Workday receiver adapter enables SAP Cloud Integration and SAP Integration Suite to accelerate the implementation time and reduce the complexity of connecting to Workday.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Xl

</td>
<td valign="top">

-   Client Certificate
-   Principal Propagation
-   Basic Authentication
-   None



</td>
<td valign="top">

[Configure the XI Receiver Adapter](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/5d2670fdfed640db8fd43991440d6da7.html "The XI receiver adapter allows you to connect a tenant to a local Integration Engine in a receiver system. The adapter supports communication over the XI 3.0 protocol.") :arrow_upper_right: 

</td>
</tr>
</table>

