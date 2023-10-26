<!-- loioad60e664a34f485b90c1620e9c249fdb -->

# Request Message Variables

Request message variables are used in policies to access message components like the header, the query parameters, form parameters, the source IP address, the HTTP message body.

API proxy applies the incoming request to a series of policies, depending on the request condition, API proxy can either modify or transform the request. Based on the content of the request variable, policies can either transform or reject the request. Supported request variables are listed in the Request Message Variables table.

**Request Message Variables**


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

The IP address of the client or system sending the message to the Edge router. For example, this could be the original client IP or a load balancer IP.

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

The time, expressed in string form, at which the proxy began receiving the request from the originating client at the ProxyEndpoint. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

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

The time, expressed in string form, when the ProxyEndpoint finished returning the response to the originating client app. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

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

client.sent.end.timestamp

</td>
<td valign="top">

The timestamp value specifying when the ProxyEndpoint finished returning the response to the originating client app. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

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

client.sent.start.time

</td>
<td valign="top">

The time, expressed in string form, when the ProxyEndpoint started returning the response to the originating client app. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

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

client.sent.start.timestamp

</td>
<td valign="top">

The timestamp value specifying when the ProxyEndpoint started returning the response to the originating client app. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

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

message.queryparam.\{queryparam\_name\}

</td>
<td valign="top">

Returns the specified message query parameter.

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

message.queryparam.\{queryparam\_name\}.values.count

</td>
<td valign="top">

The total count of a specified query parameter associated with the request sent to the ProxyEndpoint from the client app

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

message.queryparams.count

</td>
<td valign="top">

The total count of all query parameters associated with the request sent to the ProxyEndpoint from the client app.

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

message.queryparams.names

</td>
<td valign="top">

A list of all query parameter names associated with the request sent to the ProxyEndpoint from the client app.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Collection \(Java Object\)

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

message.querystring

</td>
<td valign="top">

A string containing all query parameter names and values associated with the request sent to the ProxyEndpoint from the client app.

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

message.uri

</td>
<td valign="top">

The complete URI path \(following the domain URL\) including query parameters.

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

message.verb

</td>
<td valign="top">

The HTTP verb \(GET, PUT, POST, DELETE, and so on\) associated with the request

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

message.version

</td>
<td valign="top">

The HTTP version associated with the request sent to the ProxyEndpoint from the client app.

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

messageid

</td>
<td valign="top">

This ID is logged in the error logs to correlate the messageId with the errors.

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

proxy.basepath

</td>
<td valign="top">

The value of the Base Path in your API proxy configuration. The base path is the URI fragment that follows the host in the URL. Conditional flow URIs follow the base path.

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

proxy.client.ip

</td>
<td valign="top">

The `X-Forwarded-For` address of the inbound call, which is the IP address API Management received from the last external TCP handshake. This could be the calling client.

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

proxy.pathsuffix

</td>
<td valign="top">

The value of API proxy basepath suffix that is sent from the client and received at the ProxyEndpoint.

The basepath is defined as the path component that uniquely identifies the API proxy. The public-facing URL of an API proxy is comprised of your organization name, the environment where the proxy is deployed, the basepath, the basepath suffix, and any query parameters.

For example, in the following request:

http://myorg-test.sap.net/v2/weatherapi/forecastrss?w=12797282

The basepath suffix is /forecastrss

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

proxy.url

</td>
<td valign="top">

Gets the complete URL associated with the proxy request received by the ProxyEndpoint, including any query parameters present. Note that the host in proxy.url is the router host, not the host used in the original request.

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

request.formparam.\{formparam\_name\}.

values.count

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

The un-proxied resource path \(not including the host\) to the backend service, excluding query parameters.

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

request.queryparam.\{queryparam\_name\}

</td>
<td valign="top">

The value of a particular query parameter found in the request.

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

The names of all the query parameters in the request.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Collection \(JavaObject\)

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

The complete list of query parameters in the request sent from the client app.

For example, if the request is

