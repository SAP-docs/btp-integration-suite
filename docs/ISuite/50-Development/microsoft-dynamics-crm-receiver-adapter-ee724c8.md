<!-- loioee724c8672834041a26413d94dfdb042 -->

# Microsoft Dynamics CRM Receiver Adapter

The Microsoft Dynamics CRM receiver adapter enables SAP Integration Suite to accelerate the implementation time and reduce the complexity of connecting to Microsoft Dynamics CRM.

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

Dynamics 365 Sales is an adaptive selling solution that helps your sales team navigate the realities of modern selling. Its CRM system provides capacities that include:

-   Sales Force Automation

-   Contact & Account Management

-   Opportunity & Pipeline Management.

-   Task / Activity Management

-   Territory & Quota Management

-   Desktop Integration

-   Product & Price List Management

-   Quote & Order Management

-   Customer Contract Management

-   Case Management and so on.


> ### Note:  
> You need to download the adapter from SAP Software Download Center. You can find more information on the download navigation path [here](https://api.sap.com/package/MicrosoftDynamicsCRMAdapter?section=Overview).
> 
> After you complete the download, uncompress and extract the files to your local system. Then deploy the adapter on your tenant.
> 
> -   For more information on deploying the adapter in multicloud environment, see [Importing Custom Integration Adapter](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/482286e544014098874fde0da4bcca2c.html).

Once you’ve created a receiver channel and selected the Microsoft Dynamics CRM adapter, you can configure its parameters by referring the following description:

The General tab shows general information such as the adapter type, its direction \(receiver\), the transport protocol, and the message protocol.

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

Specifies the recipient's endpoint URL. This URL connects to the Microsoft Dynamics CRM tenant. This value can also be specified dynamically. ​

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the Authentication type to be used. Possible options include:

-   *OAuth - Password Credentials:* This approach requires a username/password pair \(Credential Name\), a Login URL, a Client ID, and an optional Client Secret.
-   *OAuth – Client Credentials Secret:*This approach does not require a username/password pair \(Credential Name\). It only needs a Login URL Directory \(tenant\) ID, Client ID, and an optional Client Secret. This Authentication type can also be used in case the account used in the Connection Tab requires Federated authentication.



</td>
</tr>
<tr>
<td valign="top">

*Login URL*

</td>
<td valign="top">

Specify the login URL.

Example: `https://login.windows.net`

</td>
</tr>
<tr>
<td valign="top">

*Directory \(tenant\) ID*

</td>
<td valign="top">

Specify the ID of the Directory or Tenant.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the credential name used to authenticate against the server. This represents the Microsoft Dynamics CRM credential name \(username-password pair stored as Security Material\).

</td>
</tr>
<tr>
<td valign="top">

*Client ID Alias*

</td>
<td valign="top">

Specifies the client ID for the endpoint. This value can be retrieved from Azure AD.

</td>
</tr>
<tr>
<td valign="top">

*Client Secret Alias*

</td>
<td valign="top">

Specifies the alias for Client Secret stored in Security Material.

</td>
</tr>
</table>

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

*API Version*

</td>
<td valign="top">

The version of the API used for calling the Microsoft Dynamics CRM application. Select one of the following versions:

-   V9.1

-   V9.2




</td>
</tr>
<tr>
<td valign="top">

*Processing Mode*

</td>
<td valign="top">

Specifies the processing mode. Select one of the following processing modes:

-   Single

-   Batch




</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

To access and exchange data with Microsoft Dynamics CRM, you can select among the following operation:

-   Create Object

-   Delete Object

-   Get Object by ID

-   Query Objects

-   Update Object

-   Disassociate Object

-   Associate Object

-   Function




</td>
</tr>
<tr>
<td valign="top">

*Business Object*

</td>
<td valign="top">

Specifies the name of the entity to perform the operation on. For Example: accounts, invoices, opportunities, and so on.

</td>
</tr>
<tr>
<td valign="top">

*Business Object ID*

\(only if you select Update, Delete, Associate, Disassociate, Function \(Bound\), and Get by ID operations\)

</td>
<td valign="top">

Specifies the unique ID. The ID represents the instance of the entity that you’ve specified in the Business Object field.

</td>
</tr>
<tr>
<td valign="top">

*Affected Property*

\(only if Delete operation is used\)

</td>
<td valign="top">

Specifies the property of the entity affected by the deletion. In case you specify this property, only the specified property is deleted and the rest of the properties of the entity is left as it is. In case this field is left empty, the complete record of the entity or the business object is deleted.

</td>
</tr>
<tr>
<td valign="top">

*Suppress Duplicates*

\(only if Create or Update operation is used\)

</td>
<td valign="top">

As a default behavior, the update object doesn’t check for duplicates. This means that in case you attempt to update already existing records in the Microsoft Dynamics CRM, the feature still updates. To prevent such updates, select this checkbox.

</td>
</tr>
<tr>
<td valign="top">

*Type*

\(only if Function operation is used\)

</td>
<td valign="top">

Select the type of function from one of the following:

-   Bound

-   Unbound




</td>
</tr>
<tr>
<td valign="top">

*Function*

\(only if Function operation is used\)

</td>
<td valign="top">

The adapter supports calling Microsoft Dynamics CRM functions. You can add the function name and parameters in this field.

</td>
</tr>
<tr>
<td valign="top">

*Use Pagination*

\(only if Query or Function operation is used\)

</td>
<td valign="top">

This field specifies how to control the number of returned records. It’s useful, especially when dealing with many records. Once checked, you can specify the Page Size and the Next Page Link.

</td>
</tr>
<tr>
<td valign="top">

*Page Size*

\(only if you enable Use Pagination option\)

</td>
<td valign="top">

Specifies the maximum number of records that is returned in the response. This field is set to 500 by default.

</td>
</tr>
<tr>
<td valign="top">

*Next Page Link*

\(only if you enable Use Pagination option\)

</td>
<td valign="top">

In case, more records are returned in the response than the number specified in the Page Size, then a @odata.nextLink property is returned with the results. The value @odata.nextLink property can be used to retrieve the next result page. The Next Page Link is meant to be filled with this value. In most cases, this field needs to be made dynamic by using a property.

</td>
</tr>
<tr>
<td valign="top">

*Request*

\(only for create, update, associate, disassociate operation\)

</td>
<td valign="top">

This field specifies the format of the request message to be sent to Microsoft Dynamics CRM. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top">

*Response*

</td>
<td valign="top">

This field specifies the format of the response message to be returned by Microsoft Dynamics CRM. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top">

*Query Type*

\(only for Query Objects, Get Object by ID operation\)

</td>
<td valign="top">

Possible values include the following values:

-   Basic

-   Advanced

-   FetchXML




</td>
</tr>
<tr>
<td valign="top">

*OData Query*

\(only for Query Objects are set to Advanced\)

</td>
<td valign="top">

Specifies complex queries according to OData query options.

</td>
</tr>
<tr>
<td valign="top">

*FetchXML Query*

\(only for Query Objects are set to FetchXML\)

</td>
<td valign="top">

Specifies FetchXML queries to query data from Dynamics CRM.

</td>
</tr>
<tr>
<td valign="top">

*Limit*

\(only for the Query Objects operation\)

</td>
<td valign="top">

Specifies the maximum number of records to be returned as a response.

</td>
</tr>
<tr>
<td valign="top">

*Count*

\(only for the Query Objects operation\)

</td>
<td valign="top">

Select to include the total number of records that meet the query or filtering criteria in the response. The response includes a property called OData.count.

</td>
</tr>
<tr>
<td valign="top">

*Filters*

</td>
<td valign="top">

Specifies filter conditions to determine which type of records should be returned by the server.

</td>
</tr>
<tr>
<td valign="top">

*Response Properties*

</td>
<td valign="top">

Specifies the fields that are returned in the response. This is a way to limit, which properties of the response is returned. Each property is added in a separate row of the table. In case no properties are added to this property, all fields of the concerned entity is returned.

</td>
</tr>
<tr>
<td valign="top">

*Order Response by*

</td>
<td valign="top">

Specifies in which order the records in the response is returned. You can’t always use this feature together with the aggregate property.

</td>
</tr>
<tr>
<td valign="top">

*Expand Navigation Properties*

</td>
<td valign="top">

Specifies the properties to be included and expanded in the response. The aggregation isn’t supported while expanding.

</td>
</tr>
<tr>
<td valign="top">

*Aggregate Properties*

</td>
<td valign="top">

Specifies how to aggregate and group your response data. The aggregation isn’t supported while doing any other query options.

</td>
</tr>
<tr>
<td valign="top">

*Outbound Headers*

</td>
<td valign="top">

Specifies any additional headers that you need to send to the Microsoft Dynamics CRM.

</td>
</tr>
</table>

