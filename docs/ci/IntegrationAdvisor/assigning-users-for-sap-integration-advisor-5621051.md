<!-- loio562105156287463293dfcbee16ab8c43 -->

# Assigning Users for SAP Integration Advisor



<a name="loio562105156287463293dfcbee16ab8c43__prereq_htc_mxm_qcb"/>

## Prerequisites

You have subscribed to SAP Integration Advisor. For more information, see [Subscribing to SAP Integration Advisor](subscribing-to-sap-integration-advisor-6a18444.md).

You have the authgroup, *Authgroup.Administrator* assigned to your user. This is mandatory for being able to assign users for the application. If you do not have this role, please contact your administrator for assigning users or obtaining the administrator role.



## Context

After subscribing to Integration Advisor from the SAP BTP cockpit, you have to assign the roles *Guidelines.ReadWrite* and *TypeSystem.Read* to the users who want to access the application. This will allow them to use SAP Integration Advisor.

Here's how you can do it:



## Procedure

1.  Log in to the SAP BTP cockpit.

2.  Choose *Subscriptions*.

    You see a list of the Java applications and HTML5 applications that you have subscribed to.

3.  In the *Subscribed Java Applications* table, choose *icaapp*.

4.  Perform the following substeps to assign a role to a user:

    1.  Choose the role that you want to assign to a user or a group.

        You can choose the role *Guidelines.ReadWrite* or *TypeSystem.Read* from the *Roles* table.

        > ### Note:  
        > If you want to assign admin role to an user, then add the role *Guidelines.Administrator* to the user.

    2.  If you want to assign the role to an individual user, choose *Assign* in the *Individual Users* screen area. Enter the ID of the user and choose *Assign*.

    3.  If you want to assign the role to a group, choose *Assign* in the *Groups* screen area. Select the group from the dropdown list and choose *Assign*.

        You can manage groups by choosing *Security* \> *Authorizations* \> *Groups* after logging into the SAP BTP cockpit. For more information on managing users and groups, see [Authorizing Users or User Groups](../InitialSetup/authorizing-users-or-user-groups-c91046c.md).



