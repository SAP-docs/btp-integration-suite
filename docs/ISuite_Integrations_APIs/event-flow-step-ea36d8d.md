<!-- loioea36d8d192a0446eba318087d55ed79d -->

# Event Flow Step

Event steps enable you to define the start, end, and error-handling points of the execution flow within an API artifact. You can add these steps to the policy model of your API artifact to control how the integration process is initiated, terminated, or interrupted based on specific conditions.



## Use

You use event steps in an API artifact to:

-   Initiate the integration flow based on a defined schedule.
-   Send a custom error message as the final response in an integration process.
-   Throw exceptions to the default exception handler for further processing.
-   Trigger an exception subprocess when an error occurs in the main integration process to enable custom error handling.
-   Stop further processing of a message in the integration flow.



## Event Steps


<table>
<tr>
<th valign="top">

Policy Step

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/ Links

</th>
</tr>
<tr>
<td valign="top">

End Event

</td>
<td valign="top">

Sends a custom error message as the final response in an integration process.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Handle Exceptions](handle-exceptions-445a0c6.md).

</td>
</tr>
<tr>
<td valign="top">

Error End Event

</td>
<td valign="top">

Throws the exception to the default exception handler for further processing.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Exception Subprocess](define-exception-subprocess-690e078.md).

</td>
</tr>
<tr>
<td valign="top">

Error Start Event

</td>
<td valign="top">

Triggers the Exception Subprocess when an error occurs in the main integration process to enable custom error handling.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Exception Subprocess](define-exception-subprocess-690e078.md).

</td>
</tr>
<tr>
<td valign="top">

Start Event

</td>
<td valign="top">

Initiates the integration flow based on a defined schedule.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Exception Subprocess](define-exception-subprocess-690e078.md).

</td>
</tr>
<tr>
<td valign="top">

Terminate Message

</td>
<td valign="top">

Stops further processing of a message in the integration flow.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Terminate Message Event](define-terminate-message-event-bc3fee4.md).

</td>
</tr>
</table>

