<!-- loio4cac4a46f77e41e2a3ed87de89862760 -->

# Rate Limits on SAP Cloud Integration

Rate limiting helps prevent denial-of-service attacks on the entire product or its individual applications.



<a name="loio4cac4a46f77e41e2a3ed87de89862760__section_dhs_hgl_15b"/>

## Reasons for Rate Limits

The most common attacks include:

-   A user generates a large number of requests to overload or crash an application.
-   A user accidentally writes a script or uses a third-party application that generates so many requests that an application freezes or crashes. This can also result in all resources being allocated to a single tenant or user, making the application unavailable to others.

The requests could come from different sources:

-   Too many browser instances \(e.g. a large number of users rapidly refresh or script with tools like Selenium\)
-   Direct access to published APIs \(e.g. scripts or third-party applications generate requests without delay\)
-   Indirect access to internal APIs \(e.g. one application calls another application\)
-   Direct access to private APIs \(e.g. someone discovers internal endpoints and call them\)



## Restrictions

Rate limiting is based on the number of requests per second. It only protects against situations where an unexpectedly high request rate causes issues. It doesn't protect against the following scenarios:

-   Memory usage that depends on request parameters
-   CPU usage that depends on request parameters
-   Load that depends on the amount of data stored or returned
-   Load that depends on the number of parallel requests
-   Load that depends on the exact number of requests \(e.g. two requests per second are acceptable, but three cause a crash\)



## Rate Limits on Cloud Integration Services

To ensure fair usage across different dimensions, SAP Cloud Integration applies the following rate limitations:


<table>
<tr>
<th valign="top">

**Artifact**

</th>
<th valign="top">

**Action**

</th>
<th valign="top">

**Rate per Tenant**

**\(requests/second\)**

</th>
<th valign="top">

**Rate per User**

**\(requests/second\)**

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Number Range

</td>
<td valign="top">

Deploy

</td>
<td valign="top">

10

</td>
<td valign="top">

5

</td>
</tr>
<tr>
<td valign="top">

List

</td>
<td valign="top">

10

</td>
<td valign="top">

5

</td>
</tr>
<tr>
<td valign="top">

Design time Artifacts

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

20

</td>
<td valign="top">

10

</td>
</tr>
<tr>
<td valign="top">

Security Content

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

12

</td>
<td valign="top">

10

</td>
</tr>
<tr>
<td valign="top">

MPL

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

1000

</td>
<td valign="top">

100

</td>
</tr>
<tr>
<td valign="top">

Runtime Artifacts

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

120

</td>
<td valign="top">

50

</td>
</tr>
<tr>
<td valign="top">

Partner Directory- Alternative partners

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

50

</td>
<td valign="top">

25

</td>
</tr>
<tr>
<td valign="top">

Partner Directory- Authorized users

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

50

</td>
<td valign="top">

25

</td>
</tr>
<tr>
<td valign="top">

Partner Directory- Binary Parameters

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

50

</td>
<td valign="top">

25

</td>
</tr>
<tr>
<td valign="top">

Partner Directory- Partners

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

50

</td>
<td valign="top">

25

</td>
</tr>
<tr>
<td valign="top">

Partner Directory- String Parameters

</td>
<td valign="top">

All public APIs

</td>
<td valign="top">

50

</td>
<td valign="top">

25

</td>
</tr>
</table>

