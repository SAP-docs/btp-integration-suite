<!-- loiod9d60be9332e48bc98bbec7aa8c5af30 -->

# What's New for SAP API Management Cloud Foundry





**2023**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Environment

</th>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action

</th>
<th valign="top">

Lifecycle

</th>
<th valign="top">

Type

</th>
<th valign="top">

Line of Business

</th>
<th valign="top">

Modular Business Process

</th>
<th valign="top">

Product

</th>
<th valign="top">

Latest Revision

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Threshold Value for Charts in Advanced API Analytics

</td>
<td valign="top">

In the analytics dashboard, the values on the chart for a particular dimension are shown only up to a certain threshold. Any values beyond this threshold are grouped together and labeled as **Others**. By default, the threshold value for the charts is set to 25.

See: [Find Your Way around Advanced API Analytics Dashboard](https://help.sap.com/docs/integration-suite/sap-integration-suite/find-your-way-around-advanced-api-analytics-dashboard?version=CLOUD#report-pages) \(SAP API Management customers choose: [Find Your Way around Advanced API Analytics Dashboard](https://help.sap.com/docs/sap-api-management/sap-api-management/find-your-way-around-advanced-api-analytics-dashboard?version=Cloud#report-pages)\)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-01-20

</td>
<td valign="top">

2024-01-20

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Deprecation of Weak Client Certificate Chains in API Management

</td>
<td valign="top">

Weak client certificate chains have been deprecated to enhance the security standards.

Consequently, the OpenSSL security level has been increased to level 2, which means that weak certificates or certificate chains will no longer be accepted by the platform. For a comprehensive definition of security level 2 and further information, please see [https://www.openssl.org/docs/man3.0/man3/SSL\_CTX\_set\_security\_level.html\#DEFAULT-CALLBACK-BEHAVIOURInformation](https://www.openssl.org/docs/man3.0/man3/SSL_CTX_set_security_level.html#DEFAULT-CALLBACK-BEHAVIOURInformation) published on non-SAP site.

Please note that this change only affects client certificates. If you do not utilize client certificates or mTLS for authentication with the platform, you will not be affected.

For additional details on the command, please see [3418201 - Deprecation of Weak Client Certificate Chains in API Management \(sap.corp\)](https://i7p.wdf.sap.corp/sap(bD1lbiZjPTAwMQ==)/bc/bsp/sno/ui_entry/entry.htm?param=69765F6D6F64653D3030312669765F7361706E6F7465735F6E756D6265723D3334313832303126) published on the SAP site.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

Deprecated

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-01-20

</td>
<td valign="top">

2024-01-20

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Expiration Period for Credentials

</td>
<td valign="top">

The expiration period for the credentials needed to establish a connection to the centralized API business hub enterprise has been extended to 365 days from 65 days. Please make sure to regenerate the credentials and reestablish the connection within this timeframe. However, any credentials generated prior to February 2024 with a validity of 65 days will remain valid for that specific duration. The 365-day timeframe will apply to all newly generated credentials.

See:

-   [Updating the Connection Request Credentials for a Pending Request](https://help.sap.com/docs/integration-suite/sap-integration-suite/updating-connection-request-credentials-for-pending-request-new-design?q=centralised)

-   [Updating the Connection Request Credentials for an Approved Request](https://help.sap.com/docs/integration-suite/sap-integration-suite/updating-connection-request-credentials-for-approved-request-new-design?version=CLOUD)


SAP API Management customers choose:

-   [Updating the Connection Request Credentials for a Pending Request](https://help.sap.com/docs/sap-api-management/sap-api-management/updating-connection-request-credentials-for-pending-request-new-design?version=Cloud)

-   [Updating the Connection Request Credentials for an Approved Request](https://help.sap.com/docs/sap-api-management/sap-api-management/updating-connection-request-credentials-for-approved-request-new-design?version=Cloud)




</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-01-20

</td>
<td valign="top">

2024-01-20

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Client SDK version 1.5.2

</td>
<td valign="top">

In Cloud Foundry, authentication using X509 certificates and keys is now supported. Instead of using clientid, clientsecret, and tokenurl, you should now use certificate, privateKey, certUrl, and clientid. Additionally, security vulnerabilities reported in the SAP NOTE [https://me.sap.com/notes/3411067](https://me.sap.com/notes/3411067) have been fixed. For more information, please refer to :

See the Client SDK version 1.5.2 in: [API Services](https://help.sap.com/docs/integration-suite/sap-integration-suite/api-services?version=CLOUD) \(SAP API Management customers choose: [API Services](https://help.sap.com/docs/sap-api-management/sap-api-management/api-services?q=certificate&version=Cloud)\)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-12-13

</td>
<td valign="top">

2023-12-13

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Policy Template

</td>
<td valign="top">

If there are any default fault rules or a post-client flow available within the API proxy, they will also be appended to the policy template.

See: [Apply a Policy Template](https://help.sap.com/docs/integration-suite/sap-integration-suite/apply-policy-template) \(SAP API Management customers choose: [Apply a Policy Template](https://help.sap.com/docs/sap-api-management/sap-api-management/apply-policy-template)\)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-12-04

</td>
<td valign="top">

2023-12-04

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Manage external content in API business hub enterprise 

</td>
<td valign="top">

The new *Manage External Content* option in *Enterprise Manager* enables you to configure additional content, such as Business Data Graphs \(BDGs\), for display on the API business hub enterprise. For more information, see [Manage External Content \(New Design\)](https://help.sap.com/docs/integration-suite/sap-integration-suite/manage-external-content-new-design).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-12-04

</td>
<td valign="top">

2023-12-04

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Deprecation of Classic Design of API business hub enterprise 

</td>
<td valign="top">

The classic design of the API business hub enterprise will be deprecated soon. Starting from March 2024, the new design of the API business hub enterprise will become the default design. However, you’ll still be able to toggle between the new and old design until June 2024 using the *Set Default Design* feature in *Site Editor*. For more information, see

See: [Customize the Visual Format of the API business hub enterprise](https://help.sap.com/docs/integration-suite/sap-integration-suite/customize-visual-format-of-api-business-hub-enterprise)\(SAP API Management customers choose: [Customize the Visual Format of the API business hub enterprise](https://help.sap.com/docs/sap-api-management/sap-api-management/customize-visual-format-of-api-business-hub-enterprise)\)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

Deprecated

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-12-04

</td>
<td valign="top">

2023-12-04

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Auto-Registration of developers in API business hub enterprise 

</td>
<td valign="top">

If the AuthGroup.API.ApplicationDeveloper role is already assigned to you by the SAP BTP admin or via the IDP Role Collection mapping, you will get automatically registered as an application developer in API business hub enterprise when you logon for the first time.

See: [Register on API business hub enterprise](register-on-api-business-hub-enterprise-c85fafe.md) \(SAP API Management customers choose: [Register on API business hub enterprise](https://help.sap.com/docs/sap-api-management/sap-api-management/register-on-api-business-hub-enterprise)\)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-12-04

</td>
<td valign="top">

2023-12-04

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Revisions

</td>
<td valign="top">

Unique naming pattern for Drafts in API Revisions to clearly differentiate between the deployed draft and the working draft and the drafts originating from revisions.

See: [Creating API Revisions](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-api-revisions) \(SAP API Management customers choose: [Creating API Revisions](https://help.sap.com/docs/sap-api-management/sap-api-management/creating-api-revisions-0a0d7d41222e42e4834b30c89609f400)\)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-10-30

</td>
<td valign="top">

2023-10-30

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Artifact in Edge Integration Cell

</td>
<td valign="top">

With the introduction of the API artifact and the general availability of the Edge Integration Cell, a few navigation changes have been made to the Integration Suite API Management capability. The APIs and Policy Templates, previously located under *Design* \> *APIs* in the left navigation, have been moved to *Configure* \> *APIs*. Additionally, the term "APIs" is now referred to as "API Proxies." Furthermore, "Products" and "Applications", which were previously found under *Design* \> *APIs* can now be accessed through a new left navigation item called *Engage*. To know more, see [API Development](https://help.sap.com/docs/integration-suite/sap-integration-suite/manage-apis?version=CLOUD).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-10-30

</td>
<td valign="top">

2023-10-30

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Revisions

</td>
<td valign="top">

When publishing products, it's important to note that resources are available from the deployed API, rather than from the latest revision or draft of the API. Additionally, if a deployed resource is not available in the latest revision, you won't be able to attach that resource to the product.

The revision name now includes support for parentheses \(\) as an additional special character in the name. For more information, see .

-   : [API Revisions](https://help.sap.com/docs/integration-suite/sap-integration-suite/api-revisions)
-   API Management standalone service: [API Revisions](https://help.sap.com/docs/sap-api-management/sap-api-management/api-revisions) 



</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-09-30

</td>
<td valign="top">

2023-09-30

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Certificate-based Credentials

</td>
<td valign="top">

The connection between the centralised API business hub enterprise and the API portal has been secured with certificate-based authentication. For more information, see [Create a Connection Request for the Centralized API business hub enterprise \[Classic Design\]](APIM-Initial-Setup/create-a-connection-request-for-the-centralized-api-business-hub-enterprise-cla-02f7877.md) and [Create a Connection Request for the Centralized API business hub enterprise \[New Design\]](APIM-Initial-Setup/create-a-connection-request-for-the-centralized-api-business-hub-enterprise-new-c7bda8c.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-09-30

</td>
<td valign="top">

2023-09-30

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

mTLS Authentication

</td>
<td valign="top">

You can now utilize certificate-based credentials to seamlessly migrate API Management subscriptions from Neo to Cloud Foundry, as well as between same or different Cloud Foundry environments. For more information, see [Clone API Management Artifacts](APIM-Migration/clone-api-management-artifacts-7abd887.md) and [Clone API Management Artifacts During Cloud Foundry to Cloud Foundry Migration](APIM-Migration/clone-api-management-artifacts-during-cloud-foundry-to-cloud-foundry-migration-2e5d127.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-09-30

</td>
<td valign="top">

2023-09-30

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Client SDK

</td>
<td valign="top">

In Cloud Foundry, Authentication using the X509 certificate and key is now supported. Instead of clientid, clientsecret and tokenurl, use certificate, privateKey, certUrl and clientid. For more information, refer to the Client SDK version 1.5.0 in [API Services](api-services-007d50f.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-09-13

</td>
<td valign="top">

2023-09-13

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Revisions

</td>
<td valign="top">

You can now create a new revision of your API and make necessary changes to the API definitions, policies, and resources without causing any disruption to the already published API.

You can also see all the changes made to the API and restore the API to its previous state. For more information, see [API Revisions](api-revisions-58097ac.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-08-28

</td>
<td valign="top">

2023-08-28

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Graph

</td>
<td valign="top">

Graph is a new and innovative capability of API Management within SAP Integration Suite.It enables you to expose all your business data in the form of a semantically connected data graph, accessed via a single unified and powerful API. For more information, see [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?version=CLOUD).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-07-17

</td>
<td valign="top">

2023-07-17

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API business hub enterprise: Add Links and Email Addresses Using Markdown

</td>
<td valign="top">

You can use markdown to add links and email addresses to the title and subtitle fields as part of the banner description in *Site Editor*. For more information, see [Customize the Visual Format of the API business hub enterprise](customize-the-visual-format-of-the-api-business-hub-enterprise-2eacd52.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-07-17

</td>
<td valign="top">

2023-07-17

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Latest Version of the Tenant Cloning Tool

</td>
<td valign="top">

The 1.7.2 version of the Tenant Cloning Tool is now available. For more information, see [Clone API Management Artifacts](APIM-Migration/clone-api-management-artifacts-7abd887.md) and [Clone API Management Artifacts During Cloud Foundry to Cloud Foundry Migration](APIM-Migration/clone-api-management-artifacts-during-cloud-foundry-to-cloud-foundry-migration-2e5d127.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-06-23

</td>
<td valign="top">

2023-06-23

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Latest Version of the Tenant Cloning Tool

</td>
<td valign="top">

The 1.7.1 version of the Tenant Cloning Tool is now available. For more information, see [Clone API Management Artifacts](APIM-Migration/clone-api-management-artifacts-7abd887.md) and [Clone API Management Artifacts During Cloud Foundry to Cloud Foundry Migration](APIM-Migration/clone-api-management-artifacts-during-cloud-foundry-to-cloud-foundry-migration-2e5d127.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-05-22

</td>
<td valign="top">

2023-05-22

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Secure options to consume APIs

</td>
<td valign="top">

We have introduced secure options to consume APIs using the API Access Plan for API portal, API business hub enterprise and on-premise connectivity. You can now create service keys with credential types "binding- secret", "instance- secret" and "x509". For more information, see [Accessing API Management APIs Programmatically](APIM-Initial-Setup/accessing-api-management-apis-programmatically-24a2c37.md), [Accessing API business hub enterprise APIs Programmatically](APIM-Initial-Setup/accessing-api-business-hub-enterprise-apis-programmatically-dabee6e.md) and [Accessing On-Premise Systems through API Management](APIM-Initial-Setup/accessing-on-premise-systems-through-api-management-2fc7a5b.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-05-08

</td>
<td valign="top">

2023-05-08

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Short text field in API products.

</td>
<td valign="top">

In the API portal, a new *Short Text* field is now available for products. You can use this field to add an introductory text to your products. When you add the introductory text in this field and publish the product, this short text appears in the product tile on the corresponding API business hub enterprise page and is also available on the API proxy details page. For more information, see [Create a Product](create-a-product-d769622.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-05-08

</td>
<td valign="top">

2023-05-08

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API business hub enterprise \[New Design\] and \[Classic Design\]

</td>
<td valign="top">

If you have defined the external documentation information for an API in the OpenAPI specification, you can access this information under the *Documentation* section in the API details page under the *Overview* tab.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-04-10

</td>
<td valign="top">

2023-04-10

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API business hub enterprise 

</td>
<td valign="top">

\[New DesignThe Manage options \(for example Manage Users, Manage Domain\] Categories, and so on\) on the API business hub enterprise \[New Design\] header are now listed under *\[New DesignEnterprise Manager*. Based on the roles assigned to the users, these options will appear under the *Enterprise Manager* tab. For more information, see [Manage Domain Categories \[New Design\]](manage-domain-categories-new-design-bd9691d.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-02-20

</td>
<td valign="top">

2023-02-20

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API business hub enterprise \[New Design\]

</td>
<td valign="top">

You can now configure notifications for providing information to the API business hub enterprise end users on any website updates, events or news items from the API business hub enterprise new user interface. For more information, see [Manage Notifications \[New Design\]](manage-notifications-new-design-df32457.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-02-20

</td>
<td valign="top">

2023-02-20

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API business hub enterprise 

</td>
<td valign="top">

The mandatory Client ID and Client Secret fields on *Edit Credentials* popup have been replaced with *\*API Portal Access Credentials* field. For more information, see [Updating the Connection Request Credentials for a Pending Request \[New Design\]](APIM-Initial-Setup/updating-the-connection-request-credentials-for-a-pending-request-new-design-dd37a7b.md) and [Updating the Connection Request Credentials for a Submitted Request \[Classic Design\]](APIM-Initial-Setup/updating-the-connection-request-credentials-for-a-submitted-request-classic-des-eb84854.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2023-01-17

</td>
<td valign="top">

2023-01-17

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Migrating API Management Subscription from One Cloud Foundry to Another Cloud Foundry Environment

</td>
<td valign="top">

You can choose to migrate an existing API Management subscription that you have in the Cloud Foundry environment to another API Management subscription within the Cloud Foundry environment. This can be done to a different tenant within the same data center or to a tenant in a different data center. For more information, see [Migrating API Management Subscription from One Cloud Foundry to Same or Different Cloud Foundry Environment](APIM-Migration/migrating-api-management-subscription-from-one-cloud-foundry-to-same-or-different-c-17f09f3.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

API Management

</td>
<td valign="top">

2023-01-04

</td>
<td valign="top">

2023-01-04

</td>
</tr>
</table>

