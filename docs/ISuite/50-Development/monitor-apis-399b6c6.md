<!-- loio399b6c6d98e24cbd8087a9e36248401d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitor APIs

Check the runtime logs and the status of an API artifact.

To monitor an API artifact, log on to SAP Integration Suite, go to *Monitor* \> *Integrations and APIs*, and select the runtime from the *Runtime* drop-down menu under *Overview*.

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

    For more information, see [Monitor Message Processing](https://help.sap.com/docs/integration-suite/sap-integration-suite/monitor-message-processing?version=CLOUD&q=Log%20Configuration).

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
    

