<!-- loio1cbd94c86c054d66b3826f6cd91e0df8 -->

# Using Custom Attributes in Product Subscriptions

Custom attributes allow you to associate additional metadata with a product subscription in Developer Hub. These attributes are exposed during API execution after the API key is successfully verified, enabling API policies to retrieve and use their values at runtime.

> ### Note:  
> Only applicable for API proxies deployed on Classic API Management runtime.

**Pre-requisite**: Make sure you have the *AuthGroup.API.Admin* role collection assigned to you.

You can use subscription custom attributes to implement dynamic API behavior without creating separate API proxies or policy configurations for different applications. For example, you can define application-specific quota limits, rate-limiting parameters, backend routing information, feature flags, or other configuration values as custom attributes and reference them in API policies.

To use subscription custom attributes at runtime:

1.  Define the required custom attributes when creating or updating a product subscription.
2.  Add a **Verify API Key** policy to the API to validate the API key and expose the subscription attributes as flow variables.
3.  Reference the exposed variables in **Quota** policy to apply application-specific behavior.



## Example: Using Subscription Custom Attributes to Configure Dynamic Quotas

This example demonstrates how to use subscription custom attributes to configure different quota limits for different applications. The quota values are stored as custom attributes in each subscription. During API execution, the **Verify API Key** policy retrieves these values, and the **Quota** policy uses them to enforce the corresponding rate limits.

Consider a scenario where a Developer Hub administrator, wants to restrict the number of calls to an application based on key. but require different quota limits. To achieve this result, you create two subscriptions for applications `subscription_1` and `subscription_2`.

-   `subscription_1` contains two products namely `Prod_1` and `Prod_2`.

    `Prod_1` and `Prod_2`contain two common APIs namely `API_1` and `API_2`.

    For `subscription_1`, add the following custom attributes and its corresponding values:

    -   app\_time\_unit = minute
    -   app\_quota\_interval = 1
    -   app\_quota\_count = 9

-   `subscription_2` contains two products namely `Prod_3` and `Prod_4`.

    For `subscription_2`, add the following custom attributes and its corresponding values:

    -   app\_time\_unit = minute
    -   app\_quota\_interval = 1
    -   app\_quota\_count = 5


To leverage these custom attributes in your API execution, you must:

-   Add a verify API Key policy to the APIs that are part of your application.
-   Add a Quota policy to APIs that are part of your application.

For `API_1` and `API_2`, add the following sample policy payloads:

Sample payload for *Verify API Key* policy:

> ### Sample Code:  
> ```
>  <!--Specify in the APIKey element where to look for the variable containing the api key--> 
> <VerifyAPIKey async='true' continueOnError='false' enabled='true' 
> xmlns='http://www.sap.com/apimgmt'>
> 	<APIKey ref='request.queryparam.apikey'/>
> </VerifyAPIKey>
> ```

Sample payload for Quota policy:

> ### Sample Code:  
> ```
> <!-- can be used to configure the number of request messages that an app is allowed to submit to an API over a course of unit time -->
> <Quota async="false" continueOnError="false" enabled="true" type="calendar" xmlns="http://www.sap.com/apimgmt">
> 	<Identifier ref="verifyapikey.Verify-api-key.developer.id"/>
> 	<!-- specifies the number of requests allowed for the API -->
> 		<Allow countRef="verifyapikey.Verify-api-key.app_quota_count"/>
> 	<!-- the interval of time for which the quota should be applied -->
> 	<Interval ref="verifyapikey.Verify-api-key.app_quota_interval"/>
> 	
> 	<!-- used to specify if a central counter should be maintained and continuously synchronized across all message processors --> 
> 	<Distributed>true</Distributed>
> 	<!-- Use to specify the date and time when the quota counter will begin counting, 
> 		regardless of whether any requests have been received from any apps -->
> 	<StartTime>2015-2-11 12:00:00</StartTime>
> 	<!-- if set to true, the distributed quota counter is updated synchronously. This means that
> 		the update to the counter will be made at the same time the API call is quota-checked -->
> 	<Synchronous>true</Synchronous>
> 	<!-- Use to specify the unit of time applicable to the quota. Can be second, minute, hour, day, or month -->
> 	<TimeUnit ref="verifyapikey.Verify-api-key.app_time_unit"/>
> 
> </Quota>
> 
> ```

> ### Note:  
> The attribute names `app_quota_interval`, `app_quota_count`, and `app_time_unit` must be the same attributes that you have added while creating the application.

To verify if the custom attributes are used in runtime, make an API call with `<appKey_1>` passed as a query parameter. For example, `https://<API_proxy_URL>?apikey=<appKey_1>`.

Call the same URL repeatedly and after 9 successive calls, your API must return a Quota violation message.

Similarly, make an API call with `<appKey_2>` passed as a query parameter. For example,`https://<API_proxy_URL>?apikey=<appKey_2>`.

Call the same URL repeatedly and after 6 successive calls, your API must return a Quota violation message.

