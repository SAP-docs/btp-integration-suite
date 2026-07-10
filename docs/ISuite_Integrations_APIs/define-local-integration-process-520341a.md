<!-- loio520341af123a4c2b89796e033e9fd31d -->

# Define Local Integration Process

You use the local integration process to simplify your integration process. You can break down the main integration process into smaller fragments by using local integration processes. You combine these fragments to achieve your main integration process.



## Prerequisites

You are editing an integration flow containing local integration process element.



## Context

You use the *Local Integration Process* to define an integration process that is specific to the integration flow in which it is created. You can use this integration process with the *Process Call* step.

> ### Restriction:  
> You cannot use the following integration flow steps within the *Local Integration Process* step:
> 
> -   Another Local Integration Process
> -   End Message
> -   Sender
> -   Receiver



## Procedure

1.  Choose the local integration process element you want to configure.

2.  If you want to provide a name for the local integration process element, in the *Name* field under the *General* tab, enter name.

3.  If you want to specify the transaction handling of the message, choose a value for *Transaction Handling* under the *Processing* tab.

    To know more about Transcation Handling, see: [Defining Transaction Handling](define-transaction-handling-2a5d4bc.md)

4.  If you want to configure the elements inside the local integration process, refer to the documentation relevant to those elements.

    > ### Note:  
    > There should not be any empty element in the Local Integration Process.

5.  If you want to add the local integration process to a process call element, perform the following substeps:

    1.  Select the process call element in integration flow editor.

    2.  In *Local Integration Process* field, choose *Select*.

    3.  In *Select Local Integration Process* window, select the local integration process you want to assign to the process call.


    > ### Note:  
    > You can use an *Error End* event to throw the exception to default exception handlers.

6.  Save or deploy the configuration.


