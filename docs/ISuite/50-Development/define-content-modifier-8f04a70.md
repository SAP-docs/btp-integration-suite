<!-- loio8f04a707843a40bf9f6e07ed55b93034 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Content Modifier



## Prerequisites

You are editing the integration flow in the editor.



## Context

You use the content modifier step to modify the content of incoming message by providing additional information in the header or body of the message.

The Content Modifier allows you to modify a message by changing the content of the data containers that are involved in message processing \(message header, message body, or message exchange\). Depending on which container you want to modify, select one of the tabs *Message Header*, *Message Body*, or *Exchange Property*. If modifying the *Message Body*, you can enter the data you want to add to the message body in an editor. If modifying the *Message Header* or the *Exchange Property*, you can define how to access the content of the incoming message \(which is then used to change the selected data container\). For example, in the *Source Type*, select `XPath` to specify an XPath expression that addresses a particular element in the incoming message, which will be used to change the message header.

Note that data written to the message header during a processing step, for example, in a Content Modifier or Script step, also becomes part of the outbound message addressed to a receiver system. However, properties remain within the integration flow and are not handed over to receivers. Because of this, it is important to consider the following header size restriction if you are using an HTTP-based receiver adapter: If the message header exceeds a certain value, the receiver may not be able to accept the inbound call. This rule applies to all HTTP-based receiver adapters. The limiting value depends on the characteristics of the receiver system, but typically ranges between 4 and 16 KB. To overcome this issue, you can use a subsequent Content Modifier step to delete all headers that are not supposed to be part of the outbound message.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).



<a name="loio8f04a707843a40bf9f6e07ed55b93034__steps_g42_zqp_pz"/>

## Procedure

1.  If the *Content Modifier* step is present in the integration flow, select it to edit the properties.

2.  If you want to add *Content Modifier* step to the integration flow, perform the following substeps:

    1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Transformers\) and then choose :envelope:

    2.  Place *Content Modifier* step in the integration process.


3.  Go to the *Message Header* or *Exchange Property* tab \(depending on whether you want to modify a message header or write data to the exchange property\).

    > ### Note:  
    > Name defined for an *Exchange Property* is case-sensitive. This is a known behavior of the Camel framework.

4.  Choose *Add* to define a new entry.

