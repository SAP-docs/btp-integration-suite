<!-- loio0c6e67020af9433cb09a56736d73ca76 -->

# Workday Receiver Adapter

Workday receiver adapter enables SAP Cloud Integration and SAP Integration Suite to accelerate the implementation time and reduce the complexity of connecting to Workday.

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
>     To use the latest version of a flow step or adapter – select the adapter and choose *Update Version* from the property sheet. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

The Workday adapter supports the Workday SOAP API with basic authentication. Once you've created a receiver channel and selected the Workday adapter, you can configure its attributes.

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

Specify the recipient's endpoint URL or Workday login base URL for user authentication. This value can also be specified dynamically.

Example:`https://wd2-impl-services1.workday.com`

</td>
</tr>
<tr>
<td valign="top">

*Tenant*

</td>
<td valign="top">

Specify the ID of your Workday Tenant.

Example:`myTenant` 

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the required authentication type to connect to Workday:

-   *Basic*
-   *Certificate Based Authentication*



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the name of the *User Credentials* artifact that contains the credentials for basic authentication. This refers to the username-password pair used in authentication to Workday. This property enables the system to fetch the User Credential security material deployed in your SAP Cloud Integration tenant.

</td>
</tr>
<tr>
<td valign="top">

*Username*

</td>
<td valign="top">

Specify the Workday username specific to your tenant.

Example: `workday_user@workdaytenant`

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

</td>
<td valign="top">

Specify the alias to identify the private key used for authentication using a certificate based authentication.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message.

Example: `60000`

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

*Configuration Type*

</td>
<td valign="top">

Select the configuration type:

-   *Basic* to use the dropdowns and parameter text fields.
-   *Advanced* to specify the relative URL.



</td>
</tr>
<tr>
<td valign="top">

*API Version*

</td>
<td valign="top">

Specify the version of the Workday API.

> ### Note:  
> Currently, API versions up to v45.0 are supported by the adapter.



</td>
</tr>
<tr>
<td valign="top">

*Service*

</td>
<td valign="top">

To access and exchange data with Workday, you can choose from the following service options:

-   *Absence\_Management* 
-   *ACA\_Partner\_Integrations* 
-   *Academic\_Advising* 
-   *Academic\_Foundation* 
-   *Admissions* 
-   *Adoption* 
-   *Benefit\_Administration* 
-   *Benefits\_Partner\_Program\_Integrations* 
-   *Cash\_Management* 
-   *Campus\_Engagement* 
-   *Compensation* 
-   *Compensation\_Review* 
-   *Dynamic\_Document\_Generation* 
-   *External\_Integrations* 
-   *Financial\_Management* 
-   *Flex\_Team* 
-   *Financial\_Aid* 
-   *Human\_Resources* 
-   *Identity\_Management* 
-   *Integrations* 
-   *Inventory* 
-   *Learning* 
-   *Moments* 
-   *Notification* 
-   *Payroll* 
-   *Payroll\_CAN* 
-   *Payroll\_FRA* 
-   *Payroll\_GBR* 
-   *Payroll\_Interface* 
-   *Payroll\_AUS* 
-   *Performance\_Management* 
-   *Prism\_Analytics* 
-   *Professional\_Services\_Automation* 
-   *Recruiting* 
-   *Requests* 
-   *Resource\_Management* 
-   *Revenue\_Management* 
-   *Scheduling* 
-   *Settlement\_Services* 
-   *Staffing* 
-   *Student\_Core* 
-   *Student\_Finance* 
-   *Student\_Records* 
-   *Student\_Recruiting* 
-   *Talent* 
-   *Tenant\_Data\_Translation* 
-   *Time\_Tracking* 
-   *Workday\_Connect* 
-   *Workday\_Extensibility* 
-   *Workforce\_Planning* 



</td>
</tr>
<tr>
<td valign="top">

*Request Operation Tag*

</td>
<td valign="top">

Specify the operation tag of your payload.

Example: `Put_Cost_Center_Request`

</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

</td>
<td valign="top">

Specify the endpoint path, excluding the Host.

Example: `/ccx/service/{tenant}/v32.0/Staffing`

</td>
</tr>
<tr>
<td valign="top">

*Throw Exception on Failure*

</td>
<td valign="top">

Enable to throw an exception in case of a failed response from the remote server.

> ### Note:  
> Throw Exception on Failure checkbox is enabled by default.



</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

You can use this field to propagate a header in a request.

</td>
</tr>
</table>

