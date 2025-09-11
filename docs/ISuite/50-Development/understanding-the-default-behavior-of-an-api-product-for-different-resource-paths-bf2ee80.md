<!-- loiobf2ee804fd424da6b51e2f8a792e3fcf -->

# Understanding the Default Behavior of an API Product for Different Resource Paths

This topic outlines the default behavior of an API product for different resource paths. For instance, if the API proxy has a base path of `/v1/catalogservice`, the API product resource path applies to the path suffix after the base path.

`/v1/catalogservice` serves as the base path for the API proxy. Any path segments following this base path represent individual resources that are selectively published within the API product.

The following table describes the default behavior of an API product for different resource paths:

> ### Note:  
> The behaviors listed below are observed only when using selective publishing. There are no restrictions when the entire API is published.


<table>
<tr>
<th valign="top">

Request URI

</th>
<th valign="top">

Behavior

</th>
</tr>
<tr>
<td valign="top">

`/v1/catalogservice/` 

</td>
<td valign="top">

Allows all requests

</td>
</tr>
<tr>
<td valign="top">

`/v1/catalogservice/1` 

</td>
<td valign="top">

Allows all the subpaths for resource "**1**"

</td>
</tr>
<tr>
<td valign="top">

`/v1/catalogservice/1/` 

</td>
<td valign="top">

-   Allows all the subpaths after resource "**`1/`**"
-   Not allowed for subpath **`/catalogservice/1/`**
-   Not allowed for subpath **`/catalogservice/1(KeyValue)/`**



</td>
</tr>
</table>

