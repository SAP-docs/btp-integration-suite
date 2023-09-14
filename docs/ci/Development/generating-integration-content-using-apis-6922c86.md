<!-- loio6922c86cb4c54c669696bbac46d8e5aa -->

# Generating Integration Content using APIs

Use APIs to generate integration flows.



## Context

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

Based on specific integration requirement, you can filter and choose prepackaged APIs from the *Discover* page. These prepackaged APIs are from the SAP Business Accelerator Hub. Prepackaged API content contains different API types, and each API contains a set of resources and operations. The operations are available in the open API-specification format.

**Supported APIs and Operations**


<table>
<tr>
<th valign="top">

APIs



</th>
<th valign="top">

Operations



</th>
</tr>
<tr>
<td valign="top">

OData



</td>
<td valign="top">

GET, POST, and DELETE



</td>
</tr>
<tr>
<td valign="top">

REST



</td>
<td valign="top">

GET, POST, PUT, and DELETE



</td>
</tr>
</table>

For each API contained in an API package, you can generate an integration flow. The generated integration flow exposes an endpoint equivalent to the chosen API. Using this endpoint, you can send a request to the API exposed on a target tenant. The gererated integration flow contains a sender adapter according to the chosen API and operation. For example, from an OData API with GET operation, you generate an integration flow with OData sender adapter and GET operation.

> ### Note:  
> Generating integration flows is only possible for APIs that support basic authentication and DELETE, GET, POST, PUT, and GET\_ID operations.

To generate an integration flow and add it to the workspace of an existing integration package, do as follows:



## Procedure

1.  Choose *Discover* \> *APIs* to access the prepackaged APIs.

2.  Choose an API content package.

    For example, if you like to generate an integration flow for one of the SAP Cloud Integration OData APIs \(on SAP Business Accelerator Hub at [https://api.sap.com/package/CloudIntegrationAPI/odata](https://api.sap.com/package/CloudIntegrationAPI/odata)\), choose the package *SAP Cloud Integration*.

3.  Choose the *Artifacts* tab.

4.  Select the API for which you like to generate an integration flow.

    For example, if you've chosen the SAP Cloud Integration OData API package, the following APIs are available: *Integration Content*, *Log Files*, *Message Processing Logs*, *Message Stores*, *Partner Directory*, and *Security Content*. Let's assume that you like to generate an integration flow to read all SAP Cloud Integration message processing logs from a target tenant. Consequently, choose *Message Processing Logs*.

5.  Choose *Generate Integration Flow*.

6.  Specify the following parameters:


    <table>
    <tr>
    <th valign="top">

    Parameter


    
    </th>
    <th valign="top">

    Setting


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Package**


    
    </td>
    <td valign="top">
    
    Select the package where to add the generated integration flow.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Name**


    
    </td>
    <td valign="top">
    
    Specify the name of the generated integration flow.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Resource**


    
    </td>
    <td valign="top">
    
    Select the resource of the chosen API.

    For example, select */MessageProcessingLogs*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Operation**


    
    </td>
    <td valign="top">
    
    Select the operation. In the chosen example, only *GET* is available.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **URL**


    
    </td>
    <td valign="top">
    
    Specify the URL of the target system that exposes the API.


    
    </td>
    </tr>
    </table>
    
7.  Choose *Next*.

8.  Specify the following parameters:


    <table>
    <tr>
    <th valign="top">

    Parameter


    
    </th>
    <th valign="top">

    Setting


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Entity Set**


    
    </td>
    <td valign="top">
    
    Specify an entity set for the API, for example,`/GetAllMPLs`.

    This parameter is added to the sender adapter of the generated integration flow. In the chosen example, the generated integration flow contains an OData sender adapter, and this parameter specifies the *Entity Set* parameter of the sender adapter.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Receiver Addres**


    
    </td>
    <td valign="top">
    
    Specify the URL under which the API can be reached on the target tenant.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Credential Name**


    
    </td>
    <td valign="top">
    
    Specify a name for a *User Credentials* artifact. This artifact contains the credentials that are used to authenticate the integration flow against the target tenant \(only basic authentication is supported\). The credential name is added to the receiver dapter of the generated integration flow.


    
    </td>
    </tr>
    </table>
    
    These parameters are added to the generated integration flow as externalized parameters.




<a name="loio6922c86cb4c54c669696bbac46d8e5aa__result_mvf_pjt_cfb"/>

## Results

You have generated an integration flow and added it to an existing integration package.

