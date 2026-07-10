<!-- loio399b6c6d98e24cbd8087a9e36248401d -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Monitor APIs and MCP Servers

Check the runtime logs and the status of an API artifact.

To monitor an API artifact, log on to SAP Integration Suite, go to *Monitor* \> *Integrations and APIs*, and select the runtime from the *Runtime* drop-down menu under *Overview*.

**Tiles in the Integrations and APIs Monitoring Page**


<table>
<tr>
<th valign="top">

Container

</th>
<th valign="top">

Sub-Category

</th>
<th valign="top">

Runtime

</th>
<th valign="top">

Allows you to ...

</th>
</tr>
<tr>
<td valign="top">

Monitor Status Overview

</td>
<td valign="top">



</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

Monitor the status overview of your messages according to your custom filters. See, [Monitor Message Status Overview](monitor-message-status-overview-0cde046.md)

.

</td>
</tr>
<tr>
<td valign="top">

Monitor Message Processing

</td>
<td valign="top">



</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

Monitor message processing on the tenant.

Tiles in this section show the number and status of processed messages within a specified time window. See, [Monitor Message Processing](monitor-message-processing-314df3f.md).

</td>
</tr>
<tr>
<td valign="top">

Manage Integration Content

</td>
<td valign="top">



</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

Manage integration content for the tenant.

