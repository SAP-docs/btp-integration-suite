<!-- loio690e0784c90342669a5f1461ae65b95f -->

# Define Exception Subprocess



## Context

You use this element to catch any exceptions thrown in the integration process and handle them.

> ### Note:  
> To learn how to implement exception handling, check out the integration flow design guidelines provided for this topic under [Handle Errors Gracefully](handle-errors-gracefully-42c95f7.md).
> 
> The integration flow design guidelines provide both documentation and predefined integration content. You can deploy and run the integration content out-of-the-box to learn basic concepts of Cloud Integration. You can also access the integration flows from SAP Business Accelerator Hub as described in [How to Work with the Example Integration Flows](how-to-work-with-the-example-integration-flows-03e6959.md).



<a name="loio690e0784c90342669a5f1461ae65b95f__steps_npc_31j_gy"/>

## Procedure

1.  Open your integration flow in the editor.

2.  To add an exception subprocess to the integration flow, choose *Process* \> *Exception Subprocess* from the palette. The subprocess can be dropped into the integration process and should not be connected to any of the elements of the integration flow.

3.  Select the exception subprocess.

    1.  In the property sheet specify a name.


4.  Start the process with *Error Start* event always.

5.  End the process with either *End Message* or *Error End* or *Escalation* event.

    > ### Note:  
    > -   You can use an *End Message* event to wrap the exception in a fault message and send it back to the sender in the payload.
    > -   You can use an *Error End* event to throw the exception to default exception handlers.

6.  You can also add other flow elements between the start and end events.

    > ### Note:  
    > -   For example, you can choose *Add Service Call* from the context menu of a connection within the pool. This enables you to call another system to handle the exception.
    > 
    > -   The following elements are not supported within an *Exception Subprocess*:
    >     -   *Another Exception Subprocess*
    > 
    >     -   *Integration Process*
    > 
    >     -   *Local Integration Process*
    > 
    >     -   *Sender*
    > 
    >     -   *Receiver*
    > 
    >     -   *Start Message*
    > 
    >     -   *Terminate Message*
    > 
    >     -   *Timer Start*
    > 
    >     -   *Start Event *
    > 
    >     -   *End Event*
    > 
    >     -   *Router*
    > 
    >     -   *Aggregator*
    > 
    > 
    > -   If a Data Store Write step fails because the entry already exists \(duplicate key exception\), this exception cannot be handled by an Exception subprocess. The reason is that the database transaction is rolled back even if an Exception subprocess is used.

7.  Save the changes.

    > ### Note:  
    > -   The message processing log will be in an error state even if a user catches an exception and performs additional processing on it.
    > -   You can get more details on exception using `${exception.message}` or `${exception.stacktrace}`.
    > -   You cannot catch exceptions of local integration process in the main integration process.
    > -   When an error is thrown during integration runtime and the same is caught by the Exception Subprocess, the processing gets terminated.


**Related Information**  


[Handle Exceptions](handle-exceptions-ca95c61.md "Handle exceptions by extending an integration flow with an exception subprocess.")

