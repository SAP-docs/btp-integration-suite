<!-- loio6b9e5a3430b84fecaac1c994fff6c3ee -->

# Requesting for Custom Domain for a Virtual Host

When you subscribe to API Management service, and are creating API proxies, they get created with the default virtual host, and the default domain. To suit your requirements, you can request for a custom domain.



## Context

You can secure the custom domain with either a**one-way** or a **two-way** SSL certificate. SSL is a standard security protocol that encrypts the connection between a web server and a web client, for example the connection between a web browser and an application. Here, the one-way SSL validates only the identity of the web-server but the two-way SSL validates the identities of both the web server and the web client. For requesting the two-way SSL certificate, see [Request for Two-Way SSL Certificate](request-for-two-way-ssl-certificate-9faf7ce.md).

> ### Note:  
> If the underlying systems or Data Centers change, the API URL might get impacted. Therefore, we recommend that you configure a custom domain to have a stable API URL.

To request a custom domain with one-way SSL, perform the following steps:



## Procedure

1.  Create an incident using the link [https://launchpad.support.sap.com/](https://launchpad.support.sap.com/)

2.  In the *Create Incident* window, expand the *Description* category and enter the following details in the description field:

    1.  The custom domain name that you want.If you have multiple virtual hosts, then also mention the virtual host alias that you want the custom domain for.

    2.  Subdomain Name and ID: You find the subdomain name and ID by opening ***SAP BTP Cockpit* \> *<Your\_subaccount\>*.** On the *Overview* page of your subaccount, make a note of the value marked against the **Subdomain** attribute as well as the ID.

    3.  An e-mail ID that you intend to use for sharing the secure drive link. The secure drive link is provided once you raise this incident, and you use the secure drive link to upload private key, public certificate, and the relevant chain certificate.

        > ### Note:  
        > Please don't create certificates via Custom Domain Service \(CDS\), as it is not possible for us to export these certificates from there. Instead, use any third-party or open-source tools to generate the required certification.

    4.  One-way SSL authentication: Enabled

    5.  Component: **OPU-API-OD-OPS**


3.  Submit the incident.

    > ### Note:  
    > It’s recommended that you redeploy the API Proxies that are linked to the custom domain virtual host, after the virtual host is updated.


**Related Information**  


[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

