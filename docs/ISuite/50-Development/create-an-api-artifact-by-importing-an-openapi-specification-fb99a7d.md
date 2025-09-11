<!-- loiofb99a7d787334598a44d5b12db210511 -->

# Create an API Artifact by Importing an OpenAPI Specification

You can use the import method to create an API artifact when you already have an OpenAPI specification in formats such as .json, or when you've downloaded a .zip file. This .zip file serves as an API definition package that contains the OpenAPI specification along with other metadata related to the API artifact.



<a name="loiofb99a7d787334598a44d5b12db210511__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration capability.

-   Enable API Management capability.

-   Provision Edge Integration Cell runtime.


> ### Note:  
> -   You can use a.zip file or an OpenAPI Specification in.json format to import an API artifact.
> 
> -   The folders *APIResources*, *Documentation**FileResource*, and *Policy* aren’t required in the .zip file.
> 
> -   Ensure that the resource documentation is available in a single **OAS\_json** file. Referring to the external links in the API definitions within this json file isn’t allowed.
> -   Both Swagger and OAS 3.0 are supported. To know more about OAS 3.0, see [OpenAPISpecification 3.0](https://help.sap.com/docs/integration-suite/sap-integration-suite/openapi-specification-3-0?version=CLOUD&q=%20OpenAPI%20Specification%203.0.).



## Context

The import method allows you to quickly create an API artifact by importing an existing specification. For example, if you need to move an API artifact from a development environment to a production environment, you can create the API artifact in the development system, download it as .zip format, and then import it into the production system to recreate or deploy the same API artifact.

The supported file types for import are .json, and .zip.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Create API* dialog opens.

5.  Select the *Runtime Profile* and choose *Next*. This profile determines the runtime on which you will create and process your API artifact.

6.  To import an API specification, select *Import* from the given options and choose *Next*.

7.  In the *Import API* window:

    1.  Once you upload the specification, the *Name* and the *ID* field gets prepopulated. However, you can update the name and the ID field from this dialog.

        Enter an intuitive name. The name must start with a letter or underscore \(\_\), and may include letters, numbers, spaces, periods \(.\), or hyphens \(-\). It must not end with a period \(.\).

    2.  Select the *Runtime Profile* on which the API artifact will be deployed.

    3.  You can view the *Virtual Host URL* for the selected runtime profile.

        The virtual host defines the public-facing hostname, which is combined with the base path to expose your API.

        For example, even if your backend service is hosted at `https://internal.services.local/orders`, you can expose it externally as `https://api.yourdomain.com/v1/orders` using a virtual host.

        This helps in the proxification of the internal URL, improving security and allowing for more flexible deployment configurations.


8.  Choose *Create*.

9.  After the API artifact is created, you can choose *Edit* to further modify and configure the following:

    -   Update the API artifact details in the *Overview* tab.
    -   Change the target endpoint, in the *Target EndPoint* tab.
    -   Add resources by selecting the *Resources* tab. See, [Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md).

        > ### Note:  
        > For a given resource, choose *Switch to API Details* and correct the errors in the OpenAPI specification, if any. The error message displayed on the screen helps in error detection and correction. Choose *Save* after making the necessary corrections in the OpenAPI specification.

    -   Configure policies by navigating to the *Policies* tab. See [Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md).
    -   Edit your API artifact in the OpenAPI Specification editor by choosing *Switch to OpenAPI Specification*. See, [Use the OpenAPI Specification Editor](use-the-openapi-specification-editor-4923e5e.md).

10. Once you have filled in all the required details of the API, you can select one of the following actions for the API:


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
    

