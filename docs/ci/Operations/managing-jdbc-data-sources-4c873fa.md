<!-- loio4c873fac537248e58767f74e4a74d867 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing JDBC Data Sources

The *JDBC Data Sources* allows you to create and manage a cluster of artifact connections to interact with a database \(DB\). Each data source contains information on database type, and database-specific configuration parameters.

Create a data source to handle a connection setup to a cloud database. For the list of supported databases for Cloud Foundry tenants, see [JDBC Receiver Adapter](../Development/jdbc-receiver-adapter-88be644.md).

When you select a *JDBC Data Source*, the details are displayed to the right of the pane. The header area provides the following information on:

-   **Configuration Parameters**

    Displays information corresponding to a specific database such as *Database Type*, *User*, *Database ID* and so on.

-   **Logs**

    Displays information recorded during deployment of the data source. If the deployment fails, it displays the error details along with other technical information.






### Adding or Editing a JDBC Data Source

1.  Go to the *Monitor* view and choose the tile *JDBC Material*.
2.  Choose *JDBC Data Sources* tab and perform one of the following steps:

    -   Choose *Add* for creating a new data source.
    -   Choose *Edit* to modify an existing data source.

    > ### Note:  
    > You need not redeploy an integration flow after editing the data source.

3.  Specify the following attributes:

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

    For more information, see [JDBC Receiver Adapter](../Development/jdbc-receiver-adapter-88be644.md).

    > ### Note:  
    > JDBC drivers that are uploaded to provide connectivity to databases managed by third party are shown in the dropdown.


    
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

    \(only available for SAP ASE Service \(Neo\), SAP HANA Service \(Neo\) databases that are managed by SAP Managed\)


    
    </td>
    <td valign="top">
    
    Specify the ID of the target database.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Access Token*

    \(only available for SAP ASE Service \(Neo\), SAP HANA Service \(Neo\) databases that are managed by SAP Managed\)


    
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

    For more information, see [JDBC Receiver Adapter](../Development/jdbc-receiver-adapter-88be644.md).


    
    </td>
    </tr>
    </table>
    
4.  Deploy the data source.


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

<span class="SAP-icons"></span> \(Reload\)



</td>
<td valign="top">

Reloads the table content.



</td>
</tr>
</table>

**Related Information**  


[Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md "Learn how to upload and deploy JDBC type-4 compliant third-party drivers on Cloud Integration service.")

