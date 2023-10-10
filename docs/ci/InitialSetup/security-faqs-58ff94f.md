<!-- loio58ff94fc64784e3d9e53f357f08a0bce -->

# Security FAQs



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_jg5_jjd_x1b"/>

## How can new users and authorizations be added once a customer gets the SAP Cloud Integration tenant? Who is authorized to add new users?

When SAP provides a tenant, administrator permissions are given to the S-user ID provided by the customer in the order form during contract signing. This administrative user can go to the SAP BTP cockpit and add additional users, and assign them roles and authorizations. Since SAP Cloud Integration uses SAP Cloud Identity provider by default, all the users must have valid S-user or P-user IDs.

You can also configure Cloud Integration to use your own custom identity provider.For more information, see [Using Custom IDP with SAP Cloud Integration](../ConnectionSetup/using-custom-idp-with-sap-cloud-integration-c59610d.md).



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_k2k_sjd_x1b"/>

## Where can I find a list of all roles and authorizations that can be assigned to users?

More information:

[Persona](../SecurityNeo/persona-2937e5c.md)



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_xc2_mv1_v2b"/>

## Which recommendations are given for assigning roles to users?

The customer has full control on giving permissions to users on a tenant.

A key part of an integration project is the development and deployment of integration content \(for example, integration flows\). The related permissions are defined by the authorization group `AuthGroup.IntegrationDeveloper` and `AuthGroup.Administrator`. Note that this authorization group provides extensive permissions. Therefore, take into account special considerations when assigning this authorization group to a user.

More information:

[Identity and Access Management](../SecurityNeo/identity-and-access-management-15ca6f9.md)



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_tz2_1kd_x1b"/>

## How can I contact SAP Cloud Integration Operations support for information or issues related to tenant provisioning and security?

Create a ticket on component LOD-HCI-PI-OPS.



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_dfb_2kd_x1b"/>

## Are CA-signed certificates mandatory for transport-level authentication? Which scenarios require CA-signed certificates?

More information:

[Transport Level Security](transport-level-security-50321f2.md)



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_lwv_3kd_x1b"/>

## Where can I find a list of CAs approved by SAP?

[Load Balancer Root Certificates Supported by SAP](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/4509f605e83c4c939a91b81eb3a6cdea.html)



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_vr5_zkd_x1b"/>

## I want to use the same signed certificate for multiple systems. Can I put \* in the Common Name field \(for example, \*.xxxxx.com\) while the certificate is being signed by the CA? Does SAP allow this?

SAP recommends using the full host name in the Common Name \(CN\) field for both inbound and outbound scenarios, but technically does support the wildcard character in the CN field \(for certificate-based client authentication only\). For HTTPS outbound scenarios \(where SAP manages the CA-signed key pairs\), SAP uses the full host name in the CN field.



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_pd4_bld_x1b"/>

## Can I use self-signed certificates for HTTPS certificate-based client authentication \(also referred to as dual authentication\)?

No, self-signed certificates are not supported for inbound connections to SAP Cloud Integration. For outbound connections, we recommend using a CA-signed base certificate.



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_q12_2ld_x1b"/>

## Which scenarios support self-signed certificates? Can I use them for message-level encryption and signing?

You can use self-signed certificates for message-level encryption and signing. However, we recommend using CA-signed certificates.



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_w1h_jld_x1b"/>

## Who maintains and manages the keystore? Can control be given to the end customer?

SAP provides some keys by default, but keystore management is now a self-service, so you can manage your keystore yourself.

More information:

[Managing Keystore Entries](../Operations/managing-keystore-entries-2dc8942.md)



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_dj2_rld_x1b"/>

## What is the procedure for using certificates for message-level encryption and signing?

You can use the certificates that are in the keystore provided by SAP during tenant provisioning. If you want to use your own key pair, you can manage it yourself using the self-service. There are different ways in which you can sign and encrypt message content \(for example, PGP, X.509\).

More information:

[Message Level Security](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/463a9085156d4672bc4ee9095277e453.html).



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_cr4_hmd_x1b"/>

## Do I need to make any special requests when connecting to the SFTP/SMTP server?

The following ports are opened by default:

-   For SFTP/SSH: port 22
-   For SMTP: ports 25, 465, and 587



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_fhy_mmd_x1b"/>

## Do I need to make any special requests for HTTP\(S\) for outbound connectivity?

By default, port 443 and all HTTP ports 1024 and higher are opened.



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_hn4_4md_x1b"/>

## Which IP addresses for the SAP Cloud Integration landscape do I need to configure in my own firewall for inbound connections \(IP allowlisting\)?

See [Virtual System Landscapes](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/dd2309565a0c4be2892ecbf223bc9277.html).



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_j5w_1nd_x1b"/>

## Where can I find details on SAP Data Centers and security?

You can find this information on the SAP website under SAP Data Centers Information.

More information: [https://www.sap.com/about/cloud-trust-center/data-center.html](https://www.sap.com/about/cloud-trust-center/data-center.html)



<a name="loio58ff94fc64784e3d9e53f357f08a0bce__section_egj_2nd_x1b"/>

## What is SAP Cloud Connector? Is it mandatory?

SAP Cloud Connector is a complementary offering. It needs to be installed on premise and is an integral component of SAP BTP. It acts as a reverse proxy and creates a secure tunnel with the customer's own SAP Cloud Integration account. SAP Cloud Integration can route calls via SAP Cloud Connector for HTTP-based protocols \(for example, SOAP, OData IDoc XMLs\). SAP Cloud Connector is the preferred mode of communication for SAP BTP customers. However, it is not mandatory and customers can use other reverse proxy software \(for example, Web Dispatcher\).

More information:

[Outbound/On-Premise: Reverse Proxy or SAP Cloud Connector](../ConnectionSetup/outbound-on-premise-reverse-proxy-or-sap-cloud-connector-14567e1.md)

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="4b3bb3b1f4784cdbaf6ab103c18ea4a8.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/58ff94fc64784e3d9e53f357f08a0bce.xml" ?> 

[Connecting a Customer System to Cloud Integration](../ConnectionSetup/connecting-a-customer-system-to-cloud-integration-7cfe913.md "You can set up the technical connection between a tenant and different kinds of remote systems (in many cases located in the customer landscape).")

