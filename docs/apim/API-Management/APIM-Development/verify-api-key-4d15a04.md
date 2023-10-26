<!-- loio4d15a0427494452dbb42a319e9bb420f -->

# Verify API Key

One of the mechanisms to prevent unauthorized access to APIs exposed over the internet is to use the verify API key policy.

The verify API key policy enforces verification of the application key in order to access your APIs.

API Management automatically generates API keys on behalf of applications. It enables API providers to view and approve API keys. By applying a policy of the type VerifyApiKey, you can enforce verification of API keys at runtime. This ensures that no application can access a protected API without a valid key.

The only setting required for the VerifyAPIKey is the expected location of the API key. This policy can be attached to request or response stream of the proxy endpoint or target endpoint.

The schema for the Verify API Key policy is as follows:

> ### Note:  
> The below schema is not a working sample payload.

> ### Code Syntax:  
> ```
> <!-- The policy will prevent unauthorized users from call the api, only users with valid app key will be able to access API. The policy expects the api key to be sent as query param with name "key"-->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <VerifyAPIKey async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <APIKey ref="request.queryparam.key"></APIKey>
> </VerifyAPIKey>
> 
> ```


<table>
<tr>
<th valign="top">

**Elements & Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

APIKey\(Mandatory\)

</td>
<td valign="top">

The variable where the API key can be found.

The API key is extracted from the request message by reference to a Flow variable. For example:

`<APIKey ref="request.queryparam.apikey "/>`

If an application is expected to present the API key as the value of an HTTP header named APIKey, then set this value to request.header.APIKey.

</td>
</tr>
</table>

The policy populates several different types of flow variables, including:

-   General

-   App

-   Developer

-   Analytics


The following table lists the general flow variables populated by the Verify API Key policy.

These variables are all prefixed by: `verifyapikey.{policy_name}`

For example: `verifyapikey.{policy_name}.client_id`

**General Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

client\_id

</td>
<td valign="top">

The consumer key \(aka API key or app key\) supplied by the requesting app

</td>
</tr>
<tr>
<td valign="top">

client\_secret

</td>
<td valign="top">

The consumer secret associated with the consumer key

</td>
</tr>
<tr>
<td valign="top">

redirection\_uris

</td>
<td valign="top">

Any redirect URIs in the request

</td>
</tr>
<tr>
<td valign="top">

developer.app.id

</td>
<td valign="top">

The ID of the developer app making the request

</td>
</tr>
<tr>
<td valign="top">

developer.app.name

</td>
<td valign="top">

The app name of the developer app making the request

</td>
</tr>
<tr>
<td valign="top">

developer.id

</td>
<td valign="top">

The ID of the developer registered as the owner of the requesting app

</td>
</tr>
<tr>
<td valign="top">

DisplayName

</td>
<td valign="top">

The value of the policy's <DisplayName\> attribute

</td>
</tr>
<tr>
<td valign="top">

failed

</td>
<td valign="top">

Set to "true" when API Key validation fails.

</td>
</tr>
<tr>
<td valign="top">

apiproduct.name\*

</td>
<td valign="top">

The name of the API product used to validate the request

</td>
</tr>
<tr>
<td valign="top">

apiproduct.developer.quota.limit\*

</td>
<td valign="top">

The quota limit set on the API product, if any

</td>
</tr>
<tr>
<td valign="top">

apiproduct.developer.quota.interval\*

</td>
<td valign="top">

The quota interval set on the API product, if any

</td>
</tr>
<tr>
<td valign="top">

apiproduct.developer.quota.timeunit\*

</td>
<td valign="top">

The quota time unit set on the API product, if any

</td>
</tr>
</table>

> ### Note:  
> \* API product variables are populated automatically if the API products are configured with valid environment, proxies, and resources \(derived from the proxy.pathsuffix\).

The following flow variables containing information about the app are populated by the policy.

These variables are all prefixed by: `verifyapikey.{policy_name}.app.`

For example: `verifyapikey.{policy_name}.app.name`

**App Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

name

</td>
<td valign="top">

The name of the app

</td>
</tr>
<tr>
<td valign="top">

id

</td>
<td valign="top">

The ID of the app

</td>
</tr>
<tr>
<td valign="top">

accessType

</td>
<td valign="top">

Unused by API Management

</td>
</tr>
<tr>
<td valign="top">

callbackUrl

</td>
<td valign="top">

The callback URL of the app, typically used only for OAuth

</td>
</tr>
<tr>
<td valign="top">

DisplayName

</td>
<td valign="top">

The app's display name

</td>
</tr>
<tr>
<td valign="top">

status

</td>
<td valign="top">

The app status, such as 'approved' or 'revoked'

</td>
</tr>
<tr>
<td valign="top">

apiproducts

</td>
<td valign="top">

An array containing the list of API products associated with the app

</td>
</tr>
<tr>
<td valign="top">

appType

</td>
<td valign="top">

The app type is "Developer"

</td>
</tr>
<tr>
<td valign="top">

created\_at

</td>
<td valign="top">

The date/time stamp when the app was created

</td>
</tr>
<tr>
<td valign="top">

created\_by

</td>
<td valign="top">

