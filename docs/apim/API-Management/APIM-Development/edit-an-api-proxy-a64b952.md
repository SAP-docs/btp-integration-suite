<!-- loioa64b952578f84161829439c3ee6e967b -->

# Edit an API Proxy

Once you’ve created an API proxy you can further change the proxy, either on the API portal, or by using the embedded API designer.



## Context

When you edit an API proxy either on the API portal or using the API designer, ensure that you save and deploy the API proxy once the changes are made. Saving the API proxy is a design time activity, the changes you've made get pushed to the runtime only when you deploy the changes. Therefore, when you choose *Save* after making the changes, the changes are saved locally and don’t get published on the API business hub enterprise. Choose *Deploy* to perform an explicit deployment to bring in the new changes in the runtime during the API proxy execution.

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

1.  Log on to the API portal.

2.  Choose the navigation icon on the left and choose *Develop*.

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
    
    Target Endpoint


    
    </td>
    <td valign="top">
    
    You can choose URL, API Provider, or API proxy, as the target endpoint as well as enter target endpoint rules.


    
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

7.  Once you've made the swagger changes, click *Save*. These changes will then be reflected in the various tabs on the API portal.

    > ### Note:  
    > When you’re editing the swagger structure in the API designer, editing the same from the tabs is disabled.

    If the API proxy is already in the deployed state, then saving the changes after editing the API doesn’t deploy the latest changes. Similarly, if the API proxy is already published on the API business hub enterprise, the save action doesn’t publish the latest changes. In both cases, a message appears on the *View API* page that the changes you've made aren't deployed. For the changes to reflect during API proxy runtime flow, choose *Click to Deploy* and provide your confirmation on the popup window.




<a name="loioa64b952578f84161829439c3ee6e967b__result_nll_gkb_2qb"/>

## Results

The changes you've made to the API are saved and deployed successfully.

