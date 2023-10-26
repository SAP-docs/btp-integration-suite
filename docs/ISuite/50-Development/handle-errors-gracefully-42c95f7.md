<!-- loio42c95f752c8d4b4cad98b7608223424f -->

# Handle Errors Gracefully

Even well-designed integration flows sporadically break based on load, resource usage, and other factors. To prepare for such situations, extend the integration flow with the appropriate error handling.

> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Handle Errors Gracefully](https://api.sap.com/package/DesignGuidelinesHandleErrors?section=Overview)
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

> ### Note:  
> If you don't consider the proposed guidelines during integration design, there's the risk that your scenario is affected in the following way:
> 
> -   The scenario stops in case of an error.
> 
> -   Not enough information is made available by the system to the experts in charge of resolving error situations.

> ### Note:  
> It can be the case that you've applied the integration flow design guidelines described in this section to your best knowledge, but you still face issues during the operation of the scenario. For example, you have applied all design rules with regard to performance but still the performance isn't good enough at runtime. In such cases, you can check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).

To apply this design guideline, consider the following rules:



<a name="loio42c95f752c8d4b4cad98b7608223424f__section_lfj_c5z_2sb"/>

## Basic Exception Handling Rules

The following example scenarios cover basic exception handing use cases and features:

****


<table>
<tr>
<th valign="top">

Exception handling rule

</th>
<th valign="top">

Description and more information

</th>
<th valign="top">

Example integration flow\(s\)

</th>
</tr>
<tr>
<td valign="top">

Handle exception with an exception subprocess.

</td>
<td valign="top">

If an exception occurs, SAP Cloud Integration handles the exception and ends processing in a well-defined way.

There are different variants depending on the event type that ends exception subprocess:

-   Message End event

    Message monitoring shows *Completed* even if system raises an exception; message from exception subprocess isn’t overwritten with the standard error message template.

    You can use this end event type if you want to reply with a custom error message.

-   Error end event

    Message monitoring shows *Failed* if system raises an exception.

    You can use this end event type to catch an error in an exception subprocess to add additional information to the message processing log.

-   Escalation end event

    Message monitoring shows *Escalated* if system raises an exception.

    You can use this end event type to catch an error in an exception subprocess to add additional information to the message processing log.


See: [Handle Exceptions](handle-exceptions-ca95c61.md)

</td>
<td valign="top">

Handle Errors - Extend With Exception Subprocess - End Event

Handle Errors - Extend With Exception Subprocess – Error End Event

Handle Errors - Extend With Exception Subprocess – Escalation End Event

</td>
</tr>
<tr>
<td valign="top">

Handle exceptions in successful responses.

</td>
<td valign="top">

Use this option to handle situations where the return HTTP status code of the receiver is 200 even if an error occurred, however the response contains an error message. In this case, you can design an integration flow in such a way that SAP Cloud Integration parses the response message and reacts on the error appropriately.

See: [Handle Errors in Successful Responses](handle-errors-in-successful-responses-f066020.md)

</td>
<td valign="top">

Handle Errors - Error in Successful Response

</td>
</tr>
<tr>
<td valign="top">

Outsource exception handling into separate integration flow.

</td>
<td valign="top">

Steps to handle exception are processed in separate integration flow. If an exception occurs in the parent integration flow, the exception handling integration flow is called from the exception subprocess of the parent integration flow.

There are different variants depending on the event type that ends exception subprocess \(message end or error end event\).

> ### Note:  
> You can use this option to design a central integration flow for exception handling.

See: [Outsource Exception Handling into a Separate Integration Flow](outsource-exception-handling-into-a-separate-integration-flow-7f3bb85.md)

</td>
<td valign="top">

Handle Errors - Outsource Error Handling - Main Integration Flow with Error End Event

Handle Errors - Outsource Error Handling - Main Integration Flow with Message End Event

Handle Errors - Outsource Error Handling - Error Handling Flow

</td>
</tr>
</table>



The following tables summarize example scenarios for use cases where:

-   The integration scenario is modularized

-   An exception raised in a dependent integration flow/subprocess/receiver system is handled




### Modularization by ProcessDirect Adapter and Separate Integration Flows

Handle exceptions raised in integration flow connected by the ProcessDirect adapter.

****


<table>
<tr>
<th valign="top">

Exception handling rule

</th>
<th valign="top">

Description and more information

</th>
<th valign="top">

Integration flow\(s\)

</th>
</tr>
<tr>
<td valign="top">

Handle exception raised in a connected integration flow \(simple scenario\).

</td>
<td valign="top">

2 integration flows are connected: A parent integration flow calls a child integration flow, and in the latter one an exception is raised.

Both integration flows are designed in such a way that in this case the scenario continues to process in a well-defined way. In particular, the exception in the child integration flow doesn't stop the parent integration flow.

The child integration flow handles the exception and ends message processing in a controlled way.

See: [Handle Exceptions in Dependent Integration Flows \(Simple Scenario\)](handle-exceptions-in-dependent-integration-flows-simple-scenario-984e51a.md)

</td>
<td valign="top">

Handle Errors - Dependent Integration Flows - Simple Scenario

</td>
</tr>
<tr>
<td valign="top">

Handle exception raised in a connected integration flow in combination with a Splitter/Gather pattern and with *Stop on Exception* activated.

</td>
<td valign="top">

A parent integration flow calls a child integration flow within a Splitter/Gather pattern.

