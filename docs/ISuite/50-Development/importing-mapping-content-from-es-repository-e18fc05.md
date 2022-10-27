<!-- loioe18fc05c3ae04c4bb40f12923aaa908c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Mapping Content from ES Repository



<a name="loioe18fc05c3ae04c4bb40f12923aaa908c__prereq_omf_d5b_wcb"/>

## Prerequisites

You have configured a connection to ES Repository under *Settings* \> *Integration* \(:gear:\) tab. For more information, see [Configuring Connectivity to ES Repository](configuring-connectivity-to-es-repository-8c36fd2.md).

You have opened the integration flow in which you want to add the integration content and you are editing it.



## Context

After you have configured the connection to ES Repository, you can import content from it in the *Resources* tab of the integration flow editor. Currently, you can import:

-   Message mapping
-   Operation mapping
-   WSDL

> ### Restriction:  
> -   Import of operation mapping will fail if
> 
>     -   It contains XSLT references
> 
>     -   The interfaces contain more than one cardinality
>     -   The interfaces are asynchronous in type
> 
> -   The import process will fail if the message mapping contains
> 
>     -   User Defined Functions with function libraries or imported archives
> 
>     -   Parameters
> 
> 
> -   Importing, viewing and editing of Java UDF is supported.
> 
> -   Message Mapping containing reference to Value Mapping is not supported at runtime.

Here's how you can do it:



## Procedure

1.  Choose *Resources* tab in the integration flow settings.

    If you do not see the *Resources* tab, click the empty space in the integration flow editor. You will see the *Resources* tab at the bottom of the integration flow editor.

2.  Choose *Add* \> *Mapping* \> *Message Mapping/Operation Mapping* depending on the resource you want to import.

    An *Add Message Mapping* prompt, where you can select the source and select target system details is displayed.

3.  Choose *ES Repository* as the source. You see the details populated in *Name* and *Address* fields. *Connect*.

    A connection is established to the ES Repository. A table with the list of available content is displayed.

4.  Choose the content that you want to import and choose *Select*.

    A summary of all the artifacts that will be imported is displayed.

5.  Choose *Add*.

    You see a confirmation about all the artifacts that are successfully imported.


