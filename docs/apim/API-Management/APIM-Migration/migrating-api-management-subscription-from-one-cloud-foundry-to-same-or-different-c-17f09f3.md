<!-- loio17f09f3bd7e04b47a0a7ccfee07f95b4 -->

# Migrating API Management Subscription from One Cloud Foundry to Same or Different Cloud Foundry Environment

You can choose to migrate an existing API Management subscription that you have in one Cloud Foundry environment to another API Management subscription within the Cloud Foundry environment. This can be done to a different tenant within the same data center or to a tenant in a different data center.

> ### Note:  
> Runtime re-use of the tenant is not yet supported.
> 
> At the end of the Cloud Foundry to Cloud Foundry migration, your entities from source Cloud Foundry subscription is cloned to the target Cloud Foundry subscription.

Migration Assistant for asset migration includes the tools and utilities that enable migration of design time assets non-disruptively from the Cloud Foundry to the Cloud Foundry environment.

Your source system is the system that has your API Management subscription in the Cloud Foundry environment.

Your target system is the system that has your API Management subscription infrastructure within the Cloud Foundry environment. Here Cloud Foundry environment can be your native standalone API Management subscription or API Management capability within the Integration Suite.

**Possible Migration Paths**


<table>
<tr>
<th valign="top">

**Source Subscription** 

</th>
<th valign="top">

**Target Subscription** 

</th>
<th valign="top">

**Allowed** 

</th>
</tr>
<tr>
<td valign="top">

Standalone

</td>
<td valign="top">

Standalone

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Standalone

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Standalone

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Yes

</td>
</tr>
</table>

The target system may or may not retain the application key/secret based on the target system runtime cluster. This can be pre checked with OPS via ticket during initial steps.

If the target can't retain the application key/secret then the applications will be created with a new application key/secret in the target system. You must guide your end users to adopt to the change in application key/secret.

Source and target subscription must be in same environment. Both the source and the target subscription must be in production environment or both must be in non-production environment. Cross environment migration is not supported.

You can clone your API Management artifacts non-disruptively from the source to the target system only after completing the steps in the prerequisites section. Post cloning, you must complete some user actions and validate your target system.

> ### Note:  
> The developer portal is renamed to API business hub enterprise in Cloud Foundry environment. In this document API business hub enterprise is referred to as developer portal even in Cloud Foundry environment.

The steps assisting the migration of your API Management from your source system to a target system are:

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

    -   Incident title: API Management Migration from one Cloud Foundry to another Cloud Foundry environment

    -   Description: State that you want to migrate API Management subscription from one Cloud Foundry to another Cloud Foundry environment .

    -   Provide the Cloud Foundry account details where API Management is enabled.

    -   Provide the Cloud Foundry account details where you want to move the data .


    > ### Note:  
    > Once you receive a confirmation from SAP on the ticket, you can resume the migration process from step 2.

2.  Complete all the steps in the Prerequisite section.

3.  Clone the API Management artifacts using the Tenant Cloning tool.

4.  Complete the post cloning tasks.


