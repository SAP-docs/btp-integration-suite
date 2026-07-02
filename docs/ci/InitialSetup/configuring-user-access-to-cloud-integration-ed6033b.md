<!-- loioed6033b2eabe4a64a20cce1e6076bacf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configuring User Access to Cloud Integration

Create and modify application roles and assign users to these roles.



<a name="loioed6033b2eabe4a64a20cce1e6076bacf__prereq_nrz_1p1_1gb"/>

## Prerequisites

You're subscribed to Process Integration service in the Cloud Foundry environment.



## Context

As an administrator of SAP Cloud Integration in the Cloud Foundry environment, you can group application roles in role collections. Typically, these role collections provide authorizations for certain types of users. Once you've created a role collection, you pick the roles for that role collection. For more information on role collections, see [Roles and Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/roles-and-role-collections?version=Cloud).

Finally, you assign the role collection to the users provided by the SAP ID service.



## Procedure

1.  Go to your subaccount in SAP BTP cockpit, and choose *Security* \> *Users.*

2.  Choose *Create* to add a new user.

3.  Enter the *User Name* and *E-Mail*, and choose *Create*.

4.  Choose the user and select <span class="SAP-icons-V5"></span> under *Role Collections* section and choose *Assign Role Collection*.

5.  In the resulting dialog box, select the role collections that you want to assign and choose *Assign Role Collection*.

    > ### Note:  
    > Clear your web browser cache and cookies before navigating to *Go to Application*.

    The following role collections are available:

    **Role Collections**


    <table>
    <tr>
    <th valign="top">

    Role Collection
    
    </th>
    <th valign="top">

    You Can...
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Read\_Only*
    
    </td>
    <td valign="top">
    
    See [Read-only Persona](../SecurityNeo/personas-2937e5c.md#loio2937e5ca6ef448cfb21451a2461cc2a6__read)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Business\_Expert*
    
    </td>
    <td valign="top">
    
    See [Business Expert Persona](../SecurityNeo/personas-2937e5c.md#loio2937e5ca6ef448cfb21451a2461cc2a6__bus)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Integration\_Developer*
    
    </td>
    <td valign="top">
    
    See [Integration Developer Persona](../SecurityNeo/personas-2937e5c.md#loio2937e5ca6ef448cfb21451a2461cc2a6__dev)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Administrator*
    
    </td>
    <td valign="top">
    
    See [Tenant Administrator Persona](../SecurityNeo/personas-2937e5c.md#loio2937e5ca6ef448cfb21451a2461cc2a6__admin)
    
    </td>
    </tr>
    </table>
    
    For detailed list of scope and actions for each role, see: [Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md).


