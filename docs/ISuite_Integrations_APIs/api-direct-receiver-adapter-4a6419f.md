<!-- loio4a6419f7309e404a90061a594aca3fa6 -->

# API Direct Receiver Adapter

The API Direct receiver adapter enables a calling API artifact to invoke a reusable API artifact within SAP Integration Suite. It routes requests from the calling API artifact to the reusable API artifact using an internal API Direct connection.



The API Direct receiver adapter is configured in the calling API artifact. It invokes the target reusable API artifact, allowing shared business logic, policies, and processing steps to be reused across multiple API artifacts



## How the API Direct Receiver Adapter Works

When a calling API artifact invokes a reusable API artifact, the API Direct receiver adapter:

-   Receives the processed request of the calling API artifact.
-   Routes the request to the configured reusable API artifact through an internal API Direct connection.
-   Invokes the reusable API artifact for further processing.
-   Returns the response from the reusable API artifact to the calling API artifact.



The following table describes the properties available for configuring the API Direct receiver adapter.


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Property

</th>
<th valign="top">

Value/Options

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

General

</td>
<td valign="top">

Name

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Name of the receiver adapter channel.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Optional description for the adapter.

</td>
</tr>
<tr>
<td valign="top">

Adapter Type

</td>
<td valign="top">

APIDirect

</td>
<td valign="top">

Type of adapter used for backend communication.

</td>
</tr>
<tr>
<td valign="top" rowspan="6">

Connection

</td>
<td valign="top">

Resource

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies the reusable API artifact to invoke.

</td>
</tr>
<tr>
<td valign="top">

Address

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies the internal address of the target reusable API artifact.

</td>
</tr>
<tr>
<td valign="top">

Send Body

</td>
<td valign="top">

Selected or cleared

</td>
<td valign="top">

Specifies whether the request body is forwarded to the target reusable API artifact.

</td>
</tr>
<tr>
<td valign="top">

Retain Original Body for Next Steps

</td>
<td valign="top">

Selected or cleared

</td>
<td valign="top">

Retains the original request body for use by subsequent processing steps after the adapter call completes.

</td>
</tr>
<tr>
<td valign="top">

Request Headers

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

p. Enter a list of custom headers, separated by a pipe \(|\), that you want to send to the target system. By default, no custom headers are sent. Alternatively, use an `*` to send all custom headers to the target system. Alternatively, you can dynamically pass on the values by defining a property that includes a list of headers.

> ### Remember:  
> Use an `*` separately. If you use an `*` and custom header together that are separated by a pipe \(|\), only the custom header is considered.



</td>
</tr>
<tr>
<td valign="top">

Response Headers

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an `*` to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

