<!-- loio9778a3601dee498e875cf81fa47e65ce -->

# Migrating API Management Subscription Created Using the Starter Plan Service Instance

You can choose to migrate the design-time components that you have in the Neo environment, which was previously set up using Starter Plan instance, to the multi-cloud foundation, keeping the runtime components as is.



<a name="loio9778a3601dee498e875cf81fa47e65ce__context_qmw_v5b_xpb"/>

## Context

You can also enable the new API Management design time subscription on the same multi-cloud foundation subaccount, where you have created the starter plan service instance.

> ### Note:  
> You must subscribe to the API portal and the Developer Hub in the same multi-cloud foundation subaccount where the starter plan instance is created.
> 
> Tenant type \(for example, production and test\) of the newly onboarded API Management on the multi-cloud foundation must be same as that of the source API Management on the Neo environment.

> ### Caution:  
> The migration of the Starter Plan Service Instance might involve downtime of the API runtime calls.



<a name="loio9778a3601dee498e875cf81fa47e65ce__steps_y1l_cvb_xpb"/>

## Procedure

1.  Raise a ticket through the [SAP Support Portal](https://support.sap.com/en/index.html). For more information, see [Product Support](https://support.sap.com/en/my-support/product-support.html).

    Use the following component for your incident:


    <table>
    <tr>
    <th valign="top">

    Component Name
    
    </th>
    <th valign="top">

    Component Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    OPU-API-OD-OPS
    
    </td>
    <td valign="top">
    
    SAP API Management Operations - On Demand
    
    </td>
    </tr>
    </table>
    
    When submitting the incident, include the following information:

    -   Incident title: Starter Plan Migration

    -   Description: State that you want to migrate API Management subscription created using the Starter Plan.

    -   Provide the Neo account details where API Management is enabled.

    -   Provide the multi-cloud foundation account details where starter plan service instance is created.


    > ### Note:  
    > Once you receive a confirmation from SAP on the ticket, you can resume the migration process from step 2.

2.  Prepare the target system by enabling the API Management subscription on the multi-cloud foundation subaccount where your starter plan instance was created.

    To complete the checks, before you start migrating your API Management artifacts nondisruptively from your source system to a target system, see [Prerequisites](prerequisites-c1904bc.md).

3.  Run the Tenant Cloning Tool in the DEFAULT stage. See [Clone API Management Content](clone-api-management-content-7abd887.md) for more information.

    For the list of cloned and uncloned entities, see [Cloned and Uncloned Entities](cloned-and-uncloned-entities-8973ca0.md). For understanding the behavior of the Tenant Cloning Tool with respect to cloning some of the entities from your source system, see [Tenant Cloning Tool Behavior](tenant-cloning-tool-behavior-6d15ffd.md).

    > ### Note:  
    > Since this is starter plan migration scenario, only the API portal artifacts at this stage get cloned.

4.  After completing the cloning process, you must perform some actions, checks, and validations. For the task details, see [Post Cloning Tasks](post-cloning-tasks-116d82c.md).

    For recommendations for migration, refer the following topic: [Recommendations](recommendations-ff61cef.md) 

    To know more about the security features of the tenant cloning tool, see [Security Features of the Tenant Cloning Tool](security-features-of-the-tenant-cloning-tool-a6969cc.md).

5.  Run the Tenant Cloning Tool in the SWITCHOVER stage. For more information, see [Clone API Management Content](clone-api-management-content-7abd887.md).

    > ### Note:  
    > If applicable, Developer Hub entities are cloned in this step.

6.  After the SWITCHOVER, if you have any API Provider of the type onpremise, provide the Basic Auth password in the target system. For more information, see "API Provider Credentials" under *User Actions* in [Post Cloning Tasks](post-cloning-tasks-116d82c.md).

    > ### Note:  
    > If you skip this step, the test connection on the particular on-prem provider will fail. Also, the discovery of the on-prem providers will fail. Therefore, please ensure that you complete this step before proceeding.

7.  Inform SAP that migration is complete by updating the same ticket.

    > ### Note:  
    > If you encounter any issues during the migration process, you can report and track the updates in the same ticket. Therefore, we recommend that you keep the ticket open until you reach step 6.




<a name="loio9778a3601dee498e875cf81fa47e65ce__result_czj_hds_ypb"/>

## Results

Migration of API Management subscription created using the Starter Plan service instance is complete.There can be downtime for certain API proxies \(having policies that are specific to Neo/ multi-cloud foundation\) created out of on-premise providers.

