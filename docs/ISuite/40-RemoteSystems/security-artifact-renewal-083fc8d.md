<!-- loio083fc8d87bf046e2a9c4eafd42086cec -->

# Security Artifact Renewal

Security artifacts like certificates or passwords \(for example\) are subject to a specific lifecycle, in other words, they expire in certain time periods. To make sure that the operation of a scenario \(using security artifacts\) can be continued without any downtime, the process to renew security artifacts has to be performed in a coordinated way by the administrators of the involved components.

For the different use cases specific security artifact renewal processes have been defined.

> ### Note:  
> -   The terms *client* and *server* are preferably used in the context of the certificate-based authentication option for HTTPS-based communication \(transport level security\). The background of this is that in order to set up a mutual authentication \(that comes with this option\), certificates for both roles, *client* and *server*, are required. When a message is sent from a sender \(which has the role of a client\) to a receiver \(which has the role of a server\), authentication steps are executed both to check if the server is a trusted partner and if the client is allowed to call the server.
> -   In the context of message level security, the terms *sender* and *receiver* are preferably used in order to simplify things. These use cases typically require the following kinds of certificates or keys:
>     -   Keys owned by a *sender* to either encrypt or sign the content of a message
>     -   Keys owned by a *receiver* to either verify or decrypt the content of a message

**Related Information**  


[Basic Security Artifact Renewal Processes](basic-security-artifact-renewal-processes-c70b1f2.md "")

[Renewal of Keys Provided by SAP](renewal-of-keys-provided-by-sap-5db16f5.md "To enable secure communication between the tenant and connected remote systems, the system keystore deployed on the tenant must contain up-to-date keys owned by the tenant administrator and SAP.")

