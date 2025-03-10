<!-- loiod16dd12c5c5649e99c8939879a77f9c0 -->

# Configure the SuccessFactors OData V2 Receiver Adapter

Configure the SuccessFactors OData V2 receiver adapter by understanding the adapter parameters.

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

The SuccessFactors OData V2 receiver adapter supports externalization. To externalize the parameters of this adapter, choose *Externalize* and follow the steps mentioned in [Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md).

> ### Note:  
> -   The OData adapter doesn't support *$format* in query options.
> 
> -   The OData adapter supports sending error response in exception subprocess. The error response body is part of expression `${in.body}`.
> 
> -   OData services response code is captured in the `camelhttpresponsecode` header.
> 
> -   Retry for *Upsert* operation is now enabled for inner error code 412. Retry will be executed once and after 1 minute only.
> -   Learn how to construct the required payload for SuccessFactors OData V2 Upsert operation from the [blog](https://blogs.sap.com/2019/09/15/payload-structure-for-successfactors-upsert-in-sap-cloud-platform-integration/).

Select the *General* tab and provide information as described as follows:


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

Enter a name for the channel.

</td>
</tr>
<tr>
<td valign="top">

*Description*

</td>
<td valign="top">

Enter an optional description for the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide information as described as follows:

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

URL of the SuccessFactors data center that you're connecting to.

You can browse and select a SuccessFactors data center URL by using the *Select* option.

</td>
</tr>
<tr>
<td valign="top">

*Address Suffix* 

</td>
<td valign="top">

The field is auto-populated with `/odata/v2`. Don't edit the field.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

Type of proxy you want to use for connecting to SuccessFactors OData V2 service. Choose *Internet*. There are other proxy types that are irrelevant for this adapter that you can ignore.

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

Name of the credentials that you've deployed in *Security Material* in Operations View.

</td>
</tr>
<tr>
<td valign="top">

*Accept-Encoding*

</td>
<td valign="top">

Compresses the response data from SuccessFactors so that you improve the message processing time. GZIP is the supported compression algorithm.

-   *None*

-   *gzip*




</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

The option is enabled by default. This option enables the reuse of connection objects from the internal connection pool which in turn improves the network turnaround time for multiple communications to a same end point.

</td>
</tr>
</table>

Select the *Processing* tab and provide information as described as follows:

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

*Operation Details* 

</td>
<td valign="top">

Operation that you want to perform on the SuccessFactors OData V2 service. Supported operations are:

-   Query \(GET\)

-   Create \(POST\)

-   Update \(PUT\)

-   Read \(GET\)

-   Delete

-   Upsert \(POST\)


To leverage all operations, always use the latest version of the adapter.

</td>
</tr>
<tr>
<td valign="top">

*Resource Path* 

</td>
<td valign="top">

Path of the resource \(entity\) that you want to perform the operation on.

Choose *Select* to launch the [modeling operation](configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md#loiod16dd12c5c5649e99c8939879a77f9c0__model-operation).

> ### Note:  
> Navigation entities in the resource path aren't supported.



</td>
</tr>
<tr>
<td valign="top">

*Fields*

\(only for *PUT* and *POST* operations\)

</td>
<td valign="top">

The fields in the entity that you want to modify. You can add this using the [Model Operation Wizard](configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md#loiod16dd12c5c5649e99c8939879a77f9c0__model-operation).

</td>
</tr>
<tr>
<td valign="top">

*Query Options*

\(only for *GET* operations\)

</td>
<td valign="top">

Additional options that you want to add to the query like `$top` or how to order the results using *orderby*. You can add this using the Model Operation Wizard.

> ### Remember:  
> While forming queries, either using the wizard or manually, you must follow the query structure recommended by SuccessFactors. For example, if you want to query records effective on a defined date, you must use the `asOfDate` parameter as recommended by SuccessFactors [documentation](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/d599f15995d348a1b45ba5603e2aba9b/fce067c46f5d4d4f85a21fc9bb9b21c3.html). If a query that you form doesn't follow the recommended structure, the adapter won't be able to show errors during the design time, in turn, leading to unexpected results at runtime. This is a known limitation of the adapter.



</td>
</tr>
<tr>
<td valign="top">

*Enable Batch Processing*

\(only for *POST* – UPSERT operation\)

</td>
<td valign="top">

Select to perform multiple operations in one request to the OData V2 service in the `$batch` mode.

</td>
</tr>
<tr>
<td valign="top">

*Custom Query Options* 

</td>
<td valign="top">

Query options that are specific to the SuccessFactors OData V2 service like `purge`.

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

\(only for *PUT* and *POST* operations\)

</td>
<td valign="top">

Select one of the following content options:

-   Atom

-   JSON




</td>
</tr>
<tr>
<td valign="top">

*Content Type Encoding*

\(only for *PUT* and *POST* operations\)

</td>
<td valign="top">

Select one of the options. You can either encode the content using UTF-8 or not encode the content.

-   None

-   UTF-8




</td>
</tr>
<tr>
<td valign="top">

*Pagination*

\(only for *GET* – QUERY operation\)

</td>
<td valign="top">

Allows you to set the type of pagination for your query results.

By default the value is set to *Server Snapshot-Based* which is the recommended value for integration scenarios. The other values are:

-   *Client*: For UI Application-based Integrations.

-   *Server Cursor-Based*


> ### Remember:  
> You must enable *HTTP Session Reuse*, either *On Exchange* level or *On Integration Flow* level.
> 
> For more information, refer to [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md).



</td>
</tr>
<tr>
<td valign="top">

*Page Size*

\(only for *GET* operation\)

</td>
<td valign="top">

Maximum number of records in one page from the available results fetched from the service. The value is set to *Empty* by default.

If set to empty, fetches the default page size which is 1000 records.

</td>
</tr>
<tr>
<td valign="top">

*Retry on Failure* 

</td>
<td valign="top">

By default, retry is enabled. This option enables you to mitigate intermittent network issues. If there are network issues, you enable the integration flow to retry connecting to the SuccessFactors OData V2 service. The retry happens for the following operations:

-   Query – for HTTP response codes 502, 503, 504, and 429.

    The system retries connection every 3 minutes for a maximum of 5 times.

-   Create, Update, and Delete – for HTTP response codes 412 and 429.

    The system retries connection only once after an interval of 1 minute.

-   Upsert – for 412 inner error code along with HTTP response code 200 and HTTP response code 429.

    The system retries connection only once after an interval of 1 minute.

-   Read and Batch – for HTTP response code 429.

    The system retries connection every 3 minutes for a maximum of 5 times.




</td>
</tr>
<tr>
<td valign="top">

*Process in Pages*

\(only for *GET* – QUERY operation\)

</td>
<td valign="top">

By selecting *Process in Pages*, you enable the adapter to process messages in batches. The size of a message is defined by the value that you specify for the *Page Size*.

To use *Process in Pages*, you must use the adapter in a *Local Integration Process* that is invoked by a *Looping Process Call* step. In the *Looping Process Call*, provide the loop condition details that follow:

-   Select *Expression Type* as *Non-XML*

-   For *Condition Expression*, provide `${property.<receiver.name>.<channel.name>.hasMoreRecords} contains 'true'`

-   For *Maximum Number of Iterations*, provide `999`


This option isn’t enabled for *Content Enricher*.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in min\)* 

</td>
<td valign="top">

Maximum time the system waits for a response before terminating the connection. For more information about the supported session duration, see SAP Note [3063733](https://me.sap.com/notes/3063733).

</td>
</tr>
<tr>
<td valign="top">

*HEADER DETAILS* 

</td>
<td valign="top">

*Request Headers*: Provide the **| \(Pipe\)**separated value list of HTTP request headers that has to be sent to the OData backend.

If the value \* is entered, **all** the message headers are converted to HTTP request headers and forwarded.

*Response Headers*: Provide the **| \(Pipe\)** separated value list of HTTP response headers. The received header values are converted to message/exchange headers.

If the value \* is entered, **all** the HTTP response header values are converted to message/exchange headers.

</td>
</tr>
</table>



<a name="loiod16dd12c5c5649e99c8939879a77f9c0__model-operation"/>

## Modeling Operation

This adapter provides a wizard for modeling operations easily. It's recommended that you use this wizard to ensure that the operation doesn't contain any errors. The wizard can also fetch the *Externalized* parameters that are maintained under the *Connection* details of the OData V2 outbound adapter.

There are two main steps in this wizard:

1.  *Connect to System:* In this step, you provide the details required for connecting to the web service that you're accessing.
2.  *Select Entity and Define Operation:* In this step, you select the operation you want to perform and the entity on which you want to perform the operation on. After selecting the entity, you also select the fields, filtering and sorting conditions.
3.  *Configure Filter & Sorting:* This step is available only for data fetch operations, where you can define the order in which the records are fetched in the response payload and filter for the fields that you require.

**Connect to System**


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

*Connection Source* 

</td>
<td valign="top">

You can choose between *Remote* and *EDMX*.

If you choose *Remote*, you've to manually specify all the details like address and authentication details.

If you choose *Local EDMX File*, you select the service definition EDMX file that contains all these details that you specified manually when you selected *Remote*.

</td>
</tr>
<tr>
<td valign="top">

*Local EDMX File*

\(only if you select *Connection Source* as *Local EDMX File*\).

</td>
<td valign="top">

Choose *Select* to select the EDMX service schema. You can also manually upload it from your local file system.

</td>
</tr>
<tr>
<td valign="top">

*Address* 

</td>
<td valign="top">

URL of the service that you want to access. If you're connecting to an on-premise system, enter the *Virtual Host* in your Cloud Connector installation.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

\(only if you select *Connection Source* as *Remote*.\)

</td>
<td valign="top">

Type of proxy that you want to use to connect to the service.

</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(only if you select *Proxy Type* as *On-Premise*\).

</td>
<td valign="top">

Location ID that you've configured in the Cloud Connector installation.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

-   *Basic*

-   *OAuth2 SAML Bearer Assertion* – in the query modeler, principal propagation isn't supported. Use a technical user ID with key pair common name. For more information, see [Deploying an OAuth2 SAML Bearer Assertion](deploying-an-oauth2-saml-bearer-assertion-3ee6582.md).




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Provide the credential name that you deployed in *Operations View*.

</td>
</tr>
</table>

**Select Entity & Define Operation**


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

Select the operation that you want to perform.

</td>
</tr>
<tr>
<td valign="top">

*Sub-Levels* 

</td>
<td valign="top">

Sublevels of the entity that you want to access. For example, if you want to access the field *Description* in the entity *Products*, and the field is located at *Category* \> *Products* \> *Description*, you select the *Sub Levels* as `3` since the field you want to access is at the third level.

</td>
</tr>
<tr>
<td valign="top">

*Select Entity* 

</td>
<td valign="top">

Entity that you want to perform the operation on.

</td>
</tr>
<tr>
<td valign="top">

*Fields* 

</td>
<td valign="top">

Fields associated with the entity that you want to perform the operation on.

</td>
</tr>
<tr>
<td valign="top">

*Top* 

</td>
<td valign="top">

Specifies the top 'n' number of entries to be fetched.

For more information, see **Top System Query Option \($top\)** in [OData V2 URI Conventions](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/)

</td>
</tr>
<tr>
<td valign="top">

*Skip* 

</td>
<td valign="top">

Specifies the top 'n' number of entries to be skipped and the rest of the entries are fetched.

For more information, see **Skip System Query Option \($skip\)** in [OData V2 URI Conventions](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/).

</td>
</tr>
</table>

This step is available only for data fetch operations, *Query\(GET\), and* *Read\(GET\)*.

**Configure Filter & Sorting**


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

*Filter By* 

</td>
<td valign="top">

Select the field that you want to use as reference for filtering, choose the operation \(ex: *Less Than or Equal*\), and provide a value.

> ### Note:  
> The *IN* operation is available under the filtering menu when editing the query manually. This operation isn't available in the Query Modeling wizard.
> 
> The IN operator must be used in lower case in the query.
> 
> > ### Example:  
> > https://<hostname\>/odata/v2/User?$filter=userId in 'ctse1','mhuang1','flynch1'



</td>
</tr>
<tr>
<td valign="top">

*Sort By* 

</td>
<td valign="top">

Select the field that you want to use as sorting parameter and choose *Ascending* or *Descending* order.

</td>
</tr>
</table>

