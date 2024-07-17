<!-- loio7a9198c0d50b45849193ff096d950b9c -->

# Security

This highlights the security aspects of using Graph.

With the increasing use of distributed systems for managing business data, the demands on security are also on the rise. When using a new API, you need to be sure that it supports your business needs without allowing unauthorized access to critical information. User errors, negligence, or attempted manipulation of your system shouldn’t result in loss of information or processing time. These demands on security apply likewise to Graph.

Graph's security is ensured by the security model of SAP BTP. The following are governed by SAP BTP security principles and services:

-   Tenants separation

-   Users

-   Identification

-   Role assignment

-   Authorization


The following table summarizes the main security features of Graph:


<table>
<tr>
<th valign="top">

Security Feature

</th>
<th valign="top">

Benefit

</th>
<th valign="top">

Graph Capability

</th>
</tr>
<tr>
<td valign="top">

Choice of user or client authentication

</td>
<td valign="top">

Support the prevention of unidentified or anonymous access by client applications to data exposed via Graph.

</td>
<td valign="top" rowspan="3">

Support for OAuth 2.0

</td>
</tr>
<tr>
<td valign="top">

Application registration

</td>
<td valign="top">

No access by unregistered applications to data exposed via Graph.

</td>
</tr>
<tr>
<td valign="top">

Application blocking

</td>
<td valign="top">

Provide separate clients to different applications, which allows the revocation of access rights from rogue applications by invalidating the client ID or secrets, and without affecting others.

</td>
</tr>
<tr>
<td valign="top">

Credentials rotation

</td>
<td valign="top">

Limiting the lifespan of a client secret reduces the risk of secret-based attacks and exploits by limiting the period of time during which a compromised secret may be valid.

</td>
<td valign="top">

Every service key of the Graph instance has a different client secret.

</td>
</tr>
<tr>
<td valign="top">

Data privacy

</td>
<td valign="top">

Graph is entirely stateless and doesn't store, cache, or otherwise keep copies of any business data.

</td>
<td valign="top">

Stateless mediation

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Data exposure control

</td>
<td valign="top">

Selective exposure of business data in a business data graph by configuring used destinations.

</td>
<td valign="top">

[Data Locating Policy](data-locating-policy-28d2c2c.md) 

</td>
</tr>
<tr>
<td valign="top">

Creation of different business data graphs for different data sets.

</td>
<td valign="top">

Dedicated business data graph per business scenario

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Data access control \(Authorization\)

</td>
<td valign="top">

Authorization and read/write/delete access to critical business data is approved by the underlying business systems based on the client-user identity.

</td>
<td valign="top">

Principal propagation \(also known as identity propagation\)

</td>
</tr>
<tr>
<td valign="top">

Configuration data and the API are protected by the `Graph_Key_User` role.

</td>
<td valign="top">

`Graph_Key_User` authorization

</td>
</tr>
<tr>
<td valign="top">

Segregation of applications restricts access to personal and confidential data by the tenant \(SAP BTP subaccount\)

</td>
<td valign="top">

SAP BTP tenant isolation

</td>
</tr>
<tr>
<td valign="top">

Representation of a Graph user by a business system technical user.

</td>
<td valign="top">

User impersonation in SAP BTP destinations

</td>
</tr>
<tr>
<td valign="top">

Business data access through the Graph Navigator Application

</td>
<td valign="top">

`Graph_Navigator_Viewer` authorization

</td>
</tr>
<tr>
<td valign="top">

Data encryption

</td>
<td valign="top">

The Graph API and the business system endpoints are encrypted by applying `TLS.At-rest` encryption isn't required because Graph doesn't persist or cache any sensitive business or personal data.

</td>
<td valign="top">

Data encryption, use of TLS

</td>
</tr>
<tr>
<td valign="top">

Endpoint attack and threat protection

</td>
<td valign="top">

Graph API endpoints are protected from \(D\)DoS \(L3/L4/L7\) attacks.

Graph API endpoints are protected from overload \(Spike arrest\).

</td>
<td valign="top">

External gateway

</td>
</tr>
<tr>
<td valign="top">

Security logging

</td>
<td valign="top">

Security-relevant events are stored for further analysis.

</td>
<td valign="top">

Graph logging

</td>
</tr>
<tr>
<td valign="top">

Secure software development and deployment practices

</td>
<td valign="top">

Software deployed to Graph infrastructure is continuously scanned for known vulnerabilities. Only software whose identity is confirmed is deployed.

</td>
<td valign="top">

Graph CI/CD pipeline

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration with API Management, allows the application of additional configurable traffic and security policies, such as IP-range controls, differential throttling, and more.

</td>
<td valign="top">

Integration with API Management 

</td>
</tr>
</table>

**Related Information**  


[SAP Integration Suite Security](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/a58b2400b3094009988a53b0a63b455a.html?version=CLOUD)

[SAP BTP Security](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/e129aa20c78c4a9fb379b9803b02e5f6.html)

