<!-- loio80cad36b1a95443b8dc82211b993d836 -->

# Working with Call Flow Steps

Call steps enable you to invoke external systems or local integration processes from within an API artifact. You can add these steps to the policy model of your API artifact to make synchronous calls to external receivers or reuse integration logic through local process invocations.



## Use

You use call steps in an API artifact to:

-   Call an external receiver system synchronously and retrieve a response.
-   Send messages to external systems using supported adapters.
-   Prevent duplicate processing of incoming messages using idempotent checks.
-   Execute a local integration process repeatedly in a loop.
-   Invoke a local integration process to simplify complex scenarios by dividing the integration logic into smaller, reusable fragments.



## Call Steps


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Sub Category

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

External Call

</td>
<td valign="top">

Request Reply

</td>
<td valign="top">

Calls an external receiver system synchronously and retrieves a response.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Request Reply](define-request-reply-dc39fdd.md).

</td>
</tr>
<tr>
<td valign="top">

Send

</td>
<td valign="top">

Works with mail adapter for APIs on Edge Integration Cell.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define a Send Step](define-a-send-step-9b83f10.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Local Call

</td>
<td valign="top">

Idempotent Process Call

</td>
<td valign="top">

Checks whether an incoming message has already been processed and prevents duplicate processing.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Idempotent Process Call](define-idempotent-process-call-84c85d7.md).

</td>
</tr>
<tr>
<td valign="top">

Looping Process Call

</td>
<td valign="top">

Executes a local integration process repeatedly in a loop.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Looping Process Call](define-looping-process-call-f58c2ba.md).

</td>
</tr>
<tr>
<td valign="top">

Process Call

</td>
<td valign="top">

Invokes a local integration process from the main process to simplify complex scenarios by dividing the integration logic into smaller, reusable fragments.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Process Call](define-process-call-cf0251e.md).

</td>
</tr>
</table>

