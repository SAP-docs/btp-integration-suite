<!-- loioa0f5fe580ed846ca95f8601678509add -->

# Shadow Users

Whenever a user authenticates at an application in your subaccount using any identity provider, it’s essential that user-related data provided by the identity provider is stored in the form of shadow users.

Previously, the user account and authentication service allowed any user of any connected identity provider to authenticate to applications in the subaccount. When there was no corresponding shadow user, it automatically created one based on the information received from the identity provider.

With new subaccounts created after 24 September 2020, automatic creation of shadow users is switched off by default for the default identity provider, SAP ID service. You can enable or disable automatic shadow user creation using the information [here](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d8525671e8b14147b96ef497e1e1af80.html).

Since automatic shadow user creation is disabled, if you've not explicitly created shadow users for your developers, then they’re unable to log on to the application, and they’re asked to contact the administrator.

You can create the shadow users for your developers in the SAP BTP cockpit, typically when you assign the first role collection to them. For more information on role collection assignment, see [Assigning Role Collections to Users or User Groups](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/31532c77bd61421e9d40d100fd75ef52.html).

For information on creating shadow accounts, see [Add Users to SAP ID Service in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/760ab77e5afd4c15ae70ec7ff59e02ef.html).

You can also use the[User Management \(System for Cross-domain Identity Management \(SCIM\)\) API](https://api.sap.com/api/PlatformAPI/resource) to manage you shadow users.

**Related Information**  


[Configuring Additional Virtual Host in Cloud Foundry Environment](configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "A virtual host allows you to host multiple domain names on the API Management capability within SAP Integration Suite.")

[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-683a97c.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from SAP Integration Suite to disable your account from the API Management service.")

[Setting Up API Management with SAP Cloud Identity Services](setting-up-api-management-with-sap-cloud-identity-services-1e88d9c.md "SAP Cloud Platform allows customers to connect their SAP Cloud Identity Services with the BTP offerings.")

