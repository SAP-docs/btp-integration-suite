<!-- loio3dbf284ae5d54f59b7b9cc8f97d41fed -->

# BigCommerce Receiver GraphQL Adapter

The BigCommerce \(GraphQL\) receiver adapter connects an SAP Integration Suite tenant to BigCommerce GraphQL Admin APIs using the GraphQL message protocol. The GraphQL message protocol is used to connect to the GraphQL-based Admin APIs of a BigCommerce store.

Once you've created a receiver channel and selected the *BigCommerce* receiver adapter, you can configure the following attributes.

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

Enter the name of the BigCommerce adapter

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

BigCommerce

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

*BigCommerce Base URL* 

</td>
<td valign="top">

Enter the Base URL of your BigCommerce store.

> ### Example:  
> -   `https://api.bigcommerce.com/stores/xxxxxx`



</td>
</tr>
<tr>
<td valign="top">

*BigCommerce Secure Parameter* 

</td>
<td valign="top">

Enter the alias name of the deployed Secure Parameter artifact that contains the access token needed to connect to BigCommerce.

</td>
</tr>
<tr>
<td valign="top">

*BigCommerce Secure Bearer Token* 

</td>
<td valign="top">

Enter the alias name of the deployed Secure Parameter artifact that contains the bearer token needed to connect to BigCommerce

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

Provide the `| (Pipe)` separated value list of HTTP response headers. The received header values are then converted to message/exchange headers.

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

*Payload Format* 

</td>
<td valign="top">

Specifies the response payload format. The following are the supported payload formats:

-   Application/JSON
-   Application/XML



</td>
</tr>
</table>