http://host.com/123?name=first&surname=second&place=address

then this variable returns

name=first&surname=second&place=address

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

Transport message

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
<tr>
<td valign="top">

servicecallout.requesturi

</td>
<td valign="top">

The TargetEndpoint URI for a ServiceCallout policy. The URI is the TargetEndpoint URL without the protocol and domain specification.

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

servicecallout.\{policy-name\}.expectedcn

</td>
<td valign="top">

The expected Common Name of the TargetEndpoint as referred to in a ServiceCallout policy. This is meaningful only when the TargetEndpoint refers to an TLS/SSL endpoint.

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

servicecallout.\{policy-name\}.target.url

</td>
<td valign="top">

The TargetEndpoint URL for a particular ServiceCallout policy.

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

target.basepath

</td>
<td valign="top">

Returns basepath of TargetEndpoint

</td>
<td valign="top">

Target Request

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

target.copy.pathsuffix

</td>
<td valign="top">

When true, request forwarded from ProxyEndpoint to TargetEndpoint retains path suffix \(the URI path fragment following the URI defined in the ProxyEndpoint base path.\)

</td>
<td valign="top">

Target Request

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

target.copy.queryparams

</td>
<td valign="top">

When true, request forwarded from ProxyEndpoint to TargetEndpoint retains query parameters.

</td>
<td valign="top">

Target Request

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read/Write

</td>
</tr>
<tr>
<td valign="top">

target.cn

</td>
<td valign="top">

The Common Name of the TargetEndpoint. This is meaningful only when the TargetEndpoint refers to an TLS/SSL endpoint.

</td>
<td valign="top">

Target request

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.expectedcn

</td>
<td valign="top">

The expected Common Name of the TargetEndpoint. This is meaningful only when the TargetEndpoint refers to an TLS/SSL endpoint.

</td>
<td valign="top">

Proxy Request

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

target.name

</td>
<td valign="top">

Target to which message is reaching from targetendpoint

</td>
<td valign="top">

Target Request

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

target.sent.end.time

</td>
<td valign="top">

The time, expressed in string form, at which the proxy stopped sending the request to the URL specified in the TargetEndpoint. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

</td>
<td valign="top">

Target Request

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

target.sent.end.timestamp

</td>
<td valign="top">

The timestamp value specifying when the proxy finished sending the request to the URL specified in the TargetEndpoint. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Target Request

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

target.sent.start.time

</td>
<td valign="top">

The time, expressed in string form, at which the proxy began sending the request to the URL specified in the TargetEndpoint. For example: Wed, 21 Aug 2013 19:16:47 UTC

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

</td>
<td valign="top">

Target Request

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

target.sent.start.timestamp

</td>
<td valign="top">

The timestamp value specifying when the proxy started sending the request to the URL specified in the TargetEndpoint. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Target Request

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

target.ssl.enabled

</td>
<td valign="top">

Whether TargetEndpoint is running on TLS/SSL

</td>
<td valign="top">

Target Request

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

target.url

</td>
<td valign="top">

The URL configured in the TargetEndpoint XML file or the dynamic target URL \(if target.url is set during the message flow\). The variable does not include any additional path elements or query parameters. Returns null if called out of scope or otherwise unset.

</td>
<td valign="top">

Target Request

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

variable.expectedcn

</td>
<td valign="top">

Variable exposed for the common name if it's running on TLS/SSL

</td>
<td valign="top">

Proxy Request

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

virtualhost.aliases

</td>
<td valign="top">

Host aliases of the virtual host that is hit during a particular request

</td>
<td valign="top">

Proxy Request

</td>
<td valign="top">

String\_array

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

virtualhost.name

</td>
<td valign="top">

Name of the virtual host that serves the originating client request

</td>
<td valign="top">

Proxy Request

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

virtualhost.ssl.enabled

</td>
<td valign="top">

Returns true if TLS/SSL is enabled in the virtual host configuration

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read

</td>
</tr>
</table>

