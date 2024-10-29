<!-- loioa64b952578f84161829439c3ee6e967b -->

# Edit an API Proxy

Once you’ve created an API proxy you can further change the proxy, either on the Integration Suite, or by using the embedded API designer.



## Context

When you edit an API proxy either on the Integration Suite or using the API designer, ensure that you save and deploy the API proxy once the changes are made. Saving the API proxy is a design time activity, the changes you've made get pushed to the runtime only when you deploy the changes. Therefore, when you choose *Save* after making the changes, the changes are saved locally and don’t get published on the Developer Hub. Choose *Deploy* to perform an explicit deployment to bring in the new changes in the runtime during the API proxy execution.

Consider the following examples:

-   If you just save and not deploy the change you've made to the Target Endpoint of an API proxy, and then try to debug the API proxy and use the trace capability in runtime to trace the API call, the call points to the old Target Endpoint. Only when you save and then explicitly deploy the changes, the API call points to the new Target Endpoint.

    > ### Note:  
    > Saving the changes puts the API proxy in the local intermediate save state, only deploying it publishes the changes in runtime.

-   Similarly, if you attach new Policies or add new Resources to an API proxy, ensure that you save the changes and then explicitly deploy the proxy for the latest changes to reflect during API Proxy execution in the runtime.

-   If an API proxy \(that is already part of a published Product and is being consumed via an Application\) is changed and those changes are saved and not deployed, then the application runtime doesn't reflect the saved changes.

    > ### Note:  
    > Make sure that the API is deployed before attaching it to a Product. If you try to publish a Product that has an API with saved changes attached to it, the following error message appears: "The API proxy attach to the Product has some changes that aren't deployed yet."
    > 
    > Similarly, if you publish a Product that has multiple APIs attached to it, and few of the APIs have changes that are saved but not deployed, a warning message appears with the lists of APIs that weren't published as the changes weren’t deployed.




## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Choose the API you want to edit.

    The *View API* page is displayed. To edit the various tabs available on this screen, choose *Edit* from the top-right corner of the screen.

4.  Select the appropriate tabs, to edit the API. You can choose from the following, *Overview*, *Proxy Endpoint*, *Target Endpoint*, and *Resources*.


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
    
    Proxy Endpoint
    
    </td>
    <td valign="top">
    
    You can add the proxy endpoint and the route rules.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target EndPoint
    
    </td>
    <td valign="top">
    
    You can choose URL, API Provider, or API proxy, as the target endpoint as well as enter target endpoint rules.

    To define multiple-target endpoints, choose *Add* next to the *Target EndPoint* dropdown menu.

    In the *Add Target EndPoint* dialog, fill in the target endpoint *Name*, select the *API Provider*, where you want the target endpoint to point to, and specify the *Relative URL*, then choose *Add*.

    > ### Note:  
    > If you have an API proxy with a multi-target endpoint, it is recommended that the name of the target endpoint should be between 2 and 255 characters. If you enter a single character in the name field for the provider types OpenConnector or Cloud Integration Flow, the API proxy cannot be deployed to the runtime.

    > ### Note:  
    > Only target endpoints of the type API provider can be added in this dialog.

    Once added, the target endpoint will appear in the *Target EndPoint*dropdown menu. You can also change the type of the target endpoint from API provider to API proxy or URL.

    To add policies to the target endpoint, choose *Policies* from the top-right corner of the page. You can then view the target endpoint flow and the policies applied to it in the *Policy Editor*. To view the policies associated with a different target endpoint, you can navigate back to the *Target EndPoint* tab on the proxy details page. Select the desired target endpoint and return to the *Policy Editor*.

    > ### Note:  
    > If you wish to establish a connection with the Cloud Integration system, you must select an API provider of type *Cloud Integration Flow*. For more information on *Cloud Integration Flow*, see [Creating an API Proxy using SAP Cloud Integration API Provider](creating-an-api-proxy-using-sap-cloud-integration-api-provider-aefbd74.md).
    > 
    > If you want to select an API provider of the type *Open Connector*, please make sure that the tenant has a Key Value Map with the "kvm-map-name" that includes the "instance token" for the Open Connector. If this Key Value Map is not already present, you can use the following sample information to create it:
    > 
    > URL : https://<apiportalbaseurl\>/apiportal/api/1.0/Management.svc/GenericKeyMapEntries
    > 
    > Method : POST
    > 
    > > ### Sample Code:  
    > > ```
    > > {
    > >   "name": "apim.oc.instance.token",
    > >   "scopeId": "<apiProxyName> ",
    > >   "scope": "APIPROXY",
    > >   "isEncrypted": true,
    > >   "genericKeyMapEntryValues": [
    > >     {
    > >       "name": "default",
    > >       "mapName": "apim.oc.instance.token",
    > >       "value": "<instancesecret>",
    > >       "scopeId": ""<apiProxyName>",
    > >       "scope": "APIPROXY"
    > >     }
    > >   ]
    > > }
    > > 
    > > ```
    > 
    > Here, the <apiProxyName\> refers to the name of the API Proxy, and \`default\` is the name of the Target Endpoint. The <instancesecret\> is the secret key associated with the Open Connector instance that you wish to establish a connection with.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Resources
    
    </td>
    <td valign="top">
    
    You can add resources, or change already existing ones.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Revision
    
    </td>
    <td valign="top">
    
    Once an API is created, you can plan subsequent compatible changes to the API by creating a revision.
    
    </td>
    </tr>
    </table>
    
5.  To edit the API in the embedded API designer, you can either choose *Edit* \> *Edit in API Designer* from the top-right corner of the screen, or choose *Edit* \> *Resources*tab, click *\>* to open the API designer.

6.  You can make required changes to the swagger structure in the API designer. For more information on the API designer, see [API Designer](api-designer-51f3ca1.md).

7.  Once you've made the swagger changes, click *Save*. These changes will then be reflected in the various tabs on the Integration Suite.

    > ### Note:  
    > When you’re editing the swagger structure in the API designer, editing the same from the tabs is disabled.

    If the API proxy is already in the deployed state, then saving the changes after editing the API doesn’t deploy the latest changes. Similarly, if the API proxy is already published on the Developer Hub, the save action doesn’t publish the latest changes. In both cases, a message appears on the *View API* page that the changes you've made aren't deployed. For the changes to reflect during API proxy runtime flow, choose *Click to Deploy* and provide your confirmation on the popup window.




<a name="loioa64b952578f84161829439c3ee6e967b__result_nll_gkb_2qb"/>

## Results

The changes you've made to the API are saved and deployed successfully.

**Related Information**  


[Key Components of an API](key-components-of-an-api-19c0654.md "This section introduces you to some of the key components of an API that you need to know before building APIs.")

[Different Methods of Creating an API Proxy](different-methods-of-creating-an-api-proxy-4ac0431.md "An API proxy is the data object that contains all the functionality to be executed when an external user wants to access the backend service.")

[Additional Configurations](additional-configurations-de7285c.md " ")

