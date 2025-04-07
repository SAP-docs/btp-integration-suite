<!-- loiocd66a12cc2054e36a5dfa6b93d56c7bb -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure the OData V4 Receiver Adapter

You configure the ODataV4 receiver adapter by understanding the adapter parameters.

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

The OData V4 receiver adapter supports externalization. To externalize the parameters of this adapter, choose *Externalize* and follow the steps mentioned in [Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md).

Once you’ve created a receiver channel and selected the OData V4 Receiver Adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

> ### Note:  
> If you want to pass on null values to the receiver, your request must contain such null values with the attribute ***xsi:nil="true"***. Also note that the responses from the adapter contain null values represented as ***xsi:nil="true"***.

Select the *General* tab and provide the values in the fields as follows.

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

Select the *Connection* tab and provide the values in the fields as follows.

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

Service root URI of the OData V4 service that you want to connect to.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

The type of proxy you want to use for establishing connection with the OData V4 service. Currently, you can choose between

-   Internet

-   On-Premise




</td>
</tr>
<tr>
<td valign="top">

*Location ID*

only if *On-Premise* is selected for *Proxy Type*

</td>
<td valign="top">

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Authentication method that you want to use for connecting to the OData V4 service. Currently, you can choose between

-   *None*

-   *Basic*


The following options are enabled only if you choose *Proxy Type* as *Internet*

-   *OAuth2 Client Credentials*: Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user.

-   *Client Certificate*: The adapter in the integration artifact authenticates itself against the receiver using a client certificate. It's a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on your tenant.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if *Basic* or *OAuth2 Client Credentials* is selected for *Authentication*\)

</td>
<td valign="top">

Name of the credentials that you’ve deployed in the *Security Material* section of :eye: 

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if *Client Certificate* is selected for *Authentication*\)

</td>
<td valign="top">

Enter the alias of the deployed key pair.

</td>
</tr>
<tr>
<td valign="top">

*Allow Chunking*

</td>
<td valign="top">

Select this option if you want to allow the chunking of the data.

</td>
</tr>
<tr>
<td valign="top">

*CSRF Protected*

</td>
<td valign="top">

Keep this option selected \(default setting\). It ensures that your integration flow is protected against Cross-Site-Request-Forgery, a kind of attack where a malicious party can perform harmful actions by masquerading as the logged in user.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in min\)*

</td>
<td valign="top">

Enter the time in minutes.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

The option is enabled by default. This option enables the reuse of connection objects from the internal connection pool that in turn improves the network turnaround time for multiple communications to a same end point.

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

*Operation* 

</td>
<td valign="top">

The operation that you want to perform on the selected OData entity or resource.

-   Batch Processing \($batch\)

    > ### Remember:  
    > For the Batch Processing operation, the maximum XML payload size supported is 2 MB. If your payload is more than 2 MB, message processing fails.

-   Create\(POST\)

