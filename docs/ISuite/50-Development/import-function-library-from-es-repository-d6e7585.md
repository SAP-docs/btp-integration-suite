<!-- loiod6e758578666417e9c73a043315a9775 -->

# Import Function Library from ES Repository



<a name="loiod6e758578666417e9c73a043315a9775__prereq_kjm_4zv_4xb"/>

## Prerequisites

-   [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md)

-   [Creating a Function Libraries Artifact](creating-a-function-libraries-artifact-950b897.md)




<a name="loiod6e758578666417e9c73a043315a9775__context_md3_fqw_pxb"/>

## Context

There are certain limitations while importing and consuming the function library object:

-   Function library object with user-defined functions of ExecutionType**ALL\_VALUES\_OF\_QUEUE** is not supported.

-   Function library object that has references to imported archives is not supported.

-   The combination of the attributes `category` and `title` in a function library's method must be unique. No two methods within a function library class can have the same combination.

-   An imported function library object can be consumed in integration flows via message mapping flow steps and message mapping artifacts. For other artifacts like REST API or OData service, you can consume only via message mapping artifacts; not via message mapping flow steps.




## Procedure

1.  Open the Function Libraries that you created and choose *Edit*.

    The resource pane and editor comes up on the left and right sides respectively.

2.  In the resource pane, choose *Upload*.

3.  In the dialog box, choose *ES Repository* as the *Source*. You see the details populated in the *Name* and *Address* fields.

4.  Choose *Connect*.

    You see a list of available function library objects.

5.  Choose a function library object of your choice and choose *Select*.

    The selected function library object gets imported to resource pane.

6.  Choose the imported object.

    A java class containing the user-defined functions as methods opens up in edit mode.

7.  Make necessary changes to the java class as per your requirement and choose *Save*.


