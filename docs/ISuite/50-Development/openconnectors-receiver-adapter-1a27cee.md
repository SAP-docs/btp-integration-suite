<!-- loio1a27cee87cd14ef69ca56fb50b1e3983 -->

# OpenConnectors Receiver Adapter

You use the OpenConnectors receiver adapter in integration flows to communicate with more than 170 non-SAP cloud applications that are supported by Open Connectors.

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

The OpenConnectors adapter connects with non-SAP cloud applications through REST APIs and is not Cross-Site Request Forgery \(CSRF\) protected. You can set the content-type to either JSON or XML format while processing the request or response for a transaction. The adapter also allows you to make calls using common HTTP methods on RESTful API services for outbound transactions.

> ### Remember:  
> OpenConnectors receiver adapter cannot process payloads that have an attachment.

Create an instance of the connector before you configure the adapter. If you have not yet enabled the *Open Connectors*, read [Enable Open Connectors in trial](https://blogs.sap.com/2018/09/19/part-1-enable-sap-cloud-platform-open-connectors-in-trial/) for more information about how to enable the service using SAP BTP.

After you have enabled the service, create an instance for a third-party application from the *Connectors* catalog. This [blog](https://blogs.sap.com/2018/09/19/part-2-connect-to-a-third-party-cloud-applications-via-sap-cloud-platform-open-connectors/) walks you through the steps for authenticating the connection and testing the APIs for the specific third-party application. For more information, see [SAP Open Connectors](https://help.sap.com/viewer/p/OPEN_CONNECTORS).

> ### Note:  
> HTTP requests to the REST APIs are protected with HTTP custom authentication using your organization secret, user secret, and instance token.



Once you have created a receiver channel and selected the OpenConnectors receiver adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

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

*Base URI*

</td>
<td valign="top">

Specify the URI that depends on your region and environment, which helps you establish connection with the *Open Connecters* service.

> ### Example:  
> `https://api.openconnectors.ext.int.sap.hana.ondemand.com/elements/api-v2`



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Provide the alias value for identifying the connector credentials. This helps the adapter authenticate and communicate with the connector. You can select the relevant **OpenConnector** security artifact from the list. Choose *Select* to see and add the relevant **OpenConnector** security artifact from the list.

See: [Deploying a User Credentials Artifact](deploying-a-user-credentials-artifact-6912d63.md)

</td>
</tr>
<tr>
<td valign="top">

*Resource*

</td>
<td valign="top">

Specify the resource name of an instance that you want to access. Resources belonging to specific instances and its operations are listed by Open Connectors. Choose *Select* to see the list of resources available for this specific instance.

> ### Note:  
> -   Do not use `$` character while defining query parameters.
> 
> -   Make sure you provide the*Base URI* before selecting the resources.



</td>
</tr>
<tr>
<td valign="top">

*Method*

</td>
<td valign="top">

Specify the HTTP method to retrieve the data from the connector. Find suitable HTTP method for the action performed by API:

-   `POST`
-   `GET`
-   `PATCH`
-   `PUT`
-   `DELETE`

> ### Note:  
> For *XML* request format, the HTTP methods are read from the source.



</td>
</tr>
<tr>
<td valign="top">

*Request Format*

</td>
<td valign="top">

Specify the content format of the incoming message. You can select one of the following request formats:

-   XML
-   JSON

> ### Note:  
> You must include `<SwaggerParser>`as the root element for every XML request as shown in the sample code below.
> 
> > ### Sample Code:  
> > ```
> > <?xml version="1.0" encoding="UTF-8" standalone="no"?>
> > 
> > <SwaggerParser>
> > 
> >     <basePath>/elements/api-v2</basePath>
> > 
> >     <host>..............</host>
> > 
> >     <Resources>
> > 
> >         <Resource>
> > 
> >             <name>...........</name>
> > 
> >             <Operations>
> > 
> >                 <Operation>
> > 
> >                     <methodType>.......</methodType>
> > 
> >                     <parameters>
> > 
> >                         <parameter>
> > 
> > ............
> > 
> > ..........
> > 
> > ..........
> > 
> > ............
> > 
> > ............
> > 
> > </parameter>
> > 
> >                     </parameters>
> > 
> >                 </Operation>
> > 
> >             </Operations>
> > 
> >         </Resource>
> > 
> >     </Resources>
> > 
> > </SwaggerParser>
> > ```



</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

Specify the content format for the outgoing message. For example, if you select XML format, then the response is converted to XML and dispatched.

> ### Note:  
> Do not use either *JSON to XML* or *XML to JSON* converters in the integration flow for transforming a response message.



</td>
</tr>
<tr>
<td valign="top">

*Query Parameters for Resource*

</td>
<td valign="top">

Define the value of a variable you want to modify. For example, you have defined a variable `/name/{varname1}{varname2}` in the resource field. Now use the *Query Parameters for Resource* field to define the value for `{varname1}{varname2}` variables. Use commas to separate more than variable such as `varname1=hello world, varname2= hello SAP`.

You can now include queries to the URI to filter for specific resources from the response. For example, define the query parameters with the query data in the format as follows`${header.querydata1};${header.querydata2}`, and use `;` to sperate two distinct queries.

</td>
</tr>
<tr>
<td valign="top">

*Page Size*

</td>
<td valign="top">

Specify the maximum number of records to be fetched in one page.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages*

</td>
<td valign="top">

The message is processed in pages of size defined in the *Page Size* field.

> ### Note:  
> Enable this option only if you are using the receiver adapter in a *Local Integration Process* invoked by a *Looping Process Call*.



</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum amount of time the system waits for a response before terminating the connection.

</td>
</tr>
</table>



### Related Links

SAP Blog [How to create a sample integration scenario using Open Connectors Adapter](https://blogs.sap.com/2019/03/13/cloud-integration-how-to-create-a-sample-integration-scenario-using-open-connectors-adapter/).

[SAP Open Connectors](https://help.openconnectors.ext.hana.ondemand.com/home)

