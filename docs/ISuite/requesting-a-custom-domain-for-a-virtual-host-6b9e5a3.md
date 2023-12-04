<!-- loio6b9e5a3430b84fecaac1c994fff6c3ee -->

# Requesting a Custom Domain for a Virtual Host

A virtual host allows you to host multiple domain names on the API Management capability within Integration Suite.



<a name="loio6b9e5a3430b84fecaac1c994fff6c3ee__context_tcd_t2b_yyb"/>

## Context

After successful onboarding, API proxies are assigned a default virtual host URL. Currently, this URL uses the domain "ondemand.com," which is the common domain for the Business Technology Platform. It’s prefixed with the subdomain consisting of the subaccount name and the data center where the Integration Suite tenant is onboarded. For example, the default host alias could be https://myaccount....eu10.hana.ondemand.com.

The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as "https://api.bestrun.com/..." if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as "https://api1.bestrun.com," "https://api2.bestrun.com," and so on.

Another advantage of establishing your own custom domain with a virtual host is that it protects you from future changes, such as those that may occur when rehosting your APIs.

In addition, you have the option to secure your custom domain with either a one-way or a two-way SSL certificate. A one-way SSL certificate validates only the secure identity of the API Proxy, providing encryption and authentication for the server. On the other hand, a two-way SSL certificate validates the identities of both the API Proxy and the client, providing mutual authentication.

If you want to request a two-way SSL certificate, see [Request for a Two-Way SSL Certificate](request-for-a-two-way-ssl-certificate-9faf7ce.md). This process enables you to establish a more secure connection between your API Proxy and the client, ensuring that both parties can trust each other's identities.

To request a custom domain with one-way SSL, perform the following steps:



## Procedure

1.  Navigate to [https://launchpad.support.sap.com/](https://launchpad.support.sap.com/).

2.  On the *SAP for Me* page, select the *Enter the SAP ONE Support Launchpad* tile.

3.  On the *SAP ONE Support Launchpad*, select the *Report and Incident* tile.

4.  In the *Create Incident* window, expand the *Description* category and enter the following details in the description field:

    1.  Specify the desired custom domain name.

        If you have multiple virtual hosts, mention the virtual host alias for which you want the custom domain.

    2.  Specify the *Subdomain Name* and *ID*.

        To find the subdomain name and ID, follow these steps:

        1.  Open the SAP BTP Cockpit and navigate to your subaccount.

        2.  On the *Overview* page of your subaccount, locate the *Subdomain* attribute.
        3.  Make a note of the value marked against the *Subdomain* attribute. This value represents the subdomain name.
        4.  Additionally, note down the ID associated with your subaccount.

    3.  Please provide an email address that you intend to use for sharing the secure drive link. The secure drive link will be provided to you once you raise this incident. You’ll need to use the secure drive link to upload the private key, public certificate, and the relevant chain certificate.

        > ### Note:  
        > Refrain from using the Custom Domain Service \(CDS\) to create certificates, as it isn’t possible to export these certificates from there. Instead, use a third-party or open-source tools to generate the required certifications.

    4.  Specify that One-way SSL authentication is enabled.

    5.  Select the following component: **OPU-API-OD-OPS**


5.  Submit the incident.

    > ### Note:  
    > It’s recommended that you redeploy the API proxies that are associated with the custom domain virtual host after updating the virtual host.


**Related Information**  


[API Management, API portal as a Service](api-management-api-portal-as-a-service-e064663.md "The API Management, API portal as a service on Cloud Foundry provides different capabilities through Route Service plan, On-Premise Connectivity plan, and API Access plan.")

[API Management, API business hub enterprise as a Service](api-management-api-business-hub-enterprise-as-a-service-d59d8f9.md "The API Management, API business hub enterprise as a service on Cloud Foundry provides the API access plan.")

[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-585d639.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

[Request for a Two-Way SSL Certificate](request-for-a-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

[Assign User Roles in API Management](assign-user-roles-in-api-management-911ca5a.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "Cancel your API portal and API business hub enterprise application subscriptions to disable your account from the API Management service.")

[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

