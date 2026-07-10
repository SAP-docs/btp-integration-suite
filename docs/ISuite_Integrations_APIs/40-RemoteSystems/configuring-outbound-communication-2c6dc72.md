<!-- loio2c6dc72af618406892a212c5968bbeb6 -->

# Configuring Outbound Communication

Outbound communication refers to message processing from the integration platform to a remote system \(where the integration platform is the client\).

Configuring outbound communication means setting up the connection of a remote receiver system with the integration platform.



## Receiver Systems You Can Connect to the Integration Platform

You can connect the following kinds of receiver systems to the integration platform \(examples\):

-   A cloud application, for example, an SAP cloud application like SuccessFactors or SAP Cloud for Customer

-   An on-premise application, for example SAP ERP

    You can connect on-premise systems \(located in the customer system landscape\) such as SAP systems. Typical use cases for this are hybrid integration scenarios, where an on-premise SAP application \(for example, SAP ERP\) is integrated with an SAP cloud application \(for example, SAP Cloud for Customer or SAP SuccessFactors\).

-   An e-mail server

    In this case, the integration platform sends e-mails to the e-mail server \(for an e-mail address specified in the related adapter\).

-   An SFTP server

    In this case, the integration platform writes files to the SFTP server.


SAP Integration Suite supports the following kinds of connections: HTTP connections, SFTP \(SSH File Transfer Protocol\) connections, and connections to an e-mail server using the mail sender adapter.

**Related Information**  


[Setting Up Outbound HTTP Connections](setting-up-outbound-http-connections-92dd2a6.md "You can use various receiver adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a receiver system through the HTTP protocol.")

[Setting Up Outbound SFTP Connections](setting-up-outbound-sftp-connections-6e4de95.md "Using the SFTP receiver adapter, you connect the tenant with an SFTP server so that the tenant can write data to the SFTP server.")

[Setting Up Outbound Mail Connections](setting-up-outbound-mail-connections-8b112ba.md "Using the mail receiver adapter, you connect the tenant with an e-mail server so that the tenant can send emails to the e-mail server.")