Tiles in this section show the number and status of integration content artifacts \(such as integration flows\). See, [Manage Integration Content](manage-integration-content-09a7223.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Manage Security

</td>
<td valign="top">

Security Material

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

The Security Material tile provides access to and allows you to deploy security-related artifacts such as user credentials artifacts. See, [Manage Security for Edge Integration Cell](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/manage-security-for-edge-integration-cell?version=CLOUD).

</td>
</tr>
<tr>
<td valign="top">

Keystore

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

The Keystore tile provides access to the content of the tenant keystore and allows you to manage its content and also the lifecycle of keys and certificates. See,[Manage Keystore for Edge Integration Cell](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/manage-keystore-for-edge-integration-cell?version=CLOUD).

</td>
</tr>
<tr>
<td valign="top">

PGP Keys

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

The PGP Keys tile allows you to check the information of the PGP keys. See,[Manage PGP Keyrings for Edge Integration Cell](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/manage-pgp-keyrings-for-edge-integration-cell?version=CLOUD).

</td>
</tr>
<tr>
<td valign="top">

Access Policies

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

The Access Policies tile provides an overview of the existing access policies and allows you to maintain them. See, [Access Management for API Artifact](access-management-for-api-artifact-2a89115.md).

</td>
</tr>
<tr>
<td valign="top">

JDBC Material

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

The JDBC Material tile provides an overview of the used JDBC data sources \(artifact connections interacting with a database\) as well as of the JDBC drivers. See, [Managing JDBC Material](managing-jdbc-material-32ee7cd.md).

</td>
</tr>
<tr>
<td valign="top">

User Roles

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

The User Roles tile provides an overview of the existing user roles and allows you to maintain them. See,[Managing User Roles](managing-user-roles-4e86f0d.md).

</td>
</tr>
<tr>
<td valign="top">

Connectivity Tests

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

The Connectivity Tests tile allows you to test the connectivity to a receiver system. See, [Performing Connectivity Tests](performing-connectivity-tests-d5b2fae.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Manage Stores

</td>
<td valign="top">

Data Stores

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

The Data Stores tile provides an overview of storages on the tenant, which are temporarily used to persist data of different kind during message processing \(when using the Data Store Operations step type\). See, [Managing Data Stores](managing-data-stores-ac39f1d.md)

</td>
</tr>
<tr>
<td valign="top">

Variables

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

The Variables tile allows you to monitor variables used in integration flows. See, [Managing Variables](managing-variables-ca93653.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Manage Locks

</td>
<td valign="top">

Message Locks

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

The Message Lock tile provides an overview of the lock entries that are created \(in the in-progress repository\) to avoid the same message being processed several times in parallel, and allows you to manage them. See, [Message Locks](message-locks-bce9ae0.md).

</td>
</tr>
<tr>
<td valign="top">

Design time Artifact Locks

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

The Design time Artifact Locks tile provides an overview of the locked design time artifacts and allows you to manage them. See, [Designtime Artifact Locks](designtime-artifact-locks-5b3ecb8.md).

</td>
</tr>
<tr>
<td valign="top">

Manage Access Logs

</td>
<td valign="top">

 

</td>
<td valign="top">

-   Integration Cell



</td>
<td valign="top">

The Access Logs section allows you to monitor and to analyze errors that occurred during inbound HTTP processing \(and documented in system log files\). See, [Access Logs](access-logs-c1649cd.md).

</td>
</tr>
<tr>
<td valign="top">

Manage Virtual Host

</td>
<td valign="top">

 

</td>
<td valign="top">

-   Integration Cell



</td>
<td valign="top">

Defines the public-facing host name and base path through which your API and MCP server artifacts are exposed. See, [Virtual Hosts in Integration Cell](virtual-hosts-in-integration-cell-dd401ec.md).

</td>
</tr>
</table>

In the *Manage Integration Content* area, a set of tiles is displayed that show the number of deployed APIs.

When you click on a tile, a list of deployed artifacts is displayed, filtered according to the settings defined for the tile. On the left side of the screen, the list of artifacts is shown in a table with the following attributes for each artifact:

-   *Name*: Below the name, the artifact type \(for example, API\) is shown.

-   *Status*: Indicates the status of the deployed API. For more information on the available statuses, see [Runtime Status](runtime-status-c14a7b1.md).


To customize the list of displayed API artifacts, you can either search for specific API name or ID **or** you can filter the content of the table by attributes such as Status or Type.

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.

On the right side of the screen, more details about the artifact selected on the left side are shown. Depending on the artifact type, other functions can be accessed as well.



<a name="loio399b6c6d98e24cbd8087a9e36248401d__section_ojg_nlz_szb"/>

## Integration Content Details

The header area provides the following information about the selected artifact:

**Integration Content Details**


<table>
<tr>
<th valign="top">

Information

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Deployed on*

</td>
<td valign="top">

Time when the API was deployed

</td>
</tr>
<tr>
<td valign="top">

*Deployed by*

</td>
<td valign="top">

User who deployed the API

</td>
</tr>
<tr>
<td valign="top">

*Version*

</td>
<td valign="top">

Version of the API

</td>
</tr>
<tr>
<td valign="top">

*ID*

</td>
<td valign="top">

API artifact ID

</td>
</tr>
<tr>
<td valign="top">

*Package*

</td>
<td valign="top">

Name of the package the artifact was deployed from

</td>
</tr>
</table>

The header area also provides certain functions:

-   *Restart*

    Allows you to restart an artifact \(for example, an integration flow that has been stopped on the node\).

-   *Undeploy*

    Allows you to undeploy an API.

-   *Download*

    Allows you to download the API to your computer.

    > ### Note:  
    > Importing an API using the ZIP file downloaded from *Monitor* \> *Integrations and APIs* \> *Integration Content Details* is not supported. These ZIP files may contain runtime-specific or system-generated artifacts that are not intended for design-time import.
    > 
    > Always export APIs directly from *Design* by opening the content package, selecting the API artifact, and choosing *Export*. Avoid using the *Download* option under *Integration Content Details* for this purpose.


Below the header, the following sections contain detailed information about the selected artifact:

-   *Endpoints*: Shows the URLs of the services exposed by the API for a sending application. You can copy the URL by choosing the Copy button ![](images/CI_Copy_Icon_93e3262.png).

-   *Status Details*: Indicates whether the API is currently deployed or undeployed.

-   *Artifact Details*: The type of the selected artifact determines which kind of information is displayed.

    **Artifact Details**


    <table>
    <tr>
    <th valign="top">

    Artifact Type
    
    </th>
    <th valign="top">

    You can:
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    API
    
    </td>
    <td valign="top">
    
    Access the *Monitor Message Processing*

    For more information, see [Monitor Message Processing](monitor-message-processing-314df3f.md).

    *View deployed artifact*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    </table>
    
-   *Log Configuration*: In the Log Configuration section of the selected API, specify the desired log level to determine the level of detail in the message processing log.

    **Log Configuration**


    <table>
    <tr>
    <th valign="top">

    Log Level
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    None
    
    </td>
    <td valign="top">
    
    No data is recorded during message processing and no data is shown in data monitoring.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Info
    
    </td>
    <td valign="top">
    
    During message processing, the system records basic information, and the header is always displayed. If there are failed messages, the message processing log retains detailed information about the last 50 message steps. This information is then displayed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    The message processing log records basic information for failed message executions only. It retains and displays detailed information about the last 50 message steps. This log level is suitable if you do not need to record completed messages.

    No attachments are recorded in the message processing log.

    > ### Note:  
    > Please note that if data archiving is available and configured for your API, no data will be archived for this specific API.
    > 
    > If you have defined a retry scenario in your API and set the log level to "Error", a final successful retry will not be recorded. Consequently, the overall Message Processing Log Status will remain as "Retry" or "Failed" even though the message is successfully delivered in the end.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Debug
    
    </td>
    <td valign="top">
    
    As the Debug log level is a resource-intensive feature, we recommend setting it only in a development or test environment

    The message processing log records detailed information for each step of the message processing. Although all steps, including headers and additional information, are accessible in the graphical UI, only the last 100 steps are shown in the text view of the message processing log. The Debug log level has a time limit and expires after a certain period. Once expired, the log level reverts back to the previously set level.

    The expiry time is fixed and set to 24 hours.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Trace
    
    </td>
    <td valign="top">
    
    The log level trace is currently not supported for API artifact on Edge Integration Cell.
    
    </td>
    </tr>
    </table>
    

