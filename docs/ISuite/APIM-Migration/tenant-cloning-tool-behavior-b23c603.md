<!-- copyb23c603a651e408fbaafc7c5a09ba9a5 -->

# Tenant Cloning Tool Behavior

This topic describes the behavior of the Tenant Cloning Tool with respect to cloning some of the entities from your source system.



-   If you add or modify an entity in your source system, it is always cloned to the target system in your subsequent run of the Tenant Cloning Tool.
-   If you add a new entity to your target system at any point, it is retained in the target system after the subsequent run of the Tenant Cloning Tool, irrespective of whether the entity is present in your source system or not.
-   Newer state of an existing entity present in your source system is always migrated to the target system after the subsequent run of the Tenant Cloning Tool, and overwrites any older state of the entity in the target.
-   During the cloning of the Developer Portal entity `Application Developer`, the app developer receives email notifications while being onboarded to the target Developer Portal.

    We recommend that you inform your developers about the impending migration and email notifications that they might receive during the process.

-   Custom Charts are cloned to the target SAP Integration Suite as many times as you run the Tenant Cloning Tool.
-   All the API proxies are cloned onto the default virtual host.
-   Post cloning, the API proxies on the target system are in active and deployed state. You must reapply the desired states to the proxies.

    To know more about API proxy states, see [API Proxy States](../50-Development/api-proxy-states-091cda4.md).

    > ### Note:  
    > If the Tenant Cloning Tool is used to clone an API proxy or a product with more than 100 resources attached to it, you might notice data inconsistency in the target system \(Developer Hub or SAP Integration Suite\). It is recommended that you do not add more than 100 resources per proxy or product. For more information, see [Limits in API Management](../limits-in-api-management-f70f425.md).
    > 
    > .

-   Cloning of custom chart is now supported for migrating API Management content created using the Starter Plan service instance.

-   During migration, the product state from the source system, which reflects the number of API proxies linked to the product, overrides the product state in the target system. For instance, if Product P1 has API proxies A1 and A2, and in the target system, Product P1 only has API proxy A1, then after migrating, Product P1 will have API proxies A1 and A2 in the target state.

-   When migrating, consider bills from both the source and target systems when computing the developer's product usage. For instance, if the migration took place from the source system on the 10th of a particular month, you must take into account the billing in the source system from the 1st to the 10th, and the billing in the target system from the 11th to the end of the month \(either the 30th or 31st, depending on the month\).

-   During migration, the Key Value Map keys and values from the source override those in the target.

-   In Neo environment, API Management APIs are accessed programmatically using basic authentication. While on Cloud Foundry, these APIs are accessed programmatically using the API access plan. For more info, see [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).


> ### Note:  
> Non-SNI clients are not supported in Cloud Foundry.

