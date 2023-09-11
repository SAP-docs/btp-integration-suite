<!-- loio1cbd94c86c054d66b3826f6cd91e0df8 -->

# Example: Accessing the Custom Attributes of an Application

Let’s say as a Developer Portal Administrator, you would want to restrict the number of calls to an application based on Application Key. To achieve this result, you create two applications `Application_1` and `Application_2`.

`Application_1` contains two products namely `Prod_1` and `Prod_2`.

`Application_2` contains two products namely `Prod_3` and `Prod_4`.

`Prod_1` and `Prod_2`contain two common APIs namely `API_1` and `API_2`.

For `Application_1`, add the following custom attributes and its corresponding values:

-   app\_time\_unit = minute
-   app\_quota\_interval = 1
-   app\_quota\_count = 9

For `Application_2`, add the following custom attributes and its corresponding values:

-   app\_time\_unit = minute
-   app\_quota\_interval = 1
-   app\_quota\_count = 5

To leverage these custom attributes in your API proxy execution, you must:

-   add a verify API Key policy to the APIs that are part of your application.
-   add a Quota policy to APIs that are part of your application.

For `API_1` and `API_2`, add the following sample policy payloads:

Sample payload for Verify API Key policy:

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
> 	<!-- specifies the number of requests allowed for the API Proxy -->
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

Call the same URL repeatedly and after 9 successive calls, your API proxy must return a Quota violation message.

Similarly, make an API call with `<appKey_2>` passed as a query parameter. For example,`https://<API_proxy_URL>?apikey=<appKey_2>`.

Call the same URL repeatedly and after 6 successive calls, your API proxy must return a Quota violation message.

