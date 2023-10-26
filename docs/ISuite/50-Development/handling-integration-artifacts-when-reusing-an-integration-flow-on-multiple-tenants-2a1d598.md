<!-- loio2a1d59829a9749b1b1d39ef0cbd7dd02 -->

# Handling Integration Artifacts When Reusing an Integration Flow on Multiple Tenants

SAP Cloud Integration allows you to transport integration packages from a source tenant to a target tenant in order to re-use the content of the integration package \(integration flows, value mappings, OData APIs\) on the target tenant.

However, having transported an integration package to a target tenant does not mean that the contained integration flows run without any further actions.

For example, you need to make sure that security material and keystore content that is used/referenced by the integration flow is as well available on the target tenant. If that is not the case, the integration flow will fail.

This topic provides an overview of how to handle the different kinds of artifacts to make sure that integration content can be executed without errors also on the target tenant.


<table>
<tr>
<th valign="top">

Web UI Section

</th>
<th valign="top">

Artifact Type

</th>
<th valign="top">

Required Actions to After Content Transport

</th>
</tr>
<tr>
<td valign="top">

Design view

</td>
<td valign="top">

Integration flow, value mapping, OData API 

</td>
<td valign="top">

Can be transported as part of an integration package \(with one of the chosen transport options such like manual export/import, usage of SAP CTS+ or usage of the SAP BTP Transport Service\).

More information: [Content Transport](content-transport-e3c79d6.md)

</td>
</tr>
<tr>
<td valign="top">

Design view

</td>
<td valign="top">

Integration flow resources \(schemas, mappings\)

</td>
<td valign="top">

Are transported along with the integration flow.

</td>
</tr>
<tr>
<td valign="top">

Operations view/Keystore

</td>
<td valign="top">

Public key or certificate

</td>
<td valign="top">

Download public part of key pair \(certificate, certificate chain, root certificate, signing request\) from source tenant and import to target tenant.

More information: [Managing Keystore Entries](managing-keystore-entries-2dc8942.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Keystore

</td>
<td valign="top">

Private/public key pair

</td>
<td valign="top">

You need to newly create the key pair and upload it to the keystore of the target tenant..

More information: [Creating a Key Pair/SSH Key Pair](creating-a-key-pair-ssh-key-pair-b8a8601.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Security Material

</td>
<td valign="top">

User Credentials artifact

</td>
<td valign="top">

Cannot be reused; newly create artifact on target tenant \(and use same artifact name in order not to break any integration flow references to the artifact\).

More information: [Deploying a User Credentials Artifact](deploying-a-user-credentials-artifact-6912d63.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Security Material

</td>
<td valign="top">

Secure Parameter artifact

</td>
<td valign="top">

Cannot be reused; newly create artifact on target tenant \(and use same artifact name in order not to break any integration flow references to the artifact\).

More information: [Deploying a Secure Parameter Artifact](deploying-a-secure-parameter-artifact-4641d6c.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Security Material

</td>
<td valign="top">

OAuth2 Credentials

</td>
<td valign="top">

Cannot be reused; newly create artifact on target tenant \(and use same artifact name in order not to break any integration flow references to the artifact\).

More information: [Deploying an OAuth2 Client Credentials Artifact](deploying-an-oauth2-client-credentials-artifact-801b106.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Security Material

</td>
<td valign="top">

Known Hosts

</td>
<td valign="top">

Newly upload the known hosts file to the target tenant.

More information: [Deploying an SSH Known Hosts Artifact](deploying-an-ssh-known-hosts-artifact-46da324.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Security Material

</td>
<td valign="top">

PGP Public Keyring

</td>
<td valign="top">

Newly upload the keyring file to the target tenant.

More information: [Deploying a PGP Public Keyring](deploying-a-pgp-public-keyring-7f04458.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Security Material

</td>
<td valign="top">

PGP Secret Keyring

</td>
<td valign="top">

Newly upload the keyring file to the target tenant.

More information: [Deploying a PGP Secret Keyring](deploying-a-pgp-secret-keyring-9d8e1a9.md)

</td>
</tr>
<tr>
<td valign="top">

Operations view/Certificate-to-User Mappings

</td>
<td valign="top">

Certificate-to-User Mapping

</td>
<td valign="top">

Newly create certificate-to-user mapping on target tenant. You can reuse an existing certificate \(by manual upload from your computer\). Make sure that the role specified in the related integration flow \(sender adapter\) is defined on the target tenant and assigned to the user.

More information: [Managing Certificate-to-User Mappings, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/88ea2e5336d445f783c194c8d2780d35.html "The Manage Security area provides an overview of security-related artifacts. It also provides access to all certificate-to-user mappings defined for the tenant.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Operations view/JDBC Data Sources

</td>
<td valign="top">

Operations view/JDBC Data Source

</td>
<td valign="top">

Cannot be reused; newly create artifact on target tenant \(and use same artifact name in order not to break any integration flow references to the artifact\).

More information: [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md)

</td>
</tr>
</table>



<a name="loio2a1d59829a9749b1b1d39ef0cbd7dd02__section_mvv_qjd_fjb"/>

## Additional Content


<table>
<tr>
<th valign="top">

Artifact T

</th>
<th valign="top">

More information:

</th>
</tr>
<tr>
<td valign="top">

Partner Directory content

</td>
<td valign="top">

You need to migrate the Partner Directory content using the OData API.

More information: [Parameterizing Integration Flows Using the Partner Directory](parameterizing-integration-flows-using-the-partner-directory-b7812a5.md)

</td>
</tr>
</table>

When you plan to automate certain manual steps described in this topic, you can use the SAP Cloud Integration OData API.

For example, you can facilitate steps like:

-   Reading a security artifact from the source tenant and adding it to the target tenant

-   Exporting a certificate from the source tenant and importing it to the target tenant

-   Generating a key pair

-   Creating a certificate-to-user mapping


