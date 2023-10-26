<!-- loio09a7223883a74dcb9f4b1b96a7c7f011 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage Integration Content

The Manage Integration Content section provides an overview of integration content artifacts, such as integration flows, that have been deployed on the tenant.

In the *Manage Integration Content* area, a set of tiles is displayed that show the number of deployed integration content artifacts for a particular type \(for example, Integration Flow\) and with a particular status \(for example, Started\). You can configure each tile to filter by a different artifact type or status, or both. To do this, position the cursor on a tile and choose *Edit* from the context menu.

To open the integration content monitor for a particular set of artifacts \(as defined by the tile filter\), click a tile.

When you click a tile, a list of integration artifacts is displayed \(for the filter settings as defined for the tile\). On the left side of the screen, the list of artifacts is shown in a table with the following attributes for each artifact:

-   *Name*

    Below the name, the artifact type \(for example, Value Mapping\) is shown.

-   *Status*

    For more information on the available statuses, see [Runtime Status](runtime-status-c14a7b1.md).


To customize the list of displayed artifacts, you can either search for specific artifacts by artifact name or ID **or** you can filter the table content by attributes such as Status or Type.

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.

On the right side of the screen, more details about the artifact selected on the left side are shown. Depending on the artifact type, other functions can be accessed as well.



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

Time when the artifact was deployed.

</td>
</tr>
<tr>
<td valign="top">

*Deployed by*

</td>
<td valign="top">

User who deployed the artifact.

</td>
</tr>
<tr>
<td valign="top">

*Version*

</td>
<td valign="top">

Version of the artifact, for example, the integration flow version.

</td>
</tr>
<tr>
<td valign="top">

*ID*

</td>
<td valign="top">

Artifact ID

</td>
</tr>
<tr>
<td valign="top">

*Package*

</td>
<td valign="top">

Name of the package the artifact was deployed from.

</td>
</tr>
<tr>
<td valign="top">

*Mode*\(if applicable\)

</td>
<td valign="top">

Indicates whether it is configure-only content.

</td>
</tr>
</table>

The header area also provides certain functions \(the available functions depend on the type of the selected artifact\):

-   *Restart*

    Allows you to restart an artifact \(for example, an integration flow that has been stopped on the node\).

-   *Undeploy*

    Allows you to undeploy an active integration flow.

    > ### Caution:  
    > If you choose to undeploy your integration flow while message processing is still in progress, the undeployment is delayed for up to 1 minute to allow time to finish the message processing. If the message can't be processed within 1 minute, an error is thrown and the message processing cannot be completed.

-   *Download*

    Allows you to download the artifact to your computer.


> ### Note:  
> The functions *Restart*, *Undeploy*, and *Download* are not available for artifacts with status *Stopping* \(see [Runtime Status](runtime-status-c14a7b1.md)\).

Below the header, the following sections contain detailed information about the selected artifact:

-   *Endpoints*

    Shows the URLs of the services exposed by the artifact for a sending application. You can copy the URL by choosing the Copy button ![](images/CI_Copy_Icon_93e3262.png).

    For example, if the artifact is an integration flow with a SOAP adapter configured as the sender channel, the endpoint URL specifies how the service exposed by the integration flow can be reached by a SOAP client.

-   *Status Details*

    Shows the status of the artifact with regard to its usage at runtime \(for example, if it is starting\).

    Also shows the *Polling Information* for all message polling adapters \(such as SFTP or mail adapter\) in use. The view provides the respective information on:

    -   the adapter information,

    -   the precise date and time when the latest poll was executed,

    -   whether further polls are scheduled or not \(No further polls scheduled/Further polls scheduled\),

    -   the status of the poll \(Successful/Failed\),

    -   \(if available\) a detailed error message.


    If an error occurs during the lifecycle of an artifact, detailed information about the error is displayed. You can copy this information to the ticket you open to get the error solved.

    > ### Note:  
    > Errors can occur in various steps during the lifecycle of an artifact. If you think of the artifact as an integration flow, steps are executed on the tenant management node \(which the user is connected to when deployment of the integration flow is triggered through the Web UI\) as well as on the runtime node where the integration flow is processed at runtime.
    > 
    > Let's look at an example of an error that is related to the runtime node: If deployment of an integration flow is triggered, which requires a runtime node with a specific node profile, but no runtime node with this profile has been started in the cluster, the artifact cannot be distributed from the tenant management node to the runtime node. In this case, an error is displayed together with the information that no suitable runtime node has been started for this use case.

-   *Artifact Details*

    The type of the selected artifact determines which kind of information is displayed.

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
    
    Integration flows
    
    </td>
    <td valign="top">
    
    access the *Monitor Message Processing*

    *View deployed artifact*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Value mapping
    
    </td>
    <td valign="top">
    
    *View deployed artifact*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SOAP API
    
    </td>
    <td valign="top">
    
    access the *Monitor Message Processing*

    *View deployed artifact*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    REST API
    
    </td>
    <td valign="top">
    
    access the *Monitor Message Processing*

    *View deployed artifact*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OData API
    
    </td>
    <td valign="top">
    
    access the *Monitor Message Processing*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Integration Adapter
    
    </td>
    <td valign="top">
    
    access the *Vendor* 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Script Collection
    
    </td>
    <td valign="top">
    
    *View deployed artifact*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message Mapping
    
    </td>
    <td valign="top">
    
    *View deployed artifact*

    *Navigate to Artifact Editor*
    
    </td>
    </tr>
    </table>
    
    > ### Caution:  
    > Availability of APIs depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see [2903776](https://me.sap.com/notes/2903776)

-   *Log Configuration*

    If you deploy an artifact for the first time, the log level is set to `info`. If you want to change the log level, see: [Setting Log Levels](setting-log-levels-4e6d3fc.md)

-   If you have set up Data Archiving, *Configure* allows you to select the data to be archived.

**Related Information**  


[Runtime Status](runtime-status-c14a7b1.md "Indicates if a deployed artifact is ready to operate.")

[Setting Log Levels](setting-log-levels-4e6d3fc.md "The log level for the message processing log specifies the granularity of information collected by the message processing log")

[Configuring Archiving Settings](configuring-archiving-settings-c38760d.md "You can configure the archiving settings via the Integration Content Monitor for each integration flow.")

[Archiving Data](archiving-data-bc71f88.md "The Archiving feature allows you to store message processing logs in an archiving system such as a Content Management System (CMS).")