5.  Specify and define the parameters of the entry as shown below.

    **Content Modifier Attributes for Message Header or Exchange Property**


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Action* 
    
    </td>
    <td valign="top">
    
    You can specify whether the Content Modifier should create or delete the header or property defined by the table row.

    You must specify the name of the header or property you want to delete.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Name* 
    
    </td>
    <td valign="top">
    
    Name under which the specified data has to be stored in the selected header or property data container.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Source Type* 
    
    </td>
    <td valign="top">
    
    Indicates the kind of data you want to use to change the content of the selected header or property data container.

    You can select from the following types:

    -   *Constant* 

        Allows you to write a constant value to the header or property data container.

        Special characters like `{}` and `[]` are not allowed.

    -   *Header*

        Allows you to specify the name of a Camel header.

        You can then use this header to dynamically define properties in subsequent steps.

        For example, if you specify the header name `CamelSplitIndex`, the Camel header of the same name, which counts the actual number of splits in a message split scenario, is accessed from the incoming message.

        In a subsequent step, you use the following expression to refer to this header \(for dynamic configuration\): `${header.CamelSplitIndex}`.

        To enter a header, select *header* in the *Type* column and in the *Value* column choose *Select* to browse for predefined headers.

        > ### Note:  
        > During outbound communication, headers will be handed over to all message receivers and integration flow steps, whereas properties will remain within the integration flow and will not be handed over to receivers.

        > ### Note:  
        > The *Select Header* dialog shows you a list of headers that you have specified:
        > 
        > -   In the *Header* tab page of *Content Modifier* flow steps
        > -   In the *Allowed Headers* field of the *Runtime Configuration* tab page

    -   *XPath* 

        Allows you to retrieve data from the incoming message using XML Path Language \(XPath\). For example, if you have selected this type, you can specify the following *Value* to point to an element `customerName` in the incoming message: `/Order/Customer/CustomerNumber`.

        To enter XPath, select *XPath* in the *Type* column and in the *Value* column choose *Select* to browse for predefined xpath listed in wsdl of SOAP adapter for the sender.

        > ### Note:  
        > -   If the XPath contains a namespace prefix, specify the association between the namespace and the prefix in the *Runtime Configuration* of the integration flow.
        > 
        >     For example, let's assume that the following XPath expression is used:
        > 
        >     `/ns1:order/ns1:customer/ns1:ID`
        > 
        >     In this case, you need to specify a namespace mapping in the runtime configuration as follows:
        > 
        >     `xmlns:ns1=http://mycompany.com/order`
        > 
        > -   The step has been leveraged to use the capabilities of XPath 3.1 Enterprise Edition \(EE\). To read more about the new features of XPath 3.1 visit the saxon documentation published by Saxonica.

    -   *Expression*

        Allows you to enter a Camel Simple Expression Language expression \(see [http://camel.apache.org/simple.html](http://camel.apache.org/simple.html)\).

        For example, you can use the expression `${exchangeId}` to add the exchange ID \(a unique identifier of the message exchange\) to a data container.

        For more information on using Simple Expression Language, see [Using Camel Simple Expression Language](using-camel-simple-expression-language-4688083.md).

    -   *Property*

        Allows you to specify an exchange property.

        To enter a property, select *property* in the *Type* column and define a value based on the selected value type.

        > ### Note:  
        > During outbound communication, headers will be handed over to all message receivers and integration flow steps, whereas properties will remain within the integration flow and will not be handed over to receivers.

    -   *External Parameter*

        This option is not available in WebUI but for compatibility reasons we still support content using this field.

        Integration developer can use externalization and externalize any type of headers or exchange properties.

        Please refer to [Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md) for more details.

    -   *Local Variable*

        Allows you to define a local variable and write its value at runtime to the header or property data container. The value can then be evaluated in subsequent steps of the integration flow.

        A local variable can be used in the context of the integration flow.

    -   *Number Range*

        Allows you to retrieve the value \(a unique identifier\) of a predefined number range.

        > ### Example:  
        > -   If you want to increase the value in the message header define the name of the *Number Range*.
        > 
        > -   If you do not want to increase the value in the message header, then define the value as `<name of the Number Range>:${header.headername}` or `<name of the Number Range>:<correlation ID>`.

        > ### Note:  
        > Make sure you use the same correlation ID for all future processing.

        For more information on adding number range, see [Managing Number Ranges](managing-number-ranges-b6e17fa.md).

    -   *Global Variable*

        Allows you to define a global variable and to write its value at runtime to the header or property data container.

        A global variable can be used across different integration flows of the same tenant.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Source Value* 
    
    </td>
    <td valign="top">
    
    Value of the property
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Data Type*

    \(If you've selected *XPath* or *Expression* as *Type*\)
    
    </td>
    <td valign="top">
    
    Valid Java data type

    The data type can belong to any Java class. For example, if you are addressing a string-type element, enter `java.lang.String` as the Java data type. For more information about supported data types, see [https://camel.apache.org/components/latest/languages/simple-language.html](https://camel.apache.org/components/latest/languages/simple-language.html).

    If the XPath contains a namespace prefix, specify the association between the namespace and the prefix on the Runtime Configuration tab page of the integration flow Properties view.

    To enter an XPath, browse for an XPath from the lookup in the *Value* column.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Default Value*

    \(If you've selected *Local Variable* or *Global Variable* as *Type*\)
    
    </td>
    <td valign="top">
    
    If you have selected *Local Variable* or *Global Variable* as *Type*, the value specified as *Default* will be assigned to the header value if the variable is not found at runtime.
    
    </td>
    </tr>
    </table>
    
6.  If you have multiple entries, use the *Move Up* or *Move Down* actions to sort your entries.

    Headers and properties in a content modifier are processed from top to bottom. Therefore, if you want to process the header or properties in a certain order, first add all your entries and then use the "move" actions to sort them in the order of your choice.

7.  Go to the *Message Body* tab, and define the fields as shown below.


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Type**
    
    </td>
    <td valign="top">
    
    The default value is *Constant*. If the payload contains expressions within it, then set the type as *Expression*; if the payload is huge and it has no expressions within it, then it is recommended to use the type *Constant*.

    > ### Remember:  
    > If the payload size is more than 256 KB, the system doesn't let you use the type expression. If there are actual expressions used and you can't reduce the size of the text, use a groovy script.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Body**
    
    </td>
    <td valign="top">
    
    Enter the content expected in the outgoing message.

    > ### Remember:  
    > Ensure that you set a placeholder for the existing header information.


    
    </td>
    </tr>
    </table>
    
8.  Save or deploy the changes.

    > ### Note:  
    > -   If you add a Content Modifier step without a header, body, and property, you cannot trace the element.
    > 
    > -   The *Data Type* column is used for the XPath type. The data type can belong to any Java class. An example of a data type for an XPath is *java.lang.String*.




## Example

Let us assume that the incoming message contains the following information content:

```
<product>
	<productId>HT-1051</productId>
	<productName>Deskjet Mobile</productName>
</product>
```

The message contains information about an individual product from a product catalog.

The use case is that this message is to be enriched with the actual system time \(as order time\) and transferred into an order message.

In a first content modifier, specify the following settings in the *Exchange Property* tab:

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Expression

</td>
</tr>
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

java.lang.String

</td>
</tr>
<tr>
<td valign="top">

Value

</td>
<td valign="top">

$\{date:now:yyyy-MM-dd HH:mm:ss\}

</td>
</tr>
</table>

Using the expression `${date:now:yyyy-MM-dd HH:mm:ss}`, at runtime the actual system time is retrieved from the system.

The content modifier stores the time value in the `timestamp` property.

In a 2nd content modifier, enter the following expression in the *Message Body* tab:

```
<order>
	<time>${property.timestamp}</time>
	${in.body}
</order>
```

At runtime, the expression `${property.timestamp}` dynamically retrieves the timestamp stored in the previous content modifier.

The expression `${in.body}` is replaced by the actual content of the inbound message.

As a result, the final message \(after the 2 content modifiers\) has the following content for our example:

```

<order>
	<time>2021-05-19 09:20:56</time>
<product>
	<productId>HT-1051</productId>
	<productName>Deskjet Mobile</productName>
</product>
</order>
```

**Related Information**  


[Avoiding Encoding Issues](avoiding-encoding-issues-3018480.md "The integration runtime supports the following two kinds of (internal) data representations: binary data and string (sequence of characters). Conversions between these representations may cause issues that can result in erroneous message processing.")

[Content Modifier Basics](content-modifier-basics-b0576a8.md "")

[Smoke Test Scenario](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/8c83fcf4a72241af9f05e26b3f866aa5.html "") :arrow_upper_right:

[Smoke Test Scenario with External Data Source](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/e4bef7446ad14c5a815b93ff20efebec.html "") :arrow_upper_right:

