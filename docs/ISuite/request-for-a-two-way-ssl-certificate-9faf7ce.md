<!-- loio9faf7cee8dc042569e6d539dc4879bf0 -->

# Request for a Two-Way SSL Certificate

Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.

> ### Note:  
> The default domain of the virtual host provided with your API Management service is secured with a one-way SSL certificate. For more information, see [Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md).

You can request for a two-way SSL certificate, which validates the identities of both the web server and the web client.

> ### Note:  
> Since client certificate chains are used in the authentication process to establish the identity of clients accessing the API Management service, it is important to ensure that these chains have sufficient security measures in place. Weak client certificate chains lack the necessary security measures and are therefore vulnerable to attacks. As a result, weak client certificate chains have been deprecated. For more detailed information, please [3418201 - Deprecation of Weak Client Certificate Chains in API Management \(sap.corp\)](https://i7p.wdf.sap.corp/sap(bD1lbiZjPTAwMQ==)/bc/bsp/sno/ui_entry/entry.htm?param=69765F6D6F64653D3030312669765F7361706E6F7465735F6E756D6265723D3334313832303126).



<a name="loio9faf7cee8dc042569e6d539dc4879bf0__section_mbk_544_1kb"/>

## Procedure

1.  Create an incident using the link [https://launchpad.support.sap.com/](https://launchpad.support.sap.com/)
2.  In the *Create Incident* window, expand the *Description* category and enter the following details:
    1.  The virtual host alias.

        > ### Note:  
        > For the default domain, this is the default virtual host alias.

    2.  Subdomain Name and ID: Go to *SAP BTP Cockpit* \> *<Your\_subaccount\>*. On the *Overview* page of your subaccount, make a note of the value marked against the *Subdomain* attribute as well as the *ID*.
    3.  Two-way SSL authentication : Enabled
    4.  An e-mail ID that you intend to use for sharing the secure drive link. The secure drive link is provided once you raise this incident, and you use the secure drive link to upload the public certificate, and the relevant chain certificate.
    5.  Component: **OPU-API-OD-OPS**

3.  Submit the incident.

**Related Information**  


[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-585d639.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

[Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md "A virtual host lets you host multiple domain names on API Management capability within Integration Suite.")

[User Roles in API Management \(New\)](user-roles-in-api-management-new-911ca5a.md "Similar to other capabilities of the SAP Integration Suite, the API Management capability defines a set of technical roles that grant specific permissions to users. Users can be assigned roles through SAP BTP's role collection concept. While users have the option to create their own role collections, a set of predefined role collections is automatically created when the API Management capability is provisioned.")

[User Roles in API Management](user-roles-in-api-management-7010b58.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from Integration Suite to disable your account from the API Management service.")

