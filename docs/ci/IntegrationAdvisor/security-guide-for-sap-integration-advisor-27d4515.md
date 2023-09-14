<!-- loio27d45158e5464c339866c2ce53d8dfbb -->

# Security Guide for SAP Integration Advisor

The security guide for SAP Integration Advisor provides you an overview of all the security related aspects for the application like process related security information, identity and access management, data storage, protection and privacy, and also what SAP does to ensure the product security standards.



<a name="loio27d45158e5464c339866c2ce53d8dfbb__section_fxg_nts_ngb"/>

## Introduction

Using a cloud-based integration platform imposes dedicated security measures on the software vendor \(SAP\) that hosts the platform, as well as on those \(the customers\) who use the platform. This section describes the security-related aspects of the integration platform and shows which measures you can take to protect customer data that is passed through the platform during the execution of an integration scenario.

Customers who use SAP's cloud-based integration platform agree that a significant part of their \(and their customers'\) sensitive data is processed by and stored within an infrastructure owned by SAP.

The core task of an integration platform is to serve as the transit place for messages, which may contain sensitive customer data. First and foremost, these messages must be protected against eavesdropping and unauthorized access.

Therefore, the integration platform must fulfill the following main requirements:

-   The integration infrastructure provided by SAP is already designed and built in such a way that it meets the highest security standards. It must be guaranteed that the technical system landscape, the communication between the components of the integration platform, and the storage locations of messages are secure.

-   The processes related to the usage of the platform meet the highest security standards. This relates to the processes at SAP that are related to the development and upgrade of the platform, the processes related to the provisioning and operation of the customers' virtual environment by SAP, and the customer onboarding process during which customers set up secure connections between their infrastructure and SAP's integration platform.

-   Customers have several options to configure how messages are exchanged within an integration scenario so that the involved data is protected at the highest level. When designing integration flows, customers can choose between several options to protect messages by establishing secure communication channels \(transport-level security\) and by configuring digital encryption and digital signing of messages \(message-level security\).


