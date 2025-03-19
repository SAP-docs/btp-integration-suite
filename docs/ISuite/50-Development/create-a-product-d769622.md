<!-- loiod7696221f36947a481b154335b89010d -->

# Create a Product

Explains how to create products to publish a bundle of API proxies together.

You create a product when you want to expose one or more API proxies to the Application Developer.



## Prerequisites

-   You have the *APIPortal.Administrator* role assigned to you. For more information, see [User Roles in API Management](https://help.sap.com/docs/integration-suite/sap-integration-suite/assign-user-roles-in-api-management?version=CLOUD).

-   You’ve created the required API proxy on the *APIs* tab. For more information about how to create API proxies, see [Different Methods of Creating an API Proxy](different-methods-of-creating-an-api-proxy-4ac0431.md).




## Procedure

1.  Log on to SAP Integration Suite .

2.  Choose the navigation icon on the left and choose *Engage*.
3.  Go to the *Products* tab.

    A list of published products appears.

    You can view the number of calls made for all APIs in a product for the current month. The data is visible for each product in the *Calls* column and also on the details screen of the individual product.

    You can click the refresh icon to get the latest data.

    > ### Note:  
    > -   There may be a short delay before the data is refreshed.
    > -   Number of calls won’t be displayed for externally managed APIs.
    > 
    > .

    The data is displayed according to metric specifications, for example:

    -   999 shows as 999 and 1000 shows as 1K
    -   999000 shows as 999K and 1000000 shows as 1M
    -   1500000 shows as 1.5M and 1000000000 shows as 1G

4.  To create a product, choose *Create*.
5.  For the product, enter a *Name* and *Title*, provide an introductory text in the *Short Text* field, and a brief description in the *Description* field.

    > ### Note:  
    > If you publish a product with a short introductory text, the short text appears on the corresponding Developer Hub pages. It appears on the product tiles on the Developer Hub landing page, and on the product details page. It also appears on the search result page for the searched products.
    > 
    > If you leave the short text field empty, the product description is displayed instead of the short text in the product tile.

6.  Specify the quota limits for this product.

    > ### Note:  
    > To enforce a quota on products, you must define verify API key and quota policies on the API. Setting quota limits on a product doesn’t automatically enforce a quota on the API proxies. The quota set on the product takes precedence over that of the API proxy. It’s a default limit that is referenced in quota policies that stipulate a uniform setting across all API proxies in the product. You can make runtime changes to the quota setting on an API product, and quota policies that reference the value automatically are updated with the new quota. For more information, see [Quota](quota-1f742c1.md).

    You can use the sample payload given below to set **Verify API Key policy** for the required API:

    > ### Sample Code:  
    > ```
    > <!--Specify in the APIKey element where to look for the variable containing the api key--> 
    > <VerifyAPIKey async='true' continueOnError='false' enabled='true' 
    > xmlns='http://www.sap.com/apimgmt'>
    >                 <APIKey ref='request.header.apikey'/>
    > </VerifyAPIKey>
    > 
    > 
    > ```

    You can use the sample payload below on the same API to create **Quota policy**:

    > ### Sample Code:  
    > ```
    > <!-- can be used to configure the number of request messages that an app is allowed to submit to an API over a course of unit time -->
    > <Quota async="false" continueOnError="false" enabled="true" type="calendar" xmlns="http://www.sap.com/apimgmt">
    >     <Identifier ref='verifyapikey.vap1.client_id'/>
    >                 <!-- specifies the number of requests allowed for the API Proxy -->
    >                                <Allow countRef="verifyapikey.vap1.apiproduct.developer.quota.limit" count="100"/>
    >                <!-- the interval of time for which the quota should be applied -->
    >                <Interval ref="verifyapikey.vap1.apiproduct.developer.quota.interval">1</Interval>
    >                
    >                 <!-- used to specify if a central counter should be maintained and continuously synchronized across all message processors --> 
    >                 <Distributed>true</Distributed>
    >                <!-- Use to specify the date and time when the quota counter will begin counting, 
    >                                 regardless of whether any requests have been received from any apps -->
    >                <StartTime>2015-11-11 12:00:00</StartTime>
    >                 <!-- if set to true, the distributed quota counter is updated synchronously. This means that
    >                                 the update to the counter will be made at the same time the API call is quota-checked -->
    >                 <Synchronous>true</Synchronous>
    >                <!-- Use to specify the unit of time applicable to the quota. Can be second, minute, hour, day, or month -->
    >                <TimeUnit ref="verifyapikey.vap1.apiproduct.developer.quota.timeunit">month</TimeUnit>
    >                
    > </Quota>
    > 
    > ```

    You’ll notice that the same API key is used in the quota policy. You can now update the policy.

7.  To set the scope at product level to restrict the access of the authorization token for each application, specify the scope in the *Scope* field. For example, you can set the scope as Read-only, Read-write, and so on.

    The OAuth 2.0 policy provides a way to limit the amount of access that is granted to an access token. For example, an access token issued to a client app may be granted READ and WRITE access to protected resources, or just READ access. You can implement your APIs to enforce any scope or combination of scopes you wish. So, if a client receives a token that has READ scope, and it tries to call an API endpoint that requires WRITE access, the call will fail.

    The maximum character limit for specifying scopes is 4K characters. Each product can have zero or multiple scopes assigned, as long as the total length of all the scopes does not exceed 4K characters. These scopes can be assigned when the product is created or later. Scopes exist as a list of names and are included in the metadata associated with each product.

8.  In the *APIs* section, choose *Add*.
9.  In the *Add APIs* window, select the required APIs and the corresponding resources.

    > ### Note:  
    > If you try to publish an API product that includes API proxies with over 100 resources, the product's publishing might not succeed. For more information, see [Limits in API Management](../limits-in-api-management-f70f425.md).

    > ### Note:  
    > While selecting APIs and its resources for product creation, the following behaviours apply when API calls are made to the selected API proxies and resources:
    > 
    > -   Product creation in API Management provides precedence for product to path \(resource\) mapping over product to API mapping. Let’s understand this behavior with an example:
    > 
    >     Let’s say you want to create a product `P1` that consists of 2 APIs namely `API_1` and `API_2`.
    > 
    >     `API_1` contains resources namely `R1` and `R2`. Whereas, `API_2` contains resources namely `R2` and `R3`. That is `API_1=R1,R2` and `API_2=R2,R3`
    > 
    >     As you can see, `R2` is a common resource that exists in both the APIs.
    > 
    >     Now, for your product creation, let’s say you select resources `R1`, `R2` of `API_1` and resource `R3` of `API_2`. Thus, your product consists of resources `R1` and `R2` from `API_1` and `R3` from `API_2`. That is `P1=R1,R2,R3`.
    > 
    >     With the above resource selection criteria, API Management still allows API calls to be made to the resource `R2` of `API_2` even though you had not explicitly selected the resource under `API_2` during product creation.
    > 
    > -   If you want to publish a product with selective resource paths from multiple API proxies, you must ensure that the API proxies should have a common resource path.
    > 
    >     Consider the following example: You are trying to publish Product P1, with API proxy A1 having a resource path R1 and R2 and another API proxy A2. You must ensure that the API proxy A2 should have a common resource path as API proxy A1, which can be either R1 or R2.
    > 
    > -   API Management doesn’t support API calls to those resources whose path starts with a `/$` character. That is, if you create a product by attaching individual resources, then API calls to those resources whose path starts with `/$<resource_name>` don’t work. However, when you attach the whole API and none of its resources to a product, then API calls made to those resources of the selected API still works irrespective of whether the path starts with `/$` character or not.

    > ### Note:  
    > -   If you attempt to add a resource to a product from an API that has not been deployed, the same resource will not be published.
    > 
    > -   When publishing products, it's important to note that resources are available from the deployed API, rather than from the latest revision or draft of the API. Additionally, if a deployed resource is not available in the latest revision, you won't be able to attach that resource to the product.

    > ### Note:  
    > Select at least one API to publish a product.

    > ### Note:  
    > Make sure that the API is deployed before attaching it to a product. If you try to publish a product that has an API with saved changes attached to it, the following error message appears: "The API proxy attach to the product has some changes that aren't deployed yet."
    > 
    > Similarly, if the product has multiple API proxies attached to it, and few of the API proxies have changes that are saved but not deployed, you'll receive the following message when you try to publish the product: "The following API proxies attached to the product weren't published as they have changes that aren’t yet deployed:"

10. Choose *OK*.

    The selected API proxies are listed on the *APIs* tab.

11. Provide permissions to user roles to either discover or subscribe to the product.
12. In the *Rate plans* section, choose *Add*.
13. In the *Add Rate Plan* window, select the rate plans that you want to add to this product and choose *OK*.
14. \(Optional\) In the *Custom Attribute* section, specify the custom attributes you want to add to the product.

    A custom attribute is a name/value pair, which can be used in multiple ways, including influencing the runtime behavior of an API proxy. Custom attributes provide the flexibility to extend the functionality based on attribute value, which can be set or read during the API proxy execution flow. These attributes can be accessed during an API call via the following policies: Verify API key, Access token, and Access entity.

    > ### Note:  
    > You can add a maximum of 18 custom attributes.

    For example, you can create a custom attribute named `IsConfidential` with a value of Yes or No. Later, in your API proxy flow, you can check the value of the API product’s `IsConfidential` attribute \(for example, using the `verifyapikey.<policy_name>.apiproduct.IsConfidential` variable, which would be available automatically after you have created the custom attribute\). If the value is `Yes`, you can throw an error, for example as shown below using the Raise Fault policy.

    > ### Sample Code:  
    > ```
    > Warning: You do not have relevant authorizations to access the information.
    > ```

    > ### Note:  
    > The `verifyapikey.<policy_name>.apiproduct.IsConfidential` would be available only if the Verify API Key policy in your API proxy is executed successfully.

    You can use the following sample payload to set Verify API Key policy for the required API:

    > ### Sample Code:  
    > ```
    > <!--Specify in the APIKey element where to look for the variable containing the api key--> 
    > <VerifyAPIKey async='true' continueOnError='false' enabled='true' 
    > xmlns='http://www.sap.com/apimgmt'>
    > 	<APIKey ref='request.queryparam.apikey '/>
    > </VerifyAPIKey>
    > 
    > ```

    You can use the following condition and sample payload to set the Raise Fault policy:

    > ### Sample Code:  
    > ```
    > verifyapikey.Verify-API-Key.apiproduct.IsConfidential=True
    > ```

    > ### Sample Code:  
    > ```
    > <!-- can be used to create custom messages in case of an error condition -->
    > <RaiseFault async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
    > 	<!-- Defines the response message returned to the requesting client -->
    > 	<FaultResponse>
    > 		<Set>
    > 			<!-- Sets or overwrites HTTP headers in the respone message -->
    > 			<Headers/>
    > 			<Payload contentType="text/plain"> Warning: You do not have relevant authorizations to access the information.
    > </Payload> <StatusCode>500</StatusCode>
    > 			<!-- sets the reason phrase of the response -->
    > 			<ReasonPhrase>Server Error</ReasonPhrase>
    > 		</Set>
    > 	</FaultResponse>
    > 	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
    > </RaiseFault>
    > 
    > ```

    > ### Remember:  
    > -   You can add externally managed APIs to a product but will not be able to add rate plans or add custom attributes for them.
    > -   If your product contains only externally managed APIs, the user will not be able to subscribe to the the product.

15. Once you have filled in all the required details for the product, you can choose one of the following two actions:
    -   *Save as Draft* - The resulting state of the product is Draft, and you can publish the product anytime. The product cannot be used for creating applications when it is in the Draft state.

    -   *Publish* - The resulting state of the product is Published, and is available for creating applications. You can edit the published product anytime.

        > ### Note:  
        > When you’re selectively publishing the resources of an API proxy associated with a product, please make sure that the API resources shouldn’t contain any special characters. For example, you can use “/Employee” and not “/Employee\('\{test\}'\)” as it contains special characters.


16. If you want to delete a product, select the required product from the catalog and choose *Delete*. if it is being used in an application.
17. If you want to edit a product, select the required product, in the details view select *Edit*.

    > ### Note:  
    > Alternatively, you can use the following service to update the product:
    > 
    > > ### Sample Code:  
    > > sample payload to update a product
    > > 
    > > ```
    > > --batch_1ddf-343f-3338
    > > Content-Type: multipart/mixed; boundary=changeset_418f-1c1d-b76b
    > > 
    > > --changeset_418f-1c1d-b76b
    > > Content-Type: application/http
    > > Content-Transfer-Encoding: binary
    > > 
    > > PUT APIProducts(name='<Product_Name>') HTTP/1.1
    > > x-csrf-token: E2BE219B16E5608F21EE5A7765E1318C
    > > Accept-Language: en-US
    > > Accept: application/json
    > > MaxDataServiceVersion: 2.0
    > > DataServiceVersion: 2.0
    > > Content-Type: application/json
    > > Content-Length: <Length of below payload>
    > > 
    > > {"name":"<Product_Name>","title":"<Product_Title>","scope":"","description":"<Product_Description>","version":"1","status_code":"PUBLISHED","isRestricted":<true or false>,"isPublished":true,"quotaCount":-99,"quotaInterval":-99,"quotaTimeUnit":null}
    > > --changeset_418f-1c1d-b76b--
    > > 
    > > --batch_1ddf-343f-3338--
    > > ```


