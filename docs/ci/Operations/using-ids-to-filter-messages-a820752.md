<!-- loioa820752f17cd45afacf3f8dcc192a3c0 -->

# Using IDs to Filter Messages

You can filter message processing logs using different IDs.

The following IDs can be used:

-   *Message ID*

    Unique identifier that is associated with the message processing log.

-   *Correlation ID*

    Identifier used to correlate different messages with each other that jointly are processed in the context of an integration scenario.

    > ### Tip:  
    > For example, consider a scenario where one integration flows \(*integration flow 1*\) calls another one \(*integration flow 2*\) using the *ProcessDirect* adapter. In this case, for one message processing run two message processing logs are written: one integration flow 1 and another one for integration flow 2. Both message processing logs have different message IDs values but the same correlation ID.

-   *Application Message ID*

    Identifier set by a dedicated header \(`SAP_ApplicationID`\). You can set this ID using, for example, a *Content Modifier* step.


The ID search process is checking for message processing logs having the specified ID as :

1.  Message ID, if not found, the system checks whether there’s a message with the specified Correlation ID.

2.  Correlation ID, if no such message is found, the system searches for messages with the given Application ID.
3.  Application ID.

    This search attribute can't find messages where the Correlation ID is the same as an existing Message ID, or the Application ID equals a Correlation ID or Message ID \(by coincidence\). Searching for messages by using this attribute is helpful for support use cases \(for root cause analysis, for example\).


