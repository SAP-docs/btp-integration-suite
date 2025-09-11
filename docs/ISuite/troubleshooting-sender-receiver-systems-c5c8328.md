<!-- loioc5c83285229f49abbbdeda6e81b23975 -->

# Troubleshooting Sender/Receiver Systems

Information on troubleshooting incidents and errors when connecting from sender or reciever systems.



<a name="loioc5c83285229f49abbbdeda6e81b23975__section_dxr_ts1_k2c"/>

## Issues while connecting from sender or receiver systems

****


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top" rowspan="11">

Inbound connection and security issues

</td>
<td valign="top">

Ceritficate validity issues

</td>
<td valign="top">

Refer [2651086](https://me.sap.com/notes/2651086) - SAP certificates missing in Keystore in CPI/HCI.

For more information, see

-   [Setting Up Inbound HTTP Connections](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778c7e7835ff46408aafe0d499720dc7.html) 
-   [Cloud Integration - How to Setup Secure HTTP Inbound Connection with Client Certificates](https://community.sap.com/t5/integration-blog-posts/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client/ba-p/13336237)
-   [Cloud Integration - Inbound HTTP Connections using OAuth Client Credentials Grant](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-inbound-http-connections-using-oauth-client-credentials/ba-p/13424181)

For more information, see

-   [Setting Up Inbound HTTP Connections \(Integration Flow Processing\), Neo Environment](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/setting-up-inbound-http-connections-integration-flow-processing-neo-environment?version=Cloud) 
-   [Cloud Integration - How to Setup Secure HTTP Inbound Connection with Client Certificates](https://community.sap.com/t5/integration-blog-posts/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client/ba-p/13336237) 
-   [Cloud Integration - Inbound HTTP Connections using OAuth Client Credentials Grant](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-inbound-http-connections-using-oauth-client-credentials/ba-p/13424181) 



</td>
</tr>
<tr>
<td valign="top">

Error: SSSLERR\_PEER\_CERT\_UNTRUSTED

</td>
<td valign="top">

Refer [2728600](https://me.sap.com/notes/2728600) - SSSLERR\_ when accessing HCI/\(S\)CPI/NEO/CF servers under \*.hana.ondemand.com or \*.cloud.sap.

</td>
</tr>
<tr>
<td valign="top">

Error: ICM\_HTTP\_CONNECTION\_FAILED

</td>
<td valign="top">

Refer [Regions](https://help.sap.com/docs/btp/sap-business-technology-platform/regions?version=Cloud)

</td>
</tr>
<tr>
<td valign="top">

Error: HTTP 401

</td>
<td valign="top">

[Load Balancer Root Certificates Supported by SAP](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/load-balancer-root-certificates-supported-by-sap?state=DRAFT&version=DEV)

For more information, see [2583567](https://me.sap.com/notes/2583567) - Authorization error on connection test to CPI Tenant.

</td>
</tr>
<tr>
<td valign="top">

Error: HTTP 403

</td>
<td valign="top">

-   Basic authentication, refer
    -   [Defining Permissions for Senders to Process Messages on a Runtime Node](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/defining-permissions-for-senders-to-process-messages-on-runtime-node?version=Cloud)
    -   [2642897](https://me.sap.com/notes/2642897)

-   Direct client certificate authentication: follow this step - If certificate of sender system is missing or incorrect, add the subject DN and issuer DN of right sender certificate.
-   Certificate-to-user mapping-based authentication:
    -   Ensure that the sender's keystore includes a client certificate signed by a CA recognized by the load balancer.
    -   Verify that the username specified in the certificate-to-user mapping is assigned the correct role as required by the integration flow.
    -   For more information, see [Managing Certificate-to-User Mappings, Neo Environment](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/managing-certificate-to-user-mappings-neo-environment?version=Cloud)
    -   Refer [2642897](https://me.sap.com/notes/2642897) - Authorization error on connection test to CPI Tenant.


For more information, see

-   [Handling CSRF tokens in SAP Cloud Platform Integration](https://community.sap.com/t5/technology-blogs-by-members/handling-csrf-tokens-in-sap-cloud-platform-integration/ba-p/13338021)
-   [Invoking an OData API](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/invoking-odata-api?version=Cloud)
-   [Creating OData Service from SOAP using HCI \(beta\)](https://community.sap.com/t5/technology-blogs-by-members/creating-odata-service-from-soap-using-hci-beta/ba-p/13195594) 
-   [2354728](https://me.sap.com/notes/2354728) - Connection test to SAP Cloud Platform Integration tenant's endpoint is throwing HTTP 403 error.
-   [2600568](https://me.sap.com/notes/2600568) - RFC destination to SCI fails with 403 forbidden error.



</td>
</tr>
<tr>
<td valign="top">

Error: HTTP 404

</td>
<td valign="top">

-   The endpoint of the integration flow is case-sensitive. Ensure the correct capitalization is used.
-   Verify that the integration flow is deployed and that the endpoint is visible on the CPI tenant monitor.
-   If the sender is an SAP system, ensure the destination is properly configured in SOAManager. Verify there are no typos.

For more information, see

-   [Manage Integration Content](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/manage-integration-content?version=Cloud) 
-   [Send the HTTP Request and Process the Integration Flow](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/send-http-request-and-process-integration-flow?version=Cloud) 



</td>
</tr>
<tr>
<td valign="top">

Issue with the inbound request reaching the tenant

</td>
<td valign="top">

Refer [Cloud Integration - How to Setup Secure HTTP Inbound Connection with Client Certificates](https://community.sap.com/t5/integration-blog-posts/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client/ba-p/13336237) 

For more information, see

-   [Load Balancer Root Certificates Supported by SAP](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/load-balancer-root-certificates-supported-by-sap?version=Cloud) 
-   [Managing Client Certificate Authentication for Custom Domains](https://help.sap.com/docs/btp/sap-btp-neo-environment/managing-client-certificate-authentication-for-custom-domains?version=Cloud) 



</td>
</tr>
<tr>
<td valign="top">

Issue during authorization check

</td>
<td valign="top">

Refer [Cloud Integration - How to Setup Secure HTTP Inbound Connection with Client Certificates](https://community.sap.com/t5/integration-blog-posts/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client/ba-p/13336237) 

</td>
</tr>
<tr>
<td valign="top">

SRT Framework Exception: error when calling SOAP Runtime functions

</td>
<td valign="top">

Refer [2584066](https://me.sap.com/notes/2584066) - CPI: "Connection to partner broken" Error while Pinging the Logical Port.

</td>
</tr>
<tr>
<td valign="top">

Date header not supported by HTTP Receiver Adapter

</td>
<td valign="top">

You can use a different header name to pass the date information

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration is not active for this subaccount

</td>
<td valign="top">

Refer [Configuring User Access to Cloud Integration](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/configuring-user-access-to-application?q=process+integration&version=Cloud) 

For more information, see

-   [Subscribing and Configuring Initial Access to SAP Integration Suite](10-InitialSetup/subscribing-and-configuring-initial-access-to-sap-integration-suite-8a3c8b7.md)
-   [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md)



</td>
</tr>
<tr>
<td valign="top" rowspan="11">

Outbound connection and security issues

For more information, see

-   [Configuring Outbound Communication](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/configuring-outbound-communication?version=Cloud) 
-   [Setting Up Outbound HTTP Connections](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/setting-up-outbound-http-connections?version=Cloud) 
-   [Cloud Integration - How to Setup Secure Outbound HTTP Connection using Keystore Monitor](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-how-to-setup-secure-outbound-http-connection-using/ba-p/13336604) 



</td>
<td valign="top">

Error: Unable to find valid certification path to requested target

</td>
<td valign="top">

Refer [2354153](https://me.sap.com/notes/2354153) - 'SunCertPathBuilderException' error in Cloud Integration outbound communication.

</td>
</tr>
<tr>
<td valign="top">

Error: HTTP response '401: Unauthorized' when communicating with \[backend URL\]

</td>
<td valign="top">

Refer [2548392](https://me.sap.com/notes/2548392) - 401 Unauthorized response when connecting BTP with backend system using Basic Authentication.

</td>
</tr>
<tr>
<td valign="top">

Error: ConversionException: OSCI issue

</td>
<td valign="top">

Refer [2514249](https://me.sap.com/notes/2514249) - ConversionException: OSCI issue in SAP Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

Error: FSM Integration Sequential Processing Failed

</td>
<td valign="top">

Refer [Regions](https://help.sap.com/docs/btp/sap-business-technology-platform/regions?version=Cloud) 

You can try modifying the SMTP port in the integration flow configuration from 25 to 587.

</td>
</tr>
<tr>
<td valign="top">

SFTP adapter issues

-   Error: \[CAMEL\]\[IFLOW\]\[POLL\_FAILED\]
-   Error: \[CAMEL\]\[IFLOW\]\[EXCEPTION\]
-   Error: \[CAMEL\]\[IFLOW\]\[CAUSE\]



</td>
<td valign="top">

Refer [2448465](https://me.sap.com/notes/2448465) - Connection to SFTP Server is failing with "HostKey has been changed" error.

For more information, see

-   [Cloud Integration – How to Setup Secure Connection to sftp Server](https://community.sap.com/t5/integration-blog-posts/cloud-integration-how-to-setup-secure-connection-to-sftp-server/ba-p/13326588) 
-   [3062478](https://me.sap.com/notes/3062478) - FAQ: SFTP adapter in SAP Cloud Integration.
-   [Regions](https://help.sap.com/docs/btp/sap-business-technology-platform/regions?version=Cloud)
-   [2715005](https://me.sap.com/notes/2715005) - Add SSL/TLS Certificates from a Website into the Key Store Monitor in CPI



</td>
</tr>
<tr>
<td valign="top">

Success Factors adapter issues

-   Error: \[CAMEL\]\[IFLOW\]\[POLL\_FAILED\]
-   Error: \[CAMEL\]\[IFLOW\]\[EXCEPTION\]
-   Error: \[CAMEL\]\[IFLOW\]\[CAUSE\]



</td>
<td valign="top">

Refer [Cloud Integration - How to configure Session Handling in Integration Flow](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-how-to-configure-session-handling-in-integration-flow/ba-p/13325908) 

</td>
</tr>
<tr>
<td valign="top">

Error: Problem during invoking SuccessFactors Web service.

</td>
<td valign="top">

Refer [Cloud Integration - How to configure Session Handling in Integration Flow](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-how-to-configure-session-handling-in-integration-flow/ba-p/13325908) 

</td>
</tr>
<tr>
<td valign="top">

HTTP 503 error

</td>
<td valign="top">

Refer [2498431](https://me.sap.com/notes/2498431) - CPI connecting with SAP ERP error HTTP response '503: Service Unavailable'.

</td>
</tr>
<tr>
<td valign="top">

HTTP response '403: Forbidden' error

</td>
<td valign="top">

Refer

-   [2452568](https://me.sap.com/notes/2452568) - Log and Trace files for SAP Cloud Connector.
-   [2473005](https://me.sap.com/notes/2473005) - Calling an On-Premise system from CPI fails with HTTP 403 Forbidden error through SAP Cloud Connector.



</td>
</tr>
<tr>
<td valign="top">

Error: 403 error in POST call using x-csrf-token

</td>
<td valign="top">

Refer

-   [Handling CSRF tokens in SAP Cloud Platform Integration](https://community.sap.com/t5/technology-blogs-by-members/handling-csrf-tokens-in-sap-cloud-platform-integration/ba-p/13338021) 
-   [Cloud Integration - How to configure Session Handling in Integration Flow](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-how-to-configure-session-handling-in-integration-flow/ba-p/13325908) 



</td>
</tr>
<tr>
<td valign="top">

411 error in POST call without body

</td>
<td valign="top">

Ensure you explicitly set an empty body prior to making the POST call to the target API.

</td>
</tr>
</table>

