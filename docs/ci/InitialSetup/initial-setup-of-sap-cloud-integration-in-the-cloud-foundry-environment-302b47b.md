<!-- loio302b47b11e1749c3aa9478f4123fc216 -->

# Initial Setup of SAP Cloud Integration in the Cloud Foundry Environment

Quickly get started with SAP Cloud Integration in the Cloud Foundry \(CF\) environment.

> ### Note:  
> You can't subscribe to Process Integration or Cloud Integration service independently anymore. To provide a comprehensive integration experience, Cloud Integration is only available as a capability of the SAP Integration Suite. For a new subscription of Cloud Integration, subscribe to SAP Integration Suite. See: [Initial Setup of SAP Integration Suite](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/3dcf507f92f54597bc203600bf8f94c5.html?version=CLOUD).



<a name="loio302b47b11e1749c3aa9478f4123fc216__section_d5l_rm4_hvb"/>

## Trial Account

Trial accounts are intended for personal exploration, and not for production use or team development. The features included in a trial account are limited, compared to an enterprise account. Consider the following before using a trial account:

-   Every trial user gets one trial account only.
-   Cloud Foundry trial accounts expire after 30 days. You can extend the trial period to a maximum of 90 days, after which your account is automatically deleted.
-   Usage of runtime resources are limited only for functional evaluations. Processing of large message payloads is not supported.
-   A subaccount in your trial account is created automatically. Each subaccount is associated with exactly one Cloud Foundry organization in which you can create additional spaces.
-   You can manage members in your trial account.
-   You can activate SAP Event Mesh with limited capabilities.
-   You can use production and beta services in trial accounts.
-   A trial account includes 4 GB of memory for applications.
-   You can use 8 GB of instance memory.
-   SAP does not provide support to establish secure connection using private keys and authentication based on inbound client certificate. It’s recommended to use basic authentication for allowing a client to authenticate itself against the CF server based on user credentials \(`clientid` and `clientsecret`\)
-   You can use a maximum number of 10 JMS queues.
-   There is no service level agreement with regards to the availability of the platform.

For more information, see [Trial Accounts and Free Tier](https://help.sap.com/docs/btp/sap-business-technology-platform/trial-accounts-and-free-tier).

**Related Information**  


[Subscribing to Process Integration](subscribing-to-process-integration-3fa2bd2.md "Subscribe to the Process Integration application from the Subscriptions page in the SAP BTP cockpit.")

[Configuring User Access to Cloud Integration](configuring-user-access-to-cloud-integration-ed6033b.md "Create and modify application roles and assign users to these roles.")

[Provisioning the Tenant](provisioning-the-tenant-7439b3c.md "Provision a Cloud Integration tenant and receive a consumer-specific URL to access the application.")

[Creating Service Instances](creating-service-instances-883f025.md "Create Process Integration runtime service instances to access the endpoints after deploying the integration flows.")

