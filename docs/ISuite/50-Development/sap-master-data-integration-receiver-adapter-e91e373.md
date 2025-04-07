<!-- loioe91e373bbb5b49ccbc2977152def61a2 -->

# SAP Master Data Integration Receiver Adapter

Use SAP Master Data Integration \(MDI\) receiver adapter to synchronize your master data from SAP applications like SAP ECC and other third-party applications with SAP MDI service.

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

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loioe91e373bbb5b49ccbc2977152def61a2__section_jnr_zm2_4tb"/>

## SAP Master Data Integration \(MDI\) Adapter

The adapter does two actions: submit change requests to master data objects in SAP MDI \(via Requests API\) and query for changes of the master data objects in SAP MDI \(via Events API\). You can use the adapter for the following scenarios:

-   Request changes to your master data in the SAP MDI service.

-   Send queries to SAP MDI to know your master data.

-   Leverage message mapping in SAP Cloud Integration to map data from third-party applications to ODM equivalent data and send the same to SAP MDI.


> ### Remember:  
> The adapter uses the v1 version of MDI APIs. If you would like to recreate similar scenarios by directly communicating with the MDI service, we recommend using the v1 version of the MDI APIs.
> 
> Don't make parallel calls to SAP MDI using the adapter that could lead to data inconsistencies.

For scenario-specific detailed information, refer to the [blog](https://blogs.sap.com/2022/05/20/sap-integration-suite-integration-with-sap-master-data-integration-mdi-service/).

The adapter is available in the receiver/outbound communication channel. Once you've created a receiver channel and selected the adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).



<a name="loioe91e373bbb5b49ccbc2977152def61a2__section_xgd_1n2_4tb"/>

## Adapter Configuration

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

Provide a name for the channel.

</td>
</tr>
<tr>
<td valign="top">

*Description* 

</td>
<td valign="top">

Provide an optional description for the channel.

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

Enter the MDI host address to which you want to connect to. For example, `https://one-mds.cfapps.sap.hana.ondemand.com`.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*ODM Entity Type* 

</td>
<td valign="top">

Enter the fully qualified name of a One Data Model \(ODM\) entity type. For example, `sap.odm.businesspartner.BusinessPartner`.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*ODM Entity Version* 

</td>
<td valign="top">

Enter the ODM entity version. For example, `2.1.1`.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*API Type* 

</td>
<td valign="top">

Select one of the following values:

-   *Requests API* – if you want to request changes to your master data objects.

-   *Events API* – if you want to fetch the changes that are made on your master data objects.

    When the integration flow executes an Events API, data from the connected MDI service is queried and returned. Remember that a delta token is persisted internally, such that if you re-execute the same integration scenario at a later point in time, only delta changes are fetched.

    > ### Remember:  
    > The delta token is specific to the MDI service instance. After executing the integration flow for MDI service instance A, if you change the *Address* to connect MDI service B, the events API fails. This failure happens because the persisted delta token to specific to MDI service instance A and invalid for service instance B.
    > 
    > In such cases, you must first delete the persisted delta token using SAP Cloud Integration's [public API](https://api.sap.com/api/IntegrationContent/resource/MDI_Delta_Token) for MDI.




</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

*OAuth2 Client Credentials*is the supported authentication type and selected by default.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Enter the name of an OAuth2 Client Credentials you’ve deployed on the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in seconds\)* 

</td>
<td valign="top">

Specify the amount of time, in seconds, that the client waits for a response before it times out. Maximum allowed value is `600`. To wait indefinitely, enter `0`.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing for Events API**


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

*Page Size* 

</td>
<td valign="top">

Enter the number of records from fetched results that you want in one page. Maximum allowed value is `5000`.

</td>
</tr>
<tr>
<td valign="top">

*Response Data* 

</td>
<td valign="top">

Select one of the following values:

-   *Restricted* – if you want to fetch only a part of the data volume. By selecting this value, only 2 pages of output are fetched.

-   *All* – if you want to fetch all available data.




</td>
</tr>
<tr>
<td valign="top">

*Process in Pages* 

</td>
<td valign="top">

Enable the option mandatorily if you select *All* for *Response Data*. The option enables pagination so that you process the data in parts rather than fetching all data in a single page. To use *Process in Pages*, you must use the adapter in a *Local Integration Process* that is invoked by a *Looping Process Call* step.

In the *Looping Process Call*, provide the loop condition details that follow:

-   Select *Expression Type* as *Non-XML*

-   For *Condition Expression*, provide `${property.<receiver.name>.<channel.name>.<componentType>.hasMoreRecords}='true'`

-   For *Maximum Number of Iterations*, provide `99999`




</td>
</tr>
</table>

