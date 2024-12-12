<!-- loio6d15ffd6cc2147579be240d6aa8d3f29 -->

# Tenant Cloning Tool Behavior

This topic describes the behavior of the Tenant Cloning Tool with respect to cloning some of the entities from your source system.



-   If you add or modify an entity in your source system, it is always cloned to the target system in your subsequent run of the Tenant Cloning Tool.
-   If you add a new entity to your target system at any point, it is retained in the target system after the subsequent run of the Tenant Cloning Tool, irrespective of whether the entity is present in your source system or not.
-   Newer state of an existing entity present in your source system is always migrated to the target system after the subsequent run of the Tenant Cloning Tool, and overwrites any older state of the entity in the target.
-   During the cloning of the Developer Portal entity `Application Developer`, the app developer receives email notifications while being onboarded to the target Developer Portal.

    We recommend that you inform your developers about the impending migration and email notifications that they might receive during the process.

-   Custom Charts are cloned to the target Integration Suite as many times as you run the Tenant Cloning Tool.
-   All the API proxies are cloned onto the default virtual host.
-   Post cloning, the API proxies on the target system are in active and deployed state. You must reapply the desired states to the proxies.

    To know more about API proxy states, see [API Proxy States](../50-Development/api-proxy-states-091cda4.md).

    > ### Note:  
    > If the Tenant Cloning Tool is used to clone an API proxy or a product with more than 100 resources attached to it, you might notice data inconsistency in the target system \(Developer Hub or Integration Suite\). It is recommended that you do not add more than 100 resources per proxy or product. For more information, see [Limits in API Management](../limits-in-api-management-f70f425.md).
    > 
    > .

-   Cloning of custom chart is now supported for migrating API Management content created using the Starter Plan service instance.


