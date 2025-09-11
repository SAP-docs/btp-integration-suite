<!-- loio39c2b30f5bbc45ca9b3396a188650b7d -->

# Create an API Artifact Using an API Specification

Use this method when you want to design your API using the OpenAPI Specification editor.



<a name="loio39c2b30f5bbc45ca9b3396a188650b7d__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration capability.

-   Enable API Management capability.

-   Provision Edge Integration Cell runtime.




## Context

Design API artifact in OpenAPI specification editor.

> ### Note:  
> You can also create an OData type of API artifact using the OpenAPI Specification.

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

6.  Select *API Specification* from the given options and choose *Next*.

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
    
    Enter an intuitive name. The name must start with a letter or underscore \(\_\), and may include letters, numbers, spaces, periods \(.\), or hyphens \(-\). It must not end with a period \(.\).
    
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
    
    API artifacts can be exposed as REST, and ODATA.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Base Path
    
    </td>
    <td valign="top">
    
    Enter the path prefix for the API. For example, `v1/SFlight`.

    > ### Note:  
    > The base path shouldn't be left empty or set to only "/".


    
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
    
    Add a version if you want to improve, upgrade, or customize the functional behavior of an existing API artifact. Versioning allows the creation and management of multiple concurrent versions of an API.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Runtime Profile
    
    </td>
    <td valign="top">
    
    The runtime node on which the API artifact will be deployed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Virtual Host
    
    </td>
    <td valign="top">
    
    You can view the *Virtual Host URL* for the selected runtime profile from this page. The virtual host defines the public-facing hostname and base path through which your API is exposed.

    For example, even if your backend service is hosted at https://internal.services.local/orders, you can expose it externally as `https://api.yourdomain.com/v1/orders` using a virtual host.

    This helps in proxification of the internal URL, improving security and allowing for more flexible deployment configurations.
    
    </td>
    </tr>
    </table>
    
8.  Choose *Create*.

    The API opens in the *API Specification* editor.

9.  To model an API in Open API format, choose *Edit*. For more information, see [Use the OpenAPI Specification Editor](use-the-openapi-specification-editor-4923e5e.md).

10. To add additional attributes, see  <?sap-ot O2O class="- topic/xref " href="4ab4c8e7a09d4608abf91c04ea51f9e3.xml" text="" desc="" xtrc="xref:3" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/39c2b30f5bbc45ca9b3396a188650b7d.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

11. For a given OData-based API artifact, you can import an .edmx file to update the API artifact with the latest resources. See, [Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md).

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
    
    Save the artifact as draft version.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Save as version* 
    
    </td>
    <td valign="top">
    
    Create a new version of the artifact.

    Specify the version in the *Version Information* dialog. In the *Comment* section, you can add additional information specific to the artifact for later reference. This helps you determine the purpose of each version.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Deploy* 
    
    </td>
    <td valign="top">
    
    Deploy the API artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Delete* 
    
    </td>
    <td valign="top">
    
    Delete the API artifact from the package.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Cancel* 
    
    </td>
    <td valign="top">
    
    End your edit session without saving any of the changes you have made.
    
    </td>
    </tr>
    </table>
    

