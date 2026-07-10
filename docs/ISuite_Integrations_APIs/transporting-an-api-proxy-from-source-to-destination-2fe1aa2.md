<!-- loio2fe1aa277c5a460787ed6b9c9e1cb264 -->

# Transporting an API Proxy from Source to Destination

When transport is triggered for an API proxy, all artifacts of the API proxy get transported along with the API.



<a name="loio2fe1aa277c5a460787ed6b9c9e1cb264__context_eyj_2wq_1pb"/>

## Context

API proxies always get imported to the destination API portal in the deployed state.

> ### Note:  
> If the API proxy and its artifacts already exist in the destination, only the API proxy gets overwritten during transport. All other artifacts of the API proxy, such as API provider, Key Store Certificate, Trust Store, and Key-Value Maps remain unaffected.

> ### Note:  
> When you transport an API, a new revision of the API is created. If your API has an existing draft, the draft gets replaced by the new revision created during the transport.
> 
> If there are multiple revisions of an API, only the latest revision gets transported.

> ### Note:  
> Consider the following use case for transporting API proxies associated with multiple target endpoints:
> 
> -   Case 1- Multiple target endpoints in target endpoint XML
> 
>     This customization in the API proxy is achieved by exporting the proxy zip and modifying the target endpoint XML. In such scenarios, when the proxy is transported, the related API providers are automatically created in the target, followed by proxy creation.
> 
> -   Case 2- API provider is referenced in some policy of the API proxy
> 
>     The above use case is not supported for transport. In such cases, the provider referred to in the policy must be transported first, followed by the API proxy transport.
> 
> 
> In exceptional cases where a proxy with identical Name and Base path is present in both the source and target, but one of them is a versioned API while the other is not versioned, the transfer to the target will fail because conversion between the two is not permitted.



<a name="loio2fe1aa277c5a460787ed6b9c9e1cb264__steps_cnz_rqq_1pb"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Choose the *API* that you want to transport on the *APIs* tab page.

4.  Choose the *Action* icon against the required API and then select the *Transport* option. Alternatively, you can open the required API and in the details page select the option *Transport*.

5.  On the *Transport* popup, provide a description and choose *Yes*.

    The reference number for the transport request gets generated.

    In the Transport workbench, you can search for this API in the destination node under the *Transport Description*.

6.  Go to the Transport subaccount and perform the following steps to navigate to the *Transport Nodes*.

    1.  In your web browser, log on to SAP BTP Cockpit and navigate to your Transport subaccount.

    2.  Choose *Instances and Subscriptions* from the left pane.

    3.  Go to *Subscriptions* \> *Cloud Transport Management* and choose *Go To Application*.

    4.  Choose *Transport Nodes* from the left pane.


7.  Select the destination node, which points to the destination API portal.

8.  Under the *Transport Description* column of the destination node, search for the API for which you triggered the transport.

9.  Choose *Import Selected* to import the selected API in the queue to the destination node.




<a name="loio2fe1aa277c5a460787ed6b9c9e1cb264__result_srz_n5c_q4b"/>

## Results

The API content from the sourceAPI portal is transported to the destination API portal.



<a name="loio2fe1aa277c5a460787ed6b9c9e1cb264__postreq_h52_dvj_t4b"/>

## Next Steps

Once the API content is transported to the destination API portal, you must ensure that the dummy security values that got imported along with the API entity must be replaced with the actual values. For more information, see [Editing the Security Fields for the Imported API Entities](editing-the-security-fields-for-the-imported-api-entities-0c184e3.md).

