<!-- loio39c2b30f5bbc45ca9b3396a188650b7d -->

# Creating an API Using API Specification

Create an API from a specification that contains the single target URL endpoint.



<a name="loio39c2b30f5bbc45ca9b3396a188650b7d__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration and API Management capabilities.

-   Provision Edge Integration Cell runtime.




## Context

Design API artifact in OpenAPI specification editor.

> ### Note:  
> You can create an OData type of API artifact using the OpenAPI Specification.

The API specification editor includes rich inbuilt capabilities that enable you to do the following:

-   Import existing open APIs
-   Download APIs
-   Generate equivalent HTML output views
-   Save APIs
-   Validate open API syntax

The API designer supports OAS 2.0 and OAS 3.0 versions.

To know more about OAS 3.0 support in API Management, see [OpenAPI Specification 3.0](openapi-specification-3-0-db3537a.md).



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Create API* dialog opens.

5.  Select the *Runtime Profile* and choose *Next*. This profile determines the runtime on which you will create and process your API artifact.

6.  To import an API Definition, select *API Specification* from the given options and choose *Next*.

7.  Fill in the following *API Details*:


    <table>
    <tr>
    <th valign="top">

    API Details
    
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
    
    Provide an intuitive name in lowercase. Avoid using space, special characters, and forward slash \(/\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ID
    
    </td>
    <td valign="top">
    
    APIs are identified by their IDs on the home screen. You can use space and special characters in an ID.Provide an intuitive name in lowercase. Avoid using space, special characters, and forward slash \(/\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The HTTP endpoint URL of the service. For example, HTTP\(s\): //<host\>:<port\>/SFlight..

    > ### Note:  
    > In a REST API, it is recommended not to include query parameters in the URL field. For example, the URL should be in the format `https://httpbing.org/anything` instead of `https://httpbing.org/anything?$format=json`. Including query parameters in the URL can cause the validation of the artifact to fail during deployment.
    > 
    > If you need to use query parameters, it is best to append them during the execution of the API rather than including them in the URL field.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Service Type
    
    </td>
    <td valign="top">
    
    API Proxies can be exposed as REST, and ODATA.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Base Path
    
    </td>
    <td valign="top">
    
    Enter the path prefix for the API. For example, `v1/SFlight`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API State
    
    </td>
    <td valign="top">
    
    API state is used only for demarcation and not used to govern the lifecycle of the API. Choose Alpha if the version of an API is used for exploratory purposes, Beta if the API isn’t meant for productive use, and Active if the API is meant for productive use.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Version
    
    </td>
    <td valign="top">
    
    Add a version if you want to improve, upgrade, or customize the functional behaviour of an existing API proxy. Versioning allows the creation and management of multiple releases of an API. For example, v1.

    When you choose to version your API proxy, its name is appended with the version, and its basepath is prepended with the version. For example, if the version you enter is v1, the name is Name\_v1, and the basepath is `/v1/SalesOrder`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Runtime Profile
    
    </td>
    <td valign="top">
    
    The runtime node on which the API artifact will be deployed. Each runtime profile is mapped to one or more virtual hosts.
    
    </td>
    </tr>
    </table>
    
8.  Choose *Create*.

    The API opens in the *API Specification* editor.

9.  To model an API in Open API format, choose *Edit*. For more information, see [Creating APIs Using OpenAPI Specification](creating-apis-using-openapi-specification-4923e5e.md).

10. To add additional attributes, see [Additional Attributes in OpenAPI Specification](additional-attributes-in-openapi-specification-4ab4c8e.md).

11. For a given OData-based API artifact, you can import an .edmx file to update the API artifact with the latest resources.

    Importing an .edmx file will overwrite the existing list of resources in the API artifact. However, the description for each resource will still be maintained and not be changed.

    > ### Note:  
    > Importing the .edmx file will convert the API artifact to OpenAPI Specification 3.0.0. Please review the changes carefully before saving the API artifact.

12. Once you’ve modeled the API, you can select one of the following actions for the API:


    <table>
    <tr>
    <th valign="top">

    Action
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Save* 
    
    </td>
    <td valign="top">
    
    Saves the artifact as Draft version.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Save as version* 
    
    </td>
    <td valign="top">
    
    Creates a new version of the artifact.

    Specify the version in the *Version Information* dialog. In the *Comment* section, you can add additional information specific to the artifact for later reference. This helps you determine the purpose of each version.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Deploy* 
    
    </td>
    <td valign="top">
    
    Deployes the API artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Delete* 
    
    </td>
    <td valign="top">
    
    Deletes the API artifact from the package.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Cancel* 
    
    </td>
    <td valign="top">
    
    Ends your edit session without saving any of the changes you have made.
    
    </td>
    </tr>
    </table>
    

