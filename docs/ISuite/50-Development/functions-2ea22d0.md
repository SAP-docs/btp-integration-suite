<!-- loio2ea22d0fbc14405b82e77b12fb24f3a1 -->

# Functions

Functions are used to specify a data transformation between source and target nodes.

You can use functions to transform or compute data within the Mapping Guidelines \(MAG\) editor. The three types of data transformation available are — Functions, Date time mapping, and String processing. For more information on Date time mapping and String processing, see [Value Transformations](value-transformations-19f8374.md).

The *Function* tab on the mapping pane is available only when leaf nodes are mapped or when a function is assigned to a target leaf node with no corresponding source node. You can create and assign a function to a target leaf node that isn't mapped to any source node.

The *XSLT Code* editor in the *Function* tab of the mapping pane is used to formulate expressions based on XSLT V3.0 or XPath 3.1. A default code snippet is available when you map a source leaf node to a target leaf node. You can create your own implementation of the XSLT function by editing the default code snippet to meet your data transformation requirements.

You can use parameters to pass values to functions. For instance, you can define a default value for the parameter *PARAM* and pass it to a function as an argument. You can create a new parameter by choosing *Add New Parameter* on the *Function* tab and bind it to a parameter defined in the *Global Parameters* tab. Use the shared code feature to create frequently used code snippets and reuse it as required within your MAG.

> ### Note:  
> -   All XSLT 3.0 and XPath 3.1 functions are supported.
> 
> -   For more information, refer to XSLT or XPath specification published by W3C.



## Example

The following are a few examples of XSLT processing tasks:

-   **Source Data as an Input** - An input value is passed as an argument to a function to transform it. Use the `substring` function to extract the first three characters of the source data.

    > ### Sample Code:  
    > ```
    > <xsl:sequence select="substring($nodes_in,1,3)"/>
    > ```

-   **Function as an Input** - The `current-dateTime` function is passed as an argument to a function to extract the year component from it.

    > ### Sample Code:  
    > ```
    > <xsl:sequence select="year-from-dateTime(current-dateTime())"/>
    > ```

-   **Parameter as an Input** - A parameter is passed as an argument to a function. The global parameter *PARAM* defined and assigned a value of 01 is concatenated with the source field and assigned to the target field.

    > ### Sample Code:  
    > ```
    > <xsl:sequence select="concat($PARAM,$nodes_in)"/>
    > ```


**Related Information**  


[Using Functions](using-functions-2a1e53a.md "Use functions to specify a data transformation between source and target nodes within the Mapping Guidelines (MAG) editor.")

[Creating a Shared Code](creating-a-shared-code-e951f66.md "Create frequently used code snippets and reuse it as required within your Mapping Guidelines (MAG).")

[Defining Global Parameters](defining-global-parameters-62fe053.md "You can use Global Parameters tab to create and define reusable parameters within your Mapping Guideline (MAG).")

[Using Functions Without a Source Node Mapping](using-functions-without-a-source-node-mapping-5722493.md "Create and assign a function to a target leaf node with no corresponding source node mapping.")

