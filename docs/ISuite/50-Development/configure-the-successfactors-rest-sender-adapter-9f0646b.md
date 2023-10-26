<!-- loio9f0646b481764b4b890a342c3e14a002 -->

# Configure the SuccessFactors REST Sender Adapter

The SuccessFactors \(REST\) sender adapter connects an SAP Cloud Integration tenant to a SuccessFactors sender system using the REST message protocol.

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

Once you have created a sender channel and selected the SuccessFactors \(REST\) sender adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

> ### Note:  
> The adapter only supports SuccessFactors Learning Management System \(LMS\) OData V4 entities.

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

URL of the SuccessFactors LMS service.

</td>
</tr>
<tr>
<td valign="top">

*Address Suffix* 

</td>
<td valign="top">

URL suffix for the SuccessFactors LMS service.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Name of the credentials deployed on the SuccessFactors LMS service for authentication.

> ### Note:  
> Permits use of OAuth2 client credentials only.



</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

Type of proxy you want to use to connect to the SuccessFactors system.

If you choose *Manual*, you need to enter values for the fields *Proxy Host* and *Proxy Port*.

*Proxy Host* is the name of the proxy host you are using.

*Proxy Port* is the port number that you are using.

</td>
</tr>
<tr>
<td valign="top">

*Operation* 

</td>
<td valign="top">

Operation that you want to perform.

> ### Note:  
> You can only perform GET operations on the sender channel.



</td>
</tr>
<tr>
<td valign="top">

*Entity* 

</td>
<td valign="top">

LMS entity that you are accessing.

> ### Note:  
> See the relevant LMS API documentation for more details.



</td>
</tr>
<tr>
<td valign="top">

*Parameters* 

</td>
<td valign="top">

Operation parameters that you want to send.

</td>
</tr>
<tr>
<td valign="top">

*Page Size* 

</td>
<td valign="top">

Maximum number of records on each page of response.

</td>
</tr>
</table>

Select the *Scheduler* tab and provide values in the fields as follows.

**Scheduler**


<table>
<tr>
<th valign="top">

Parameter

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

*On Time* 

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

