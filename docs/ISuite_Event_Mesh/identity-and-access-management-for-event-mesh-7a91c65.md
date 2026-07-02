<!-- loio7a91c65432454a0c9a15537c261d02f7 -->

# Identity and Access Management for Event Mesh

Learn about identity and access management for Event Mesh.



<a name="loio7a91c65432454a0c9a15537c261d02f7__section_zrw_p25_hbc"/>

## Authentication and Authorization



### Authentication

Users who access Event Mesh-related features in SAP Integration Suite are authenticated against an identity provider. SAP Identity Service \(ID Service\) is used by default. SAP ID Service is the central service for the process of managing identities and their life cycles.

User authentication is provided by the authentication methods supported by SAP BTP, which uses the Security Assertion Markup Language \(SAML\) 2.0 protocol for both authentication and single sign-on.



### Authorization

Authorization for Event Mesh determines the level of access. Administrators generally authorize users with appropriate roles and role collections.



### Authentication for Components

The following table describes the components and their associated authentication actions:


<table>
<tr>
<th valign="top">

Component

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Messaging gateways

</td>
<td valign="top">

The consumer application, for example SAP S/4 HANA, calls the messaging gateways with the OAuth token of the OAuth client. The OAuth token is created when you create a service instance of the *Event Mesh Message Client* in the SAP Business Technology Platform cockpit.

</td>
</tr>
<tr>
<td valign="top">

Integration Suite user interface

</td>
<td valign="top">

An integration developer or administrator of the Event Mesh capability accesses the Integration Suite user interface. While doing so, the user initiates an OAuth-based login and forwards the OAuth token to the Event Mesh back end. The back-end component validates the token and checks for the appropriate scope.

</td>
</tr>
</table>

