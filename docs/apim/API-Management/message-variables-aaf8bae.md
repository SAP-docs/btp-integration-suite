<!-- loioaaf8bae37d28424cbbf789129e4b750a -->

# Message Variables

Message variables refer to different message types like request, response, or error depending on the point within the APIproxy flow in which they are called.

Supported message variables are listed in the Message Variables table.

**Message Variables**


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

message

</td>
<td valign="top">

A contextual object, with the same value as request in the request Flow or as response in the response Flow or as error in the Error flow.

</td>
<td valign="top">

Proxy request

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

message.content

</td>
<td valign="top">

Content of the request, response, or error message

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

message.formparam.\{formparam\_name\}

</td>
<td valign="top">

Value of the specified form parameter

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

message.formparam.\{formparam\_name\}.values

</td>
<td valign="top">

All values of the specified form parameter in the message

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

message.formparam.\{formparam\_name\}.values.count

</td>
<td valign="top">

Count of the values of the specified form parameters in the message

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

message.formparams.count

</td>
<td valign="top">

Count of all form parameters in the message

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

message.formparams.names

</td>
<td valign="top">

Value of all form parameters in the message

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

message.formstring

</td>
<td valign="top">

Value of form string in the message

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

message.header.\{header\_name\}

</td>
<td valign="top">

Gets or sets the value of the specified HTTP header in the message

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

message.reason.phrase

</td>
<td valign="top">

Scope begins: Target response

Type: String

Permission: Read

ReasonPhrase of the response message from target

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

message.header.\{header\_name\}.values

</td>
<td valign="top">

All values of the specified HTTP header name in the message

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

message.header.\{header\_name\}.values.count

</td>
<td valign="top">

Count of the values of the specified HTTP header name in the message

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

message.headers.count

</td>
<td valign="top">

Count of all HTTP headers in the message

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

message.headers.names

</td>
<td valign="top">

Value of all HTTP headers in the message

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

messagelogging.\{policy-name\}.failed

</td>
<td valign="top">

Failure flag for the referenced Message logging policy

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
<tr>
<td valign="top">

messagelogging.failed

</td>
<td valign="top">

Failure flag for Message logging policy

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
</tr>
<tr>
<td valign="top">

message.queryparam.\{queryparam\_name\}.values

</td>
<td valign="top">

Value of the specified query parameter in the message

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

message.transport.message

</td>
<td valign="top">

Message of type `TransportMessage` which is a contextual object

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

TransportMessage

</td>
<td valign="top">

Read

</td>
</tr>
</table>

