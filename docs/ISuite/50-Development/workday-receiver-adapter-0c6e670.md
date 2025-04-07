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
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

The Workday adapter supports the Workday SOAP API with basic authentication. Once you've created a receiver channel and selected the Workday adapter, you can configure its attributes.

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

Specify the recipient's endpoint URL, the Workday login base URL, for user authentication. This value can also be specified dynamically. Example: https://wd2-impl-services1.workday.com

</td>
</tr>
<tr>
<td valign="top">

*Tenant*

</td>
<td valign="top">

Specify the ID of your Workday Tenant. For example: myTenant1.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the name of the **User Credentials** artifact that contains the credentials for basic authentication. This refers to the username-password pair used in authentication to Workday. This property enables the system to fetch the User Credential security material deployed in your SAP Cloud Integration tenant.

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

Specify the version of the Workday SOAP API to be used for calling Workday. Select one of the following versions:

-   v32.0
-   v34.1
-   v34.2



</td>
</tr>
<tr>
<td valign="top">

*Service*

</td>
<td valign="top">

To access and exchange data with Workday, you can choose among the following service options:

-   Absence Management

-   Academic Advising

-   Academic Foundation

-   Admissions

-   Adoption

-   Benefit Administration

-   Cash Management

-   Campus Engagement

-   Compensation

-   Compensation Review

-   Dynamic Document Generation

-   External Integrations

-   Financial Management

-   Financial Aid

-   Human Resources

-   Identity Management

-   Integrations

-   Inventory

-   Learning

-   Moments

-   Notification

-   Payroll

-   Payroll CAN

-   Payroll FRA

-   Payroll GBR

-   Payroll Interface

-   Performance Management

-   Professional Services Automation

-   Recruiting

-   Resource Management

-   Revenue Management

-   Settlement Services

-   Staffing

-   Student Core

-   Student Finance

-   Student Records

-   Student Recruiting

-   Talent

-   Tenant Data Translation

-   Time Tracking

-   Workday Connect

-   Workday Extensibility

-   Workforce Planning




</td>
</tr>
<tr>
<td valign="top">

*Request Operation Tag*

</td>
<td valign="top">

Specify the operation tag of your payload. Example: Put\_Cost\_Center\_Request.

</td>
</tr>
</table>

