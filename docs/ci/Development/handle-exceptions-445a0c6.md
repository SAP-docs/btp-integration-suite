<!-- loio445a0c67ec1441f7807feae2c85ccd2f -->

# Handle Exceptions

Handle exceptions by extending an integration flow with an exception subprocess.



<a name="loio445a0c67ec1441f7807feae2c85ccd2f__handleExceptions"/>

## Implementation

To handle exceptions, add an exception subprocess to the integration flow.

Exceptions that occur during message processing are caught and handled by the logic implemented in the exception subprocess. The exception handling can even distinguish between different error situations in the exception subprocess and, according to the error category, send back a custom error message to the sender application system.

You can implement 3 variants - using different types of end events:


<table>
<tr>
<th valign="top">

Exception Subprocess Ending with ...

</th>
<th valign="top">

Use Case and Exception Handling

</th>
</tr>
<tr>
<td valign="top">

End event

</td>
<td valign="top">

Use this variant if you want to reply with a custom error message.

In this case, the message is set to status *Completed*. You've the option to define a custom status that allows you to distinguish this error situation from successfully processed messages.

</td>
</tr>
<tr>
<td valign="top">

Error end event

</td>
<td valign="top">

Use this variant to catch an error in an exception subprocess to add additional information to the message processing log.

In this use case, the message status is set to *Failed*.

</td>
</tr>
<tr>
<td valign="top">

Escalation end event

</td>
<td valign="top">

Use this variant to catch an error in an exception subprocess to add additional information to the message processing log.

In this use case, the message status is set to *Escalated* that allows you to search for messages based on the dedicated Escalated message status.

</td>
</tr>
</table>

> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Handle Errors Gracefully](https://api.sap.com/package/DesignGuidelinesHandleErrors?section=Overview)
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

**Related Information**  


[Variant: Exception Subprocess with End Event](variant-exception-subprocess-with-end-event-5f7b1c7.md "Use this variant if you like to reply with a custom error message. In this case, the message is set to status Completed. You've the option to define a custom status that allows you to distinguish this error situation from successfully processed messages.")

[Variant: Exception Subprocess with Error End Event](variant-exception-subprocess-with-error-end-event-c032016.md "Use this variant to catch an error in an exception subprocess to add additional information to the message processing log. In this use case, the message status is set to Failed.")

[Variant: Exception Subprocess with Escalation End Event](variant-exception-subprocess-with-escalation-end-event-5649cde.md "Use this variant to catch an error in an exception subprocess to add additional information to the message processing log. In this use case, the message status is set to Escalated that allows you to search for messages based on the dedicated Escalated message status.")

