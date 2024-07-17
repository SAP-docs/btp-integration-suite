<!-- loioe18fc05c3ae04c4bb40f12923aaa908c -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Importing Mapping Content from ES Repository



<a name="loioe18fc05c3ae04c4bb40f12923aaa908c__prereq_omf_d5b_wcb"/>

## Prerequisites

-   You've configured a connection to ES Repository under *Settings* \> *Integration* \(:gear:\) tab. For more information, see [Configuring Connectivity to an SAP Process Orchestration System](configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).

-   You've opened the integration flow in which you want to add the integration content and you are editing it.




## Context

After you've configured the connection to ES Repository, you can import content from it in the *References* tab of the integration flow editor. Currently, you can import:

-   Message mapping

-   Value mapping

-   Operation mapping

-   WSDL


> ### Restriction:  
> -   Import of operation mapping fails if:
> 
>     -   It contains XSLT references.
> 
>     -   The interfaces contain more than one cardinality.
>     -   The interfaces are asynchronous in type.
> 
> -   Importing, viewing, and editing of Java UDF is supported.
> 
> -   Message Mapping containing reference to Value Mapping isn't supported at runtime.
> 
> -   Import of a message mapping object fails if it contains a XSD in the source or target message.

Here's how you can do it:



## Procedure

1.  Choose *References* \> *Local* tab in the integration flow properties sheet.

    If you can't find the *References* tab, choose the empty space in the integration flow editor. You will find the *References* tab at the end of the integration flow editor.

2.  Choose *Add* and select a supported resource. See the supported sources here: [Manage Resources](../manage-resources-b5968b2.md).

3.  Choose *ES Repository* as the source.

4.  Select a ES Repository from the *Name* list. Choose *Connect*.

    A connection is established to the ES Repository. A table with the list of available content is displayed.

5.  Choose the resource that you want to import and choose *Select*.

    A summary of all the artifacts that are available for import is displayed.

6.  Choose *Add*.

    You see a confirmation about all the artifacts that are successfully imported.