-   Query\(GET

-   Update\(PUT\)

-   Delete\(DELETE\)

-   Patch\(PATCH\)


To leverage all operations, always use the latest version of the adapter.

</td>
</tr>
<tr>
<td valign="top">

*Resource Path* 

</td>
<td valign="top">

Enter a valid resource path.

> ### Note:  
> You can choose *Select* to open the query modeler/wizard with which you can model your query.
> 
> You can also specify the Resource Path parameter dynamically using a header or a property \(with an expression such like `${header.resourcePath}`, for example\). Note that, however, XPath expressions aren’t supported for this parameter.



</td>
</tr>
<tr>
<td valign="top">

*Query Options*

\(enabled for *Query\(GET\)* operation\).

</td>
<td valign="top">

Query options that you’re passing as a part of the URI to the OData V4 service.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages* 

</td>
<td valign="top">

By selecting *Process in Pages*, you enable the adapter to process messages in pages, the page size of which is defined in the server-side system. To use *Process in Pages*, you must use the adapter in a Local Integration Process that is invoked by a Looping Process Call step.

</td>
</tr>
<tr>
<td valign="top">

*Attach Error Details on Failure* 

</td>
<td valign="top">

By default, the option is enabled. This option enables the creation of attachments for request header, response headers, and response body when the message processing fails.

Having these attachments during message processing failures can be unnecessary as it leads to persistence of attachments that doesn't help. Especially, if multiple message processing failures occur, you have attachments piled up for each failure. If you don't require the attachments for failure scenarios, disable the option. Though you disable the creation of attachments, the content of the same are added to the message processing logs.

If you're using older versions of the adapter where you don't see the option, define the property `SAP.DisableAttachments.ODataV4` in the message exchange with the value `true`.

</td>
</tr>
<tr>
<td valign="top">

*Request Headers* 

</td>
<td valign="top">

*Request Headers*: Provide the **| \(Pipe\)** separated value list of HTTP request headers that has to be sent to the OData back end.

If the value \* is entered, **all** the message headers are converted to HTTP request headers and forwarded.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers* 

</td>
<td valign="top">

*Response Headers*: Provide the **| \(Pipe\)** separated value list of HTTP response headers. The received header values are then converted to message/exchange headers.

If the value \* is entered, **all** the HTTP response header values are converted to message/exchange headers.

</td>
</tr>
<tr>
<td valign="top">

*METADATA DETAILS* 

</td>
<td valign="top">

The adapter makes an internal $metadata call during the message processing, before the actual endpoint call. Not all headers or query parameters are passed to the $metadata call. If your service needs some headers or parameters, provide the same in the request headers and query parameters fields. However, the custom parameters configured for $metadata call will also be appended to the service document call.

*Request Headers* – provide a pipe-separated \(|\) list of HTTP request headers to be sent to the $metadata call.

*Custom Query Parameters* – provide an ampersand-separated \(&\) list of key-value pairs.

</td>
</tr>
</table>



<a name="loiocd66a12cc2054e36a5dfa6b93d56c7bb__section_zgf_zrn_znb"/>

## Modeling Operation

This adapter provides a wizard for modeling operations easily. It’s recommended that you use this wizard to ensure that the operation doesn’t contain any errors. The wizard can also fetch the *Externalized* parameters that are maintained under the *Connection* details of the OData receiver adapter.

There are two main steps in this wizard:

1.  *Connect to System:* In this step, you provide the details required for connecting to the Web Service that you’re accessing.
2.  *Select Entity and Define Operation:* In this step, you select the operation you want to perform and the entity on which you want to perform the operation. After selecting the entity, you also select the fields, filtering and sorting conditions.
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

If you choose *Remote*, you’ve have to manually specify all the details like address and authentication details.

If you choose *Local EDMX File*, you select the service definition EDMX file that contains all these details that you specified manually when you selected *Remote*.

</td>
</tr>
<tr>
<td valign="top">

*Local EDMX File*

\(only if you select *Connection Source* as *Local EDMX File*\)

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

URL of the service that you want to access. If you’re connecting to an on-premise system, enter the *Virtual Host* in your Cloud Connector installation.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

\(only if you select *Connection Source* as *Remote*\)

</td>
<td valign="top">

Type of proxy that you want to use to connect to the service.

</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(only if you select *Proxy Type* as *On-Premise*\)

</td>
<td valign="top">

Location ID that you’ve configured in the Cloud Connector installation.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Only *Basic* authentication is supported. You can deploy credentials in :eye: and provide the *Credential Name* or provide the *Username* and *Password*.

For other authentication types, download the EDMX from the service and use the *Local EDMX File* to model the operation.

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

-   Batch Processing \($batch\)

    > ### Remember:  
    > For the Batch Processing operation, the maximum XML payload size supported is 2 MB. If your payload is more than 2 MB, message processing fails.

-   Create\(POST\)

-   Query\(GET\)

-   Update\(PUT\)

-   Delete\(DELETE\)

-   Patch\(PATCH\)


To leverage all operations, always use the latest version of the adapter.

</td>
</tr>
<tr>
<td valign="top">

*Sub Levels* 

</td>
<td valign="top">

Sub-levels of the entity that you want to access. For example, if you want to access the field *Description* in the entity *Products*, and the field is located at *Category* \> *Products* \> *Description*, you select the *Sub Levels* as `3` since the field you want to access is at the third level.

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

*Generate XML Schema Definition* 

</td>
<td valign="top">

Enable the check box if you want to generate an XSD file for the operation. You can also provide a name of your choice for the XSD file. This XSD file is needed when you create a message mapping.

There could be a scenario in which you wish to edit or update your modeling. In such cases, you can overwrite the XSD file instead of generating a new file every time.

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

*Filter Fields* 

</td>
<td valign="top">

Type the field name that you're looking for out to narrow down your search.

</td>
</tr>
<tr>
<td valign="top">

*Top* 

</td>
<td valign="top">

Specifies the top 'n' number of entries to be fetched.

For more information, see **Top System Query Option \($top\)** in [OData V4 URL Conventions](https://docs.oasis-open.org/odata/odata/v4.01/os/part2-url-conventions/odata-v4.01-os-part2-url-conventions.html).

</td>
</tr>
<tr>
<td valign="top">

*Skip* 

</td>
<td valign="top">

Specifies the top 'n' number of entries to be skipped and the rest of the entries are fetched.

For more information, see **Skip System Query Option \($skip\)** in [OData V4 URL Conventions](https://docs.oasis-open.org/odata/odata/v4.01/os/part2-url-conventions/odata-v4.01-os-part2-url-conventions.html).

</td>
</tr>
</table>

This step is available only for data fetch operations, Query\(GET\), and *Read\(GET\)*.

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

Select the field that you want to use as a reference for filtering, choose the operation \(ex: *Less Than or Equal*\), and provide a value.

> ### Note:  
> The *IN* operation is available with filtering when editing the query manually. This operation isn’t available in the Query Modeling wizard.
> 
> The IN operator must be used in lower case in the query.
> 
> > ### Example:  
> > https://<hostname\>/odata/v2/User?$filter=userId in 'ctse1','mhuang1','flynch1'
> 
> For more information, see [Customized Operators](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/1902/en-US/ded5808b5edb4bc9a8acfb5e9fe1b025.html).



</td>
</tr>
<tr>
<td valign="top">

*Sort By* 

</td>
<td valign="top">

Select the field that you want to use as a sorting parameter and choose *Ascending* or *Descending* order.

</td>
</tr>
</table>

