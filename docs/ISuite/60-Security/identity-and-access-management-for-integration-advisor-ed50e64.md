<!-- loioed50e648bfea4ca08c9be8d64abc5bed -->

# Identity and Access Management for Integration Advisor



<a name="loioed50e648bfea4ca08c9be8d64abc5bed__section_bk2_hdt_ngb"/>

## Access Management

Dialog users who access the platform are authenticated against an identity provider. SAP Identity Service \(ID Service\) is used by default. SAP ID Service is the central service for the process of managing identities and their lifecycles.

The authentication of inbound calls to the platform depends on the chosen authentication mode. If the client sends a client certificate, the authentication is done by the load balancer. The load balancer terminates the TLS connection; therefore, it checks the client certificate of the calling component against a list of trusted certification authorities \(CAs\). This certificate is mapped to a user. If basic authentication is configured, the calling entity is checked by the connected identity provider. Besides client certificate authentication, the platform supports basic authentication, OAuth, and Security Assertion Markup Language \(SAML\).



<a name="loioed50e648bfea4ca08c9be8d64abc5bed__section_jzt_3dt_ngb"/>

## User Management and Authorizations

Access to dedicated functions of the platform is controlled and protected by authorization checks. Several authorization groups are available to manage the authorizations of dialog users. An authorization group is based on a persona and defines a set of dedicated permissions relating to the tasks that come into play during the lifecycle of an integration project.



<a name="loioed50e648bfea4ca08c9be8d64abc5bed__section_f55_kxm_gfc"/>

## Role Collections in SAP BTP Cockpit

To work with Integration Advisor, assign the relevant role collection to your user. See [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).

The following table outlines the available role collections and what tasks they enable you to perform.


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*iadv-content-developer*

</td>
<td valign="top">

-   Discover the different Type systems enabled for the B2B standards
-   Design your own custom type system
-   Create Message Implementation Guidelines \(MIGs\) using the type systems
-   Simulate and activate your MIGs
-   Create interfaces and mappings from these MIGs using Mapping Guidelines \(MAGs\)
-   Simulate and activate your MAGs
-   Inject or export these data as Runtime Artifacts
-   Export and import your MIGs and MAGs



</td>
</tr>
<tr>
<td valign="top">

*iadv-content-administrator*

</td>
<td valign="top">

-   iadv-content-developer tasks
-   Unlock MIGs and MAGs locked by other users
-   Disable Proposal service



</td>
</tr>
<tr>
<td valign="top">

*iadv-content-read*

</td>
<td valign="top">

-   Read-only access to view the following artefacts:

    -   Type system library

    -   MIGs
    -   MAGs
    -   Custom Type Systems

-   Simulate MIGs and MAGs
-   Export artefacts

> ### Note:  
> Users with this role can view and browse these objects, but cannot edit or modify them in any way.
> 
> This role does not include importing artefacts \(MIGs/MAGs\).



</td>
</tr>
</table>

