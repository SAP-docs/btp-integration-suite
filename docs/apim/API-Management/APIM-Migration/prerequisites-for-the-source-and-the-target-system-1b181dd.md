<!-- loio1b181dd730264f928b97878927ceba41 -->

# Prerequisites for the Source and the Target System

Checks to be completed before you start migrating your API Management artifacts nondisruptively from your source system to a target system.



Both the source and the target system are the system that has your API Management subscription on the hyperscalers-managed infrastructure within the Cloud Foundry environment.





### Prerequisites for the source system

-   You must have a valid API Management system \(API portal and API business hub enterprise\) running in the Cloud Foundry environment.
-   The source system must support Oauth client credentials for Cloud Foundry. You need the auth token url and key secret to access the API portal and API business hub enterprise. For more information, refer [API Access Plan for API Portal](../APIM-Initial-Setup/api-access-plan-for-api-portal-24a2c37.md) and [API Access Plan for API business hub enterprise](../APIM-Initial-Setup/api-access-plan-for-api-business-hub-enterprise-dabee6e.md)
-   Make a note of the API portal and API business hub enterprise URLs of the source system and keep handy.
-   Ensure that API access is enabled for the API portal and API business hub enterprise systems for the following roles:

    -   APIPortal.Administrator role in the API portal
    -   AuthGroup.API.Admin role in the API business hub enterprise

    The client id, client secret are used while filling in the details of the `apim-tct-input.json` file before running the Tenant Cloning Tool. See [Clone API Management Artifacts](clone-api-management-artifacts-7abd887.md).

    > ### Note:  
    > During Cloud Foundry to Cloud Foundry migration, the default input.json shipped with Tenant Cloning Tool maven zip bundle has username and password as the source field. Please ensure that you change this to token URL, clientId, and client secret as mentioned in the sample configuration in [Clone API Management Artifacts During Cloud Foundry to Cloud Foundry Migration](clone-api-management-artifacts-during-cloud-foundry-to-cloud-foundry-migration-2e5d127.md).




### Prerequisites for the target system

-   If API Management isn’t already enabled on your target system, complete the setup. See [Initial Setup](../APIM-Initial-Setup/initial-setup-65c5110.md).

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
    
        You can’t use this subaccount for migration. Create a new subaccount in the hyperscalers-managed infrastructure within the cloud foundry environment and enable API Management on that subaccount for it to act as your target system.

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
    
    You can also consider the "Possible Migration Paths" table in [Migrating API Management Subscription from One Cloud Foundry to Same or Different Cloud Foundry Environment](migrating-api-management-subscription-from-one-cloud-foundry-to-same-or-different-c-17f09f3.md) to choose the target subscription type.

    If you have already enabled API Management on your target system, and want to reuse the same for migration, you can refer the following recommendations:

    -   It's recommended that you don’t have any pre-existing entities such as API proxies or products on this system.

        > ### Note:  
        > Any entity, if pre-existing in your target API Management subscription, can be over-written during the cloning process.


-   If your target system is connected to a custom IDP, ensure that your IDP is configured correctly, and mapping for the details like your first name, last name, email ID, and user ID is done.

    > ### Note:  
    > Please ensure that the application developer’s attributes, like first name, last name, email ID, and user ID, are identical in both source and target identity providers. In API Management, the application developer’s attributes are case-sensitive.
    > 
    > Consider the following example: During cloning, the email address `john.smith@abc.com` in the source becomes `John.Smith@abc.com` in target due to the change in configurations in Custom IDP. This mismatch might lead to data discrepancy during application creation and metering in the target after cloning.

-   Ensure that API access is enabled for the API portal and the API business hub enterprise for the following roles:

    -   APIPortal.Administrator role in the API portal
    -   AuthGroup.API.Admin role in the API business hub enterprise

    Note the service keys \(***url***, ***tokenurl***, ***clientId***, and ***clientSecret***\) for the given roles, and keep handy.

    To know more about API access plan for API portal, see [API Access Plan for API Portal](../APIM-Initial-Setup/api-access-plan-for-api-portal-24a2c37.md).

    To know more about API access plan for API business hub enterprise, see [API Access Plan for API business hub enterprise](../APIM-Initial-Setup/api-access-plan-for-api-business-hub-enterprise-dabee6e.md).

    Follow the steps in [API Access Plan for API business hub enterprise](../APIM-Initial-Setup/api-access-plan-for-api-business-hub-enterprise-dabee6e.md), without which the cloning of the API business hub enterprise entities might fail.

-   When you have API Products protected by the custom roles permission in the source Cloud Foundry system, ensure that custom roles creation and assignments are done in the target Cloud Foundry environment before starting the migration.


Once you complete these checks, you can start cloning your API Management artifacts from the source to the target system. See [Clone API Management Artifacts During Cloud Foundry to Cloud Foundry Migration](clone-api-management-artifacts-during-cloud-foundry-to-cloud-foundry-migration-2e5d127.md).

