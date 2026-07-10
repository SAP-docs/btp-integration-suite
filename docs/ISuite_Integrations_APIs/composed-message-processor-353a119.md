<!-- loio353a11956dbc43d8a6146330e16680e4 -->

# Composed Message Processor

You want to handle a message with multiple elements, and each element requires different processing. You use a Composed Message Processor pattern to split the message into multiple sub messages, route the split messages to different destinations, and then reaggregate the responses back into one single message.



<a name="loio353a11956dbc43d8a6146330e16680e4__section_p1v_wsh_xjb"/>

## Use Case

You want to send an order to a supplier, however, some information is missing. Depending on the product category, you need to send the different items to different inventory systems to get the message enriched.

Before applying this pattern, the message has the following structure:

> ### Sample Code:  
> ```
> <?xml version="1.0"?>
> <ns0:PurchaseOrder
> xmlns:ns0="http://demo.sap.com/eip/composed-
> message-processor" PurchaseOrderNumber="99401"
> OrderDate="2019-05-06">
> <Items>
> <Item ItemNumber="10">
> <ProductId>HT-1000</ProductId>
> <ProductName>Notebook Basic 15</ProductName>
> <Category>Notebooks</Category>
> <Quantity>1</Quantity>
> <CurrencyCode>EUR</CurrencyCode>
> <Price>956.00</Price>
> </Item>
> <Item ItemNumber="20">
> <ProductId>HT-1101</ProductId>
> <ProductName>Smart Design</ProductName>
> <Category>Software</Category>
> <Quantity>10</Quantity>
> <CurrencyCode>EUR</CurrencyCode>
> <Price>799.00</Price>
> </Item>
> </Items>
> </ns0:PurchaseOrder>
> ```

After processing, the message has the following structure:

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?> 
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/composed-message-processor" PurchaseOrderNumber="99401" OrderDate="2019-05-06"> 
> <Items> 
> <Item ItemNumber="10"> 
> <ProductId>HT-1000</ProductId> 
> <ProductName>Notebook Basic 15</ProductName> 
> <Category>Notebooks</Category> 
> <MainCategoryName>Computer systems</MainCategoryName> 
> <Quantity>1</Quantity> 
> <CurrencyCode>EUR</CurrencyCode> 
> <Price>956.00</Price> </Item> 
> <Item ItemNumber="20"> 
> <ProductId>HT-1101</ProductId> 
> <ProductName>Smart Design</ProductName> 
> <Category>Software</Category> 
> <MainCategoryName>Software</MainCategoryName> 
> <Quantity>10</Quantity> 
> <CurrencyCode>EUR</CurrencyCode> 
> <Price>799.00</Price> 
> </Item> 
> </Items> 
> </ns0:PurchaseOrder>
> ```



<a name="loio353a11956dbc43d8a6146330e16680e4__section_hdd_vsh_xjb"/>

## Implementation

The *Pattern Composed Message Processor* integration flow illustrates such a simple scenario.

![](images/Pattern_ComposedMessageProcessor_44b9b89.png)

In this example, a General Splitter is used to break up the order into multiple individual messages, according to the number of items within the original order. In a subsequent step, the Router forwards the items to a different inventory system, depending on the product category. Then, the Content Enricher reads data synchronously from an external system and appends the additional information to the original message before routing to the actual receiver. Finally, the Gather step reaggregates the multiple responses back into a single message within the original order.

1.  The General Splitter breaks up the order into multiple individual messages, according to the number of items within the original order. Its attributes are specified in the following way:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Expression Type
    
    </td>
    <td valign="top">
    
    XPath
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    XPath Expression
    
    </td>
    <td valign="top">
    
    /ns0:PurchaseOrder/Items/Item
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Grouping
    
    </td>
    <td valign="top">
    
    1
    
    </td>
    </tr>
    </table>
    
2.  The Router addresses this requirement to a different inventory system, depending on the product category. Its attributes are specified in the following way:


    <table>
    <tr>
    <th valign="top">

    Route Name
    
    </th>
    <th valign="top">

    Condition Expression
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Route1
    
    </td>
    <td valign="top">
    
    /ns0:PurchaseOrder/Items/Item/Category = 'Notebooks'
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Route2
    
    </td>
    <td valign="top">
    
    /ns0:PurchaseOrder/Items/Item/Category = 'Software'
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Route3
    
    </td>
    <td valign="top">
    
    \(Default route\)
    
    </td>
    </tr>
    </table>
    
3.  The Content Enricher reads data synchronously from an external system. The attributes of the associated OData receiver adapter are specified in the following way:

    Under *Connection Details*, the following address is specified:

    *https://espmrefapps.hana.ondemand.com/espm-cloud-web/espm.svc*

    Under *Processing Details*, the following query option is specified:


    <table>
    <tr>
    <td valign="top">
    
    For Inventory1
    
    </td>
    <td valign="top">
    
    $select=Category,MainCategoryName&$filter=Category eq 'Notebooks'
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    For Inventory2
    
    </td>
    <td valign="top">
    
    $select=Category,MainCategoryName&$filter=Category eq 'Software'
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    For Inventory3
    
    </td>
    <td valign="top">
    
    $select=Category,MainCategoryName
    
    </td>
    </tr>
    </table>
    
    The attributes of the associated Content Enricher make sure that the additional information is appended to the original message:

    For *Aggregation Algorithm*, the *Enrich* option is selected.

    Under *Original Message*, the following settings are specified:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Path to Node
    
    </td>
    <td valign="top">
    
    PurchaseOrder/Items
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Element
    
    </td>
    <td valign="top">
    
    Item/Category
    
    </td>
    </tr>
    </table>
    
    Under *Lookup Message*, the following settings are specified:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Path to Node
    
    </td>
    <td valign="top">
    
    ProductCategory
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Element
    
    </td>
    <td valign="top">
    
    Category
    
    </td>
    </tr>
    </table>
    
4.  The Gather step reaggregates the multiple responses back into a single message. Its attributes are specified in the following way:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Aggregation Algorithm
    
    </td>
    <td valign="top">
    
    Combine at XPath
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Combine from source \(XPath\)
    
    </td>
    <td valign="top">
    
    /ns0:PurchaseOrder/Items/Item
    
    </td>
    </tr>
    </table>
    
5.  The mapping step removes the comparison field from the order.


