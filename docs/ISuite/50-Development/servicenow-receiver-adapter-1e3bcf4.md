<!-- loio1e3bcf40403441d4898e6badd53c2b79 -->

# ServiceNow Receiver Adapter

ServiceNow receiver adapter enables SAP Cloud Integration and SAP Integration Suite to accelerate the implementation time and reduce the complexity of connecting to ServiceNow.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

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

You configure the receiver channel with the ServiceNow adapter to enable your tenant to send data to ServiceNow. The ServiceNow adapter supports the Now Namespace using both Basic and OAuth authentication.

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

Specify the recipient's endpoint URL, the ServiceNow login base URL, for user authentication. This value can also be specified dynamically. Example: https://dev12345.service-now.com

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the authentication mechanism to be used while connecting to ServiceNow. It's possible to choose between the following options:

-   Basic
-   OAuth2 Client Credentials



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the name of the **User Credentials** artifact that contains the credentials for basic authentication. This refers to the username-password pair used in authentication to ServiceNow. This property enables the system to fetch the User Credential security material deployed in your Cloud Integration tenant.

</td>
</tr>
<tr>
<td valign="top">

*Client ID Alias*

\(Only if you select the Authentication OAuth2 Client Credentials\)

</td>
<td valign="top">

Specify the alias to the security material that contains the Client ID for the endpoint.

</td>
</tr>
<tr>
<td valign="top">

*Client Secret Alias*

\(Only if you select the Authentication OAuth2 Client Credentials\)

</td>
<td valign="top">

Specify the alias to the security material that contains the Client Secret for the endpoint.

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

Specify the version of the API to be used for calling the ServiceNow. Select one of the following versions:

-   Latest \(The adapter automatically picks the latest version of the API\).
-   V1
-   V2



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

To access and exchange data with ServiceNow, you can choose among the following operation options:

-   Create Object

-   Delete Object

-   Get Object by ID

-   Modify Object

-   Query Objects

-   Query Objects \(Advanced\)

-   Update Object




</td>
</tr>
<tr>
<td valign="top">

*Table Name*

</td>
<td valign="top">

Specify the technical name of the ServiceNow table. Example: incident.

</td>
</tr>
<tr>
<td valign="top">

*System ID*

\(only if update, modify, delete, or Get Object by ID operation is used\)

</td>
<td valign="top">

The unique ID of the record. Specifies the unique ID that represents the instance of the record that you specified in the Table Name field. Also known as sys\_id in ServiceNow.

</td>
</tr>
<tr>
<td valign="top">

*Display Value*

</td>
<td valign="top">

Select if the response returned by ServiceNow should be in display, actual values, or both forms.

</td>
</tr>
<tr>
<td valign="top">

*Access Data Across Domains*

</td>
<td valign="top">

Select if data should be accessed across domains or not.

</td>
</tr>
<tr>
<td valign="top">

*Response Fields*

</td>
<td valign="top">

Specify the fields or properties to be returned in the ServiceNow response. Use comma to separate multiple fields.

</td>
</tr>
<tr>
<td valign="top">

*Limit*

\(only if you enable for the operation Query or Query Advanced\)

</td>
<td valign="top">

Specify the limit to be applied on pagination. The default value is 1000.

</td>
</tr>
<tr>
<td valign="top">

*Offset*

\(only if you enable for the operation Query or Query Advanced\)

</td>
<td valign="top">

Specify the offset to be applied on pagination. The default value is 0.

</td>
</tr>
<tr>
<td valign="top">

*Render Response for*

</td>
<td valign="top">

Select if the response should be rendered according to the specified UI view \(overridden by Response Fields\). Possible values include:

-   Desktop
-   Mobile
-   Both

The default value is set to Both.

</td>
</tr>
<tr>
<td valign="top">

*Suppress System Fields Auto Generation*

</td>
<td valign="top">

Select to suppress the auto-generation of system fields. The default value is false.

</td>
</tr>
<tr>
<td valign="top">

*Suppress Pagination Header*

\(only if you enable for the operation Query or Query Advanced\)

</td>
<td valign="top">

Select to remove the Link header from the response. The Link header allows you to request additional pages of data when the number of records matching your query exceeds the query limit.

</td>
</tr>
<tr>
<td valign="top">

*Display Raw Value*

</td>
<td valign="top">

Select to make ServiceNow return raw values in its response.

</td>
</tr>
<tr>
<td valign="top">

*Exclude Reference Link*

</td>
<td valign="top">

Select to suppress and remove additional information provided for reference fields. These references include URI to other resources.

</td>
</tr>
<tr>
<td valign="top">

*Count*

\(only if you enable for the operation Query or Query Advanced\)

</td>
<td valign="top">

Select to execute a select count\(\*\) on the table. Note that by default count is unchecked.

</td>
</tr>
<tr>
<td valign="top">

*Query*

\(Only if the Query Advanced operation is used\)

</td>
<td valign="top">

Specify a query to represent a complex filter on a list of records manually. Example: unit\_name=day^ORDERBYvalue.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

FORMAT

</td>
</tr>
<tr>
<td valign="top">

*Request*

\(Only if the Delete, Create, Update, or Modify operation is used\)

</td>
<td valign="top">

Select the format of the request message toward ServiceNow. Possible values include:

-   Application/XML
-   Application/JSON
-   Text/XML

The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top">

*Response*

\(Only if the Delete, Create, Update, or Modify operation is used\)

</td>
<td valign="top">

Select the format of the response message to be returned by ServiceNow. Possible values include:

-   Application/XML
-   Application/JSON
-   Text/XML

The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

HEADER PARAMETERS

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Specify the name of the header Parameter.

</td>
</tr>
<tr>
<td valign="top">

*Value*

</td>
<td valign="top">

Specify the value of the header Parameter.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

FILTERS

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Specify the name of the Query Strings to be used for filtering the data to be returned by the ServiceNow Service.

</td>
</tr>
<tr>
<td valign="top">

*Function*

</td>
<td valign="top">

Specify the function to be used for your filter. Several functions are provided:

-   Equal
-   Not Equal
-   Starts with
-   Ends with
-   Contains
-   Does not contain
-   Is empty
-   Is not empty
-   Less than
-   Greater than
-   Less than or is
-   Greater than or is
-   Between
-   Is anything
-   Is same
-   Is different
-   Greater than field
-   less than field
-   Greater than or is field
-   Less than or is field
-   Changes
-   Changes from
-   Changes to
-   Is one of
-   Is not one of

The default value for this field is Equal.

</td>
</tr>
<tr>
<td valign="top">

*Value*

</td>
<td valign="top">

Specify the value of the Query Strings.

</td>
</tr>
<tr>
<td valign="top">

*Condition*

</td>
<td valign="top">

In case multiple filters need to be used, select the condition to be used for joining the different filters. Possible values include:

-   OR
-   AND

The default value is OR.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

QUERY PARAMETERS

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Specify the name of the Query Parameter.

</td>
</tr>
<tr>
<td valign="top">

*Value*

</td>
<td valign="top">

Specify the value of the Query Parameter.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

ORDER BY

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Specify the name of the field to be used for sorting the results.

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Specify if the result needs to be sorted using the ascending or descending order. Possible values include:

-   Ascending
-   Descending

The default value is Ascending.

</td>
</tr>
</table>