Parent and child integration flows are designed in such a way that in this case the scenario continues to process in a well-defined way. In particular, the exception in the child integration flow doesn't stop the parent integration flow.

See: [Handle Exceptions in Dependent Integration Flows](handle-exceptions-in-dependent-integration-flows-3973cc3.md)

</td>
<td valign="top">

Handle Errors - Dependent Integration Flows - Parent

Handle Errors - Dependent Integration Flows - Child

</td>
</tr>
</table>



### Modularization by Local Process Call and Subprocesses

Handle exceptions raised in local subprocess initiated by Local Process call. Exception raised in subprocess. Main process calls subprocess \(where exception occurs\).

****


<table>
<tr>
<th valign="top">

Exception handling rule

</th>
<th valign="top">

Description and more information

</th>
<th valign="top">

Integration flow\(s\)

</th>
</tr>
<tr>
<td valign="top">

Handle exception raised in a subprocess \(simple scenario\).

</td>
<td valign="top">

Within 1 integration flow, the main process calls a subprocess using a local process call.

If an exception is raised in the subprocess, the processing of the main integration process ends.

See: [Handle Exceptions in Subprocess \(Simple Scenario\)](handle-exceptions-in-subprocess-simple-scenario-e8b10b6.md)

</td>
<td valign="top">

Handle Errors - Local Integration Process

</td>
</tr>
<tr>
<td valign="top">

Handle exception raised in a subprocess in combination with a Splitter with *Stop on Exception* activated.

</td>
<td valign="top">

Within 1 integration flow, the main process calls a subprocess using a local process after a Splitter step. The subprocess contains an exception subprocess that ends with an error end event.

If an exception is raised, processing ends because of the *Stop on Exception* option in the Splitter. The next split is not executed. The message gets a *Failed* status in the monitoring.

See: [Variant 1: Splitter Without Gather with Stop on Exception and with Exception Subprocess](variant-1-splitter-without-gather-with-stop-on-exception-and-with-exception-subprocess-d2445ff.md)

</td>
<td valign="top">

Handle Errors - Splitter with Stop on Exception

</td>
</tr>
<tr>
<td valign="top">

Handle exception raised in a subprocess in combination with a Splitter with *Stop on Exception* deactivated.

</td>
<td valign="top">

Within 1 integration flow, the main process calls a subprocess using a local process call after a Splitter step.

The subprocess contains an exception subprocess that ends with a message end event. If an exception is raised, the overall processing continues until all splits are executed. The message gets a *Completed* status in the monitoring.

See: [Variant 2: Splitter Without Gather Without Stop on Exception and with Exception Subprocess](variant-2-splitter-without-gather-without-stop-on-exception-and-with-exception-subprocess-f9a508a.md)

</td>
<td valign="top">

Handle Errors - Splitter without Stop on Exception

</td>
</tr>
<tr>
<td valign="top">

Handle exception raised in a subprocess in combination with a Splitter/Gather pattern and with *Stop on Exception* activated.

</td>
<td valign="top">

Within 1 integration flow, the main process calls a subprocess using a local process call within a Splitter/Gather pattern.

The subprocess contains an exception subprocess that ends with an error end event. If an exception is raised, processing ends because of the *Stop on Exception* option in the Splitter. The next split is not executed. The message gets a *Failed* status in the monitoring.

See: [Variant 3: Splitter with Gather with Stop on Exception and with Exception Subprocess](variant-3-splitter-with-gather-with-stop-on-exception-and-with-exception-subprocess-4eac8a7.md)

</td>
<td valign="top">

Handle Errors - Splitter Gather with Stop on Exception

</td>
</tr>
<tr>
<td valign="top">

Handle exception raised in a subprocess in combination with a Splitter/Gather pattern and with *Stop on Exception* deactivated.

</td>
<td valign="top">

Within 1 integration flow, the main process calls a subprocess using a local process call within a Splitter/Gather pattern.

The subprocess contains an exception subprocess that ends with a message end event. If an exception is raised, the overall processing continues until all splits are executed. The message gets a *Completed* status in the monitoring.

See: [Variant 4: Splitter with Gather Without Stop on Exception and with Exception Subprocess](variant-4-splitter-with-gather-without-stop-on-exception-and-with-exception-subprocess-77b89c1.md)

</td>
<td valign="top">

Handle Errors - Splitter Gather without Stop on Exception

</td>
</tr>
</table>



### Modularization by Local Process Call and Subprocesses

Handle exceptions raised in local subprocess initiated by Local Process call. Exception raised in subprocess. Main process calls subprocess \(where exception occurs\).

****


<table>
<tr>
<th valign="top">

Exception handling rule

</th>
<th valign="top">

Description and more information

</th>
<th valign="top">

Integration flow\(s\)

</th>
</tr>
<tr>
<td valign="top">

Handle exception raised in a receiver system.

</td>
<td valign="top">

An integration flow calls a receiver system using the HTTP receiver adapter.

If an exception is raised in the receiver, processing of the message is continued by the calling integration flow, and the HTTP error message received from the receiver is handled accordingly.

See: [Don't Throw Exception on Failure](don-t-throw-exception-on-failure-0e6ec4f.md)

</td>
<td valign="top">

Handle Errors - Do not throw Error on Failure

Webshop Wrapper

</td>
</tr>
</table>

**Related Information**  


[Log the Behavior of an Integration Flow](log-the-behavior-of-an-integration-flow-5a3ec6d.md "Log the behavior of an integration flow to collect data for later troubleshooting.")

