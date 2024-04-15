<!-- loiob8ccb53b9ec44652b885476f02184a0f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Security Material

The Manage Security Material area provides an overview of security-related artifacts.

You open the *Manage Security Material* area with the following actions:

Select the tile *Security Material*.

Security artifacts with the corresponding status \(of the tile\) are displayed.



## Security Material Overview

A list of security material is displayed in a table. For each artifact, the following attributes are displayed:

**Attributes of Security-Related Artifacts**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name* 

</td>
<td valign="top">

Display name of the artifact

</td>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top">

Possible values:

-   *User Credentials*

    For *User Credentials* artifacts \(a tooltip indicates the kind of the artifact\).

-   *OAuth2 Credentials*
-   *OAuth2 Authorization Code*

-   *Secure Parameter*

    For *Secure Parameter* artifacts \(a tooltip indicates the kind of the artifact\).

-   *Known Hosts \(SSH\)*




</td>
</tr>
<tr>
<td valign="top">

*Status* 

</td>
<td valign="top">

Displays the state with regard to the artifact deployment.

This status indicates whether an artifact has been deployed successfully on a tenant or whether it still needs to be authorized.

Possible values:

-   *Stored* 

    > ### Note:  
    > Refresh the list to see the current status.

-   *Deployed* 

-   *Error*

-   *Unauthorized* \(for OAuth2 Authorization Code\)




</td>
</tr>
<tr>
<td valign="top">

*Deployed By* 

</td>
<td valign="top">

User who deployed the artifact

</td>
</tr>
<tr>
<td valign="top">

*Deployed On* 

</td>
<td valign="top">

Time when the artifact was deployed

</td>
</tr>
</table>

> ### Note:  
> To add PGP keyrings, see [Managing PGP Keys](managing-pgp-keys-cd478a7.md). To maintain keystore entires, see [Managing Keystore Entries](managing-keystore-entries-2dc8942.md)

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.



## Actions

**Actions**


<table>
<tr>
<td valign="top">

*Create*

</td>
<td valign="top">

To create/deploy a new artifact, choose *Create* and select the artifact type \(possible for the following artifact types: *User Credentials*, *OAuth2 Client Credentials*, *OAuth2 SAML Bearer Assertion*, *OAuth2 Authorization Code* and *Secure Parameter*\).

</td>
</tr>
<tr>
<td valign="top">

*Upload*

</td>
<td valign="top">

To add a *Known Hosts \(SSH\)* file, select *Upload*.

</td>
</tr>
<tr>
<td valign="top">

*Authorize*

</td>
<td valign="top">

To authorize an existing artifact, select the artifact in the table and choose *Authorize* \(only supported for OAuth2 Authorization Code\).

</td>
</tr>
<tr>
<td valign="top">

*Edit*

</td>
<td valign="top">

To edit and redeploy an existing artifact, select the artifact in the table and choose *Edit* \(only supported for Credentials\).

</td>
</tr>
<tr>
<td valign="top">

*Download*

</td>
<td valign="top">

To download an artifact, select the artifact in the table and choose *Download* \(only supported for Known Hosts\).

</td>
</tr>
<tr>
<td valign="top">

*Delete*

</td>
<td valign="top">

You can also delete an artifact \(supported for all artifact types except *Keystore*\).

</td>
</tr>
</table>

**Related Information**  


[Deploying a User Credentials Artifact](deploying-a-user-credentials-artifact-6912d63.md "To set up a connection using basic authentication or username token authentication, you have to specify the required attributes (for example, user name and password).")

[Deploying an SSH Known Hosts Artifact](deploying-an-ssh-known-hosts-artifact-46da324.md "This artifact type specifies the known hosts file used when configuring secure connectivity based on SSH File Transfer Protocol (SFTP).")

[Deploying a Secure Parameter Artifact](deploying-a-secure-parameter-artifact-4641d6c.md "Use the secure parameter artifact to deploy confidential data, for example, for custom adapters.")

[Deploying an OAuth2 Client Credentials Artifact](deploying-an-oauth2-client-credentials-artifact-801b106.md "Many web servers use OAuth 2.0 for authorization purposes. If you want to connect to a system that uses OAuth 2.0 authentication, you need to deploy an OAuth2 Credentials artifact using the following procedure.")

[Deploying a PGP Secret Keyring](deploying-a-pgp-secret-keyring-9d8e1a9.md "This artifact contains the PGP secret keys for the usage of Open Pretty Good Privacy (PGP). The private key enables the tenant to decrypt or sign messages.")

[Deploying a PGP Public Keyring](deploying-a-pgp-public-keyring-7f04458.md "This artifact contains the public key that enables the tenant to encrypt or verify messages using the Pretty Good Privacy (PGP) standard.")

