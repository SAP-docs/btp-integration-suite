<!-- loio62690e524ddc4b9b9fb95a25928a08b0 -->

# Configuring Inbound Communication

Configuring inbound communication means setting up the connection between a remote sender system and the integration platform. Inbound communication refers to message processing from a remote system, often located in the customer landscape, to Cloud Integration. Here, the integration platform is the server.



## Sender Systems You Can Connect to the Integration Platform

You can connect different kinds of sender systems to the integration platform, for example:

-   A cloud application, for example, SAP SuccessFactors

-   An on-premise application, for example, SAP ERP

    > ### Note:  
    > If an SAP system based on Application Server ABAP sends requests to Cloud Integration and there are 2 or more worker nodes enabled on Cloud Integration side, you can receive an `HTTP/1.1 403` authentication error. The root cause is that the SAP kernel encodes the cookies' value by default, which breaks the load-balancing feature. To solve the issue, set profile parameter `ict/disable_cookie_urlencoding` to `1` or `2` depending on kernel level. For more information, see SAP note [2681175](https://me.sap.com/notes/2681175).

-   A SOAP client

-   An e-mail server

-   An SFTP server

    In this case, the integration platform reads files from the SFTP server \(polling\).


To enable communication with such a variety of systems, Cloud Integration supports the following kinds of connections:

-   HTTP connections that allow

    -   Sender systems to call integration flow endpoints \(through one of the adapters based on the HTTP protocol like, for example, the HTTPS adapter or the SOAP adapter\)

    -   API clients to call the OData API


-   SFTP \(SSH File Transfer Protocol\) connections

-   Connections to an FTP server using the Secure File Transfer Protocol \(FTPS\)

-   Connections to an e-mail server using the mail sender adapter

-   Connections to a Java Message System \(JMS\) message broker

-   Connections to an external message broker using the Advanced Message Queuing Protocol \(AMQP\)


**Related Information**  


[Configuring Inbound HTTP Connections](configuring-inbound-http-connections-f568400.md "")

[Setting Up Inbound Mail Connections](setting-up-inbound-mail-connections-6ad4956.md "Using the mail sender adapter, you connect the tenant with an e-mail server so that the tenant can read data from the e-mail server (in a process referred to as polling).")

[Tutorial: Set Up Inbound OAuth Client Credentials Grant Authentication for API Clients with SAP-Generated Certificate](https://developers.sap.com/tutorials/btp-integration-suite-oauth-client-certificate.html)

[Tutorial: Set Up Inbound OAuth Client Credentials Grant Authentication for Senders Calling Integration Flows with SAP-Generated Certificate](https://developers-qa-blue.wcms-nonprod.c.eu-de-2.cloud.sap/tutorials/btp-integration-suite-oauth-integration-flow.html)

