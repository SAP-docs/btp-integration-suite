<!-- loio874e4b1e7d754b08a0b9e0b606e18a7f -->

# Configure the SuccessFactors \(SOAP\) Sender Adapter

The SuccessFactors \(SOAP\) sender adapter connects an SAP Cloud Integration tenant to SOAP-based Web Services of a SuccessFactors sender system \(synchronous or asynchronous communication\).

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

> ### Remember:  
> You must enable *HTTP Session Reuse* with either the *On Exchange* or *On Integration Flow* level.
> 
> For more information, see [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md).

Once you've created a sender channel and selected the SuccessFactors \(SOAP\) sender adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows.

**General**


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

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

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

*Address*

</td>
<td valign="top">

URL of the SuccessFactors data center that you want to connect to. You can browse and select the SuccessFactors data center URL by using the *Select* option.

</td>
</tr>
<tr>
<td valign="top">

*Address Suffix*

</td>
<td valign="top">

The system automatically populates this field with */sfapi/v1/soap* as you've selected the SOAP message protocol.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select one of the following authentication methods:

-   *Basic*

-   *OAuth2 SAML Bearer Assertion* – you can choose either principal propagation or technical user propagation. For more information, see [Deploying an OAuth2 SAML Bearer Assertion](deploying-an-oauth2-saml-bearer-assertion-3ee6582.md).




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Credential name for your credentials that has been deployed on the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Type of proxy you want to use to connect to the SuccessFactors system.

If you choose *Manual*, you need to enter values for the fields *Proxy Host* and *Proxy Port*.

*Proxy Host* is the name of the proxy host you’re using.

*Proxy Port* is the port number that you're using.

</td>
</tr>
<tr>
<td valign="top">

*Call Type* 

</td>
<td valign="top">

Default value is *Synchronous Query*.

If you want to execute an ad hoc operation, select *Asynchronous/Adhoc Query* from the dropdown list.

</td>
</tr>
<tr>
<td valign="top">

*Operation* 

</td>
<td valign="top">

You can only perform a GET operation to read information from the SuccessFactors system that you're connecting to.

</td>
</tr>
<tr>
<td valign="top">

*Entity* 

</td>
<td valign="top">

Entity that you want to access in the SuccessFactors system.

To select or change the entity, see [Modifying SuccessFactors SOAP Entity and Operation](modifying-successfactors-soap-entity-and-operation-a6ee603.md).

</td>
</tr>
<tr>
<td valign="top">

*Query* 

</td>
<td valign="top">

Provide your query values to look out for the relevant table or field in the SuccessFactors system.

</td>
</tr>
<tr>
<td valign="top">

*Parameters* 

</td>
<td valign="top">

Enter the key-value pairs from the SuccessFactors system to fetch the necessary information.

</td>
</tr>
<tr>
<td valign="top">

*Page Size* 

</td>
<td valign="top">

Maximum number of records to be fetched in a page of response.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in min\)* 

</td>
<td valign="top">

Maximum time the system waits for a response.

</td>
</tr>
</table>

Select the *Scheduler* tab and provide values in the fields as follows.

**Scheduler**


<table>
<tr>
<th valign="top">

Scheduler Option

</th>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Run Once* 

</td>
<td valign="top">

NA

</td>
<td valign="top">

Select to execute the operation immediately after deploying the integration content.

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

*Schedule on Day* 

</td>
<td valign="top">

*On Date* 

</td>
<td valign="top">

Specify the date on which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

*At Time* 

</td>
<td valign="top">

Specify the time at which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

*Every* 

</td>
<td valign="top">

Specify the interval at which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

*Time Zone* 

</td>
<td valign="top">

Select the time zone that you want the scheduler to use as a reference for the date and time settings.

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

*Schedule to Recur* 

</td>
<td valign="top">

*Daily* 

</td>
<td valign="top">

Select the time or interval and time zone for the schedule to recur.

</td>
</tr>
<tr>
<td valign="top">

*Weekly* 

</td>
<td valign="top">

Select the checkboxes to indicate the days of the week on which you want the operation to be executed. Also, specify the time or interval for the schedule to recur.

</td>
</tr>
<tr>
<td valign="top">

*Monthly* 

</td>
<td valign="top">

Select the day of the month on which you want the operation to be executed. Also indicate the time or the interval for the schedule to recur.

</td>
</tr>
</table>

> ### Note:  
> Whenever the SuccessFactors SOAP adapter is used, the following headers with the specified values are sent to the SuccessFactors backend as HTTP request headers:
> 
> 1.  X-SF-Correlation-Id: MPL ID
> 
> 2.  X-SF-Client-Tenant-Id: Client/Tenant ID
> 
> 3.  X-SF-Process-Name: iFlow Name
> 
> 4.  X-Agent-Name: SAP Cloud Integration

