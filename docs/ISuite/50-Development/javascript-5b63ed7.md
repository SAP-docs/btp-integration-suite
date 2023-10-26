<!-- loio5b63ed7782ab4b4ea96bf84119059039 -->

# JavaScript

JavaScript Policy is used to configure the JavaScript code to execute within the context of an API proxy flow.

A JavaScript policy contains no actual code. Instead, a JavaScript policy references a JavaScript resource and defines the step in the API flow where the JavaScript executes. The JavaScript resource that is referenced by the JavaScript policy can be stored in the API Proxy bundle. The JavaScript resource always has a .js extension.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!–- Use case: Remove forward slash from incoming URL present at the end using a library function in a different script file -->
> 
> <Javascript async="false" continueOnError="false" enabled="true" timeLimit="200" xmlns='http://www.sap.com/apimgmt'>
> 	<IncludeURL>jsc://lib.js</IncludeURL>
> 	<ResourceURL>jsc://maincode.js</ResourceURL>
> </Javascript>
> 
> <!–- =====Content of lib.js ==== -->
>  
> 
> //Trims the last chars from the string
> function trimEnd(value, searchChar){
>   if (value.charAt(value.length - 1) == searchChar) {
>     value = value.substr(0, value.length - 1);
>   }
>   return value;
> }
> 
> <!–- ======= Contents of maincode.js ==== -->
> 
> //Returns the proxy  path suffix by escaping the trailing ‘/’
> function getTrimmedPathSuffix(){
>   return trimEnd(context.getVariable("proxy.pathsuffix"),'/');
> }
> 
> context.setVariable("trimmedPathSuffix", getTrimmedPathSuffix());
>  
> ```


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

timeLimit \(required\)

</td>
<td valign="top">

Specifies the maximum time \(in milliseconds\) that the script is permitted to execute.

</td>
</tr>
<tr>
<td valign="top">

ResourceURL \(required\)

</td>
<td valign="top">

Specifies the JavaScript resource \(file\). This is the main code file from which the execution begins.

Syntax: `<ResourceURL>jsc://example-javascript.js</ResourceURL>`

</td>
</tr>
<tr>
<td valign="top">

IncludeURL \(optional\)

</td>
<td valign="top">

Specifies a JavaScript library to be loaded as dependency. Store libraries under /APIProxy/FileResources/<`policy name`\>.js in your API proxy bundle. The scripts are evaluated in the order in which they are listed in the policy.

Syntax: `<IncludeURL>jsc://my-javascript-URL.js</IncludeURL>`

</td>
</tr>
<tr>
<td valign="top">

Display name \(optional\)

</td>
<td valign="top">

Labels the policy in the management UI proxy editor with a different, natural-language name.

If you skip this element, the value of the `name` attribute is applied to the policy.

Syntax: `<DisplayName>Policy-Display-Name</DisplayName>`

</td>
</tr>
</table>

During the policy execution, the following errors can occur:


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

ScriptExecutionFailed

</td>
<td valign="top">

A runtime error occurred in the JavaScript code. See the fault string for details.

</td>
</tr>
<tr>
<td valign="top">

ScriptExecutionFailedLineNumber

</td>
<td valign="top">

An error occurred in the JavaScript code. See the fault string for details.

</td>
</tr>
<tr>
<td valign="top">

ScriptSecurityError

</td>
<td valign="top">

A security error occurred when the JavaScript executed. See the fault string for details.

</td>
</tr>
<tr>
<td valign="top">

WrongResourceType

</td>
<td valign="top">

In the <ResourceURL\> and <IncludeURL\> elements, you must refer to a JavaScript file correctly using the jsc resource type.

For example, here is the correct way to refer to the JavaScript file in the policy:

<ResourceURL\>jsc://JavaScript-1.js</ResourceURL\>

</td>
</tr>
<tr>
<td valign="top">

NoResourceForURL

</td>
<td valign="top">

The <ResourceURL\> and <IncludeURL\> elements refer to a JavaScript file that does not exist.

</td>
</tr>
<tr>
<td valign="top">

ScriptCompilationFailed

</td>
<td valign="top">

An error occurred during compilation of the JavaScript code. Refer to the error message for details.

</td>
</tr>
<tr>
<td valign="top">

InvalidResourceUrlFormat

</td>
<td valign="top">

This error occurs when the format of the resource URL specified within the <ResourceURL\> or the <IncludeURL\> element of the JavaScript policy is invalid, resulting in the deployment of the API proxy to fail.

</td>
</tr>
<tr>
<td valign="top">

InvalidResourceUrlReference

</td>
<td valign="top">

This error occurs when the <ResourceURL\> or the <IncludeURL\> elements refer to a JavaScript file that does not exist, resulting in the deployment of the API proxy to fail.

</td>
</tr>
</table>

Following fault variables are set when the policy triggers an error at runtime:


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

The \[prefix\] is javascript.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

javascript.JavaScript-1.failed = true

</td>
</tr>
<tr>
<td valign="top">

fault.\[error\_name\]

</td>
<td valign="top">

\[error\_name\] is the specific error name to check for as listed in the table above.

</td>
<td valign="top">

fault.name Matches "ScriptExecutionFailed"

</td>
</tr>
</table>

Following is an example of an error response:

> ### Sample Code:  
> ```
> {
>   "fault": {
>     "faultstring": "Execution of SetResponse failed with error: Javascript runtime error: "ReferenceError: "status" is not defined. (setresponse.js:6)\"",
>     "detail": {
>       "errorcode": "steps.javascript.ScriptExecutionFailed"
>     }
>   }
> }
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> ```
> <FaultRule name="JavaScript Policy Faults">
>     <Step>
>         <Name>AM-CustomErrorResponse</Name>
>         <Condition>(fault.name Matches "ScriptExecutionFailed") </Condition>
>     </Step>
>     <Condition>(javascript.JavaScript.failed = true) </Condition>
> </FaultRule>
> ```

