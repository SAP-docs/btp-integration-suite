<!-- loio3cdbc29ca2b641738513ab8665bab9fd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# ODC Receiver Adapter

The ODC adapter enables you to communicate with systems that expose data through the OData Channel for SAP Gateway.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the ODC Receiver Adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the Connection tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Enter the URL of the SAP NetWeaver Gateway OData Channel that you are accessing.

</td>
</tr>
<tr>
<td valign="top">

*Client*

</td>
<td valign="top">

Enter the backend system client you want to connect to.

</td>
</tr>
<tr>
<td valign="top">

*Namespace*

</td>
<td valign="top">

Enter the namespace of the service.

</td>
</tr>
<tr>
<td valign="top">

*Service Name*

</td>
<td valign="top">

Enter the name of the service.

</td>
</tr>
<tr>
<td valign="top">

*Version*

</td>
<td valign="top">

enter the version of the service.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the authentication method you want to use for connecting to the system.

-   `Basic Authentication`

-   `Deployed Credentials`




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Enter the alias you used while deploying basic authentication credentials.

</td>
</tr>
<tr>
<td valign="top">

*Location ID*

</td>
<td valign="top">

Enter the location ID.

</td>
</tr>
</table>

Select the Processing tab and provide values in the fields as follows.

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation that you want to perform from the dropdown list.

</td>
</tr>
<tr>
<td valign="top">

*Resource Path*

</td>
<td valign="top">

Enter the path to the resource that you want to perform the operation on.

</td>
</tr>
<tr>
<td valign="top">

*EDMX*

</td>
<td valign="top">

In the *<EDMX\>* field, choose *Select*.

If you have already added a system, perform the following substeps:

1.  In the *<System\>* field, select the system from dropdown list.

2.  If you want to use basic authentication, in *<Authenticate Using\>* field, choose `Basic Authentication` from dropdown list. Provide username and password in the relevant fields and choose *Connect*.

3.  If you want to use the deployed credentials, in *<Authenticate Using\>* field, choose `Deployed Credentials` from dropdown list. In *<Credential Name\>* field, enter the alias you used while deploying basic authentication credentials and choose *Connect*.


If you want to connect to a new system, perform the following substeps:

1.  Choose :heavy_plus_sign:.

2.  Provide values in fields based on description in table and choose *Connect*.


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
    
    System
    
    </td>
    <td valign="top">
    
    Enter the system name that you want to specify. You can use this name as reference for selecting the same system for future use.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address
    
    </td>
    <td valign="top">
    
    Enter the URL of the system that you are connecting to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client
    
    </td>
    <td valign="top">
    
    Enter the backend system client that you are connecting to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Namespace
    
    </td>
    <td valign="top">
    
    Enter the namespace of the service.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Service Name
    
    </td>
    <td valign="top">
    
    Enter the name of the service.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Version
    
    </td>
    <td valign="top">
    
    Enter the version of the service.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Location ID
    
    </td>
    <td valign="top">
    
    Enter the location ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authenticate Using
    
    </td>
    <td valign="top">
    
    Select the authentication method you want to use for connecting to the system. You can choose `Basic Authentication` or `Deployed Credentials`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name
    
    </td>
    <td valign="top">
    
    Enter the credential name.
    
    </td>
    </tr>
    </table>
    



</td>
</tr>
</table>

