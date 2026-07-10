<!-- loio84c85d753dcd4400a440fb1915899b72 -->

# Define Idempotent Process Call

Execute a process call step to check if an incoming message was already processed, and skip the processing of this message.



## Context

The Idempotent Process Call detects if a message ID has already been successfully processed and stores the status of the successful process in the idempotent repository. If there is duplicate execution with the same message ID \(for example if there’s a retry by the sender system\), the called subprocess can either be skipped or the message is marked as a duplicate. You can then decide how to handle the duplicate in the subprocess.

The Idempotent Process Call is useful for modeling at-most-once or exactly-once handling in the integration flow. For example, if you have a receiver system \(let's say a third-party legacy system\) that can’t handle duplicate messages properly, you can call the receiver system from within an Idempotent Process Call.

> ### Note:  
> -   The execution of a message in the subprocess is only marked as done when the complete subprocess was successful. If after the occurrence of an error in the subprocess, the sender system performs a retry, all steps are repeated that precede the step in which the error occurred. To avoid multiple sources of error, keep the subprocess. as simple as possible. Ideally, use only one step in the subprocess.
> 
> -   Exactly-once scenarios require an idempotent receiver. The duplicate detection via the Idempotent Process Call in the Integration Flow is only the second-best solution. There might still be problems if the call runs into a timeout or the target application doesn't acknowledge the call. In this case, it isn't clear if the message is successfully processed by the application and duplicates can't be completely ruled out.
> -   Message IDs stored in the idempotent repository are deleted by default after 90 days. After this period, message IDs that have already been stored in the database can no longer be detected as duplicates during a new processing.

> ### Note:  
> The uniqueness check is bound to the specific flow step instance. That means:
> 
> -   Each instance of the idempotent process call is independent from other instances. If a message is marked as `done` by one flow step instance, this doesn't influence other flow step instances which use the same message ID.
> 
> -   If you delete and remodel the flow step, you get a new instance with an empty history. If a message was marked as `done` by a previous instance of the flow step, the new instance will not detect this.

> ### Note:  
> To learn how to use this feature to implement integration scenarios with quality of service **Exactly Once** \(see [Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md)\), check out the integration flow design guidelines and example integration flows:
> 
> See:
> 
> -   [Idempotent Process Call Handles Duplicates](idempotent-process-call-handles-duplicates-da18f73.md)
> 
> -   [Idempotent Process Call Handles Duplicates \(with JMS and Data Store Operations\)](idempotent-process-call-handles-duplicates-with-jms-and-data-store-operations-727724f.md)
> 
> -   [Idempotent Process Call Handles Duplicates \(With Alternative Response\)](idempotent-process-call-handles-duplicates-with-alternative-response-a870621.md)
> 
> -   [Aggregator](aggregator-86f97fd.md)



## Procedure

1.  In the palette, choose *Call* \> *Local Call* \> *Idempotent Process Call*.

2.  Click anywhere inside the *Integration Process* box of the integration flow model.

3.  Specify the following attribute in the *General* tab.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Specify a name.
    
    </td>
    </tr>
    </table>
    
4.  Specify the following attributes in the *Processing* tab.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Local Integration Process* 
    
    </td>
    <td valign="top">
    
    Select a pre-defined local integration process that you want to invoke.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Message ID* 
    
    </td>
    <td valign="top">
    
    To check against, enter a unique message ID. Use `${header.headername}` or `${property.propertyname}` to dynamically read the value from a header or a property.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Skip Process Call for Duplicates* 
    
    </td>
    <td valign="top">
    
    -   *Selected \(default case\)*

        If you select this option, the local integration process doesn't run if there’s a duplicate message.


    -   *Deselected*

        If you deselect this option, you always run the local integration process. Use the following NON-XML condition to check if you're processing a duplicate message: *$\{property.CamelDuplicateMessage\}='true'*



    
    </td>
    </tr>
    </table>
    
5.  Save and deploy the integration flow.


