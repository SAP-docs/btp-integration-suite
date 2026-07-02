<!-- loio733f8dceaf094a8bb8afa2628285f64e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Filter



## Context

You use *Filter* to extract information from an incoming message. In other words, you filter out parts of the message that you do not want and extract only the data that you want.

> ### Note:  
> The *Filter \(1.1 version\)* step has been leveraged to use the capabilities of XPath 3.1 Enterprise Edition \(EE\), for extracting information from an incoming XML message. To read more about the new features of XPath 3.1 visit the saxon documentation published by Saxonica.

Here's an example for a message:

```
<Message>
<orders>
		<order>
			<clientId>I0001</clientId>
			<count>100</count>
		</order>
		<order>
			<clientId>I0002</clientId>
		     	 <count>10</count>
		</order>
</orders>
</Message>
```

Let us assume that you are interested only in the *count*. You use the *Filter* and specify an Xpath `/Message/orders/order/count/text()`.

The output of the content filter would be data in *count* fields of the message. The output in this example with the specified Xpath is *10010*.

For more examples, see [Examples](examples-eb2e601.md).



## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> and, then *Filter*.

2.  Place *Filter* in the integration process and define the message path.

3.  Select *Filter* and provide values in fields based on description in table.


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Specify a name for filter step. By default, the value is *Filter*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    XPath Expression
    
    </td>
    <td valign="top">
    
    Specify Xpath to the message node that contains information to be extracted
    
    </td>
    </tr>
    </table>
    
4.  In *Value Type* dropdown list, select value type based on description in table.


    <table>
    <tr>
    <th valign="top">

    Value Type
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    The output of filter is of type string
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Integer
    
    </td>
    <td valign="top">
    
    The output of filter is of type integer
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Boolean
    
    </td>
    <td valign="top">
    
    The output of filter is of type boolean
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Node
    
    </td>
    <td valign="top">
    
    The output of filter is of type node
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Nodelist
    
    </td>
    <td valign="top">
    
    The output of filter is a collection of nodes
    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the configuration.


