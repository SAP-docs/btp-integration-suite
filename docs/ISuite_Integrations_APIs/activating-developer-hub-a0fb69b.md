<!-- loioa0fb69bf8ccf47b3b8487b64945e42cc -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Activating Developer Hub 

Steps to activate Developer Hub in SAP Integration Suite. Developer Hub is one of the the sub-capabilities of API Management with SAP Integration Suite.


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

Subscribe to SAP Integration Suite in SAP BTP cockpit and assign the *Integration\_Provisioner* role to gain access. For more information, see [Getting Started with SAP Integration Suite](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/3dcf507f92f54597bc203600bf8f94c5.html "Get onboarded to SAP Integration Suite.") :arrow_upper_right:.

> ### Note:  
> Please make sure that you do not have a starter plan instance created in the same subaccount where you intend to create an SAP Integration Suite subscription. Additionally, please note that API Management capabilities from SAP Integration Suite and API Management subscriptions using the stand-alone tile cannot coexist in the same subaccount.



</td>
</tr>
<tr>
<td valign="top">

Activate Developer Hub 

</td>
<td valign="top">

Add and activate Developer Hub in SAP Integration Suite. For more information, see [Activating and Managing Capabilities](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/2ffb343c163c48a4b3a90f9f3c487328.html "Activate capabilities for SAP Integration Suite.") :arrow_upper_right:.

> ### Note:  
> The Developer Hub checkbox is **not** selected by default if you've subscribed to the premium/standard service plan and have activated API Management.



</td>
</tr>
<tr>
<td valign="top">

Access Developer Hub 

</td>
<td valign="top">

Click on the <span class="SAP-icons-V5"></span> product switcher icon and select Developer Hub.

> ### Note:  
> If you have an SAP Build subscription, the Developer Hub tile appears on the home page under*Quick Links* section. Select the tile to navigate to the Developer Hub web page. Alternatively, you can click on the <span class="SAP-icons-V5"></span> product switcher icon on the page header and select Developer Hub.

> ### Note:  
> To onboard the Developer Hub web page, you must be assigned the *AuthGroup.SelfService.Admin* role collection. Once this role collection is assigned, only the *AuthGroup.API.Admin* role collection is automatically assigned in the production account, enabling you to onboard additional users.
> 
> This is a one-time activity, and the *AuthGroup.SelfService.Admin* role collection should only be assigned during the initial onboarding process.

> ### Note:  
> If you are using a trial account, the following role collections are assigned automatically:
> 
> -   *AuthGroup.API.Admin*
> -   *AuthGroup.Content.Admin*
> -   *AuthGroup.Site.Admin*
> -   *AuthGroup.ContentAuthor*



</td>
</tr>
</table>

