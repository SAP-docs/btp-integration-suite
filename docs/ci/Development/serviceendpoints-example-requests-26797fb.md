<!-- loio26797fbe259349b387a74a5a8f9785c1 -->

# ServiceEndpoints Example Requests

The ServiceEndpoints resource enables you to obtain information about the service endpoints exposed by Cloud Integration on a tenant.

The Service Endpoints also provides you with the adapter-specific protocol information. The protocol is the type of the APIs such as SOAP, REST, and OData. The API protocol includes the protocol version, if applicable.


<table>
<tr>
<th valign="top">

Adapter

</th>
<th valign="top">

Protocol Type

</th>
</tr>
<tr>
<td valign="top">

SOAP

</td>
<td valign="top">

SOAP

</td>
</tr>
<tr>
<td valign="top">

IDoc

</td>
<td valign="top">

SOAP

</td>
</tr>
<tr>
<td valign="top">

OData V2

</td>
<td valign="top">

ODATAV2

</td>
</tr>
<tr>
<td valign="top">

AS2

</td>
<td valign="top">

AS2

</td>
</tr>
<tr>
<td valign="top">

AS4

</td>
<td valign="top">

AS4

</td>
</tr>
<tr>
<td valign="top">

HTTPS

</td>
<td valign="top">

REST

</td>
</tr>
</table>



<a name="loio26797fbe259349b387a74a5a8f9785c1__section_wws_3k5_r4b"/>

## Specific Example Requests for Service Endpoints

-   To return information about all service endpoints with only the entrypoints information expanded, send the following GET request:

    `https://<host address>/api/v1/ServiceEndpoints?$expand=EntryPoints`

    The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

    An entrypoint is an array of type `EntryPoint`. Following are the properties of the EntryPoint entity:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    \(Required\) Name of the entry point.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    \(Required\) Fully qualified endpoint or the base path of the API.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Enumerated String
    
    </td>
    <td valign="top">
    
    \(Optional\) Possible values are DEV, TEST, PROD, SANDBOX.
    
    </td>
    </tr>
    </table>
    
-   To return information about all service endpoints with only the API definitions expanded, send the following GET request:

    `https://<host address>/api/v1/ServiceEndpoints?$expand=ApiDefinitions`

    An API definition is an array of type `APIDefinition` containing links to the machine-readable API definitions like Open API specification files, OData metadata, and so on. Following are the properties of the `APIDefinition` entity:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    \(Required\) Fully qualified endpoint to the API definitions file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Enumerated String
    
    </td>
    <td valign="top">
    
    \(Required\) Name of the API definition endpoint. Possible values are oas-yaml, oas-json, raml, edmx, wsdl.
    
    </td>
    </tr>
    </table>
    
-   To return the service endpoints only for the integration flow with name `Getting Started Flow`, send the following GET request:

    `https://<host address>/api/v1/ServiceEndpoints?$expand=EntryPoints&$filter=Name eq 'Getting Started Flow'`

-   To return only the service endpoints information of protocol type SOAP, send the following GET request:

    `https://<host address>/api/v1/ServiceEndpoints?$expand=EntryPoints&$filter=Protocol eq 'SOAP'`


