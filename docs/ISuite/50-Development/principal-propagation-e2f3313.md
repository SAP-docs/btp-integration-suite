<!-- loioe2f3313988b64fc48bb3d44989804c52 -->

# Principal Propagation

Principal propagation is a process that provides a secure way of forwarding the identity of a cloud user to the Cloud Connector, and from there to an on-premise system. The user information is kept confidential and, even more importantly, not changed during transit.



<a name="loioe2f3313988b64fc48bb3d44989804c52__section_q34_nzt_glb"/>

## Prerequisites

-   Your on-premise back-end system supports X.509 certification.

-   On-premise connectivity is enabled in your Cloud Connector application, Cloud Controller settings. To verify the same:

    -   Navigate to *Cloud To On-Premise* \> *PRINCIPAL PROPAGATION* in your Cloud Connector application, Cloud Controller settings.
    -   Using the Name and Description column, identify the IDP connected to your Cloud Foundry subaccount, which needs to be trusted for principal propagation.
    -   In the *Trusted* column, check if on-premise connectivity is enabled, else select the checkbox to enable it.

    For information on how to connect your system via Cloud Connector, see [Cloud Connector](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e6c7616abb5710148cfcf3e75d96d596.html#loioe6c7616abb5710148cfcf3e75d96d596__scenarios)




<a name="loioe2f3313988b64fc48bb3d44989804c52__section_lqv_nc5_glb"/>

## Context

A principal forwarded to the API Proxy is validated with the IDP connected to the user's subaccount on Cloud Foundry where is enabled. To obtain an OAuth token, which is validated, the user has to create credentials using on-premise-connectivity plan in the Cloud Foundry environment.



In API Management the Principal Propagation supports two flows namely:

-   **Principal Propagation from the Neo to the Cloud Foundry Environment**: Enable an application in your subaccount in the Neo environment to access an API Management proxy created on a Cloud Foundry based API Management without a user login. For this scenario to work, the Neo subaccount needs to be trusted by the Cloud Foundry subaccount where API Management, API portal is enabled. Now, the application on Neo can call API Management proxy using OAuth2SAMLBearer destination. For step-by-step details, see [Principal Propagation from the Neo to the Cloud Foundry Environment](principal-propagation-from-the-neo-to-the-cloud-foundry-environment-da0e97b.md).
-   **Principal Propagation from the same Cloud Foundry subaccount**: Enable an application in your subaccount in the Cloud Foundry environment to access an API Management proxy created on the same Cloud Foundry based API Management without a user login. The JWT user token in your application can be exchanged with the API Management token using the Service Key credentials created for API Management. The application on Cloud Foundry can call API Management proxy using OAuth2UserTokenExchange destination. For step-by-step details, see [Principal Propagation from the Same Cloud Foundry Subaccount](principal-propagation-from-the-same-cloud-foundry-subaccount-0e3d3e7.md).

**Related Information**  


[Accessing On-Premise Systems through API Management](../accessing-on-premise-systems-through-api-management-2fc7a5b.md "The on-premise-connectivity plan helps in achieving principal propagation while connecting to an on-premise backend system.")

