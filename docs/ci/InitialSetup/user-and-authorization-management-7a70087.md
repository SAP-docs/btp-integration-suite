<!-- loio7a7008723ec142f393d3798a7cd1bfa5 -->

# User and Authorization Management

When defining permissions for sending applications to access Cloud Integration \(either integration flow endpoints or Cloud Integration resources through the OData API\), you need to deal with roles.

A typical concept is to group permissions for individual activities along personas - fictitious persons that are associated with typical task areas. For example, the integration developer persona is in charge of tasks such like integration flow development and deployment and of monitoring message processing.

-   In Cloud Foundry, there are *role collections* that contain all roles associated with a dedicated persona. An individual role can be defined based on predefined role templates available on SAP BTP.

-   In Neo, there are *authorization groups* that contain all roles associated with a dedicated persona.


For more information and a comparison of Cloud Foundry / Neo entities, check out the topics:

-   [Persona](../SecurityNeo/persona-2937e5c.md)

-   [Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)


Managing users and permissions is done differently in Cloud Foundry and in Neo.

-   Cloud Foundry: [SAP Authorization and Trust Management Service in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6373bb7a96114d619bfdfdc6f505d1b9.html)

-   Neo: [User Management for SAP BTP, Neo Environment](../Operations/user-management-for-sap-btp-neo-environment-f319277.md)


Due to the difference in the user and permission management, also the configuration of access policies is different in both environments:

-   Cloud Foundry: [Managing Access Policies, Cloud Foundry Environment](../Operations/managing-access-policies-cloud-foundry-environment-7db3c87.md)

-   Neo: [Managing Access Policies, Neo Environment](../Operations/managing-access-policies-neo-environment-18f06d4.md)


