<!-- loiof36aab9b289a4d5b8d835ad100ed812a -->

# BigCommerce Receiver REST Adapter

The BigCommerce \(REST\) receiver adapter connects an SAP Integration Suite tenant to BigCommerce REST Admin APIs using the REST message protocol.

The REST message protocol is used to connect to the REST-based Admin APIs of a BigCommerce store.

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

*BigCommerce Base URL*

</td>
<td valign="top">

Enter the Base URL of your BigCommerce store.

> ### Example:  
> `https://api.bigcommerce.com/stores/xxxxxx`



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

Specifies the version of the BigCommerce REST API to be used

</td>
</tr>
<tr>
<td valign="top">

*Response Payload Format*

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

Specifies the BigCommerce Resource. The following are the supported resources:

-   Order
-   Customer
-   Inventory
-   Product
-   Promotion



</td>
</tr>
<tr>
<td valign="top">

*Operations*

</td>
<td valign="top">

Specifies the operation group for the currently selected*Resource*.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specifies an operation for the currently selected *Resource & Operations*group. Operations are the actions which can be performed with a certain *Resource*.

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

*Query Parameters*

</td>
<td valign="top">

Specifies an operation for currently selected *Resource*. The *Query Parameters* are individual for each *Resource* and *Operation*. They can also be used for filtering the response results.

</td>
</tr>
</table>

