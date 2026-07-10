<!-- loio11bebe12aaed4099bd566e5ebbd025f4 -->

# Response Message Variables

Response message variables are used in policies to access message components like the header, the query parameters, form parameters, the source IP address, the HTTP message body.

API proxy applies the received response to a series of policies, depending on the request condition, API proxy can either modify or transform the request. Based on the content of the response variable, policies can either transform or reject the request. Supported response variables are listed in the Response Message Variables table.

**Response Message Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
<th valign="top">

Scope

</th>
<th valign="top">

Type

</th>
<th valign="top">

Permission

</th>
</tr>
<tr>
<td valign="top">

client.sent.end.time

</td>
<td valign="top">

The time, expressed in string form, at which the proxy finished sending the response from the ProxyEndpoint to the client. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

</td>
<td valign="top">

Proxy response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

client.sent.end.timestamp

</td>
<td valign="top">

The timestamp value specifying when the proxy finished sending the response to the client from the ProxyEndpoint. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Proxy response

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

client.sent.start.time

</td>
<td valign="top">

The time, expressed in string form, at which the proxy began sending the response from the ProxyEndpoint to the client. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

</td>
<td valign="top">

Proxy response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

client.sent.start.timestamp

</td>
<td valign="top">

The timestamp value specifying when the proxy began sending the response to the client from the ProxyEndpoint. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Proxy response

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

message.reason.phrase

</td>
<td valign="top">

ReasonPhrase of the response message from target

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

message.status.code

</td>
<td valign="top">

HTTP status code of the response message from target

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response

</td>
<td valign="top">

Complete response message returned by target

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Message

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

response.content

</td>
<td valign="top">

Payload content of the response message returned by the target

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

response.formparam.\{formparam\_name\}

</td>
<td valign="top">

The value of a form parameter in the response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

response.formparam.\{formparam\_name\}.values.count

</td>
<td valign="top">

Count of all the values of the specified form parameter in response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response.formparams.count

</td>
<td valign="top">

Count of all form parameters in the response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response.formparams.names

</td>
<td valign="top">

The names of all the form parameters in the response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Collection

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response.header.\{header\_name\}

</td>
<td valign="top">

Gets or sets the value of a specified HTTP header in the response. If the header has multiple values \(such as a CSV list\), a GET returns the first value only.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

response.header.\{header\_name\}.values

</td>
<td valign="top">

All the values of a specified HTTP header in response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Collection

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response.header.\{header\_name\}.values.count

</td>
<td valign="top">

Count of all the values of the specified HTTP header in response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response.headers.count

</td>
<td valign="top">

Count of all the headers in the response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response.headers.names

</td>
<td valign="top">

The names of all the headers in the response

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Collection

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

response.reason.phrase

</td>
<td valign="top">

The response reason phrase for a particular request

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

response.status.code

</td>
<td valign="top">

The response code returned for a request. You can use this variable to override the response status code, which is stored in message.status.code.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

response.transport.message

</td>
<td valign="top">

Response of type TransportMessage which is a contextual object

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.country

</td>
<td valign="top">

Country/region of the TLS/SSL certificate presented by the target server

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.email.address

</td>
<td valign="top">

E-mail address of the TLS/SSL certificate presented by the target server

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.organization

</td>
<td valign="top">

Organization of the TLS/SSL certificate presented by the target server

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.organization.unit

</td>
<td valign="top">

Organization unit of the TLS/SSL certificate presented by the target server

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.locality

</td>
<td valign="top">

Locality \(city\) of the TLS/SSL certificate presented by the target server

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.received.end.time

</td>
<td valign="top">

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.received.end.timestamp

</td>
<td valign="top">

The timestamp value specifying when the TargetEndpoint finished receiving the response from the target. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.received.start.time

</td>
<td valign="top">

The time, expressed in string form, at which the TargetEndpoint finished receiving the response from the target. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.received.start.timestamp

</td>
<td valign="top">

The timestamp value specifying when the TargetEndpoint started receiving the response from the target. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.state

</td>
<td valign="top">

State of the TLS/SSL certificate presented by the target server

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.host

</td>
<td valign="top">

The domain name of the target service returning the response to the API proxy.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.ip

</td>
<td valign="top">

The IP address of the target service returning the response to the API proxy.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.port

</td>
<td valign="top">

The port number of the target service returning the response to the API proxy.

</td>
<td valign="top">

Target response

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.scheme

</td>
<td valign="top">

Returns http or https depending on the request message

</td>
<td valign="top">

Target response

</td>
<td valign="top">

String

</td>
<td valign="top">

Read/Write

</td>
</tr>
</table>