**Processing for Requests API**


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

*Consider Operation from Payload* 

</td>
<td valign="top">

Enable if the incoming payload contains the Operation for request API. The payload could be in an earlier step like Content modifier or Script.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

Enabled only if the option *Consider Operation from Payload* isn't opted.

</td>
<td valign="top">

Manually select the operation to be performed on the ODM Entity, if you don't enable *Consider Operation from Payload*. Allowed operations are:

-   Create

-   Delete

-   Forcepatch – this operation is the default selection.

-   Patch

-   Update




</td>
</tr>
<tr>
<td valign="top">

*Consider Change Token from Payload* 

</td>
<td valign="top">

Enable if the incoming payload contains the change token for request API. The payload could be in an earlier step like Content modifier or Script.

Change token is a string value of the corresponding change request. It confirms the status that resulted from your change with that token. It avoids initial load and supplies all changes that have happened since the mentioned change token.

For the operation *Forcepatch*, we strongly recommend you to enable the option. Forcepatch is an equivalent to an upsert operation and it's essential to carry a change token for such operation.

</td>
</tr>
<tr>
<td valign="top">

*Change Token Prefix*

Enabled only if the option *Consider Change Token from Payload* isn't opted.

</td>
<td valign="top">

Enter a prefix for the change token that is less than or equal to 5 characters. The format of the change token is: *<prefix\>*\_*<date in yy-mm-dd-hh-mm-ss\>*\_*<hashcode of UUID\>*.

</td>
</tr>
<tr>
<td valign="top">

*Retry for Change Request Confirmation* \> *Retry Interval \(in seconds\)* 

</td>
<td valign="top">

Select the amount of time after which you want the adapter to try again for change request confirmation.

**Why Retry is important** – When you send a change request \(Requests API\) to MDI, you also need to trigger an Events API to ensure that the change request was successfully executed. The adapter does this part automatically – that is, upon receiving a success message \(status code 202\) for the change request, the adapter triggers an Events API to let you know the changes were successfully made. If there's no response from MDI, the retry option enables the adapter to trigger another Events API to check the change request confirmation.

</td>
</tr>
<tr>
<td valign="top">

*Retry for Change Request Confirmation* \> *Retry Iterations* 

</td>
<td valign="top">

Select the number of retries to be attempted.

</td>
</tr>
<tr>
<td valign="top">

*Change Request Contains LocalIds* 

</td>
<td valign="top">

Enable if your change request contain local identifiers. You can include a local identifier either from an incoming payload or manually adding it in the adapter.

*<localId\>* is an identifier for the specific master data object that you can pass on to MDI. If you change request is successfully processed, the *<localId\>* is stored by MDI.

</td>
</tr>
<tr>
<td valign="top">

*Consider LocalId from Payload* 

</td>
<td valign="top">

Enable if the incoming payload contains the local identifier for request API. The payload could be in an earlier step like Content modifier or Script. Else, use the parameters in the table that follows to manually add a local identifier.

</td>
</tr>
</table>

Choose *Add* and provide values in the fields as follows:

**Parameters for a Local ID**


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

*Application* 

</td>
<td valign="top">

Enter the application that owns the local identifier.

</td>
</tr>
<tr>
<td valign="top">

*Tenant* 

</td>
<td valign="top">

Enter the tenant identifier in the application.

</td>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top">

Optional – Enter the fully qualified entity type. For example, `sap.odm.businesspartner.BusinessPartner`.

</td>
</tr>
<tr>
<td valign="top">

*Additional Context* 

</td>
<td valign="top">

Optional – Provide additional information if other fields are unable to uniquely identify the master data object.

</td>
</tr>
<tr>
<td valign="top">

*LocalId* 

</td>
<td valign="top">

Enter the unique value of the entity.

</td>
</tr>
<tr>
<td valign="top">

*Status* 

</td>
<td valign="top">

Optional – Enter the status of the local identifier. Accepted values are: `active` and `inactive`.

</td>
</tr>
<tr>
<td valign="top">

*LocalId Source* 

</td>
<td valign="top">

Select one of the following values:

-   *Constant* – if you want to define the identifier in the table using the *LocalId* field.

-   *Header* – if you want to fetch the value from a header created in the integration flow. For example, from a content modifier or script step.

-   *JSON Path* – if you want to provide the JSON path of the file that contains the identifier.

-   *Property* – if you want to fetch the value from a property created in the integration flow. For example, from a content modifier or script step.




</td>
</tr>
</table>

[SAP Master Data Integration Documentation](https://help.sap.com/docs/SAP_MASTER_DATA_INTEGRATION)

[SAP One Domain Model](https://api.sap.com/sap-one-domain-model)

