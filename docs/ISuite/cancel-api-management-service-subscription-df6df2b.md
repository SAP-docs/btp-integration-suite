<!-- loiodf6df2b90c354ca7b83c4e7045b2279c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Cancel API Management Service Subscription

You can deactivate your API Management capability from Integration Suite to disable your account from the API Management service.



<a name="loiodf6df2b90c354ca7b83c4e7045b2279c__section_avg_shr_b1c"/>

## Deactivate the API Management Capability from Integration Suite

**Prequisite**: The *Integration\_Provisioner* role must be assigned to you.

If you've enabled the API Management capability via Integration Suite, perform the following steps to cancel the API portal and the API business hub enterprise subscriptions:

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

2.  Navigate to *Services* \> *Instances and Subscriptions*.

3.  Select *Integration Suite* under *Subscriptions*, choose <span class="SAP-icons-V5"></span> Actions, and choose *Go To Application*.

    You’re navigated to the *Integration Suite* home page where the *Design, Develop, and Manage APIs* tile is displayed.

4.  On the *Design, Develop, and Manage APIs* tile, choose <span class="SAP-icons-V5"></span> Actions, and choose *Manage Capability*.

    You’re navigated to the *Integration Suite* *Provisioning* page.

5.  To cancel the API Management subscription, choose *Deactivate*.

    The *Deactivate API Management* confirmation dialog appears.

6.  Once you choose *Deactivate*, the *API Management, API Portal* and *API Management, API Business Hub Enterprise* applications are deactivated.


**Related Information**  


[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-585d639.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

[Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md "A virtual host lets you host multiple domain names on API Management capability within Integration Suite.")

[Request for a Two-Way SSL Certificate](request-for-a-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

[User Roles in API Management \(New\)](user-roles-in-api-management-new-911ca5a.md "Similar to other capabilities of the SAP Integration Suite, the API Management capability defines a set of technical roles that grant specific permissions to users. Users can be assigned roles through SAP BTP's role collection concept. While users have the option to create their own role collections, a set of predefined role collections is automatically created when the API Management capability is provisioned.")

[User Roles in API Management](user-roles-in-api-management-7010b58.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

