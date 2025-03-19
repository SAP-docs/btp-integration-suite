<!-- loiof6eb4332cd5144ef91f4a84cc614ba1c -->

# Activating and Configuring API Management Capability

Steps to activate and configure API Management capability in SAP Integration Suite.


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

Subscribe to SAP Integration Suite in SAP BTP cockpit and assign the *Integration\_Provisioner* role to gain access. For more information, see [Initial Setup of SAP Integration Suite](10-InitialSetup/initial-setup-of-sap-integration-suite-3dcf507.md).

> ### Note:  
> Please make sure that you do not have a starter plan instance created in the same subaccount where you intend to create an Integration Suite subscription. Additionally, please note that API Management capabilities from SAP Integration Suite and API Management subscriptions using the stand-alone tile cannot coexist in the same subaccount.



</td>
</tr>
<tr>
<td valign="top">

Activate the API Management capability

</td>
<td valign="top">

Add and activate API Management capability in SAP Integration Suite. For more information, see [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md).

</td>
</tr>
<tr>
<td valign="top">

Configure the API Management capability

</td>
<td valign="top">

Access the *API Settings* page, and complete the onboarding process. For more information, see [Setting Up API Management Capability](50-Development/setting-up-api-management-capability-f34e86c.md).

To access the *API Settings*, the *APIManagement.Selfservice.Administrator* role must be assigned to you.

> ### Note:  
> If you are using a trial account, your account will be automatically provisioned once you select the *APIs* option in the *Settings* menu. During the provisioning process, the system will assign a default virtual host for you. You will receive a notification when the provisioning is complete. At this point, the *APIs* option will no longer be visible in the side-navigation menu under *Settings*. You will be logged out of SAP Integration Suite automatically. To continue, simply log in again. After logging in, you will have the ability to create APIs, build API proxies as a service provider, and utilize other convenient services offered by the platform.



</td>
</tr>
</table>

> ### Note:  
> For visual intructions on how to activate and configure API Management capability from SAP Integration Suite, refer the tutorial [Set Up API Management from Integration Suite | Tutorials for SAP Developers](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html).

**Related Information**  


[Assign User Roles in API Management](https://help.sap.com/viewer/de4066bb3f9240e3bfbcd5614e18c2f9/Cloud/en-US/911ca5a620e94ab581fa159d76b3b108.html "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.") :arrow_upper_right:

[Create an API Provider](50-Development/create-an-api-provider-6b263e2.md "Define the details of the host you want an application to reach by creating an API provider.")

[Different Methods of Creating an API Proxy](50-Development/different-methods-of-creating-an-api-proxy-4ac0431.md "An API proxy is the data object that contains all the functionality to be executed when an external user wants to access the backend service.")

[Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md "The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as &quot;https://api.bestrun.com/...&quot; if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as &quot;https://api1.bestrun.com,&quot; &quot;https://api2.bestrun.com,&quot; and so on.")

[Configuring Mutual TLs for Virtual Host](configuring-mutual-tls-for-virtual-host-9faf7ce.md "You can configure mutual TLs for a virtual host, which validates the identities of both the web server and the web client.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from SAP Integration Suite to disable your account from the API Management service.")

