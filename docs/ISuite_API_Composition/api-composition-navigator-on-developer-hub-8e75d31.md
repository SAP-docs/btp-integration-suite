<!-- loio8e75d3178a684912a4b28d3b9593539c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# API Composition Navigator on Developer Hub

The API Composition Navigator is a tool that you use to inspect business data graphs.



<a name="loio8e75d3178a684912a4b28d3b9593539c__section_npq_fxr_xvb"/>

## Prerequisites

-   You are assigned the role of *GraphNavigator.Viewer*. For more information, see [Define Users for API Composition](initial-setup-12ad448.md#loio12ad448225ac47049982d9faab7978a3__section_DefineUsers).

-   You are optionally assigned the role of *GraphNavigator.Tryout* which allows you to explore business data graphs. See [Define Users for API Composition](initial-setup-12ad448.md#loio12ad448225ac47049982d9faab7978a3__section_DefineUsers).

-   You have already created a business data graph in API Composition on the SAP Integration Suite home page. For more information, see:

    -   [Create a Business Data Graph in SAP Integration Suite](create-a-business-data-graph-in-sap-integration-suite-42daf3b.md)

    -   [Extend Your Business Data Graph](extend-your-business-data-graph-bb4f072.md)





## Setting Up API Composition Navigator Tryout Connectivity

In order to send live requests to your business data graphs using the *Try Out* feature in the API Composition Navigator, you must first establish connectivity between the API Composition Navigator and API Composition.



### Prerequisites

You have created a Process Integration Runtime \(Client Credentials\) service instance in your SAP BTP subaccount. For more information, see [Enable Client Applications](enable-client-applications-e904119.md).



### Procedure

1.  Go to SAP BTP cockpit *Services* \> *Instances and Subscriptions* and search for your *Process Integration Runtime* service instance. Note down the contents of the service key.
2.  Go to *SAP Integration Suite* \> *Design* \> *API Composition*. In the upper right-hand corner, choose the <span class="SAP-icons-V5"></span> information icon and copy down your API Composition tenant domain.
3.  Go back to the SAP BTP cockpit *Connectivity* \> *Destinations*. Choose *Create* \> *From Scratch* \> *Create* and enter the following:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    `api_composition_navigator_access` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    HTTP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    https://<Your API Composition tenant domain\>/graph
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    OAuth2ClientCredentials
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    `<oauth.clientid>` from the Process Integration Runtime service key
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    `<oauth.clientsecret>` from the Process Integration Runtime service key
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    `<oauth.tokenurl>` from the Process Integration Runtime service key
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL Type
    
    </td>
    <td valign="top">
    
    Dedicated
    
    </td>
    </tr>
    </table>
    
4.  Choose *Create*.



<a name="loio8e75d3178a684912a4b28d3b9593539c__section_sy2_1l5_vvb"/>

## Using the API Composition Navigator

> ### Note:  
> To access the API Composition Navigator in Developer Hub, the API Composition capability of API Management in SAP Integration Suite must be activated. For more information, see [Activate API Composition on SAP Integration Suite](https://help.sap.com/docs/api-composition/isuite-api-composition/initial-setup?version=CLOUD#2.-activate-api-composition-on-sap-integration-suite).



### Procedure

1.  Go to *SAP Integration Suite homepage* \> *API Composition Navigator*.

    > ### Note:  
    > You can also go to *SAP Integration Suite homepage* \> ** and choose *API Composition* from the menu bar.

2.  Select a business data graph.

3.  Your selected business data graph with a list of available entities appears.

    Select a business system to see all of the available entities.

4.  Go to the *Try Out* tab to make requests for data objects. The *Navigate* panel shows available options to navigate to connected data objects. Choose *Run* to the see the API response.


