<!-- loio47f27da841424fc5a2973edad270f5b4 -->

# Flow Variables

This topic provides information about the flow variables.

**Client Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
<th valign="top">

Scope begins

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

client.cn

</td>
<td valign="top">

The common name specified in the TLS/SSL certificate presented by the client app.

> ### Note:  
> If the common name in the TLS/SSL certificate contains comma separated values, then the client.cn flow variable returns only the first value before comma. If you need to read all the values, then it is recommended to use the tls.client.s.dn flow variable. For more information, see [TLS/SSL Connection Information Variables](tls-ssl-connection-information-variables-9326107.md).
> 
> This behaviour applies to all the client flow variables that are associated with TLS/SSL context. For example, client.country, client.email.address, client.organization, client.organization.unit, client.locality, and client.state.



</td>
<td valign="top">

Proxy request

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

client.country

</td>
<td valign="top">

The country/region in the TLS/SSL certificate presented by the client app.

</td>
<td valign="top">

Proxy request

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

client.email.address

</td>
<td valign="top">

The e-mail address in the TLS/SSL certificate presented by the client app.

</td>
<td valign="top">

Proxy request

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

client.host

</td>
<td valign="top">

The HTTP host IP associated with the request received by the ProxyEndpoint.

</td>
<td valign="top">

Proxy request

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

client.ip

</td>
<td valign="top">

The IP address of the client or system sending the message. For example, this could be the original client IP or a load balancer IP.

</td>
<td valign="top">

Proxy request

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

client.locality

</td>
<td valign="top">

The locality \(City\) in the TLS/SSL certificate presented by the client.

</td>
<td valign="top">

Proxy request

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

client.organization

</td>
<td valign="top">

The organization in the TLS/SSL certificate presented by the client.

</td>
<td valign="top">

Proxy request

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

client.organization.unit

</td>
<td valign="top">

The organizational unit in the TLS/SSL certificate presented by the client.

</td>
<td valign="top">

Proxy request

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

client.port

</td>
<td valign="top">

The HTTP port associated with the originating client request to ProxyEndpoint.

</td>
<td valign="top">

Proxy request

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

client.received.end.time

</td>
<td valign="top">

-   The time, expressed in string form, at which the proxy finished receiving the request from the originating client at the ProxyEndpoint. For example: Wed, 21 Aug 2013 19:16:47 UTC
-   This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.



</td>
<td valign="top">

Proxy request

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

client.received.end.timestamp

</td>
<td valign="top">

The timestamp value specifying when the proxy finished receiving the request from the originating client at the ProxyEndpoint. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Proxy request

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

client.received.start.time

</td>
<td valign="top">

-   The time, expressed in string form, at which the proxy began receiving the request from the originating client at the ProxyEndpoint. For example: Wed, 21 Aug 2013 19:16:47 UTC
-   This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.



</td>
<td valign="top">

Proxy request

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

client.received.start.timestamp

</td>
<td valign="top">

The timestamp value specifying when the proxy began receiving the request from the originating client at the ProxyEndpoint. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Proxy request

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

client.sent.end.time

</td>
<td valign="top">

-   The time, expressed in string form, when the ProxyEndpoint finished returning the response to the originating client app. For example: Wed, 21 Aug 2013 19:16:47 UTC
-   This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.



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

The timestamp value specifying when the ProxyEndpoint finished returning the response to the originating client app. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

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

-   The time, expressed in string form, when the ProxyEndpoint started returning the response to the originating client app. For example: Wed, 21 Aug 2013 19:16:47 UTC
-   This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.



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

The timestamp value specifying when the ProxyEndpoint started returning the response to the originating client app. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

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

client.scheme

</td>
<td valign="top">

Returns http or https depending on the transport used by client app to send the request message.

</td>
<td valign="top">

Proxy request

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

client.state

</td>
<td valign="top">

The state in the TLS/SSL certificate presented by the client.

</td>
<td valign="top">

Proxy request

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

client.ssl.enabled

</td>
<td valign="top">

Returns true or false, depending on whether the ProxyEndpoint is configured for TLS/SSL.

