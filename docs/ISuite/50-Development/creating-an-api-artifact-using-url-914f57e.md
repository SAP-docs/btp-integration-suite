<!-- loio914f57e52c8945f5b3ef97a79548aeec -->

# Creating an API Artifact Using URL

Create an API artifact of the type REST, SOAP, and OData using the HTTP endpoint URL.



<a name="loio914f57e52c8945f5b3ef97a79548aeec__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration and API Management capabilities.

-   Provision Edge Integration Cell runtime.




<a name="loio914f57e52c8945f5b3ef97a79548aeec__steps_xh1_ksv_fxb"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select the *API*.

    The *Create API* wizard opens.

5.  Select the *Runtime Profile* and choose *Next*. This profile determines the runtime on which you will create and process your API artifact.

6.  To create an API using the HTTP endpoint URL, select *URL* from the given options and choose *Next*.

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
    
    APIs are identified by their IDs on the home screen. You can use space and special characters in an ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The HTTP endpoint URL of the service. For example, `HTTP(s): //<host>:<port>/SFlight..`

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
    
    API Proxies can be exposed as REST, SOAP, and OData APIs.
    
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
    > If there is an issue while parsing the .edmx file, the OData API artifact will still get created. However, you have the option to add the necessary resources by selecting *Add Resources* in the *Resources* tab. Alternatively, you can choose *Switch to the API Specification* tab and paste a valid .edmx file there.


    
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
    
    Add a version if you want to improve, upgrade, or customize the functional behavior of an existing API proxy. Versioning allows the creation and management of multiple releases of an API. For example, v1.

    When you choose to version your API proxy, its name is appended with the version, and its basepath is prepended with the version. For example, if the version you enter is v1, the name is Name\_v1, and the basepath is `/v1/SalesOrder`.
    
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
    
    You can view the *Virtual Host URL* for the selected Runtime Profile from this page.
    
    </td>
    </tr>
    </table>
    
8.  Choose *Create*.

9.  To add a resource to the API artifact, choose *Edit*.

    -   To add a resource to a REST-based API artifact:

        1.  Choose + \(*Add*\).

        2.  In the popup, enter a title and path prefix for the resource.

        3.  Select the methods that need to be supported for this resource.

        4.  Add descriptions in the editor and choose *OK*.

            The added resource appears on the *Resources* tab.

        5.  Choose *Add* to add more resources to the same API.


    -   To add a resource to a SOAP-based API artifact:

        1.  Choose + \(*Add*\).

        2.  Enter a title and specify the SOAP operation name in the path prefix.

        3.  Use the editor to enter the relevant API documentation in the description field, and choose *Add*.

            The added resource appears on the *Resources* tab. By default, only the *POST* operation is selected.

        4.  Choose *Add* to add more resources to the same API.



10. For a given OData-based API artifact, you can import an .edmx file to update the API artifact with the latest resources.

    Importing an .edmx file will overwrite the existing list of resources in the API artifact. However, the description for each resource will still be maintained and not be changed.

    > ### Note:  
    > Importing the .edmx file will convert the API artifact to OpenAPI Specification 3.0.0. Please review the changes carefully before saving the API artifact.

11. For a given resource, choose *Show/Hide* to view the list of properties and their associated API documentation. You can add descriptions for each resource in the editor.

12. To define policies on the API, go to the *Policies* tab. For more information about how to add a policy, see [Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md).

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
    

