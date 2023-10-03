<!-- loio6b9e5a3430b84fecaac1c994fff6c3ee -->

# Requesting a Custom Domain for a Virtual Host

Virtual host is an entity where the API proxy gets deployed, and API proxies can be accessed using the URL defined in the virtual host.



<a name="loio6b9e5a3430b84fecaac1c994fff6c3ee__context_tcd_t2b_yyb"/>

## Context

During onboarding, when you subscribe to the API Managemnt service, a virtual host is created by default, and you can execute the APIs using the URL of this virtual host. The domain for this virtual host URL is specific to the SAP data center where the tenant is onboarded.

Once onboarding is completed, you can create an additional virtual host. You have the option to create the virtual host with a domain that is specific to your organization. This domain is referred to as a Custom Domain.

Here are the reasons why you need a custom domain:

-   To meet your branding needs, where you can configure API proxy endpoint URLs specific to your organization.

-   To migrate the proxy definitions to another BTP region or even outside of BTP, without affecting the URLs that API clients use to access the API.


You can secure the custom domain with either a one-way or a two-way SSL certificate. SSL is a standard security protocol that encrypts the connection between a web server and a web client, for example the connection between a web browser and an application. Here, the one-way SSL validates only the identity of the web-server but the two-way SSL validates the identities of both the web server and the web client. For requesting the two-way SSL certificate, see [Request for Two-Way SSL Certificate](request-for-two-way-ssl-certificate-9faf7ce.md).

To request a custom domain with one-way SSL, perform the following steps:



## Procedure

1.  Create an incident using the link [https://launchpad.support.sap.com/](https://launchpad.support.sap.com/).

2.  In the *Create Incident* window, expand the *Description* category and enter the following details in the description field:

    1.  Specify the desired custom domain name.

        If you have multiple virtual hosts, please mention the virtual host alias for which you want the custom domain.

    2.  Specify the *Subdomain Name* and *ID*.

        To find the subdomain name and ID, follow these steps:

        1.  Open the SAP BTP Cockpit and navigate to your subaccount.

        2.  On the *Overview* page of your subaccount, locate the *Subdomain* attribute.
        3.  Make a note of the value marked against the *Subdomain* attribute. This value represents the subdomain name.
        4.  Additionally, note down the ID associated with your subaccount.

    3.  Please provide an email address that you intend to use for sharing the secure drive link. The secure drive link will be provided to you once you raise this incident. You’ll need to use the secure drive link to upload the private key, public certificate, and the relevant chain certificate.

        > ### Note:  
        > Refrain from using the Custom Domain Service \(CDS\) to create certificates, as it is not possible to export these certificates from there. Instead, use a third-party or open-source tools to generate the required certifications.

    4.  Specify that One-way SSL authentication is enabled.

    5.  Select the following component: **OPU-API-OD-OPS**


3.  Submit the incident.

    > ### Note:  
    > It’s recommended that you redeploy the API proxies that are associated with the custom domain virtual host after updating the virtual host.


**Related Information**  


[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

