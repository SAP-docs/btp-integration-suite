<!-- loioed50e648bfea4ca08c9be8d64abc5bed -->

# Identity and Access Management



<a name="loioed50e648bfea4ca08c9be8d64abc5bed__section_bk2_hdt_ngb"/>

## Access Management

Dialog users who access the platform are authenticated against an identity provider. SAP Identity Service \(ID Service\) is used by default. SAP ID Service is the central service for the process of managing identities and their lifecycles.

The authentication of inbound calls to the platform depends on the chosen authentication mode. If the client sends a client certificate, the authentication is done by the load balancer. The load balancer terminates the TLS connection; therefore, it checks the client certificate of the calling component against a list of trusted certification authorities \(CAs\). This certificate is mapped to a user. If basic authentication is configured, the calling entity is checked by the connected identity provider. Besides client certificate authentication, the platform supports basic authentication, OAuth, and Security Assertion Markup Language \(SAML\).



<a name="loioed50e648bfea4ca08c9be8d64abc5bed__section_jzt_3dt_ngb"/>

## User Management and Authorizations

Access to dedicated functions of the platform is controlled and protected by authorization checks. Several authorization groups are available to manage the authorizations of dialog users. An authorization group is based on a persona and defines a set of dedicated permissions relating to the tasks that come into play during the lifecycle of an integration project.



<a name="loioed50e648bfea4ca08c9be8d64abc5bed__section_r1z_kdt_ngb"/>

## Personas and Roles

There are two personas associated with Integration Advisor: Tenant Administrator and Content Developer. Here’s a brief description of the responsibilities of each role and the roles required for those personas.


<table>
<tr>
<th valign="top">

Persona



</th>
<th valign="top">

Responsibilities



</th>
<th valign="top">

Roles Required in Application



</th>
<th valign="top">

Roles Required in SAP BTPAccount



</th>
</tr>
<tr>
<td valign="top">

Tenant Admin



</td>
<td valign="top">

Manage Consumer accounts and subscriptions

Responsibilities:

-   Enable IA Subscription.

-   Manage users and roles in consumer account




</td>
<td valign="top">

None



</td>
<td valign="top">

Administrator



</td>
</tr>
<tr>
<td valign="top">

Content Developer



</td>
<td valign="top">

Develops and maintains customer content

Responsibilities:

-   Read & consume type systems

-   Create & maintain Message Guidelines

-   Create & maintain Mapping Guidelines

-   Refresh B2B license entitlements.




</td>
<td valign="top">

Typesystem.Read

Guidelines.ReadWrite



</td>
<td valign="top">

None



</td>
</tr>
<tr>
<td valign="top">

IA Administrator



</td>
<td valign="top">

Develops and maintains customer content

Responsibilities:

-   Read & consume type systems

-   Create & maintain Message Implementation Guidelines
-   Create & maintain Mapping Guidelines
-   Refresh B2B license entitlements
-   Unlock Message Guidelines & Mapping Guidelines locked by other users



</td>
<td valign="top">

Guidelines.Administrator

Guidelines.ReadWrite

Typesystem.Read



</td>
<td valign="top">

None



</td>
</tr>
</table>

