<!-- loio77d004175cf846479edd4f88a42a0a6e -->

# Define Error Configuration

You can define how to handle errors when message processing fails at runtime.



## Context

Error messages can include sensible data about systems. Therefore, error messages aren't directly returned to the sender by default. Instead, an error template is returned. With this template, you can access the error message after authenticating against SAP Cloud Integration. You can enable this setting if you want to provide the error message to the sender without any indirection.



## Procedure

1.  Open the integration flow and select the graphical area outside the integration flow model.

2.  Choose the *Error Configuration* tab.

3.  Specify the error handling strategy.

    If you select *Return Exception to Sender*, certain adapters send the complete exception information back to the sender in case of an error. This setting is not recommended for security reasons as, when selected, internal details of the SAP Cloud Integration runtime can be exposed.

    If you like to ensure that no detailed exception information is sent back to the sender, make sure that *Return Exception to Sender* is **deselected** \(which is the default setting\). In this case, an error template is returned to the sender that contains the message processing log ID for further error analysis.


