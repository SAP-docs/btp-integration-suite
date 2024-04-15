<!-- loio6d15ffd6cc2147579be240d6aa8d3f29 -->

# Tenant Cloning Tool Behavior

This topic describes the behavior of the Tenant Cloning Tool with respect to cloning some of the entities from your source system.



-   If you add or modify an entity in your source system, it is always cloned to the target system in your subsequent run of the Tenant Cloning Tool.
-   If you add a new entity to your target system at any point, it is retained in the target system after the subsequent run of the Tenant Cloning Tool, irrespective of whether the entity is present in your source system or not.
-   Newer state of an existing entity present in your source system is always migrated to the target system after the subsequent run of the Tenant Cloning Tool, and overwrites any older state of the entity in the target.
-   During the cloning of the Developer Portal entity `Application Developer`, the app developer receives email notifications while being onboarded to the target Developer Portal.

    We recommend that you inform your developers about the impending migration and email notifications that they might receive during the process.

-   Custom Charts are cloned to the target as many times as you run the Tenant Cloning Tool.
-   All the API proxies are cloned onto the default virtual host.
-   Post cloning, the API proxies on the target system are in active and deployed state. You must reapply the desired states to the proxies.

    To know more about API proxy states, see [API Proxy States](../api-proxy-states-091cda4.md).

    > ### Note:  
    > If the Tenant Cloning Tool is used to clone an API proxy or a product with more than 100 resources attached to it, you might notice data inconsistency in the target system \(API business hub enterprise or \). It is recommended that you do not add more than 100 resources per proxy or product. For more information, see [Limits in API Management](../limits-in-api-management-f70f425.md).
    > 
    > .

-   Cloning of custom chart is now supported for migrating API Management content created using the Starter Plan service instance.


> ### Note:  
> Known constraints of migrating applications:
> 
> **Use Case 1**:
> 
> You are migrating application A1, subscribed to a product P1 with no rate plans. You associate product P1 with a rate plan later in the source.
> 
> Now if you attempt to migrate application A1 from the source developer portal to the target developer portal, the application created in the target fails with an error.
> 
> **Reason for the error**: During migration, the product gets cloned along with the newly added rate plan in the target tenant. However, while creating the application in the target tenant, the system couldn't locate the rate plan ID. The rate plan ID was not present in the payload as it belonged to an older subscription, resulting in application creation failure.
> 
> **Use Case 2**:
> 
> You already have a rate plan attached to a product P1 while creating application A1. However, you decide to add a revised rate plan to product P1 after application A1 gets created. In such a scenario, application A1 will continue to have a rate plan that was present during the creation of the application. If you migrate application A1 from the source developer portal to the target developer portal, application creation will fail, and the same error as Use Case 1 will get generated.
> 
> **Reason for the error**: During migration, the product gets cloned along with the newly revised rate plan in the target tenant. However, while creating the application in the target tenant, the system couldn't locate the revised rate plan ID. The revised rate plan ID was not present in the payload as it belonged to an older subscription, resulting in application creation failure.

> ### Note:  
> CacheResources cloning is currently not supported via the Tenant Cloning Tool. You must create it manually on the target using the following service: `<apiportal-host>/apiportal/api/1.0/Management.svc/CacheResources`.

