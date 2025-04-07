<!-- loiofb99a7d787334598a44d5b12db210511 -->

# Creating an API Using an Imported API Definition

Import an API definition and use it to build your API.



<a name="loiofb99a7d787334598a44d5b12db210511__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration and API Management capabilities.

-   Provision Edge Integration Cell runtime.

    > ### Note:  
    > -   You can use a.zip bundle or an OpenAPI Specification to import an API artifact.
    > 
    > -   The folders *APIResources*, *Documentation**FileResource*, and *Policy* aren’t required in the .zip file.
    > 
    > -   Ensure that the resource documentation is available in a single **OAS\_json** file. Referring to the external links in the API definitions within this json file isn’t allowed.
    > -   Both Swagger and OAS 3.0 are supported. To know more about OAS 3.0, see [OpenAPISpecification 3.0](https://help.sap.com/docs/integration-suite/sap-integration-suite/openapi-specification-3-0?version=CLOUD&q=%20OpenAPI%20Specification%203.0.).




## Context

The supported file types for an import are json, and .zip.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Create API* dialog opens.

5.  Select the *Runtime Profile* and choose *Next*. This profile determines the runtime on which you will create and process your API artifact.

6.  To import an API Definition, select *Import* from the given options and choose *Next*.

7.  In the *Import API* window:

    1.  Choose *Browse*. Navigate and choose the required API from your local file system.

        You can attach files of type .zip and .json.

        You can also include the configurations for health monitor and load balancer in the .zip file. For more information, see [Load Balancing Across API Providers](https://help.sap.com/docs/integration-suite/sap-integration-suite/load-balancing-across-api-providers?version=CLOUD&q=load%20balancer).

    2.  Once you upload the file, the *Name* and the *ID* field gets prepopulated. However, you can update the name and the ID field from this dialog.

    3.  Select the *Runtime Profile* on which the API artifact will be deployed.

        You can also view the virtual host URL for the runtime profile from this page.


8.  Choose *Create*.

9.  To add a resource to the API artifact, choose *Edit*.

    For a REST service:

    1.  Choose + \(*Add*\).

    2.  In the popup, enter a title and path prefix for the resource.

    3.  Select the methods that need to be supported for this resource.

    4.  Add descriptions in the editor and choose *Add*.

        The added resource appears on the *Resources* tab.

    5.  Choose *Add* to add more resources to the same API.
    6.  Proceed to Step 10.


    For a SOAP service, add a resource as follows:

    1.  Choose + \(*Add*\).

    2.  Enter a title and specify the SOAP operation name in the path prefix.

    3.  Use the editor to enter the relevant API documentation in the description field, and choose *Add*.

        The added resource appears on the *Resources* tab. By default, only the *POST* operation is selected.

    4.  Choose *Add* to add more resources to the same API.

    5.  Proceed to Step 10.


10. For a given resource, choose *Show/Hide* to view the list of properties and their associated API documentation. You can add descriptions for each resource in the editor.

    > ### Note:  
    > For a given resource, choose *Switch to API Details* and correct the errors in swagger definition, if any. The error message displayed on the screen helps in error detection and correction. Choose *Save* after making the necessary corrections in the swagger file.

11. To define policies on the API, go to the *Policies* tab. For more information about how to add a policy, see [Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md).

12. If you want to define multiple proxy endpoints, navigate to *Proxy EndPoint* tab.

    In the *Proxy Endpoint Properties*section, choose *Add*. Enter the *Property Name* and the *Values*. For the Proxy Endpoint property specifications, see [Proxy Endpoint Properties](https://help.sap.com/docs/integration-suite/sap-integration-suite/proxy-endpoint-properties?version=CLOUD).

13. Once you’ve filled in all the required details of the API, you can select one of the following actions for the API:


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
    
14. Once you’ve created an API, you can do the following:

    Go to the *Resources* tab, use the *Try out* button to test the API resource.


