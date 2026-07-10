<!-- loio5ce1f15f54244d4aa557e9c79d93a684 -->

# Create XSLT Mapping

You perform this task to assign XSLT mapping that is available in your local workspace.



## Context

You perform this task to assign XSLT mapping that is available in your local workspace.

> ### Note:  
> You can now leverage the XSLT 3.0 capabilities through XSLT mapping version 1.2. Some of the capablities are:
> 
> -   Converting JSON to XML
> 
> -   Addition of two new data structures:
> 
>     -   maps
> 
>     -   arrays
> 
> 
> -   Streaming of source documents
> 
> 
> The XSLT Mapping step version 1.2 also allows invocation of the Java function call from the XSLT resource.
> 
> Read this [blog](https://blogs.sap.com/2019/04/16/cloud-platform-integration-xslt-mapping-is-enriched-with-xslt-3.0-specification/) to know more about the capabilities.



## Procedure

1.  Choose *Edit*.

2.  In the palette, choose *XSLT Mapping*.

3.  In the *General* tab enter details for *Name* field.

4.  In the *Processing* tab, select either *Integration Flow* or *Header* for mapping *Source* field.

    1.  If you select integration flow as source, then *Select* to choose the xslt or xsl file from *Resource* folder or file system.

        > ### Note:  
        > -   To view or modify content of xslt mapping in the editor, click on the resource name in the *Resource* field.
        > -   For XSLT mapping, you can select the output format of the message to be either string or bytes from the *Output Format* field.

    2.  If you select header as source, then enter name for the header in the *Header Name* field.


5.  Save or deploy the changes.


