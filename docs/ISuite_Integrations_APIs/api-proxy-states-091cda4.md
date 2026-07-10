<!-- loio091cda4bc3d3402aa5a8663b8d1541f6 -->

# API Proxy States

As an API Management administrator, you can set states for an API proxy while creating or updating the API proxy.



The following states can be set for an API proxy:


<table>
<tr>
<th valign="top">

State

</th>
<th valign="top">

Information

</th>
</tr>
<tr>
<td valign="top">

`Alpha`

</td>
<td valign="top">

A version of an API meant for exploratory purposes.

</td>
</tr>
<tr>
<td valign="top">

`Beta`

</td>
<td valign="top">

A version of an API that isn't meant for productive use.

</td>
</tr>
<tr>
<td valign="top">

`Active`

</td>
<td valign="top">

A version of an API that is meant for productive use.

</td>
</tr>
<tr>
<td valign="top">

`Deprecated`

</td>
<td valign="top">

When an API is marked as deprecated, the customer is encouraged to use a successor API.

</td>
</tr>
<tr>
<td valign="top">

`Decommissioned`

</td>
<td valign="top">

A version of an API where the service is no longer available, and can't be used productively.

</td>
</tr>
</table>



When you deprecate or decommission an API proxy, you must provide a deprecation or decommissioning date, as well as a successor API. This could be another API within the Integration Suite or an external link. You can only mark an API proxy as `Deprecated` or `Decommissioned` while updating the proxy and not while creating it.

The API state is to be used only for demarcation, and doesn’t play a role in the governance or lifecycle of the API.

> ### Note:  
> An application developer can view the states of the deprecated and decommissioned API proxies \(if published in the Integration Suite\) in the API details screen of the Developer Hub.

