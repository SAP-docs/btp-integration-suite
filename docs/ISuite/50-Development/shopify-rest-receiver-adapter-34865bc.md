<!-- loio34865bc5af5d4996b112d2e3c1c3a0fe -->

# Shopify REST Receiver Adapter

The Shopify adapter facilitates the connectivity to Shopify REST Admin APIs, accelerates the implementation time, and reduces the complexity of connecting to Shopify.

The REST message protocol is used to connect to the REST-based Admin APIs of a Shopify store.

> ### Note:  
> A new API version is released every three months and is supported for a minimum of 12 months. Older versions are not immediately removed but will no longer receive updates and will ultimately be discontinued.
> 
> > ### Recommendation:  
> > Migrate to a newer version to use the latest features and security updates of the Shopify adapter in your custom integration flows.

Once you've created a receiver channel and selected the Shopify receiver adapter, you can configure the following attributes.

Select the *General* tab to access the parameters described in the following table.

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter the name of the Shopify adapter

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type*

</td>
<td valign="top">

Shopify

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol*

</td>
<td valign="top">

HTTPS

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol*

</td>
<td valign="top">

REST

</td>
</tr>
<tr>
<td valign="top">

*Description*

</td>
<td valign="top">

Add useful information to describe the adapter

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as described in the following table.

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Shopify Base URL*

</td>
<td valign="top">

Enter the Base URL of your Shopify store.

> ### Example:  
> `https://xxxxxx.myshopify.com`



</td>
</tr>
<tr>
<td valign="top">

*Shopify Secure Parameter*

</td>
<td valign="top">

Enter the alias name of the deployed Secure Parameter artifact that contains the access token needed to connect to Shopify.

</td>
</tr>
<tr>
<td valign="top">

*Attach Error Details on Failure*

</td>
<td valign="top">

By default, the option is enabled. This option enables the creation of attachments for request headers, response headers, and response body when the message processing fails.

If you do not require attachments for failure scenarios, disable the option.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Provide the `| (Pipe)` separated value list of HTTP response headers. The received header values are then converted to message/exchange headers.

If the value is a wildcard – “\*”, all HTTP response header values are converted to message/exchange headers.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as described in the following table.

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*API Version*

</td>
<td valign="top">

Specifies the version of the Shopify REST API to be used

</td>
</tr>
<tr>
<td valign="top">

*Payload Format*

</td>
<td valign="top">

Specifies the response payload format. The following are the supported payload formats:

-   Application/JSON
-   Application/XML



</td>
</tr>
<tr>
<td valign="top">

*Resource*

</td>
<td valign="top">

Specifies the Shopify Resource. The following are the supported resources:

-   Balance
-   Balance Transactions
-   Collect
-   Collection
-   Custom Collection
-   Customer
-   Discount Code
-   Dispute
-   Dispute Evidence
-   Dispute File Upload
-   Event
-   Inventory Item
-   Inventory Level
-   Location
-   Metafield
-   Order
-   Order Risk
-   Payouts
-   Price Rule
-   Product
-   Product Variants
-   Refund
-   Smart Collection
-   Tender Transaction
-   Transaction



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specify an operation for the currently selected *Resource*. Operations are the actions which can be performed with a certain *Resource*.

</td>
</tr>
<tr>
<td valign="top">

*Resource ID*

</td>
<td valign="top">

Used for retrieving specific instances of a resource by their ID. For example, to retrieve a single customer by its ID.

This parameter is present only for certain operations.

</td>
</tr>
<tr>
<td valign="top">

*Fields*

</td>
<td valign="top">

You can specify which fields you want to only be included in the response payload by listing them and separating them with comma.

> ### Example:  
> `id,subject_id`

If a value for this parameter is not specified, all fields will be returned.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specifies an operation for currently selected *Resource*. The *Query Parameters* are individual for each *Resource* and *Operation*. They can also be used for filtering the response results.

</td>
</tr>
</table>

