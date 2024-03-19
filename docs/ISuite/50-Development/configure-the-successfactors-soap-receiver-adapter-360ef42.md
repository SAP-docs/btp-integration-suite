<!-- loio360ef42b1d4e4b86a6867b6f0adce4ce -->

# Configure the SuccessFactors SOAP Receiver Adapter

The SuccessFactors SOAP receiver adapter connects a tenantSAP Cloud Integration to SOAP-based Web services of a SuccessFactors receiver system \(synchronous or asynchronous communication\).

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

Once you've created a receiver channel and selected the SuccessFactors \(SOAP\) receiver adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

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

Select the *Connection* tab and provide values in the fields as follows.

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

URL of the SuccessFactors data center that you want to connect to. You can browse to and select the SuccessFactors data center URL by using the *Select* option.

You can also dynamically define the address using a header or property in the message exchange.

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

    > ### Note:  
    > Support for *OAuth2 SAML Bearer Assertion* was released in June 2021. If you're using an older version of the adapter \(where you don't see the dropdown *Authentication*\) and yet want to use this authentication type without editing the adapter, do the following:
    > 
    > In a content modifier step, define the following in the *Exchange Property*:
    > 
    > 
    > <table>
    > <tr>
    > <th valign="top">
    > 
    > Parameter
    > 
    > </th>
    > <th valign="top">
    > 
    > Value
    > 
    > </th>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Action
    > 
    > </td>
    > <td valign="top">
    > 
    > Create
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Name
    > 
    > </td>
    > <td valign="top">
    > 
    > SAP\_SF\_OAuth2SAML\_Auth
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Type
    > 
    > </td>
    > <td valign="top">
    > 
    > Constant
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Value
    > 
    > </td>
    > <td valign="top">
    > 
    > true
    > 
    > </td>
    > </tr>
    > </table>




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Enter the credential name for the security artifact that has been deployed on the tenant.

You can also dynamically define the credential using a header or property in the message exchange.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

Type of proxy you want to use to connect to the SuccessFactors system – *Internet* or *Manual*.

If you choose *Manual*, you need to enter values for the fields *Proxy Host* and *Proxy Port*.

*Proxy Host* is the name of the proxy host you’re using.

*Proxy Port* is the port number that you're using.

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

Operation that you want to perform on the entity that you're accessing on the SuccessFactors system. Supported operations are:

-   Query

-   Delete

-   Insert

-   Update

-   Upsert




</td>
</tr>
<tr>
<td valign="top">

*Entity* 

</td>
<td valign="top">

Entity that you want to access in the SuccessFactors system. For example, `CompoundEmployee`, `JobPosting`, or `PerEmergencyContacts`.

If you want to select or change the entity, and modify the query, choose *Select* and follow the steps in [Modifying SuccessFactors SOAP Entity and Operation](modifying-successfactors-soap-entity-and-operation-a6ee603.md).

</td>
</tr>
<tr>
<td valign="top">

*Query* 

</td>
<td valign="top">

Query that you want to construct. For example, from the entity `JobPosting`, you only want to fetch a list of job postings that are open using the property `postingStatus`.

> ### Note:  
> The parameter `${deltasync.maxDateFromLastRun}` supports a timestamp of 3 months.



</td>
</tr>
<tr>
<td valign="top">

*Parameters* 

</td>
<td valign="top">

Enter the parameters.

</td>
</tr>
<tr>
<td valign="top">

*Page Size* 

</td>
<td valign="top">

Maximum number of records to be fetched in one page of response.

</td>
</tr>
<tr>
<td valign="top">

*Timeout* 

</td>
<td valign="top">

Maximum time the system waits for a response.

</td>
</tr>
<tr>
<td valign="top">

*Retry on Connection Failure* 

</td>
<td valign="top">

Select of you want to retry on connection failure.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages* 

</td>
<td valign="top">

By selecting *Process in Pages*, you enable the adapter to process messages in batches. The size of a message is defined by the value that you specify for the *Page Size*.

> ### Note:  
> After fetching the first page in the local integration process, if the processing of this page by subsequent flow steps results in SuccessFactors idle session timeout, then the SuccessFactors connector internally uses the `startRow` API to fetch the next page.

You can't use the *Process in Pages* option with the *Query* operation if the *Process Call* step is used in a *Multicast* branch.

To use *Process in Pages*, you must use the adapter in a *Local Integration Process* that is invoked by a *Looping Process Call* step. In the *Looping Process Call*, provide the loop condition details that follow:

-   Select *Expression Type* as *Non-XML*.

-   For *Condition Expression*, provide `${property.SAP_SuccessFactorsHasMoreRecords.<receiver.name>} contains 'true'`.

    In case you've also set a channel name, set the *Condition Expression* as `${property.SAP_SuccessFactorsHasMoreRecords.<receiver.name>.<channel.name>} contains 'true'`.

-   For *Maximum Number of Iterations*, provide `999`.




</td>
</tr>
</table>

> ### Note:  
> Whenever the SuccessFactors SOAP adapter is used, the following headers with the specified values are sent to the SuccessFactors back end as HTTP request headers:
> 
> 1.  X-SF-Correlation-Id: MPL ID
> 
> 2.  X-SF-Client-Tenant-Id: Client/Tenant ID
> 
> 3.  X-SF-Process-Name: iFlow Name
> 
> 4.  X-Agent-Name: SAP Cloud Integration

