<!-- loiobff88cdc1d3b4f859852340dd750ba85 -->

# User Authentication and Authorization

Edge Integration Cell is based on authentication and authorization mechanisms provided by SAP Business Technology Platform, Cloud Foundry environment. For information about security recommendations and guidelines for user administration, authentication, and authorizations, see [Security Administration: Managing Authentication and Authorization](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/1ff47b2d980e43a6b2ce294352333708.html) in the SAP Business Technology Platform Security Guide.

Identity and access management features provided by SAP Business Technology Platform are used during the lifecycle of an integration scenario. Extended Services - User Account and Authentication \(XSUAA\) is the central service for business user authentication and authorization. Edge Integration Cell components rely on XSUAA service instances to access cloud services, such as object store or secure store.



<a name="loiobff88cdc1d3b4f859852340dd750ba85__section_ets_xn1_mvb"/>

## Authentication and Authorization Options for Inbound Calls

When a sender system calls Edge Integration Cell using HTTPS-based \(inbound\) requests, there are different ways for the calling sender to authenticate itself against the integration platform:

-   Basic authentication

-   OAuth

-   Client certificate authentication


For more information about XSUAA, see [What Is the SAP Authorization and Trust Management Service?](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/649961f8d4ad463daca33b3a20deba4c.html).

