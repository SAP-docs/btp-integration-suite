<!-- loio4c873fac537248e58767f74e4a74d867 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing JDBC Data Sources

The *JDBC Data Sources* allows you to create and manage a cluster of artifact connections to interact with a database \(DB\). Each data source contains information on database type, and database-specific configuration parameters.

Create a data source to handle a connection setup to a cloud or on-premise database. For the list of supported databases, see [JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md).

When you select a *JDBC Data Source*, the details are displayed to the right of the pane. The header area provides the following information on:

-   **Configuration Parameters**

    Displays information corresponding to a specific database such as *Database Type*, *User*, *Database ID* and so on.

-   **Logs**

    Displays information recorded during deployment of the data source. If the deployment fails, it displays the error details along with other technical information.






### Prerequisites to Configure Data Source for On-Premise Database

Note the following when configuring the connection between a cloud application an an on-premise system using SAP Cloud Connector: The internal host and internal port configurations are different compared to virtual host and virtual port.

1.  Log in to your Cloud Connector subaccount, to establish link between your tenant and the on-premise database.

2.  Enable your cloud application to access a back-end system. For more information, see [Configure Access Control](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/f42fe4471d6a4a5fb09b7f3bb83c66a4.html).

3.  Connect your cloud application to an on-premise system. For more information, see [Consuming the Connectivity Service](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/313b215066a8400db461b311e01bd99b.html).


If you choose to access SAP HANA Platform database on SAP BTP, see [Configure a Service Channel for an SAP HANA Database](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/3dc28b456bb64fad89084d2d10af602c.html).

After you complete the above configuration, now create a JDBC data source for your on-premise database.



### Adding or Editing a JDBC Data Source

1.  Go to the *Monitor* view and choose the tile *JDBC Material*.
2.  If you have activated Edge Integration Cell, select the target runtime.

3.  Choose *JDBC Data Sources* tab and perform one of the following steps:

    -   Choose *Add* for creating a new data source.
    -   Choose *Edit* to modify an existing data source.

    > ### Note:  
    > You need not redeploy an integration flow after editing the data source.

4.  Specify the following attributes:

    **Database-Specific Configuration Parameters**


    <table>
    <tr>
    <th valign="top">

    Field
    
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
    
    Define a name for the data source.

    > ### Note:  
    > You allowed to enter only alphanumeric characters. Special characters and white space aren’t supported.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Provide a detailed description of the data source.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Database Type*
    
    </td>
    <td valign="top">
    
    Select one of the supported database types.

    For more information, see [JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md).

    > ### Note:  
    > JDBC drivers that are uploaded to provide connectivity to databases managed by third party are shown in the dropdown.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Runtime*
    
    </td>
    <td valign="top">
    
    Selected runtime is displayed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User*
    
    </td>
    <td valign="top">
    
    Enter the username corresponding of the target database.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Enter the password corresponding of the target database.

    > ### Note:  
    > Re-enter the same password in the *Repeat Password* field to confirm that the provided password is correct.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Database ID*
    
    </td>
    <td valign="top">
    
    Specify the ID of the target database.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Access Token*
    
    </td>
    <td valign="top">
    
    Specify the access token generated for this application and that is used to identify the user that accesses the databases. SAP BTP provides the token to access SAP database. For more information for managing access, see [Managing Access to Databases for Other Subaccounts](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/65d582dc5f0f4c5092acc2bedc9f636d.html).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *JDBC URL*
    
    </td>
    <td valign="top">
    
    Specify the database connection URL that the JDBC driver uses to connect with the cloud or on-premise database.

    For more information, see [JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location ID*

    \(for on-premise database only\)
    
    </td>
    <td valign="top">
    
    Identifies the location of this Cloud Connector for a specific subaccount. The location ID must be unique per subaccount and should be an identifier that can be used in a URI. To route requests to a Cloud Connector with a location ID, the location ID must be configured in the respective destinations.

    If you don't specify any value for Location ID, the default is used.
    
    </td>
    </tr>
    </table>
    
5.  Deploy the data source.


> ### Recommendation:  
> Limit the number of deployed data sources to 49 at any point of time to avoid any business process disruption.

> ### Note:  
> To undeploy a data source, select it from the list and choose *Undeploy*. The system displays a warning and requires you to confirm the task. After confirmation the data source is undeployed and removed from the list.



### Quick Actions


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

:gear:

</td>
<td valign="top">

Helps to sort and filter the content of the table. You can define how the table entries are to be sorted \(in ascending or descending order\). You can also filter the table entries for certain attributes.

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-V5"></span> \(Reload\)

</td>
<td valign="top">

Reloads the table content.

</td>
</tr>
</table>

**Related Information**  


[Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md "Learn how to upload and deploy JDBC type-4 compliant third-party drivers on SAP Integration Suite.")