</td>
<td valign="top">

Proxy request

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

onpremise.target.host

</td>
<td valign="top">

The onpremise virtual host configured in onpremise APIProvider

</td>
<td valign="top">

Proxy target endpoint request

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

onpremise.target.port

</td>
<td valign="top">

The onpremise virtual port configured in onpremise APIProvider

</td>
<td valign="top">

Proxy target endpoint request

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

onpremise.target.basepath

</td>
<td valign="top">

Determines the actual base path.

</td>
<td valign="top">

Proxy target endpoint request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
</table>

**Error Flow Variables**


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

error

</td>
<td valign="top">

Error of type Message, which is a contextual object in the error flow

</td>
<td valign="top">

Error

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

error.content

</td>
<td valign="top">

Content of the error

</td>
<td valign="top">

Error

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

error.message

</td>
<td valign="top">

Message associated with an error, whose value is available only before the error Flow is executed.

</td>
<td valign="top">

Error

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

error.status.code

</td>
<td valign="top">

The HTTP status code associated with the error. For example: "400".

</td>
<td valign="top">

Error

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

error.reason.phrase

</td>
<td valign="top">

The reason phrase associated with the error. For example: "Bad Request"

</td>
<td valign="top">

Error

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

error.transport.message

</td>
<td valign="top">

Any error of type TransportMessage

</td>
<td valign="top">

Error

</td>
<td valign="top">

Transport\_Message

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

error.state

</td>
<td valign="top">

State in the Flow where an error occurred

</td>
<td valign="top">

Error

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

error.header.<name\>

</td>
<td valign="top">

Get or set the response header.

</td>
<td valign="top">

Error

</td>
<td valign="top">

integer

</td>
<td valign="top">

Read/Write

</td>
</tr>
</table>

**Request Flow Variables**


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

request

</td>
<td valign="top">

The complete request, including any payload present.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Message

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

request.content

</td>
<td valign="top">

Gets or sets the payload of the request message.

</td>
<td valign="top">

Proxy request

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

request.formparam.\{formparam\_name\}

</td>
<td valign="top">

Gets or sets the value of the specified form parameter in the request sent from the client app.

</td>
<td valign="top">

Proxy request

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

request.formparam.\{formparam\_name\}.values.count.

</td>
<td valign="top">

Count of all values for the specified form parameter associated with the request.

</td>
<td valign="top">

Proxy request

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

request.formparams.count

</td>
<td valign="top">

Count of all form parameters associated with the request sent from the client app.

</td>
<td valign="top">

Proxy request

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

request.formparams.names

</td>
<td valign="top">

A list of all form parameter names associated with the request.

</td>
<td valign="top">

Proxy request

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

request.header.\{header\_name\}

</td>
<td valign="top">

Gets or sets the value of a particular header found in the request.

> ### Note:  
> If the \{header\_name\} has multiple values, you can read or retrieve all the values of the header. For more information on extracting multiple values of an HTTP header, see [Multi-value HTTP Headers in an API Proxy](multi-value-http-headers-in-an-api-proxy-5eb7100.md)



</td>
<td valign="top">

Proxy request

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

request.header.\{header\_name\}.values

</td>
<td valign="top">

All the values of a particular header in the request

</td>
<td valign="top">

Proxy request

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

request.header.\{header\_name\}.values.count

</td>
<td valign="top">

Count of all the values of a particular header in the request.

</td>
<td valign="top">

Proxy request

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

request.formparams.count

</td>
<td valign="top">

Count of all form parameters associated with the request sent from the client a

</td>
<td valign="top">

Proxy request

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

request.formparams.names

</td>
<td valign="top">

A list of all form parameter names associated with the request.

</td>
<td valign="top">

Proxy request

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

request.header.\{header\_name\}

</td>
<td valign="top">

Gets or sets the value of a particular header found in the request.

</td>
<td valign="top">

Proxy request

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

request.header.\{header\_name\}.values

</td>
<td valign="top">

All the values of a particular header in the request

</td>
<td valign="top">

