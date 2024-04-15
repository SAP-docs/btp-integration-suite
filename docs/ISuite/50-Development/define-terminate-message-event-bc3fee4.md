<!-- loiobc3fee45bfec4f588adfaf49c1f30ca9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Terminate Message Event

A Terminate Message event stops further processing of a message.



## Context

You use a Terminate Message event if you want to stop a message from further processing. This can be the case if, for example, you have defined specific values on the payload. If the payload doesn't match those values, the process is terminated.

> ### Note:  
> The message status displayed in the message processing log is `Completed`, because it has terminated the message succesfully.

If you like to configure your integration flow that way that the message status displayed in the message processing log is `Failed` \(even in case an exception occurs during the processing sequence which has been handled successfully in an Exception Subprocess\), you have the following options:

-   Use an Error End event.

-   Use an Escalation End Event \(sets a message status to Escalated in that case\).


This blog provides more information on the different message events that you can use in an integration flow: [Message Events in Integration Flows](https://blogs.sap.com/2015/01/16/blog-7-message-events-in-integration-flows/)



## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"> Events</span> \> :radio_button:*Terminate Message*

2.  Place the event icon in the desired location of your integration flow.

3.  In the *Name* field in the *General* tab, you can rename your message event.

4.  Save the changes.


**Related Information**  


[Define End Message Event](define-end-message-event-4774b5f.md "An End Message event ends a message processing sequence.")

[Define an Escalation Event](define-an-escalation-event-f5b3ac8.md "")

[Define a Timer Start Event](define-a-timer-start-event-ae14ad7.md "You can configure an integration flow to automatically start and run on a particular schedule.")

