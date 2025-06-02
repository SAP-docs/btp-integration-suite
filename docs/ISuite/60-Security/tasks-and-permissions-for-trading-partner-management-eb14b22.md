<!-- loioeb14b2279fca422d9b64b6525a23fbdf -->

# Tasks and Permissions for Trading Partner Management

The following table provides an overview of which roles are required in order to accomplish the various tasks related to Trading Partner Management. It's also indicated in how far the tasks and roles are relevant for the main persona defined for Cloud Integration.

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

-   Configure company profile, trading partner profile and agreement template

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

Read and deploy credentials in node manager

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

Execute operational tasks for interchanges:

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

