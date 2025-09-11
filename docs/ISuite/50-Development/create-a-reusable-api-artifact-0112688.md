<!-- loio0112688ab000469f9939f8f53fcb2ff6 -->

# Create a Reusable API Artifact

A reusable API artifact is created so that its components and services can be leveraged repeatedly across various applications, projects, or contexts without needing substantial rewrites or modifications.



<a name="loio0112688ab000469f9939f8f53fcb2ff6__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration and API Management capabilities.

-   Provision Edge Integration Cell runtime.




## Context

Reusable API artifacts encompass policies for managing concerns such as authentication and rate limiting, schemas to maintain consistent data structures, named values for centralized configuration, products to group APIs and control access, API versions to enable smooth transitions, and documentation templates to ensure uniform API descriptions. By leveraging these reusable artifacts, you can simplify API development, enhance governance, and deliver a more seamless experience for API consumers.



## Procedure

1.  Log on to the Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Create API* wizard opens.

5.  Select the *Edge Integration Cell* as the *Runtime Profile* and choose *Next*.

    This profile determines the runtime on which you will create and process your API artifact.

6.  Select *Reusable API* from the available methods and choose *Next*.

7.  Fill in the following *API Details* and choose *Next*:


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
    
    API Base Path
    
    </td>
    <td valign="top">
    
    Enter the path prefix for the API. For example, `v1/SFlight`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Version
    
    </td>
    <td valign="top">
    
    Add a version if you want to improve, upgrade, or customize the functional behavior of an existing API artifact. Versioning allows the creation and management of multiple releases of an API artifact.
    
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
    </table>
    
    The reusable API artifact gets created and you are presented with the following two tabs on the reusable API details page:

    -   *Overview*: From this section, you can edit the basic information like the name, short text, description, along with the API base path
    -   *Policies*: From this section, you can design the policies and the integration steps.

8.  To set policies on the API artifact, navigate to the *Policies* tab.

    You will notice a template has been generated that references a new adapter called *API Direct*. For more information about how to add a policy, see [Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md).

    To create a reusable API artifact that addresses security concerns, you can start by bundling all relevant security policies into it. This includes adding authentication, authorization, rate limiting, and JSON threat protection policies. Additionally, you can include a mediation step such as a content modifier to handle any necessary message transformations.

    To view the properties of API Direct, hover your cursor over the dotted line labeled*API Direct* and click on it. This will open the API Direct properties section. Then, navigate to the *Connection* tab, where you’ll find the base path or address associated with the reusable API artifact.

9.  Once you’ve filled in all the required details of the API, you can select one of the following actions for the API:


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

    Select the runtime profile where you want to deploy the reusable API artifact and choose *Yes*
    
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
    
    > ### Note:  
    > A reusable API artifact cannot be invoked externally; it can only be invoked by a calling API artifact \(i.e., the API artifact that consume the reusable API artifact\) via API Direct adapter.
    > 
    > A reusable API artifact cannot reference or call other reusable APIs. Nesting is not supported.




<a name="loio0112688ab000469f9939f8f53fcb2ff6__postreq_shs_ngf_nfc"/>

## Next Steps

To confirm that the reusable API artifact has been successfully deployed, navigate to *Monitor* \> *Integrations and APIs*. From the dropdown, select the runtime profile where the reusable API artifact was deployed.

Scroll down to the *Manage Integration Content* section and select the tile containing all integration packages.

Open the relevant package and check the deployment status. If the artifact is marked as *Deployed*, the deployment was successful.

Note that since this is a reusable API artifact and not exposed externally, it does not have a public endpoint. As a result, the endpoint details tab will not be visible. All other aspects of the artifact interface remain unchanged.

