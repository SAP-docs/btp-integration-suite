<!-- loio914f57e52c8945f5b3ef97a79548aeec -->

# Create an API Artifact Using a Target URL

The method allows you to quickly create an API artifact by specifying the HTTP endpoint URL of a backend service. This method is useful when you already have a working backend \(e.g., a REST service\) and want to manage it.



<a name="loio914f57e52c8945f5b3ef97a79548aeec__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).
-   Activate Cloud Integration capability. See, [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?version=CLOUD).

-   Activate API Management capability. See, [Activate and Configure the API Management Capability](../activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Edge Integration Cell runtime. See, [Activate Edge Integration Cell](https://help.sap.com/docs/integration-suite/sap-integration-suite/activate-edge-integration-cell?version=CLOUD&q=Activate+Edge+Inte)




<a name="loio914f57e52c8945f5b3ef97a79548aeec__context_b4x_hdk_dgc"/>

## Context

When you use this method, you provide the target URL of your backend service—for example, `https://backend.mycompany.com/service`. The API management platform then uses this URL to route incoming API requests to the backend, effectively acting as a gateway between the client and the underlying service.

You deploy the API on a virtual host, which acts as the public-facing entry point—defining the hostname and base path through which consumers access your API.For instance, even if your actual backend resides at `https://backend.mycompany.com/service`, you can expose it externally as `https://api.example.com/v1/service`. This abstraction helps shield internal endpoints, enhancing both security and architectural flexibility.



<a name="loio914f57e52c8945f5b3ef97a79548aeec__steps_xh1_ksv_fxb"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Create API* artifact wizard opens.

5.  Select the *Runtime Profile* Edge Integration Cell and choose *Next*. This profile determines the runtime on which you will model an deploy your API artifact.

6.  To create an API artifact using an HTTPS target URL, select *URL* from the given options and choose *Next*.

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
    
    APIs are identified by their IDs on the home screen. You can use space and special characters in an ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The target HTTPS endpoint URL of the service. For example, `https://www.sap.com`

    > ### Note:  
    > In a REST API, it is recommended not to include query parameters in the URL field. For example, the URL should be in the format `https://abc.org/anything` instead of `https://abc.org/anything?$format=json`. Including query parameters in the URL can cause the validation of the artifact to fail during deployment.
    > 
    > If you need to use query parameters, it is best to append them during the execution of the API rather than including them in the URL.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Service Type
    
    </td>
    <td valign="top">
    
    API artifacts can be exposed as REST, SOAP, and OData APIs.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    File Name \(Optional\)
    
    </td>
    <td valign="top">
    
    This field is only visible when creating an API artifact of type OData.

    > ### Note:  
    > You can create an OData API artifact by browsing and uploading your .edmx file.
    > 
    > If there is an issue while parsing the .edmx file, the OData API artifact will still get created. However, you have the option to add the resources by selecting *Add Resources* in the *Resources* tab. See, [Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md). Alternatively, you can choose *Switch to the API Specification* tab and paste a valid .edmx file there.


    
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
    
    Virtual Host URL
    
    </td>
    <td valign="top">
    
    You can view the *Virtual Host URL* for the selected runtime profile. The virtual host defines the public-facing hostname, which is combined with the base path to expose your API.

    For example, even if your backend service is hosted at `https://internal.services.local/orders`, you can expose it externally as `https://api.yourdomain.com/v1/orders` using a virtual host.

    This helps in the proxification of the internal URL, improving security and allowing for more flexible deployment configurations.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Expose as MCP Server
    
    </td>
    <td valign="top">
    
    Enable this option to allow AI agents to access the API via the Model Context Protocol \(MCP\).
    
    </td>
    </tr>
    </table>
    
8.  Choose *Create*.

9.  After the API artifact is created, you can choose *Edit* to further modify and configure the following:

    -   Update the API artifact details in the *Overview* tab.
    -   Change the target endpoint, in the *Target EndPoint* tab.
    -   Add resources in the *Resources* tab. See, [Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md).
    -   Configure a policy in the *Policies* tab. See [Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md).
    -   Edit your API artifact in the OpenAPI Specification editor by choosing *Switch to OpenAPI Specification*. See, [Use the OpenAPI Specification Editor](use-the-openapi-specification-editor-4923e5e.md).

10. Once you’ve filled in all the required details of the API, you can select one of the following actions for the API artifact:


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
    
    Save the API artifact as draft version.
    
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
    
    Delete the API artifact and removes it from the package.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Cancel* 
    
    </td>
    <td valign="top">
    
    End your edit session without saving any of the changes you made.
    
    </td>
    </tr>
    </table>
    

