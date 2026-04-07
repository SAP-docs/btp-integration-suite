<!-- loioeb14b2279fca422d9b64b6525a23fbdf -->

# Tasks and Permissions for Trading Partner Management

The following table provides an overview of which roles are required to accomplish the various tasks related to Trading Partner Management. It's also indicated in how far the tasks and roles are relevant for the main persona defined for Cloud Integration.

**Tasks and Permissions**


<table>
<tr>
<th valign="top">

Area

</th>
<th valign="top">

Task

</th>
<th valign="top">

Role Collection

</th>
<th valign="top">

Persona

</th>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

*Read Only*

-   View company profile

-   View trading partner profile
-   View agreement template
-   View partner agreement



</td>
<td valign="top">

PI\_Read\_Only

</td>
<td valign="top">

Integration Developer

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

*TPM Configuration*

-   Configure company profile, trading partner profile, and agreement template

-   Read and write trading partner agreement



</td>
<td valign="top">

PI\_Integration\_Developer

</td>
<td valign="top">

Integration Developer

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Publish trading partner agreement

</td>
<td valign="top">

PI\_Integration\_Developer

</td>
<td valign="top">

Integration Developer

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

*Push to Partner Directory*

Read and write tenant partner directory

</td>
<td valign="top">

PI\_Adminstrator

</td>
<td valign="top">

Tenant administrator

Technical user

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

*Push to Partner Directory*

Read and deploy credentials in the node manager

</td>
<td valign="top">

PI\_Integration\_Developer

</td>
<td valign="top">

Integration Developer

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

*Sensitive data management*

-   Read and write company sensitive data

-   Read and write partner sensitive data



</td>
<td valign="top">

PI\_Business\_Expert

</td>
<td valign="top">

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Read monitoring data

</td>
<td valign="top">

PI\_Read\_Only

</td>
<td valign="top">

Integration Developer

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Read payload data

</td>
<td valign="top">

PI\_Business\_Expert

</td>
<td valign="top">

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Perform operational tasks for interchanges:

-   Retry
-   Restart
-   Cancel



</td>
<td valign="top">

PI\_Business\_Expert

</td>
<td valign="top">

Business Expert

</td>
</tr>
</table>

To know more about the tasks and permissions involved in Cloud Integration, see [Task and Permissions](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/fda781c59e4b46a390ce5b409f60365e.html).



## Role Templates for Trading Partner Management

The following role templates exist for Trading Partner Management:

**Role Templates**


<table>
<tr>
<th valign="top">

Role Templates

</th>
<th valign="top">

Allowed Actions

</th>
</tr>
<tr>
<td valign="top">

TPMCompanyProfileRead

</td>
<td valign="top">

Read all company and subsidiary profile data, excluding sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMCompanyProfileEdit

</td>
<td valign="top">

Read, update, and delete all company and subsidiary profile data, excluding sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMCompanyProfileSensitiveRead

</td>
<td valign="top">

Read all company and subsidiary profile data, including sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMCompanyProfileSensitiveEdit

</td>
<td valign="top">

Read all company and subsidiary profile data, including sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMPartnerProfileRead

</td>
<td valign="top">

Read all trading partner and communication partner profile-related data, excluding sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMPartnerProfileEdit

</td>
<td valign="top">

Read, update, and delete all trading partner and communication partner profile-related data, excluding sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMPartnerProfileSensitiveDataRead

</td>
<td valign="top">

Read all trading partner and communication partner profile-related data, including sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMPartnerProfileSensitiveDataEdit

</td>
<td valign="top">

Read, update, and delete all trading partner and communication partner profile-related data, including sensitive contact person details

</td>
</tr>
<tr>
<td valign="top">

TPMAgreementConfigurationRead

</td>
<td valign="top">

-   Read all company and subsidiary profile data, excluding sensitive contact person details
-   Read all trading partner and communication partner profile-related data, excluding sensitive contact person details
-   Read agreement template-related data
-   Read trading partner agreement-related data
-   View published partner directory-related data
-   View list and details of executed cross actions, and export agreements
-   View custom search attributes, retry configuration, acknowledgment configuration, and custom rules



</td>
</tr>
<tr>
<td valign="top">

TPMAgreementConfigurationEdit

</td>
<td valign="top">

-   Read all company and subsidiary profile data, excluding sensitive contact person details
-   Read all trading partner and communication partner profile-related data, excluding sensitive contact person details
-   Read and maintain agreement template-related data
-   Read and maintain trading partner agreement-related data, excluding activating or deactivating agreements
-   View partner directory-related data
-   View and update the list of cross actions, and update and export logs details
-   Update, export, and import agreements
-   Migrate templates and agreements
-   View custom search attributes, retry configuration, acknowledgment configuration, and update custom rules



</td>
</tr>
<tr>
<td valign="top">

TPMAgreementConfigurationActivate

</td>
<td valign="top">

-   Read all company and subsidiary profile data, excluding sensitive contact person details
-   Read all trading partner and communication partner profile-related data, excluding sensitive contact person details
-   Read agreement template-related data
-   Read, activate, and deactivate trading partner agreement-related data \(if the TPMAgreementConfigurationEdit role is also assigned\)
-   View partner directory-related data
-   View and update the list of cross actions, and update and export logs details
-   Activate and deactivate agreements
-   View custom search attributes, retry configuration, acknowledgment configuration, and update custom rules



</td>
</tr>
</table>

Additionally, the following Cloud Integration role templates are relevant to users of Trading Partner Management:

**Additional Role Templates**


<table>
<tr>
<th valign="top">

Role Template \(Cloud Integration\)

</th>
<th valign="top">

Allowed Actions

</th>
</tr>
<tr>
<td valign="top">

AuthGroup\_TenantPartnerDirectoryConfigurator

</td>
<td valign="top">

Delete orphaned Partner Directory entries

</td>
</tr>
<tr>
<td valign="top">

ContentRead \(Integration Advisor\)

</td>
<td valign="top">

Read MIGs & MAGs

</td>
</tr>
<tr>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Read number ranges

</td>
</tr>
<tr>
<td valign="top">

WorkspacePackagesRead

</td>
<td valign="top">

Read integration packages and integration flows

</td>
</tr>
<tr>
<td valign="top">

CredentialsRead

</td>
<td valign="top">

Read user credentials and keystore entries

</td>
</tr>
<tr>
<td valign="top">

WorkspaceArtifactLocksDelete

</td>
<td valign="top">

Take over resource locks from other users

</td>
</tr>
</table>

