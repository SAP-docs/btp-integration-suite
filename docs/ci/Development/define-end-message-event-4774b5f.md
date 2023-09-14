<!-- loio4774b5f6f30745d78ba2d7d0ceece516 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define End Message Event

An End Message event ends a message processing sequence.



## Context

This is how using an End Message event has an impact on the message status \(shown in the message processing log\).

> ### Note:  
> To catch any exceptions thrown in the integration process and handle them, you can use an Exception Subprocess.

If an exception occurs during the processing sequence which has been handled in an Exception Subprocess, the message status displayed in the message processing log is `Failed`.

When there is no error during exception handling, the message status displayed in the message processing log is `Completed`.

If you like to configure your integration flow that way that the message status displayed in the message processing log is `Failed` \(even in case an exception occurs during the processing sequence which has been handled successfully in an Exception Subprocess\), you have the following options:

-   Use an Error End event.

-   Use an Escalation End event \(sets message status to `Escalated` in that case\).




<a name="loio4774b5f6f30745d78ba2d7d0ceece516__steps_k1p_xct_2z"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons"></span> ** \> *End Message Event*.

2.  Save the changes.


