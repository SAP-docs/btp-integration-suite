<!-- loio069b461074a14d7b8cb2e2e273ac67db -->

# Troubleshooting HTTP Error Catalog

Information on troubleshooting HTTP errors in your integration scenarios.



<a name="loio069b461074a14d7b8cb2e2e273ac67db__section_xwh_g5j_dfc"/>

## Issues related to HTTP errors

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
<td valign="top" rowspan="4">

Inbound HTTP errors

</td>
<td valign="top">

HTTP 401 Error

1.  Cloud Foundry \> Authentication issues

    -   SAP ID Service \> Login issue

        -   Basic Authentication issue
        -   Certificate Based issue

    -   Custom IDP issue




</td>
<td valign="top">

For more information, see

[How to check Cloud Integration logs for errors- Troubleshooting inbound HTTP errors section](https://help.sap.com/docs/SUPPORT_CONTENT/sci/3361897730.html)

[Monitoring System Log Files, Cloud Foundry Environment](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/monitoring-system-log-files-cloud-foundry-environment?version=Cloud)

Gather both Cloud Integration and Sender systems logs.

> ### Note:  
> -   For Basic Authentication issues, create a support ticket on the component LOD-HCI-PI-OPS with the following information:
>     1.  Affected Tenant
>     2.  Name of the affected Integration flow
>     3.  Sender logs
>     4.  Endpoint used
>     5.  Screenshot of test outside of Cloud Integration
>     6.  Screenshots and logs of the troubleshooting done
> 
> -   For OAuth 2.0 issues, create a support ticket to this team BC-CP-CF-SEC-IAM.

Also see [1808560](https://me.sap.com/notes/1808560) - How to reset an S-user ID password - SAP ID Service.

For Custom IDP issue, see [2651199](https://me.sap.com/notes/2651199) - How to unlock user password in Identity Authentication.

> ### Note:  
> For further issues,
> 
> -   Create a support ticket to this team BC-IAM-IDS with the following information:
>     1.  Screenschot of the user unlocked
>     2.  Tenant URL
> 
> -   Create a support ticket to this team BC-CP-CF-SEC-IAM.

For more information, refer [Cloud Integration on CF - How to Setup Secure HTTP Inbound Connection with Client Certificates](https://community.sap.com/t5/integration-blog-posts/cloud-integration-on-cf-how-to-setup-secure-http-inbound-connection-with/ba-p/13393777)

For more information, refer [Access Logs, Neo Environment](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/access-logs-neo-environment?version=Cloud)

</td>
</tr>
<tr>
<td valign="top">

HTTP 403 error

</td>
<td valign="top">

Refer

[Defining Permissions for Senders to Process Messages on a Runtime Node](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/defining-permissions-for-senders-to-process-messages-on-runtime-node?version=Cloud)

[2642897](https://me.sap.com/notes/2642897) - Authorization error on connection test to CPI Tenant.

[Handling CSRF tokens in SAP Cloud Platform Integration](https://community.sap.com/t5/technology-blogs-by-members/handling-csrf-tokens-in-sap-cloud-platform-integration/ba-p/13338021)

[Invoking an OData API](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/invoking-odata-api?version=Cloud)

[Creating OData Service from SOAP using HCI \(beta\)](https://community.sap.com/t5/technology-blogs-by-members/creating-odata-service-from-soap-using-hci-beta/ba-p/13195594)

-   [2354728](https://me.sap.com/notes/2354728) - Connection test to SAP Cloud Platform Integration tenant's endpoint is throwing HTTP 403 error.
-   [2600568](https://me.sap.com/notes/2600568) - RFC destination to SCI fails with 403 forbidden error.



</td>
</tr>
<tr>
<td valign="top">

HTTP 404 error

</td>
<td valign="top">

Refer

-   [Manage Integration Content](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/manage-integration-content?version=Cloud)
-   [Send the HTTP Request and Process the Integration Flow](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/send-http-request-and-process-integration-flow?version=Cloud) 



</td>
</tr>
<tr>
<td valign="top">

HTTP 405 error

</td>
<td valign="top">

Refer

-   [2584066](https://me.sap.com/notes/2584066) - CPI: "Connection to partner broken" Error while Pinging the Logical Port.
-   [2400906](https://me.sap.com/notes/2400906) - HTTP HEAD request is not allowed in SAP Cloud Platform Integration, message "405 Method Not Allowed".



</td>
</tr>
<tr>
<td valign="top" rowspan="8">

Outbound HTTP errors

</td>
<td valign="top">

HTTP 302 error

</td>
<td valign="top">

Refer to the blog [HTTP redirections in CPI](https://community.sap.com/t5/technology-blogs-by-members/http-redirections-in-cpi/ba-p/13357622) 

</td>
</tr>
<tr>
<td valign="top">

HTTP 400 error

</td>
<td valign="top">

Refer

-   [2656227](https://me.sap.com/notes/2656227) - Error: com.sap.gateway.core.ip.component.odata.exception.OsciException: Bad Request : 400 : HTTP/1.1.
-   [2725165](https://me.sap.com/notes/2725165) - HTTP 400 Bad Request Error: Encountered with OData v2 Adapter during Update/Merge/Patch Operations.



</td>
</tr>
<tr>
<td valign="top">

HTTP 401 error

</td>
<td valign="top">

Refer [2548392](https://me.sap.com/notes/2548392) - 401 Unauthorized response when connecting BTP with backend system using Basic Authentication.

</td>
</tr>
<tr>
<td valign="top">

HTTP 403 error

</td>
<td valign="top">

Refer

-   [2473005](https://me.sap.com/notes/2473005) - Calling an On-Premise system from CPI fails with HTTP 403 Forbidden error through SAP Cloud Connector.
-   [2681175](https://me.sap.com/notes/2681175) - Undesired cookie percent-encoding of SET\_COOKIE after GET\_COOKIE.



</td>
</tr>
<tr>
<td valign="top">

HTTP 404 error

</td>
<td valign="top">

Refer [2599585](https://me.sap.com/notes/2599585) - CPI: HTTP response '404: Not found' when communicating between CPI and backend system.

</td>
</tr>
<tr>
<td valign="top">

HTTP 500 error

</td>
<td valign="top">

Investigate this system's logs for the reason it is returning this error. Additionally, refer to the [Message Processing Log](50-Development/message-processing-log-b32f8cd.md) on level DEBUG for more information.

</td>
</tr>
<tr>
<td valign="top">

HTTP 502 error

</td>
<td valign="top">

Refer [2768622](https://me.sap.com/notes/2768622) - HTTP response '502: Bad Gateway' on CPI - SAP CPI/HCI vs SAP ERP HCM.

</td>
</tr>
<tr>
<td valign="top">

HTTP 503 error

</td>
<td valign="top">

Refer

-   [2724278](https://me.sap.com/notes/2724278) - CPI error: HTTP response '503: Service Unavailable' when connecting to an external server.
-   [2498431](https://me.sap.com/notes/2498431) - CPI connecting with SAP ERP error HTTP response '503: Service Unavailable'.



</td>
</tr>
</table>

