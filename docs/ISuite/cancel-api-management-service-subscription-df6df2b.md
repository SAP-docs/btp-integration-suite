<!-- loiodf6df2b90c354ca7b83c4e7045b2279c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Cancel API Management Service Subscription

Cancel your API portal and API business hub enterprise application subscriptions to disable your account from the API Management service.

> ### Remember:  
> If you’re using the stand-alone service for API Management, ensure that you first cancel the subscription for the API business hub enterprise application, followed by the API portal application.
> 
> If you’re using API Management via the Integration Suite, you can unsubscribe from the applications in any order of your preference.
> 
> Unsubscribing deletes the data stored in the respective applications.

-   **Cancel the API Management Subscription for Standalone API Management Service**

    Perform the following steps to cancel the subscriptions for API portal and the API business hub enterprise for the stand-alone API Management service:

    1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

    2.  From the left pane, choose *Services* \> *Instances and Subscriptions*.

    3.  Select *API Management, API Business Hub Enterprise* under *Subscriptions* section, choose <span class="SAP-icons"></span> Actions , and choose *Delete*. In the *Delete Subscription* confirmation dialog, choose *Delete Subscription*.

    4.  Select *API Management, API portal* under *Subscriptions* section, choose <span class="SAP-icons"></span> Actions, and choose *Delete*. In the *Delete Subscription* confirmation dialog, choose *Delete Subscription*.


-   **Cancel the API Management Subscription from Integration Suite**

    If you've enabled the API Management capability via Integration Suite, perform the following steps to cancel the API portal and the API business hub enterprise subscriptions:

    1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

    2.  Navigate to *Services* \> *Instances and Subscriptions*.

    3.  Select *Integration Suite* under *Subscriptions*, choose <span class="SAP-icons"></span> Actions, and choose *Go To Application*.

        You’re navigated to the *Integration Suite* home page where the *Design, Develop, and Manage APIs* tile is displayed.

    4.  On the *Design, Develop, and Manage APIs* tile, choose <span class="SAP-icons"></span> Actions, and choose *Manage Capability*.

        You’re navigated to the *Integration Suite* *Provisioning* page.

    5.  To cancel the API Management subscription, choose *Deactivate*.

        The *Deactivate API Management* confirmation dialog appears.

    6.  Once you choose *Deactivate*, the *API Management, API Portal* and *API Management, API Business Hub Enterprise* applications are deactivated.



**Related Information**  


[API Management, API portal as a Service](api-management-api-portal-as-a-service-e064663.md "The API Management, API portal as a service on Cloud Foundry provides different capabilities through Route Service plan, On-Premise Connectivity plan, and API Access plan.")

[API Management, API business hub enterprise as a Service](api-management-api-business-hub-enterprise-as-a-service-d59d8f9.md "The API Management, API business hub enterprise as a service on Cloud Foundry provides the API access plan.")

[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-585d639.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

[Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md "A virtual host allows you to host multiple domain names on the API Management capability within Integration Suite.")

[Request for a Two-Way SSL Certificate](request-for-a-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

[Assign User Roles in API Management](assign-user-roles-in-api-management-911ca5a.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

