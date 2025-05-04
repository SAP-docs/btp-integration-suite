<!-- loiodf6df2b90c354ca7b83c4e7045b2279c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Cancel API Management Service Subscription

You can deactivate your API Management capability from SAP Integration Suite to disable your account from the API Management service.



<a name="loiodf6df2b90c354ca7b83c4e7045b2279c__section_avg_shr_b1c"/>

## Deactivate the API Management Capability from SAP Integration Suite

**Prequisite**: The *Integration\_Provisioner* role must be assigned to you.

If you've enabled the API Management capability via SAP Integration Suite, perform the following steps to cancel the API portal and the Developer Hub subscriptions:

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

2.  Navigate to *Services* \> *Instances and Subscriptions*.

3.  Select *Integration Suite* under *Subscriptions*, choose <span class="SAP-icons-V5"></span> Actions, and choose *Go To Application*.

    You’re navigated to the *Integration Suite* home page where the *Design, Develop, and Manage APIs* tile is displayed.

4.  On the *Design, Develop, and Manage APIs* tile, choose <span class="SAP-icons-V5"></span> Actions, and choose *Manage Capability*.

    You’re navigated to the *Integration Suite* *Provisioning* page.

5.  To cancel the API Management subscription, choose *Deactivate*.

    The *Deactivate API Management* confirmation dialog appears.

6.  Once you choose *Deactivate*, the *API Management, API Portal* and **API Management, Developer Hub** applications are deactivated.


**Related Information**  


[Configuring Additional Virtual Host in Cloud Foundry Environment](configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "A virtual host allows you to host multiple domain names on the API Management capability within SAP Integration Suite.")

[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-683a97c.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Shadow Users](shadow-users-a0f5fe5.md "Whenever a user authenticates at an application in your subaccount using any identity provider, it’s essential that user-related data provided by the identity provider is stored in the form of shadow users.")

[Setting Up API Management with SAP Cloud Identity Services](setting-up-api-management-with-sap-cloud-identity-services-1e88d9c.md "SAP Cloud Platform allows customers to connect their SAP Cloud Identity Services with the BTP offerings.")

