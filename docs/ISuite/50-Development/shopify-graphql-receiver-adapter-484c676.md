<!-- loio484c6767291840b3957c9ae3c8341745 -->

# Shopify GraphQL Receiver Adapter

The Shopify adapter facilitates the connectivity to Shopify GraphQL Admin APIs and accelerates the implementation time and reduces the complexity of connecting to Shopify. The GraphQL message protocol is used to connect to the GraphQL-based Admin APIs of a Shopify store.

> ### Note:  
> A new API version is released every three months and is supported for a minimum of 12 months. Older versions are not immediately removed but will no longer receive updates and will ultimately be discontinued.
> 
> > ### Recommendation:  
> > Migrate to a newer version to use the latest features and security updates of the Shopify adapter in your custom integration flows.

Once you've created a receiver channel and selected the *Shopify* receiver adapter, you can configure the following attributes.

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

GraphQL

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
> -   `https://xxxxxx.myshopify.com`



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

Provide the | \(Pipe\) separated value list of HTTP response headers. The received header values are then converted to message/exchange headers.

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

Specifies the version of the Shopify GraphQL API to be used.

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
</table>

