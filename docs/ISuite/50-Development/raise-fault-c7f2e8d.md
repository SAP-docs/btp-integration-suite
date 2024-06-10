<!-- loioc7f2e8d9de4249cfa8cc2655ebd4878b -->

# Raise Fault

The RaiseFault policy allows you to create custom messages in case of error conditions. This policy returns a FaultResponse to the requesting application if it encounters an error condition.

A FaultResponse can consist of HTTP headers, query parameters, and a message payload. These elements can be populated using variables. This enables you to send customized FaultResponses that are specific to the error conditions.

During execution, the RaiseFault policy transfers the message flow to the default ErrorFlow, which in turn returns the designated FaultResponse to the requesting application. When the message flow switches to the default ErrorFlow, no further policy processing occurs. All remaining processing steps are bypassed, and the FaultResponse is returned directly to the requesting app.

You can attach this policy in the following locations:![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows::

> ### Code Syntax:  
> ```
> <!-- The policy will create a custom response of status code as 500 and message as Server error in case of error condition is met  -->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <RaiseFault async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <FaultResponse>
>         <Set>
>             <Headers/>
>             <Payload contentType="text/plain"> </Payload>
>             <StatusCode>500</StatusCode>
>             <ReasonPhrase>Server Error</ReasonPhrase>
>         </Set>
>     </FaultResponse>
>     <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
> </RaiseFault>
> 
> ```


<table>
<tr>
<th valign="top">

**Field Name**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

IgnoreUnresolvedVariables\(Optional\)

</td>
<td valign="top">

Ignores any unresolved variable error in the flow.

Valid values: `true` or `false`

Default value: `true`

</td>
</tr>
<tr>
<td valign="top">

FaultResponse\(Optional\)

</td>
<td valign="top">

Defines the response message returned to the requesting application.

</td>
</tr>
</table>

The following predefined flow variables are available after Raise Fault policy executes.

**Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Type

</th>
<th valign="top">

Permission

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

fault.name

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

Returns the fault name in the error and if not available, an empty string.

</td>
</tr>
<tr>
<td valign="top">

fault.type

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

Returns the fault type in the error and if not available, an empty string.

</td>
</tr>
<tr>
<td valign="top">

fault.category

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

Returns the fault category in the error and if not available, an empty string.

</td>
</tr>
</table>

During the policy execution, the following error can occur:

**Error Cause**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

RaiseFault

</td>
<td valign="top">

See fault string.

</td>
</tr>
</table>

Following fault variables are set when the policy triggers an error at runtime:

**Fault Variables**


<table>
<tr>
<th valign="top">

Variable Set

</th>
<th valign="top">

Where

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

\[prefix\].\[policy\_name\].failed

</td>
<td valign="top">

The \[prefix\] is raisefault.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

raisefault.RF-ThrowError.failed = true

</td>
</tr>
<tr>
<td valign="top">

fault.\[error\_name\]

</td>
<td valign="top">

\[error\_name\] = The specific error name to check for as listed in the table above.

</td>
<td valign="top">

fault.name = "RaiseFault"

</td>
</tr>
</table>

