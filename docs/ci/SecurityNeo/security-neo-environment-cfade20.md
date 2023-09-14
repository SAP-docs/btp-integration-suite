<!-- loiocfade2084f364d1597e1946afaa4e7d3 -->

# Security, Neo Environment

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



Using a cloud-based integration platform imposes dedicated security measures on the software vendor \(SAP\) that hosts the platform, as well as on those \(the customers\) who use the platform.

This section describes the security-related aspects of the integration platform and shows which measures you can take to protect customer data that is passed through the platform during the execution of an integration scenario.

Customers who use SAP Cloud Integration agree that a significant part of their \(and their customers'\) sensitive data is processed by and stored within an infrastructure not owned by themselves.

The core task of an integration platform is to serve as the transit place for messages, which may contain sensitive customer data. First and foremost, these messages must be protected against eavesdropping and unauthorized access.

Therefore, the integration platform must fulfill the following main requirements:

-   The integration infrastructure is already designed and built in such a way that it meets the highest security standards.

    In particular, it must be guaranteed that the technical system landscape, the communication between the components of the integration platform, and the storage locations of messages are secure.

-   The processes related to the usage of Cloud Integration meet the highest security standards.

    This relates to the processes at SAP that are related to the development and upgrade of the Cloud Integration software, the processes related to the provisioning and operation of the customers' virtual environment by the infrastructure provider, and the customer onboarding process during which customers set up secure connections between their infrastructure and SAP's integration platform.

-   Customers have several options to configure how messages are exchanged within an integration scenario so that the involved data is protected at the highest level.

    In particular, when designing integration flows, customers can choose between several options to protect messages by establishing secure communication channels \(transport-level security\) and by configuring digital encryption and digital signing of messages \(message-level security\).


This documentation summarizes the measures that are taken by SAP to fulfill these requirements.

**Related Information**  


[Technical Landscape, Neo Environment](technical-landscape-neo-environment-7fec71d.md "The technical infrastructure comprises a set of technical components that can communicate with each other and with remote components in a secure way based on certain protocols such as HTTPS or SFTP, for example. In addition, user access to the technical infrastructure is designed in such a way that only users with well-defined permissions can access the different segments.")

[Security Aspects of Processes](security-aspects-of-processes-f504a92.md "Processes that are related to the provisioning, update, and usage of the cloud-based integration platform meet the highest security standards.")

[Security Aspects of Data, Data Flow](security-aspects-of-data-data-flow-702ddb5.md "All data in transit, either exchanged with remote components or internal, can be protected by methods such as encryption.")

[Identity and Access Management](identity-and-access-management-15ca6f9.md "Identity and access management features are used during the lifecycle of an integration scenario.")

[Data Storage Security](data-storage-security-32e84c4.md "Customer data can be stored in dedicated steps during message processing.")

[Data Protection and Privacy](data-protection-and-privacy-c43df85.md "Various types of customer data are processed by and stored on the integration platform at different times. This data gets the highest level of protection, and SAP takes dedicated measures to guarantee this security level.")

[Other Security-Related Information](other-security-related-information-7752ba9.md "")

