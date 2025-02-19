<!-- loiof70f42555871469ba2167d9e078948d1 -->

# Limits in API Management

This topic describes the product configuration and the naming conventions for API Management.

Consider the boundary conditions mentioned in the following tables for building, managing, and reviewing the APIs. API Management is designed to perform at its maximum, when it is configured within the specified conditions. Exceeding these values leads to:

-   High API latency
-   Low API throughput
-   Failing API calls.

Currently, certain configurations are automatically enforced for optimal performance.

**Product Configurations**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Specified Configuration Values

</th>
<th valign="top">

Automatically Enforced

</th>
</tr>
<tr>
<td valign="top" colspan="3">

**API Proxies**

</td>
</tr>
<tr>
<td valign="top">

Port

</td>
<td valign="top">

Virtual host URL can only be configured only on the secured port 443 over https.

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

API proxy resource file size \(such as XSL, JavaScript or Python\).

</td>
<td valign="top">

15 MB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Maximum number of resources in an API product

</td>
<td valign="top">

-   An API product with more than 100 resources may experience timeouts when updating, deploying an API proxy, or publishing the product.

    If your API product includes API proxies with more than 100 resources, please raise a support ticket through the [SAP Support Portal](https://support.sap.com/en/index.html) using the component OPU-API-OD-DT.




</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" colspan="3">

Certificates

</td>
</tr>
<tr>
<td valign="top">

Certificate expiry and Credential Rotation

</td>
<td valign="top">

When your certificate expires or you need to rotate your credentials, create a new Keystore and upload the updated certificate to this new store.

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Certificate name length in Keystore

</td>
<td valign="top">

It is recommended that you keep your certificate name in a Keystore to no more than 25 characters.

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top" colspan="3">

**Virtual Host**

</td>
</tr>
<tr>
<td valign="top">

Additional virtual host in Cloud Foundry

</td>
<td valign="top">

By default, only 3 virtual hosts can be configured per tenant. In case you have a business requirement to have more than 3 virtual hosts within a tenant, please raise a support ticket through the [SAP Support Portal](https://support.sap.com/en/index.html) using the component OPU-API-OD-OPS.

> ### Note:  



</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top" colspan="3">

**Cache and KVM**

</td>
</tr>
<tr>
<td valign="top">

Caches

</td>
<td valign="top">

100 MB

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Cache key size

</td>
<td valign="top">

2 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Cache value size

</td>
<td valign="top">

512 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Cache expiration

</td>
<td valign="top">

\>=180 seconds, <= 30 days

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Key Value Map \(KVM\) key size

</td>
<td valign="top">

2 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Key Value Map \(KVM\) value size

</td>
<td valign="top">

10 KB

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top" colspan="3">

**Keys, Developers, Apps, Products**

</td>
</tr>
<tr>
<td valign="top">

API key size

</td>
<td valign="top">

2 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Custom attribute name size

</td>
<td valign="top">

255 characters

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Custom attribute value size

</td>
<td valign="top">

1024 characters

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Number of custom attributes permitted

</td>
<td valign="top">

18

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" colspan="3">

**OAuth**

</td>
</tr>
<tr>
<td valign="top">

OAuth access token expiration

</td>
<td valign="top">

\>= 180 seconds, <= 30 days

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

OAuth refresh token expiration

</td>
<td valign="top">

\>= 1 day, <= 90 days

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

OAuth access and refresh token size

</td>
<td valign="top">

2 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" colspan="3">

**System**

</td>
</tr>
<tr>
<td valign="top">

API proxy request URL size

</td>
<td valign="top">

7 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Request header size

</td>
<td valign="top">

18 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Response header size

</td>
<td valign="top">

25 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Request size \(for non-streamed HTTP requests\)

</td>
<td valign="top">

10 MB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Request size \(for streamed HTTP requests\)

</td>
<td valign="top">

<500 MB. However, if the connection is terminated unexpectedly, you must reinitiate the connection.

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Response size \(for non-streamed HTTP requests\)

</td>
<td valign="top">

10 MB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Timeout \( Applicable for all API Proxies and the Backend Server is expected to respond within the value set \)

</td>
<td valign="top">

55 Seconds

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Security Protocol

</td>
<td valign="top">

TLSv 1.2 only \( on Hyperscalers \)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

TLSv 1.2 & TLSv1.1 \( on SAP DC \)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

TLSv1.1 \(deprecated, planned to be removed by end of 2019\)

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

TLSv1.0 \(Unsupported\)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

SNI \( Server Name Indication \) Enforcement

</td>
<td valign="top">

In API Management, the client is expected to pass a SNI extension \(server\_name\) with target endpoint hostname as part of the initial TLS handshake. Based on the server\_name SNI extension the APIM servers will determine the certificate that would be served to the client.

For Client which doesn't support SNI extension, APIM would send a default certificate which is provided by SAP.

For Reference on SNI : [https://en.wikipedia.org/wiki/Server\_Name\_Indication](https://en.wikipedia.org/wiki/Server_Name_Indication)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Security Protocol applicable for API Management Runtime

</td>
<td valign="top">

TLSv 1.2 only \( on Hyperscalers & SAP DC \)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

TLSv1.0 & TLS 1.1 \(Unsupported\)

</td>
<td valign="top">

Yes

</td>
</tr>
</table>

**Naming Conventions**

Table below describes the naming constraints for API Management.


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Maximum Characters

</th>
<th valign="top">

Permitted Characters

</th>
</tr>
<tr>
<td valign="top">

API product

</td>
<td valign="top">

 

</td>
<td valign="top">

Alphanumeric, space, and the following: \_ - . \# $ %

</td>
</tr>
<tr>
<td valign="top">

Cache name

</td>
<td valign="top">

255

</td>
<td valign="top">

Alphanumeric

</td>
</tr>
<tr>
<td valign="top">

Developer app

</td>
<td valign="top">

 

</td>
<td valign="top">

Alphanumeric, space, and the following: \_ - . \# $ %

</td>
</tr>
<tr>
<td valign="top">

E-mail ID

</td>
<td valign="top">

 

</td>
<td valign="top">

Valid e-mail address syntax

</td>
</tr>
<tr>
<td valign="top">

Policy name

</td>
<td valign="top">

255

</td>
<td valign="top">

Alphanumeric and underscore.

</td>
</tr>
<tr>
<td valign="top">

Resource file names.

</td>
<td valign="top">

255

</td>
<td valign="top">

Alphanumeric, space, and the following: : / \\ ! @ \# $ % ^ & \{ \} \[ \] \( \) \_ + - = , . ~ '

</td>
</tr>
<tr>
<td valign="top">

Revision name

</td>
<td valign="top">

5

</td>
<td valign="top">

Numeric

</td>
</tr>
</table>

**Related Information**  


[Monitor the Health of Custom Domain Virtual Host Certificates Using SAP Cloud ALM](monitor-the-health-of-custom-domain-virtual-host-certificates-using-sap-cloud-alm-7bd9d9f.md "You can use SAP Cloud Application Lifecycle Management (ALM) application to proactively detect issues and monitor the health of custom domain virtual host certificates in API Management.")

[API Management FAQs](api-management-faqs-2d16070.md "Frequently asked questions for SAP API Management.")

