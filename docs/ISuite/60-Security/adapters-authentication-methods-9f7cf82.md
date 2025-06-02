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

[Configure the Advanced Event Mesh Sender Adapter](../50-Development/configure-the-advanced-event-mesh-sender-adapter-abd2efc.md) 

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

[Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md) 

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

[Configure the AMQP Sender Adapter](../50-Development/configure-the-amqp-sender-adapter-99ce674.md) 

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

[Configure the Ariba Sender Adapter](../50-Development/configure-the-ariba-sender-adapter-0629b58.md) 

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the AS2 Sender Adapter](../50-Development/configure-the-as2-sender-adapter-5d7ee17.md)

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the AS2 MDN Sender Adapter](../50-Development/configure-the-as2-mdn-sender-adapter-c54effe.md)

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [AS4 Sender Adapter](../50-Development/as4-sender-adapter-a448605.md)

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

[AmazonWebServices Sender Adapter](../50-Development/amazonwebservices-sender-adapter-16772e3.md) 

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

[Configure the AzureStorage Sender Adapter](../50-Development/configure-the-azurestorage-sender-adapter-d42134a.md) 

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

[Data Store Sender Adapter](../50-Development/data-store-sender-adapter-4f5ef3f.md) 

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

[Configure the Dropbox Sender Adapter](../50-Development/configure-the-dropbox-sender-adapter-de61991.md) 

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

[Configure the FTP Sender Adapter](../50-Development/configure-the-ftp-sender-adapter-239042f.md) 

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the IDoc Sender Adapter](../50-Development/configure-the-idoc-sender-adapter-bf769d6.md)

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

[Configure the JMS Sender Adapter](../50-Development/configure-the-jms-sender-adapter-161791b.md) 

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

[Configure the Kafka Sender Adapter](../50-Development/configure-the-kafka-sender-adapter-0d849e5.md) 

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

[Mail Sender for IMAP](../50-Development/mail-sender-for-imap-5b94e42.md) 

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

[Mail Sender for POP3](../50-Development/mail-sender-for-pop3-c52a4da.md) 

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

[Configure the Microsoft SharePoint Sender Adapter](../50-Development/configure-the-microsoft-sharepoint-sender-adapter-ce41e85.md) 

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the OData Sender Adapter](../50-Development/configure-the-odata-sender-adapter-de7aee5.md)

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

[Configure the ProcessDirect Sender Adapter](../50-Development/configure-the-processdirect-sender-adapter-e340d4c.md) 

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

[Configure the RabbitMQ Sender Adapter](../50-Development/configure-the-rabbitmq-sender-adapter-4e3c554.md) 

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

[Salesforce Sender Adapter](../50-Development/salesforce-sender-adapter-ba6420d.md) 

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

[Configure the SFTP Sender Adapter](../50-Development/configure-the-sftp-sender-adapter-2de9ee5.md) 

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

[Configure the Slack Sender Adapter](../50-Development/configure-the-slack-sender-adapter-1d93850.md) 

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

[Configure the SMB Sender Adapter](../50-Development/configure-the-smb-sender-adapter-95bf6e9.md) 

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the SOAP \(SAP RM\) Sender Adapter](../50-Development/configure-the-soap-sap-rm-sender-adapter-6962234.md)

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the SOAP \(SOAP 1.x\) Sender Adapter](../50-Development/configure-the-soap-soap-1-x-sender-adapter-a178913.md)

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

[Configure the Splunk Sender Adapter](../50-Development/configure-the-splunk-sender-adapter-271ad20.md) 

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

[Configure the SuccessFactors REST Sender Adapter](../50-Development/configure-the-successfactors-rest-sender-adapter-9f0646b.md) 

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

[Configure the SuccessFactors \(SOAP\) Sender Adapter](../50-Development/configure-the-successfactors-soap-sender-adapter-874e4b1.md) 

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

-   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

-   [Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-integration-flow..html)


See also: [Configure the XI Sender Adapter](../50-Development/configure-the-xi-sender-adapter-41a1a57.md)

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

[Configure the Advanced Event Mesh Receiver Adapter](../50-Development/configure-the-advanced-event-mesh-receiver-adapter-881f656.md) 

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

[Amazon DynamoDB Receiver Adapter](../50-Development/amazon-dynamodb-receiver-adapter-36620d5.md) 

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

[Amazon EventBridge Receiver Adapter](../50-Development/amazon-eventbridge-receiver-adapter-ff3f9ed.md) 

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

[Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md) 

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

[Configure the AMQP Receiver Adapter](../50-Development/configure-the-amqp-receiver-adapter-d5660c1.md) 

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

[Anaplan Receiver Adapter](../50-Development/anaplan-receiver-adapter-364ab57.md) 

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

[Configure the Ariba Receiver Adapter](../50-Development/configure-the-ariba-receiver-adapter-49dffa3.md) 

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

[Configure the AS2 Receiver Adapter](../50-Development/configure-the-as2-receiver-adapter-9db62be.md) 

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

[AS4 Receiver Adapter](../50-Development/as4-receiver-adapter-3a2fde8.md) 

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

[AmazonWebServices Receiver Adapter](../50-Development/amazonwebservices-receiver-adapter-bc7d1aa.md) 

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

[Configure the AzureStorage Receiver Adapter](../50-Development/configure-the-azurestorage-receiver-adapter-30f59b0.md) 

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

