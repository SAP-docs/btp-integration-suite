<!-- loio482192514b7c4ec9a15b6ab6ed971e35 -->

# Path Variables

Supported path variables are listed in the Path Variables table.

**Path Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Path

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

Request variables

</td>
<td valign="top">

request.uri

</td>
<td valign="top">

The HTTP request path, which includes a path and a query string separated by a question mark \( ? \)

</td>
</tr>
<tr>
<td valign="top">

request.path

</td>
<td valign="top">

The HTTP request path without the query string

</td>
</tr>
<tr>
<td valign="top">

request.querystring

</td>
<td valign="top">

The portion of the HTTP request path after the question mark \( ? \)

</td>
</tr>
<tr>
<td valign="top">

Application variables

</td>
<td valign="top">

application.basepath

</td>
<td valign="top">

The deployment base path \(specified during API deployment\)

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Proxy variables

</td>
<td valign="top">

proxy.basepath

</td>
<td valign="top">

The base path as configured in the proxy XML file.

</td>
</tr>
<tr>
<td valign="top">

proxy.pathsuffix .

</td>
<td valign="top">

The portion of the request path after the proxy basepath, which is determined by any conditional flow URIs

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Target variables

</td>
<td valign="top">

request.url

</td>
<td valign="top">

The complete URL of the final request made.

</td>
</tr>
<tr>
<td valign="top">

target.basepath

</td>
<td valign="top">

The path \(without host or port\) in the URL configured in the target XML file or the dynamic target URL \(if target.url is set during the message flow\)

</td>
</tr>
<tr>
<td valign="top">

target.url

</td>
<td valign="top">

The URL configured in the target XML file or the dynamic target URL \(if target.url is set during the message flow\). Returns null if called out of scope or otherwise unset.

</td>
</tr>
</table>