Proxy request

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

request.header.\{header\_name\}.values.count

</td>
<td valign="top">

Count of all the values of a particular header in the request.

</td>
<td valign="top">

Proxy request

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

request.headers.count

</td>
<td valign="top">

Count of all the headers in the request.

</td>
<td valign="top">

Proxy request

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

request.path

</td>
<td valign="top">

The unproxied resource path \(not including the host\) to the backend service, excluding query parameters.

</td>
<td valign="top">

Proxy request

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

request.queryparam.\{queryparam\_name\}

</td>
<td valign="top">

The value of a particular query parameter found in the request.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

string

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

request.queryparam.\{queryparam\_name\}.values.count

</td>
<td valign="top">

The count of all the values of a particular query parameter in the request.

</td>
<td valign="top">

Proxy request

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

request.queryparams.count

</td>
<td valign="top">

The count of all the query parameters in the request.

</td>
<td valign="top">

Proxy request

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

request.queryparams.names

</td>
<td valign="top">

request.queryparams.names

</td>
<td valign="top">

Proxy request \(Java Object\)

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

request.querystring

</td>
<td valign="top">

The complete list of query parameters in the request sent from the client app. For example, if the request is `http://host.com/123?name=first&surname=second&place=address` then this variable returns name=first&surname=second&place=address

</td>
<td valign="top">

Proxy request

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

request.transportid

</td>
<td valign="top">

ID of the request as type TransportMessage which is a contextual object

</td>
<td valign="top">

Proxy request

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

request.transport.message

</td>
<td valign="top">

Request of type TransportMessage which is a contextual object

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Transport

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

request.uri

</td>
<td valign="top">

In an API proxy, the proxy <BasePath\> in the ProxyEndpoint \(in addition to the proxy's base URL\) maps to the target service URL in the TargetEndpoint. For example:

<ProxyEndpoint\>

...

<BasePath\>/my-mock-proxy</BasePath\>

points to

<TargetEndpoint\>

...

<HTTPTargetConnection\>

http://mocktarget.sap.com

</HTTPTargetConnection\>

In the request, the request.uri is the proxy base path + the remainder of the address, including query parameters.

In the response, the request.uri is the remainder of the address, including query parameters, after the HTTPTargetConnection.

The difference is because the original request came into the proxy, but then the proxy makes another request to the target service.

Let's say the following call is made to our sample proxy, which has a base path of /my-mock-proxy:

http://my\_org-test.sap.com/my-mock-proxy/user?user=test

and the proxy calls

http://mocktarget.apigee.net \(which appends /user?user=test to that URL\).

Request: request.uri = /my-mock-proxy/user?user=test

Response: request.uri = /user?user=test

</td>
<td valign="top">

Proxy request \(differs with response\)

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

request.url

</td>
<td valign="top">

Returns the exact complete URL of the final request made.

</td>
<td valign="top">

Target request

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

request.verb

</td>
<td valign="top">

The HTTP verb used for the request. For example: GET, PUT, DELETE

</td>
<td valign="top">

Proxy request

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

request.version

</td>
<td valign="top">

Gets the HTTP version of the request.

</td>
<td valign="top">

Proxy request

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

response.formstring

</td>
<td valign="top">

The complete list of form parameters in the request.

For example: name=test&type=first&group=A

</td>
<td valign="top">

Target request

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

route.name

</td>
<td valign="top">

The name of the RouteRule that was executed in the ProxyEndpoint. For example: default. A RouteRule references an API proxy TargetEndpoint to execute.

</td>
<td valign="top">

Target request

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

route.target

</td>
<td valign="top">

The name of the TargetEndpoint that was executed. For example: default.

</td>
<td valign="top">

Target request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
</table>

**Response Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
<th valign="top">

Scope begins

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

> ### Note:  
> To read or retrieve all the values of the header, you can see [Multi-value HTTP Headers in an API Proxy](multi-value-http-headers-in-an-api-proxy-5eb7100.md)



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

All the values of a specified HTTP header in response.

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

Integer

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

Read

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
</table>

