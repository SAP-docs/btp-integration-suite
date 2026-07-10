<!-- loio39b4b013c82e434c943ed3b5534e95ca -->

# Escalation End Event Behavior

This topic describes the behavior of integration processes containing an escalation end event.

The *Escalation Event* does not abort the integration flow processing as a whole but only throws the *Escalation Event* .

Main integration process:

If an*Escalation End Event* is used in the main integration process, the escalation end event throws an *Escalated* event and the processing stops afterwards as there are no further steps to execute

Local integration process:

If an integration process is calling a local integration process and an escalation event has been defined in the local integration process, the *Escalation Event* is thrown, and the processing continues in the calling flow. If there are still steps to process in the main flow, the processing continues normally at this level and the main flow message status will be*Completed*.

> ### Note:  
> In case of a synchronous exchange pattern, the process raises an exception and the message will be marked as *Escalated*. This behavior violates the process described above that no exception will be raised, but this handling was explicitly chosen, since the event is usually defined in the exception sub-process and the sender expects a valid response in a synchronous exchange pattern.

> ### Note:  
> In case of an asynchronous exchange pattern no exception will be raised and the message status will be *Escalated*.

> ### Note:  
> If the Escalation End Event is used within an exception subprocess, the message processing stops and the message status will be *Escalated*. This is regardless of whether the exception subprocess is used in the main Integration Process or a Local Integration Process.

**Related Information**  


[Define an Escalation Event](define-an-escalation-event-f5b3ac8.md "")