The e-mail address of the developer who created the app

</td>
</tr>
<tr>
<td valign="top">

last\_modified\_at

</td>
<td valign="top">

The date/time stamp when the app was last updated

</td>
</tr>
<tr>
<td valign="top">

last\_modified\_by

</td>
<td valign="top">

The e-mail address of the developer who last updated the app

</td>
</tr>
</table>

The following flow variables containing information about the developer are populated by the policy.

These variables are all prefixed by: `verifyapikey.{policy_name}.developer.`

For example: `verifyapikey.{policy_name}.developer.id`

**Developer Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

userName

</td>
<td valign="top">

The developer's user name

</td>
</tr>
<tr>
<td valign="top">

id

</td>
<td valign="top">

Returns \{org\_name\}@@@\{developer\_id\}

</td>
</tr>
<tr>
<td valign="top">

firstName

</td>
<td valign="top">

The developer's first name

</td>
</tr>
<tr>
<td valign="top">

lastName

</td>
<td valign="top">

The developer's last name

</td>
</tr>
<tr>
<td valign="top">

e-mail

</td>
<td valign="top">

The developer's e-mail address

</td>
</tr>
<tr>
<td valign="top">

status

</td>
<td valign="top">

The developer's status, as active, inactive, or login\_lock

</td>
</tr>
<tr>
<td valign="top">

apps

</td>
<td valign="top">

An array of apps associated with the developer

</td>
</tr>
<tr>
<td valign="top">

created\_at

</td>
<td valign="top">

The date/time stamp when the developer was created

</td>
</tr>
<tr>
<td valign="top">

created\_by

</td>
<td valign="top">

The e-mail address of the user who created the developer

</td>
</tr>
<tr>
<td valign="top">

last\_modified\_at

</td>
<td valign="top">

The date/time stamp when the developer was last modified

</td>
</tr>
<tr>
<td valign="top">

last\_modified\_by

</td>
<td valign="top">

The e-mail address of the user who modified the developer

</td>
</tr>
</table>

The following variables are automatically populated in Analytics when a Verify API Key policy is enforced for a valid API key.

-   apiproduct.name
-   developer.app.name
-   client\_id
-   developer.id

During the policy execution, the following errors can occur:

**Error Code**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

HTTP Status

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

DeveloperStatusNotActive

</td>
<td valign="top">

401

</td>
<td valign="top">

The developer who created the Developer App that has the API key you are using has an inactive status. When an App Developer's status is set to inactive, any Developer Apps created by that developer are deactivated.

</td>
</tr>
<tr>
<td valign="top">

FailedToResolveAPIKey

</td>
<td valign="top">

401

</td>
<td valign="top">

The policy expects to find the API key in a variable that is specified in the policy's <APIKey\> element. This error arises when the expected variable does not exist.

</td>
</tr>
<tr>
<td valign="top">

InvalidApiKey

</td>
<td valign="top">

401

</td>
<td valign="top">

An API key was received by API Management, but it is invalid. When API Management looks up the key in its database, it must exactly match the one that was sent in the request. If the API worked previously, make sure the key was not regenerated. If the key was regenerated, you will see this error if you try to use the old key.

</td>
</tr>
<tr>
<td valign="top">

InvalidApiKeyForGivenResource

</td>
<td valign="top">

401

</td>
<td valign="top">

An API key was received by API Management, and it is valid; however, it does not match an approved key in the Developer App associated with your API proxy through a Product.

</td>
</tr>
<tr>
<td valign="top">

invalid\_client-app\_not\_approved

</td>
<td valign="top">

401

</td>
<td valign="top">

The Developer App associated with the API key is revoked.

</td>
</tr>
</table>

Following errors can occur when you deploy a proxy containing this policy:

**Deployment errors**


<table>
<tr>
<th valign="top">

Error name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

SpecifyValueOrRefApiKey

</td>
<td valign="top">

The APIKey element does not have a value or key specified.

</td>
</tr>
</table>

Following fault variables is set when the policy triggers an error at runtime:

**Fault Variables**


<table>
<tr>
<th valign="top">

Variable Set

</th>
<th valign="top">

Where

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

\[prefix\].\[policy\_name\].failed

</td>
<td valign="top">

The fault variable \[prefix\] is oauthV2.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

oauthV2.VK-VerifyAPIKey.failed = true

</td>
</tr>
<tr>
<td valign="top">

fault.\[error\_name\]

</td>
<td valign="top">

\[error\_name\] = The specific error name to check for as listed in the table above.

</td>
<td valign="top">

fault.name Matches "FailedToResolveAPIKey"

</td>
</tr>
</table>

Following is an example of an error response:

> ### Sample Code:  
> ```
> {  
>    "fault":{  
>       "faultstring":"Invalid ApiKey",
>       "detail":{  
>          "errorcode":"oauth.v2.InvalidApiKey"
>       }
>    }
> }
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> ```
> <FaultRule name="FailedToResolveAPIKey">
>     <Step>
>         <Name>AM-FailedToResolveAPIKey</Name>
>     </Step>
>     <Condition>(fault.name Matches "FailedToResolveAPIKey") </Condition>
> </FaultRule>
> ```

