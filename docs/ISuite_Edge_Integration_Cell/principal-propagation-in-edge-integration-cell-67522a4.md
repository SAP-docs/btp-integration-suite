<!-- loio67522a4e56ed4e4b9b9db9b53823e491 -->

# Principal Propagation in Edge Integration Cell

When a user triggers an integration in SAP Integration Suite, the backend system often needs to know the identity of the authenticated user, not just the integration service. Principal Propagation securely passes the user's identity through the integration layer to the backend system, allowing the backend to enforce user-specific authorizations and maintain accurate audit logs.



<a name="loio67522a4e56ed4e4b9b9db9b53823e491__section_Overview_eic_PP"/>

## Overview

Without principal propagation, all requests appear to originate from the same technical service account. As a result, the backend system cannot distinguish individual users, apply user-specific permissions, or create a meaningful audit trail.

With principal propagation, the integration layer forwards the authenticated user's identity to the backend system, enabling the backend to process the request according to that user's own roles and authorizations.



## Persona

This information is intended for administrators and integration developers who use SAP Integration Suite on Edge Integration Cell runtime profile.



## Supported Scenarios

Principal Propagation in Edge Integration Cell supports the following backend scenarios:

Choose the configuration procedure that matches your backend system.


<table>
<tr>
<th valign="top">

Backend System

</th>
<th valign="top">

Identity Mechanism

</th>
</tr>
<tr>
<td valign="top">

SAP cloud applications \(such as SAP SuccessFactors and SAP Concur\)

</td>
<td valign="top">

OAuth 2.0 access token using a SAML 2.0 Bearer Assertion

</td>
</tr>
<tr>
<td valign="top">

On-premise SAP systems \(such as SAP ERP, SAP S/4HANA\)

</td>
<td valign="top">

Short-lived X.509 client certificate

</td>
</tr>
</table>

For more information about setup and configuration details, see:

-   [Principal Propagation to SAP Cloud Applications](principal-propagation-to-sap-cloud-applications-d914798.md)
-   [Principal Propagation to On-Premise SAP Systems](principal-propagation-to-on-premise-sap-systems-78ab561.md)

