<!-- loiob7a3906a083f44da86fde70e81d7bb97 -->

# Troubleshooting Adapters

Information on troubleshooting incidents and errors with sender and receiver adapters.



<a name="loiob7a3906a083f44da86fde70e81d7bb97__section_vkl_b1w_ffc"/>

## Issues with OData Sender Adapter

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
<td valign="top">

Sender Adapter issue

</td>
<td valign="top">

Common errors with OData Sender Adapter

</td>
<td valign="top">

Refer [2905000](https://me.sap.com/notes/2905000) - How to Troubleshoot an Error Occurred with SAP Cloud Integration OData Sender Adapter?.

</td>
</tr>
</table>



<a name="loiob7a3906a083f44da86fde70e81d7bb97__section_ivj_p1w_ffc"/>

## Issues with OData V2 Receiver Adapter

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
<td valign="top">

V2 Receiver adapter issue

</td>
<td valign="top">

Ccommon errors with OData V2 Receiver Adapter

</td>
<td valign="top">

Refer [2857920](https://me.sap.com/notes/2857920) - How to Troubleshoot Common Errors in SAP Cloud Integration OData V2 Receiver Adapter.

</td>
</tr>
</table>



<a name="loiob7a3906a083f44da86fde70e81d7bb97__section_pvd_z1w_ffc"/>

## Issues with HTTP Sender and Receiver Adapters

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
<td valign="top" rowspan="8">

Client side issues.

</td>
<td valign="top">

HTTP 401/411 error - Client-Length header issue

</td>
<td valign="top">

Refer [HTTP Receiver Adapter](50-Development/http-receiver-adapter-2da452e.md)

</td>
</tr>
<tr>
<td valign="top">

HTTP 403 forbidden error - Client Certificate authentication issue

</td>
<td valign="top">

Refer [HTTPS Sender Adapter](50-Development/https-sender-adapter-0ae4a78.md).

For more information, see [Cloud Integration on CF - How to Setup Secure HTTP Inbound Connection with Client Certificates](https://community.sap.com/t5/integration-blog-posts/cloud-integration-on-cf-how-to-setup-secure-http-inbound-connection-with/ba-p/13393777)

</td>
</tr>
<tr>
<td valign="top">

No 'Access-Control-Allow-Origin' header is present on the requested resource issue

</td>
<td valign="top">

The HTTP Adapter does not support the "Access-Control-Allow-Origin" header in AJAX responses, hindering cross-origin resource sharing.

</td>
</tr>
<tr>
<td valign="top">

HTTP 500 error - Null pointer exception issue

</td>
<td valign="top">

Redeploy the integration flow. Analyze the logs to identify the error details.

</td>
</tr>
<tr>
<td valign="top">

HTTP - POST call fails with 403 error

</td>
<td valign="top">

Refer

[Cloud Integration - How to configure Session Handling in Integration Flow](https://community.sap.com/t5/technology-blog-posts-by-sap/cloud-integration-how-to-configure-session-handling-in-integration-flow/ba-p/13325908#:~:text=On%20Exchange%3A%20If%20this%20configuration,meaning%20for%20one%20message%20exchange.&text=On%20Integration%20Flow%3A%20Using%20this,calls%20of%20the%20integration%20flow.)

[Handling CSRF tokens in SAP Cloud Platform Integration](https://community.sap.com/t5/technology-blog-posts-by-members/handling-csrf-tokens-in-sap-cloud-platform-integration/ba-p/13338021)

</td>
</tr>
<tr>
<td valign="top">

HTTP - POST call fails with 411 error

</td>
<td valign="top">

Ensure the request body is explicitly set as empty before making a POST call to the target API.

</td>
</tr>
<tr>
<td valign="top">

Integration flow processing getting stuck at HTTP Receiver

</td>
<td valign="top">

Contact SAP product support to assist with increasing your tenant's worker thread count.

</td>
</tr>
<tr>
<td valign="top">

org.apache.camel.component.ahc.AhcOperationFailedException: HTTP operation failed invoking some URL with status code 400

</td>
<td valign="top">

Set the **SAP\_DisableMonitoringHeaders** property to `true` in the Content Modifier immediately before the HTTP Adapter step.

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Server Side issues

</td>
<td valign="top">

org.apache.camel.TypeConversionException error

</td>
<td valign="top">

Use a content modifier to manually remove the header.

</td>
</tr>
<tr>
<td valign="top">

Connection errors - java.io.IOException: Remotely closed

</td>
<td valign="top">

Upgrading to a newer version of the cloud connector may resolve the issue. If the problem persists, further investigation into network-related aspects is necessary.

</td>
</tr>
<tr>
<td valign="top">

The input lacks data, causing a JSON to XML conversion issue

</td>
<td valign="top">

Ensure that integration flow is compatible with an empty body.

</td>
</tr>
<tr>
<td valign="top">

Multiple MPLs are generated for a single call to Cloud Integration

</td>
<td valign="top">

Review the HTTP access logs and MPLs to verify if multiple calls are reaching Cloud Integration, particularly at fixed intervals. This should be investigated on the client side. And also reduce the load to complete processing before a timeout occurs.

</td>
</tr>
<tr>
<td valign="top">

javax.servlet.ServletException: Error during write of the response: causes java.io.IOException: Broken pipe

</td>
<td valign="top">

Investigate the reason for the client terminating the connection. Additionally, verify whether the client's timeout setting is shorter than the server's response processing time.

</td>
</tr>
<tr>
<td valign="top">

Server called with HTTP adapter do not support Transfer-Encoding header and expects content-length header

</td>
<td valign="top">

Perform the following:

1.  HTTP 1.1 permits both headers but prevents their use in the same request. The endpoint should ideally conform to this standard, as followed by the adapter.
2.  Use a Groovy script to convert the stream to a byte array or string to alter the body generator type. Ensure correct encoding to avoid potential issues.



</td>
</tr>
<tr>
<td valign="top">

Error: java.net.UnknownHostException

</td>
<td valign="top">

Create a support ticket on the component **BC-MID-SCC**.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Comfiguration issues

</td>
<td valign="top">

Unable to fetch OAuth token

</td>
<td valign="top">

Refer [Cloud Platform Integration OAuth2 Credentials](https://community.sap.com/t5/technology-blog-posts-by-members/cloud-platform-integration-oauth2-credentials/ba-p/13446596)

</td>
</tr>
<tr>
<td valign="top">

403 error while calling deployed integration flow endpoint

</td>
<td valign="top">

Refer [Self-Service Enablement of Cloud Integration Service on Cloud Foundry Environment](https://community.sap.com/t5/technology-blog-posts-by-sap/self-service-enablement-of-cloud-integration-service-on-cloud-foundry/ba-p/13404094).

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Network issues

</td>
<td valign="top">

Does not receive acknowledgement and sends same payload after one min.

</td>
<td valign="top">

For further analysis, create a support ticket to the network team **BC-NEO-IT-NW**.

</td>
</tr>
<tr>
<td valign="top">

Error 400 when calling SuccessFactors endpoint - Error: org.apache.camel.component.ahc.AhcOperationFailedException: HTTP operation failed invoking https://api12preview.sapsf.eu/odata/v2/generateNextPersonID?$format=json with statusCode: 400

</td>
<td valign="top">

Refer [2642240](https://me.sap.com/notes/2642240) - HTTP 400 from endpoint. Operation Failed due to a previous Successfactors call.

</td>
</tr>
<tr>
<td valign="top">

Connection to Cloud Integration using HTTP channel – Error

</td>
<td valign="top">

Investigate which component takes more time in your integration flow. Further investigate tcp dump to find at which side the connection close request comes from.

</td>
</tr>
<tr>
<td valign="top">

Outbound calls work usually for the endpoint. However, with more frequent calls \(higher load\), a timeout or unavailability is observed as response to HTTP requests

</td>
<td valign="top">

Perform the following:

1.  Performance test to check if the server is resilient to the load.
2.  For further investigation, create a support ticket on the component **LOD-HCI-PI-OPS** or to the team **BC-NEO-IT-NW**.



</td>
</tr>
<tr>
<td valign="top">

Prolonged time taken by a request, which used to finish much quicker earlier. Maybe observed after software or system update.

</td>
<td valign="top">

Check for changes from Network or Proxy team that occurred lately. Test without proxy and observe.

</td>
</tr>
<tr>
<td valign="top">

Network errors after specified interval when accessed from different physical locations or using different clients.

</td>
<td valign="top">

Create a ticket with Cloud Integration so that the Network/Ops team can look into the issue. Alternatively, reduce the processing time.

</td>
</tr>
<tr>
<td valign="top">

When an outbound calls is made, HTTP receiver could not complete TLS negotiation inside stipulated connect timeout of 10000ms.

</td>
<td valign="top">

Perform the following:

1.  Check if the failures happen around the same time - 10 failures in 1 minute for one endpoint and then no issue during next 1 minute. This could be a server side issue.
2.  Are the failures happening for only on worker - that is, the issue is happening only in one worker and not a single failure for other workers. This could be a possible issue with Cloud Integration. Create a ticket with component **BC-NEO-IT-NW**.
3.  If the issue is happening only for one endpoint - that is, only integration flow with a specific endpoint fails and passes for all other endpoints. This could be a server side issue.



</td>
</tr>
</table>

