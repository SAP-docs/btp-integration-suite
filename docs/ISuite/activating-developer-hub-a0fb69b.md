<!-- loioa0fb69bf8ccf47b3b8487b64945e42cc -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Activating Developer Hub 

Steps to activate Developer Hub in SAP Integration Suite. Developer Hub is one of the the sub-capabilities of API Management with SAP Integration Suite


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

To set up the API Management capability from SAP Integration Suite, you should first have SAP Integration Suite subscription.

Subscribe to SAP Integration Suite in SAP BTP cockpit and assign the *Integration\_Provisioner* role to gain access. For more information, see [Initial Setup of SAP Integration Suite](10-InitialSetup/initial-setup-of-sap-integration-suite-3dcf507.md).

> ### Note:  
> Please make sure that you do not have a starter plan instance created in the same subaccount where you intend to create an SAP Integration Suite subscription. Additionally, please note that API Management capabilities from SAP Integration Suite and API Management subscriptions using the stand-alone tile cannot coexist in the same subaccount.



</td>
</tr>
<tr>
<td valign="top">

Activate Developer Hub 

</td>
<td valign="top">

Add and activate Developer Hub in SAP Integration Suite. For more information, see [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md).

> ### Note:  
> The Developer Hub checkbox is **not** selected by default if you've subscribed to the premium/standard service plan and have activated API Management.



</td>
</tr>
<tr>
<td valign="top">

Access Developer Hub 

</td>
<td valign="top">

Click on the<span class="SAP-icons-V5"></span> product switcher icon and select Developer Hub.

> ### Note:  
> If you have an SAP Build subscription, the Developer Hub tile appears on the home page under*Quick Links* section. Select the tile to navigate to the Developer Hub web page. Alternatively, you can click on the<span class="SAP-icons-V5"></span> product switcher icon on the page header and select Developer Hub.

> ### Note:  
> To onboard the Developer Hub web page, the *AuthGroup.SelfService.Admin* role must me assigned to you. This is an one time activity.
> 
> Please be aware that the *Authgroup.API.Admin* role is required for onboarding into Developer Hub. This role will be automatically assigned to your scope once you have been assigned the *AuthGroup.SelfService.Admin* role. After the onboarding process is completed, it is necessary for an admin to assign the *Content Administrator* role to a user in order to access and discover the APIs from different business systems in Developer Hub.



</td>
</tr>
</table>

