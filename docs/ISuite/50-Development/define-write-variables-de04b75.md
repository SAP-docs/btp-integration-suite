<!-- loiode04b758d0634d4aae66593ed5e4a0ea -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Write Variables

You define variables to share data across different integration flows \(deployed on the same tenant\).



## Context

To use a variable across multiple integration flows deployed on the same tenant, define it as a global variable.

You use the *Write Variables* step type to create a variable at a certain point within the message exchange. To consume the variable \(either in another step of the same integration flow or in another integration flow\), you can use a *Content Modifier*. With this step, you can set a header or an Exchange property based on a variable.

> ### Note:  
> You can also use a variable to share data across different steps of the same integration flow. In this case, define it as a local variable.
> 
> This component stores data on your tenant. Note that the tenant space is limited and shared with other tenant data like message processing logs.
> 
> Therefore, if you can avoid it, don't use local variables to share data within a single integration flow. As an alternative, it's recommended that you use Exchange properties instead of variables.
> 
> For more information on guidelines about using variables, see [Anticipate Message Throughput When Choosing a Storage Option](anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md) and in particular: [Variant: Sharing Data Across Integration Flows That Operate Independently from Each Other](variant-sharing-data-across-integration-flows-that-operate-independently-from-each-other-1459948.md).
> 
> For an example scenario where a variable is shared by two integration flows, see: [Example Scenario: Sharing a Variable Across Two Integration Flows](example-scenario-sharing-a-variable-across-two-integration-flows-303562c.md).

> ### Remember:  
> A variable gets expired after the retention period, which is 400 days.
> 
> The retention period starts as soon as the integration flow that contains the variable is successfully processed for the first time. The retention period of the variable keeps extending after every successful processing of the integration flow.

> ### Remember:  
> If you use a variable in your integration flow that doesn't exist or is expired, you experience a message processing error at runtime.

To design an integration flow step to write a variable, perform the following steps.



## Procedure

1.  If a *Write Variables* element is present in the integration flow, choose it to define variables.

2.  If you want to add a *Write Variables* element to the integration flow, perform the following substeps:

    1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Persistence\), then *Write Variables*.

    2.  Place the *Write Variables* element in the integration process and define the message path.


3.  On the *General* tab, you can change the name of the *Write Variables* element.

4.  On the *Processing* tab, choose *Add* to add a new variable.

    Specify the following parameters for each new variable.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Enter the variable name.

    The variable name can either be constant or type `${header.source}`. For example, a valid value is `Variable1` or type `${header.source}`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Select a value from the dropdown list based on the descriptions in the following list:

    -   *Constant*

        If you like the variable to contain a constant.

    -   *Header*

        If you want the variable to contain header information.

        If you've chosen this option, you can use a *Select* button to specify the header.

    -   *XPath*

        If you want the variable to be defined with an XPath expression.

        You can either enter the XPath expression manually or choose *Select* to browse predefined XPath listed in WSDL of the SOAP adapter for the sender.

        > ### Note:  
        > -   Enter a valid Java data type when you define a variable of type XPath.
        > 
        > -   The step has been leveraged to use the capabilities of XPath 3.1 Enterprise Edition \(EE\). To read more about the new features of XPath 3.1, visit the saxon documentation published by Saxonica.

    -   *Expression*

        If you want the variable to contain an expression.

    -   *Property*

        If you want the variable to contain a property.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Data Type*

    \(only if for parameter *Type* you've selected one of the following options: *Expression*, *Constant*, or *Xpath*\)
    
    </td>
    <td valign="top">
    
    Enter a valid Java type \(for example, `java.lang.String`\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Value*
    
    </td>
    <td valign="top">
    
    Enter the value of the variable.

    Examples:

    If for parameter *Type* you've selected *Expression*, you can enter the following expression to create a timestamp:

    `${date:now:yyyy-MM-dd HH:mm:ss}`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Global Scope*
    
    </td>
    <td valign="top">
    
    Select this option if you want the variable to be used in other integration flows deployed on the same tenant.

    If not selected, the variable can be shared only across different components of the same integration flow and is invisible for other integration flows.

    For more information and guidelines how to use this parameter, see [Anticipate Message Throughput When Choosing a Storage Option](anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md).
    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the configuration.

    > ### Note:  
    > Variables can't be downloaded using the data store viewer.


