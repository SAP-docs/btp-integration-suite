<!-- loiod96ddf70caaf488ba87233f54f79ede6 -->

# SugarCRM Receiver Adapter

The SugarCRM receiver adapter enables an SAP Cloud Integration tenant to accelerate the implementation time and reduce the complexity of connecting to SugarCRM.

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

You configure the receiver channel with the SugarCRM adapter to enable your tenant to send data to SugarCRM customer relationship management \(CRM\) platform. The following functionalities that are offered by SugarCRM:

-   Salesforce Automation

-   Marketing Campaigns

-   Customer Support

-   Collaboration

-   Mobile CRM

-   Social CRM

-   Reporting


> ### Note:  
> In the Cloud Foundry environment, you can trigger auto-import and auto-deploy of the adapter. For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).

Once you’ve created a receiver channel and selected the SugarCRM adapter, you can configure its parameters by referring the following description:

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

Specify the SugarCRM endpoint URL.

</td>
</tr>
<tr>
<td valign="top">

*Client ID Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the Client ID needed to connect to SugarCRM.

</td>
</tr>
<tr>
<td valign="top">

*Security Token Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the Client Secret needed to connect to SugarCRM.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the name of the User Credentials artifact that contains the credentials for basic authentication. This refers to the username-password pair in SugarCRM.

</td>
</tr>
<tr>
<td valign="top">

*Platform*

</td>
<td valign="top">

Specify the SugarCRM platform name for the connection. A platform provides the possibility to define custom metadata and views in SugarCRM. Hence, it helps customers to customize their experience. The default platform used for connection is “base”, some other platforms are “Mobile” and “Portal”. Register the platform using SugarCRM Platform Extensions or via the Administration Panel.

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

Select the version of the API used for fetching data from the SugarCRM.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

To access and exchange data with the SugarCRM, you can select among the following operations:

-   Bulk

-   Create Record

-   Delete Record

-   Get Record by ID

-   Global Search

-   Query Records

-   Update Record

-   Upload a file




</td>
</tr>
<tr>
<td valign="top">

*Module Name*

</td>
<td valign="top">

Specifies the name of the SugarCRM Module. For example: Accounts, Contacts, and so on.

</td>
</tr>
<tr>
<td valign="top">

*Module Record ID*

\(if the operation is Delete Record, Get Record by ID, Update Record, Create Record or Upload a file\)

</td>
<td valign="top">

Specifies the unique ID that represents an instance of a SugarCRM Module.

</td>
</tr>
<tr>
<td valign="top">

*Link*

</td>
<td valign="top">

Select to perform operation on a relationship of a specified SugarCRM Module. If checked the details need to be provided for the Relationship Name and Module Record ID.

</td>
</tr>
<tr>
<td valign="top">

*Relationship Name*

\(only when Link is selected\)

</td>
<td valign="top">

Specifies the relationship name of the specified SugarCRM Module. For example: "contacts".

</td>
</tr>
<tr>
<td valign="top">

*Relationship Record ID*

\(if the operation is Delete Record, Get Record by ID, Update Record operation and when you select the Link\)

</td>
<td valign="top">

Specifies the record ID of the specified relationship \(in Relationship Name\).

</td>
</tr>
<tr>
<td valign="top">

*Request*

\(if the operation is Bulk, Create Record, Delete Record, or Update Record\)

</td>
<td valign="top">

Specifies the format of the request message sent to SugarCRM. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top">

*Response*

\(All operations\)

</td>
<td valign="top">

Specifies the format of the response message returned by the SugarCRM adapter. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top">

*Limit*

\(only for the Global Search and Query Records operations\)

</td>
<td valign="top">

Specifies the maximum number of records to be returned in the response.

</td>
</tr>
<tr>
<td valign="top">

*Offset*

\(only for the Global Search and Query Records operations\)

</td>
<td valign="top">

Specifies the number of records to skip before returning the results. For example: "10".

</td>
</tr>
<tr>
<td valign="top">

*Response Fields*

\(only for the Global Search and Query Records operations\)

</td>
<td valign="top">

Specifies a comma-separated list of fields to be returned in response. For example: "name, id".

</td>
</tr>
<tr>
<td valign="top">

*Count*

\(only for the Query Records operation\)

</td>
<td valign="top">

Select to get the count of the records from SugarCRM.

</td>
</tr>
<tr>
<td valign="top">

*Module List*

\(only for Global Search operation\)

</td>
<td valign="top">

Comma-separated list of modules to search. If omitted, all search enabled modules are queried. For example: Accounts, Contacts.

</td>
</tr>
<tr>
<td valign="top">

*Filter Type*

</td>
<td valign="top">

Select one of the following Filter Type:

-   None

-   And

-   Or

-   Simple




</td>
</tr>
<tr>
<td valign="top">

*Filter ID*

</td>
<td valign="top">

Refers to the identifier for a pre-existing filter. You can create Custom filters in SugarCRM WebUI. If the filter is also set, the two filters are joined with an AND logic.

</td>
</tr>
<tr>
<td valign="top">

*View*

</td>
<td valign="top">

Instead of defining the field's argument, the view argument can be used. The field list is constructed at the server-side based on the view definition, which is requested. Common views are "record" and "list".

</td>
</tr>
<tr>
<td valign="top">

*Search*

</td>
<td valign="top">

Refers to the search expression. Multiple terms can be specified at once. All enabled fields are searched. The results are ordered by relevance, which is based on a multitude of settings based on token counts, hit ratio, weighted boost values, and type of field. Currently, no operators are supported in the search expression itself. By refining the search expression more relevant results are displayed at the top. If no search expression is given, then the results are returned based on the last modified date.

</td>
</tr>
<tr>
<td valign="top">

*Deleted*

</td>
<td valign="top">

Boolean to show deleted records in the result set.

</td>
</tr>
<tr>
<td valign="top">

*Nulls Last*

</td>
<td valign="top">

Boolean to return records with null values in *order\_by* fields last in the result set.

</td>
</tr>
<tr>
<td valign="top">

*Order Response by*

</td>
<td valign="top">

Specifies in which order the records in the response are returned. You can’t always use this feature together with the aggregate property.

</td>
</tr>
<tr>
<td valign="top">

*Field Name*

\(only for Upload a file operation\)

</td>
<td valign="top">

Specifies the target field name in the Record where the file is uploaded. For example: Under the module Name Contacts, a photo of the contact can be uploaded in the field picture.

</td>
</tr>
<tr>
<td valign="top">

*Attachment Name*

\(only for Upload a file operation\)

</td>
<td valign="top">

Refers to the exchange attachment name that contains the upload file.

</td>
</tr>
<tr>
<td valign="top">

*File Name*

\(only for Upload a file operation\)

</td>
<td valign="top">

Specifies the name of the file that you want to be visible in SugarCRM.

</td>
</tr>
<tr>
<td valign="top">

*Content-Type*

\(only for Upload a file operation\)

</td>
<td valign="top">

Refers to the content type of the attached file. For example: image/png, image/jpg

</td>
</tr>
</table>