[Coupa Receiver Adapter](../50-Development/coupa-receiver-adapter-648ac01.md) 

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

[Configure the Dropbox Receiver Adapter](../50-Development/configure-the-dropbox-receiver-adapter-16ef7b4.md) 

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

[ELSTER Receiver Adapter](../50-Development/elster-receiver-adapter-e374ef7.md) 

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

[Facebook Receiver Adapter](../50-Development/facebook-receiver-adapter-3dcc408.md) 

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

[Configure the FTP Receiver Adapter](../50-Development/configure-the-ftp-receiver-adapter-c16d331.md) 

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

[HTTP Receiver Adapter](../50-Development/http-receiver-adapter-2da452e.md) 

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

[HubSpot Receiver Adapter](../50-Development/hubspot-receiver-adapter-48cfaa8.md) 

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

[Configure the IDoc Receiver Adapter](../50-Development/configure-the-idoc-receiver-adapter-018aa88.md) 

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

[JDBC Receiver Adapter](../50-Development/jdbc-receiver-adapter-88be644.md) 

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

[Jira Receiver Adapter](../50-Development/jira-receiver-adapter-d15b560.md) 

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

[Configure the JMS Receiver Adapter](../50-Development/configure-the-jms-receiver-adapter-79edc04.md) 

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

[Configure the Kafka Receiver Adapter](../50-Development/configure-the-kafka-receiver-adapter-fc6ee1f.md) 

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

[LDAP Receiver Adapter](../50-Development/ldap-receiver-adapter-06a753f.md) 

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

[Configure the Mail Receiver Adapter](../50-Development/configure-the-mail-receiver-adapter-f68d5e0.md) 

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

[Microsoft Dynamics CRM Receiver Adapter](../50-Development/microsoft-dynamics-crm-receiver-adapter-ee724c8.md) 

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

[Configure the Microsoft SharePoint Receiver Adapter](../50-Development/configure-the-microsoft-sharepoint-receiver-adapter-b12b33a.md) 

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

[NetSuite Receiver Adapter](../50-Development/netsuite-receiver-adapter-618127a.md) 

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

[Configure the OData V2 Receiver Adapter](../50-Development/configure-the-odata-v2-receiver-adapter-c5c2e38.md) 

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

[Configure the OData V4 Receiver Adapter](../50-Development/configure-the-odata-v4-receiver-adapter-cd66a12.md) 

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

[ODC Receiver Adapter](../50-Development/odc-receiver-adapter-3cdbc29.md) 

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

[OpenConnectors Receiver Adapter](../50-Development/openconnectors-receiver-adapter-1a27cee.md)

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

[Configure the ProcessDirect Receiver Adapter](../50-Development/configure-the-processdirect-receiver-adapter-5b7327d.md) 

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

[Configure the RabbitMQ Receiver Adapter](../50-Development/configure-the-rabbitmq-receiver-adapter-e9dfc37.md) 

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

[RFC Receiver Adapter](../50-Development/rfc-receiver-adapter-5c76048.md) 

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

[Salesforce Receiver Adapter](../50-Development/salesforce-receiver-adapter-a548be9.md) 

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

[SAP Master Data Integration Receiver Adapter](../50-Development/sap-master-data-integration-receiver-adapter-e91e373.md) 

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

[ServiceNow Receiver Adapter](../50-Development/servicenow-receiver-adapter-1e3bcf4.md) 

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

[Configure the SFTP Receiver Adapter](../50-Development/configure-the-sftp-receiver-adapter-4ef52cf.md) 

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

[Configure the Slack Receiver Adapter](../50-Development/configure-the-slack-receiver-adapter-7c2ea64.md) 

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

[Configure the SMB Receiver Adapter](../50-Development/configure-the-smb-receiver-adapter-ddd0d59.md) 

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

[Snowflake Receiver Adapter](../50-Development/snowflake-receiver-adapter-1299e68.md) 

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

[Configure the SOAP \(SAP RM\) Receiver Adapter](../50-Development/configure-the-soap-sap-rm-receiver-adapter-8366495.md) 

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

[Configure the SOAP \(SOAP 1.x\) Receiver Adapter](../50-Development/configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md) 

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

[Configure the Splunk Receiver Adapter](../50-Development/configure-the-splunk-receiver-adapter-e8e6ba6.md) 

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

[Configure the SuccessFactors OData V2 Receiver Adapter](../50-Development/configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md) 

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

[SuccessFactors OData V4 Receiver Adapter](../50-Development/successfactors-odata-v4-receiver-adapter-cd091fc.md) 

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

[Configure the SuccessFactors REST Receiver Adapter](../50-Development/configure-the-successfactors-rest-receiver-adapter-9cff562.md) 

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

[Configure the SuccessFactors SOAP Receiver Adapter](../50-Development/configure-the-successfactors-soap-receiver-adapter-360ef42.md) 

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

[SugarCRM Receiver Adapter](../50-Development/sugarcrm-receiver-adapter-d96ddf7.md) 

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

[Twitter Receiver Adapter](../50-Development/twitter-receiver-adapter-453c174.md) 

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

[Workday Receiver Adapter](../50-Development/workday-receiver-adapter-0c6e670.md) 

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

[Configure the XI Receiver Adapter](../50-Development/configure-the-xi-receiver-adapter-5d2670f.md) 

</td>
</tr>
</table>

