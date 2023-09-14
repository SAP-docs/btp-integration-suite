<!-- loio68071199dcd047d180b1bceb83016d81 -->

# Enabling and Configuring a Tenant

Enable the Cloud Integration service for provisioning a tenant in Cloud Integration and use this procedure to activate enterprise messaging for JMS capabilities.



## Context

The tenant administrator performs these tasks before provisioning a tenant to host services in Cloud Integration.

> ### Note:  
> The following tasks are only required if you have purchased a consumption-based license model.



## Procedure

1.  From the newly created subaccount navigate to *Services* \> *Service Marketplace* and then choose the *Process Integration* tile.

2.  On the service page, choose *Create* for creating your instance or subscription.

    > ### Note:  
    > Once you have enabled the service, a new subscription is created for the provision application.

3.  The green *Enabled* badge appears.

4.  On the service page, choose *Configure Process Integration* to configure and provision a tenant.

5.  Select the required environment for the tenant.

6.  Choose *Provision* and wait for a few minutes until the provisioning task is complete.

    > ### Note:  
    > Consumption-based account holders must always create a new account to provision a new tenant. The tenant administrator cannot provision a new tenant for an existing account.

7.  **\(Optional\)** Use the *Enterprise Messaging* service to design and deploy integration flows configured with JMS capabilities such as JMS and AS2 adapters. Perform the steps below to activate the service for processing messages asynchronously:

    1.  Go to the *Enterprise Messaging* tab, and choose *Activate*.

    2.  *Activate* to start the service and wait for a few minutes until the task is complete.


8.  \(Optional\) You can choose to edit an existing tenant environment based on your operational needs.

    > ### Note:  
    > For Non-Production Cloud Integration tenants, as per contract, billing will include only Cloud Integration instance charges and additional connections will not be billed. For more information, see [2784487](https://me.sap.com/notes/2784487).




<a name="loio68071199dcd047d180b1bceb83016d81__postreq_anp_mcc_wcb"/>

## Next Steps

Once the tenant is activated, you need to assign the roles on the tenant before choosing *Go to Service*. For information about how to assign users and grant them the necessary user roles, see [Assigning Users and Roles](assigning-users-and-roles-73af55c.md).

> ### Posting Instructions:  
> After you have assigned the user roles, launch a new browser instance to access the service page of the subaccount. Then choose *Go to Service* to access the tenant.

**Related Information**  




[Managing Users and Role Assignments, Neo Environment](../Operations/managing-users-and-role-assignments-neo-environment-1d470b0.md "You specify the members of the account and assign roles to them.")

