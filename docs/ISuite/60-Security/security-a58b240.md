<!-- loioa58b2400b3094009988a53b0a63b455a -->

# Security

This security guide provides an overview of all the security-related aspects for the different capabilities of SAP Integration Suite.



This section describes the security-related aspects of SAP Integration Suite and shows which measures you can take to protect customer data that is passed through SAP Integration Suite during the execution of an integration scenario.

Customers who use SAP Cloud Integration agree that a significant part of their \(and their customers'\) sensitive data is processed by and stored within an infrastructure not owned by themselves.

The core task of an integration platform is to serve as the transit place for messages, which may contain sensitive customer data. First and foremost, these messages must be protected against eavesdropping and unauthorized access.

Therefore, the integration platform must fulfill the following main requirements:

-   The integration infrastructure is already designed and built in such a way that it meets the highest security standards.

    In particular, it must be guaranteed that the technical system landscape, the communication between the components of the integration platform, and the storage locations of messages are secure.

-   The processes related to the usage of SAP Integration Suite meet the highest security standards.

    This relates to the processes at SAP that are related to the development and upgrade of the SAP Integration Suite software, the processes related to the provisioning and operation of the customers' virtual environment by the infrastructure provider, and the customer onboarding process during which customers set up secure connections between their infrastructure and SAP's integration platform.

-   Customers have several options to configure how messages are exchanged within an integration scenario so that the involved data is protected at the highest level.

    For example, when designing integration flows, customers can choose between several options to protect messages by establishing secure communication channels \(transport-level security\) and by configuring digital encryption and digital signing of messages \(message-level security\).


This documentation summarizes the measures that are taken by SAP to fulfill these requirements.



> ### Note:  
> The role collection *Integration\_Provisioner* has been made available for managing security settings for SAP Integration Suite. For detailed information on how to assign this role collection, refer to [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).

**Related Information**  


[Technical Landscape](technical-landscape-daea676.md "")

[Security Aspects of Processes](security-aspects-of-processes-51e36ff.md "Processes that are related to the provisioning, update, and usage of SAP Integration Suite meet the highest security standards.")

[Security Aspects of Data, Data Flow](security-aspects-of-data-data-flow-55c45ab.md "")

[Identity and Access Management](identity-and-access-management-77868c2.md "")

[Data Protection and Privacy](data-protection-and-privacy-3df9abf.md "")

[Auditing and Logging Information](auditing-and-logging-information-86a75cd.md "Here you can find a list of the security events that are logged by SAP Integration Suite.")

[Malware Scanner for Cloud Integration](../50-Development/IntegrationSettings/malware-scanner-for-cloud-integration-37df657.md "Scan your design time artifacts for malware before the users upload them to the tenant.")

