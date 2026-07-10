<!-- loioedf281e6f1dc43478fd9aa7b5fd2ba32 -->

# Error Variables

Supported error variables are listed in the Error Variables table.

**Error Variables**


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

The reason phrase associated with the error. For example: "Bad Request".

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

String

</td>
<td valign="top">

Read/Write

</td>
</tr>
</table>

