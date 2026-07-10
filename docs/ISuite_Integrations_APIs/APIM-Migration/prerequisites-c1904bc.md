<!-- loioc1904bc5015641d8bc1a49a2dd9b492d -->

# Prerequisites

Checks to be completed before you start migrating your API Management content nondisruptively from your source system to a target system.



-   Your source system is the system that has your API Management subscription in the Neo environment.

-   Your target system is the system that has your API Management content on the hyperscalers-managed infrastructure within the multi-cloud foundation.






### Prerequisites for the source system

-   You must have a valid API Management system \(API portal and Developer Hub\) running in the Neo environment.
-   The source system must support basic authentication for API access on SAP Integration Suite and Developer Hub\(which is the developer portal\).
-   Make a note of the SAP Integration Suite and Developer Hub\(developer portal\) URLs of the source system and keep it handy.
-   You must have identified a user with the following roles assigned in your source systems:

    -   APIPortal.Administrator
    -   AuthGroup.API.Admin role

    Keep the credentials of this user handy. These credentials are used while filling in the details of the `apim-tct-input.json` file before running the Tenant Cloning Tool. See [Clone API Management Content](clone-api-management-content-7abd887.md).




### Prerequisites for the target system

-   If API Management is not already enabled on your target system, complete the set-up. See [Initial Setup](https://help.sap.com/docs/integration-suite/sap-integration-suite/initial-setup?state=DRAFT&version=CLOUD) and [Enable API Management Capability](https://help.sap.com/docs/integration-suite/sap-integration-suite/enabling-api-management-capability-from-integration-suite?state=DRAFT&version=CLOUD).

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

    Additionally, if you want to reuse the existing runtime then follow the steps mentioned in the [Migrating API Management Subscription Created Using the Starter Plan Service Instance](migrating-api-management-subscription-created-using-the-starter-plan-service-instance-9778a36.md).
    
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
    
-   If you have already enabled API Management on your target system, and want to reuse the same for migration, it's recommended that you do not have any pre-existing entities such as API proxies or products on this system.

    > ### Note:  
    > Any entity, if pre-existing in your target API Management capability, can be over-written during the cloning process.

-   If your target system is connected to a custom IDP, ensure that your IDP is configured correctly, and mapping for the details like your first name, last name, email ID, and user ID is done.

    > ### Note:  
    > Please ensure that the application developer’s attributes, like first name, last name, email ID, and user ID, are identical in both source and target identity providers. In API Management, the application developer’s attributes are case-sensitive.
    > 
    > Consider the following example: During cloning, the email address `john.smith@abc.com` in the source becomes `John.Smith@abc.com` in target due to the change in configurations in Custom IDP. This mismatch might lead to data discrepancy during application creation and metering in the target after cloning.

-   Ensure that API access is enabled for the SAP Integration Suite and the Developer Hub\(developer portal\) for the following roles:

    -   APIPortal.Administrator
    -   AuthGroup.API.Admin

    For SAP Integration Suite, see [Accessing API Management APIs Programmatically](https://help.sap.com/docs/integration-suite/sap-integration-suite/api-access-plan-for-api-portal?version=CLOUD)

    For Developer Hub, execute the following mandatory steps:

    -   Make a note of the service keys \(`url`, `tokenurl`, `clientId`, and `clientSecret`\) for the given roles, and keep handy.

    -   Create a service instance under the *Authorization and Trust Management* tile.

    -   Create a destination of type *OAuth2Credentials* to the XSUAA APIs by using the credentials you derived from creating the service key.

    -   Create a service instance with the *AuthGroup.API.Admin* role to access theDeveloper Hub APIs.

        To perform the above steps, see [Accessing Developer Hub APIs Programmatically](../accessing-developer-hub-apis-programmatically-dabee6e.md).


-   When you have API products protected by the custom roles permission in the source Neo system, ensure that custom roles creation and assignments are done in the target system within the multi-cloud foundation before starting the migration.


Once you complete these checks, you can start cloning your API Management content from the source to the target system. See [Clone API Management Content](clone-api-management-content-7abd887.md).

