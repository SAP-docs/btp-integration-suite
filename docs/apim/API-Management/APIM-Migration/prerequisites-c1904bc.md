<!-- loioc1904bc5015641d8bc1a49a2dd9b492d -->

# Prerequisites

Checks to be completed before you start migrating your API Management artifacts nondisruptively from your source system to a target system.



Your source system is the system that has your API Management subscription in the Neo environment.

Your target system is the system that has your API Management subscription on the hyperscalers-managed infrastructure within the Cloud Foundry environment.





### Prerequisites for the source system

-   You must have a valid API Management system \(API portal and Developer Portal\) running in the Neo environment.
-   The source system must support basic authentication for API access on API portal and Developer Portal.
-   Note the API portal and Developer Portal URLs of the source system and keep handy.
-   You must have identified a user with the following roles assigned in your source API portal and Developer Portal systems:

    -   APIPortal.Administrator role in the API portal
    -   AuthGroup.API.Admin role in the Developer Portal

    Keep the credentials of this user handy. These credentials are used while filling in the details of the `apim-tct-input.json` file before running the Tenant Cloning Tool. See [Clone API Management Artifacts](clone-api-management-artifacts-7abd887.md).




### Prerequisites for the target system

-   If API Management is not already enabled on your target system, complete the set-up. See [Initial Setup](../APIM-Initial-Setup/initial-setup-65c5110.md).

    Check whether the API Management service broker service instance is created with the Starter Plan in the same subaccount.


    <table>
    <tr>
    <th valign="top">

    Service Instance for Starter Plan in the Subaccount
    
    </th>
    <th valign="top">

    Instruction
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Already present
    
    </td>
    <td valign="top">
    
    You cannot use this subaccount for migration. Create a new subaccount in the hyperscalers-managed infrastructure within the cloud foundry environment and enable API Management on that subaccount for it to act as your target system.

    Additionally, if you want to reuse the existing runtime then follow the steps mentioned in the [Migrating API Management Subscription Created Using the Starter Plan Service Instance](migrating-api-management-subscription-created-using-the-starter-plan-service-instan-9778a36.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Not present
    
    </td>
    <td valign="top">
    
    You can choose to reuse this account as your target system for migration, or create a new subaccount.
    
    </td>
    </tr>
    </table>
    
    If you have already enabled API Management on your target system, and want to reuse the same for migration:

    -   It's recommended that you do not have any pre-existing entities such as API proxies or products on this system.

        > ### Note:  
        > Any entity, if pre-existing in your target API Management subscription, can be over-written during the cloning process.


-   If your target system is connected to a custom IDP, ensure that your IDP is configured correctly, and mapping for the details like your first name, last name, email ID, and user ID is done.

    > ### Note:  
    > Please ensure that the application developer’s attributes, like first name, last name, email ID, and user ID, are identical in both source and target identity providers. In API Management, the application developer’s attributes are case-sensitive.
    > 
    > Consider the following example: During cloning, the email address `john.smith@abc.com` in the source becomes `John.Smith@abc.com` in target due to the change in configurations in Custom IDP. This mismatch might lead to data discrepancy during application creation and metering in the target after cloning.

-   Ensure that API access is enabled for the API portal and the Developer Portal for the following roles:

    -   APIPortal.Administrator role in the API portal
    -   AuthGroup.API.Admin role in the Developer Portal

    Note the service keys \(`url`, `tokenurl`, `clientId`, and `clientSecret`\) for the given roles, and keep handy.

    To know more about API access plan for API portal, see [API Access Plan for API Portal](../APIM-Initial-Setup/api-access-plan-for-api-portal-24a2c37.md).

    To know more about API access plan for Developer Portal, see [API Access Plan for API business hub enterprise](../APIM-Initial-Setup/api-access-plan-for-api-business-hub-enterprise-dabee6e.md).

    Follow the steps in [API Access Plan for API business hub enterprise](../APIM-Initial-Setup/api-access-plan-for-api-business-hub-enterprise-dabee6e.md), without which the cloning of the Developer portal entities might fail.

-   When you have API Products protected by the custom roles permission in the source Neo system, ensure that custom roles creation and assignments are done in the target Cloud Foundry environment before starting the migration.


Once you complete these checks, you can start cloning your API Management artifacts from the source to the target system. See [Clone API Management Artifacts](clone-api-management-artifacts-7abd887.md).

