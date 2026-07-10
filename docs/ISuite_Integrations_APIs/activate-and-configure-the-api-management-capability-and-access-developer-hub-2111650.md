<!-- loio21116500df4a4b59b026e9008f8157f9 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Activate and Configure the API Management Capability and Access Developer Hub

Steps to activate and configure the API Management capability in SAP Integration Suite and access Developer Hub from SAP Integration Suite home page.


<table>
<tr>
<th valign="top">

Steps

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Subscribe to SAP Integration Suite 

</td>
<td valign="top">

To set up the API Management capability from SAP Integration Suite, you should first have an Integration Suite subscription.

Subscribe to SAP Integration Suite in SAP BTP cockpit and assign yourself the *Integration\_Provisioner* role collection to gain access. For more information, see [Getting Started with SAP Integration Suite](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/3dcf507f92f54597bc203600bf8f94c5.html "Get onboarded to SAP Integration Suite.") :arrow_upper_right:.

> ### Note:  
> Please make sure that you do not have a starter plan instance created in the same subaccount where you intend to create an Integration Suite subscription. Additionally, please note that API Management capabilities from SAP Integration Suite and API Management subscriptions using the stand-alone tile cannot coexist in the same subaccount.



</td>
</tr>
<tr>
<td valign="top">

Activate the API Management capability

</td>
<td valign="top">

1.  On the Integration Suite home page, go to *Capabilities* and select *Add Capabilities*.
2.  To design, develop, publish, and oversee APIs in a secure and scalable environment, choose *Manage APIs* and choose *Next*.

    On the next screen, the *API Modelling* checkbox appears, and is enabled by default.

3.  To discover, consume and monitor APIs from a centralized API catalogue, select the *Developer Hub* checkbox.
4.  For exposing data as a connected graph, select *API Composition* checkbox.
5.  Once all desired capabilities are selected, choose *Review*.
6.  Review the details and choose *Activate*.

![](images/SUI_API_e159e2f.png)

For more information, see:

-   [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?version=CLOUD)
-   [API Composition](https://help.sap.com/docs/api-composition/isuite-api-composition/what-is-api-composition?version=CLOUD)



</td>
</tr>
<tr>
<td valign="top">

Configure the API Management capability for Integration Cell

</td>
<td valign="top">

To configure the system for Integration Cell Runtime, you must first activate it. For more information, see [Activate Integration Cell](activate-integration-cell-1a627da.md).

</td>
</tr>
<tr>
<td valign="top">

Access Developer Hub

</td>
<td valign="top">

From the Integration suite home page, choose the <span class="SAP-icons-V5"></span> product switcher icon and select *Developer Hub*. For this option to appear in the product switcher within Integration Suite, *Integration\_Provisioner* role collection must be assigned to you and *Developer Hub* must be activated.

> ### Note:  
> To access Developer Hub, the *AuthGroup.SelfService.Admin* role must me assigned to you. This is an one time activity.
> 
> Please be aware that the *Authgroup.API.Admin* role is required for onboarding into Developer Hub. This role will be automatically assigned to your scope once you have been assigned the *AuthGroup.SelfService.Admin* role. After the onboarding process is completed, it is necessary for an admin to assign the *AuthGroup.Content.Admin* role to a user in order to access and discover the APIs from different business systems in Developer Hub. For more information, see [User Roles and Responsibilities in Developer Hub](user-roles-and-responsibilities-in-developer-hub-54b4607.md).



</td>
</tr>
</table>

