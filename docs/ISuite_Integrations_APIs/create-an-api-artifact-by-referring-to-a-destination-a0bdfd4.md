<!-- loioa0bdfd44f53149f2b2dc3bf100ed3f2a -->

# Create an API Artifact by Referring to a Destination

You can create an API artifact by selecting the destination of your choice from the list of available destinations.



<a name="loioa0bdfd44f53149f2b2dc3bf100ed3f2a__prereq_dfg_hfb_pcc"/>

## Prerequisites

-   Enable API Management capability. For more information, see [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Integration Cell runtime. For more information, see [Activate Integration Cell](activate-integration-cell-1a627da.md).

-   The *PI\_Integration\_Developer* role collection must be assigned to you.

-   Set up a destination in SAP BTP Cockpit. To set up a HTTP destination from scratch, navigate to *Connectivity* \> *Destinations* from the side navigation pane, and follow the step-by-step instructions in [Create HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/create-http-destinations?version=Cloud). Also, ensure that you scroll to the *Labels* section \(below Additional Properties\) and add the label*IntegrationCell.Include* and set its value to *true*.

    > ### Note:  
    > Only destinations with the *Proxy Type* set to `Internet` or `OnPremise` are currently supported.
    > 
    > The following authentication mechanisms are supported for Internet and OnPremise destinations:
    > 
    > 
    > <table>
    > <tr>
    > <th valign="top">
    > 
    > Gateway
    > 
    > </th>
    > <th valign="top">
    > 
    > Authentication Mechanism
    > 
    > </th>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Internet
    > 
    > </td>
    > <td valign="top">
    > 
    > -   Basic Auth
    > 
    > -   No Auth
    > 
    > -   OAuth2ClientCredentials
    > 
    > -   OAuth2Password
    > 
    > -   ClientCertificate
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > OnPremise
    > 
    > </td>
    > <td valign="top">
    > 
    > -   Basic Auth
    > 
    > -   No Auth
    > 
    > -   OAuth2ClientCredentials
    > 
    > -   OAuth2Password
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > </table>

    To set up a HTTP destination from scratch, navigate to SAP BTP Cockpit, select *Destination* from the side navigation pane, and follow the step-by-step instructions in [Create HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/create-http-destinations?version=Cloud).




<a name="loioa0bdfd44f53149f2b2dc3bf100ed3f2a__context_sfm_3mh_rcc"/>

## Context

Your sub-account administrator configures the destinations for the APIs in your sub-account.

This destination contains a full specification of the access information for a system, which includes:

-   A tenant-unique destination name

-   The URL of the target system

-   The authentication method used, and corresponding credentials \(token service, client secret, passwords, etc.\)

-   Additional required headers




<a name="loioa0bdfd44f53149f2b2dc3bf100ed3f2a__steps_efv_wb5_ncc"/>

## Procedure

1.  Log on to the SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Create API* dialog opens.

5.  Select the Integration Cell *Runtime Profile* and choose *Next*.

6.  Select *API Provider* from the available methods and choose *Next*.

    This navigates you to the page where you can select the type of API provider.

7.  Select *Destinations* as the provider type.

8.  Select a destination from the list of available destinations, and then choose *Next*.

    This navigates you to the *API Details* page.

9.  The *API Details* page auto-populates the details.


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
    
    APIs are identified by their IDs on the home screen. You can use space and special characters in an ID. Provide an intuitive name in lowercase. Avoid using space, special characters, and forward slash \(/\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Provider
    
    </td>
    <td valign="top">
    
    The relevant destinations connected to the API's consumption bundle.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Relative URL
    
    </td>
    <td valign="top">
    
    This is the relative path of the service. For example, in this URL < HTTP\(s\): //<host\>:<port\>/sap/opu/odata/iwbep/GWSAMPLE\_BASIC, "/sap/opu/odata/iwbep/GWSAMPLE\_BASIC" is the relative path.

    > ### Note:  
    > In a REST API, it is recommended not to include query parameters in the URL field. For example, the URL should be in the format `https://abc.org/anything` instead of `https://abc.org/anything?$format=json`. Including query parameters in the URL can cause the validation of the artifact to fail during deployment.
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
    
    The path prefix for the API. For example, `v1/SFlight`.

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
    
    Add a version if you want to improve, upgrade, or customize the functional behavior of an existing API artifact. Versioning allows the creation and management of multiple releases of an API. For example, v1.
    
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
    
10. Choose *Create*.

    The API artifact gets created. You can edit it further and configure the following:


    <table>
    <tr>
    <th valign="top">

    Tab
    
    </th>
    <th valign="top">

    Details
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Overview
    
    </td>
    <td valign="top">
    
    You can edit the following:

    -   Name of the API
    -   Host Alias
    -   API Base Path
    -   API State
    -   API Description


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Endpoint
    
    </td>
    <td valign="top">
    
    You can change the API provider by choosing an appropriate destination from the list of available destinations. You can also edit the Relative URL at this point if you want to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Resources
    
    </td>
    <td valign="top">
    
    You can add resources. Resources refer to the individual endpoints or services that are exposed through APIs. For more information, see [Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Policies
    
    </td>
    <td valign="top">
    
    To enforce security or control API traffic, add policies to the API artifact. For more information about how to create a policy, see [Add Policies to Artifacts](add-policies-to-artifacts-c2b3e56.md).
    
    </td>
    </tr>
    </table>
    
11. Once you’ve modeled and managed your API artifact, you can select one of the following actions:


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
    
    Deploys the API artifact.
    
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
    

