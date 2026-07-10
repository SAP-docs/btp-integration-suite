<!-- loio6fd4a865c9f3456ea452e6b3da4715f6 -->

# Content Filter

Assume that you get an order from a partner in a standard format that you've agreed upon. The message contains numerous fields that are required for communicating with your partner, however your backend system only needs a small fraction of the fields.

There are 2 options to implement such a scenario:

-   Using a Filter step

-   Using Message Mapping




<a name="loio6fd4a865c9f3456ea452e6b3da4715f6__section_zr2_sh2_5jb"/>

## Use Case

The incoming order contains multiple items. However, you're only interested in items of a specific product category. Implement the content filter in such a way that only those few data items are included in the message. In addition, you need to ensure that the header information, such as the purchase order, is kept.

Before applying the Content Filter, the message has the following structure:

> ### Sample Code:  
> ```
> <?xml version="1.0"?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/content-filter" PurchaseOrderNumber="99401" OrderDate="2019-05-06">
> <Address Type="Shipping">
> <Name>Ellen Adams</Name>
> <Street>123 Maple Street</Street>
> <City>Mill Valley</City>
> <State>CA</State>
> <Zip>10999</Zip>
> <Country>USA</Country>
> </Address>
> <Address Type="Billing">
> <Name>Tai Yee</Name>
> <Street>8 Oak Avenue</Street>
> <City>Old Town</City>
> <State>PA</State>
> <Zip>95819</Zip>
> <Country>USA</Country>
> </Address>
> <DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>
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
> <ProductId>HT-1001</ProductId>
> <ProductName>Notebook Basic 17</ProductName>
> <Category>Notebooks</Category>
> <Quantity>1</Quantity>
> <CurrencyCode>EUR</CurrencyCode>
> <Price>1249.00</Price>
> </Item>
> <Item ItemNumber="30">
> <ProductId>HT-1000</ProductId>
> <ProductName>Notebook Basic 15</ProductName>
> <Category>Notebooks</Category>
> <Quantity>1</Quantity>
> <CurrencyCode>EUR</CurrencyCode>
> <Price>956.00</Price>
> </Item>
> <Item ItemNumber="40">
> <ProductId>HT-1030</ProductId>
> <ProductName>Ergo Screen</ProductName>
> <Category>Flat screens</Category>
> <Quantity>2</Quantity>
> <CurrencyCode>EUR</CurrencyCode>
> <Price>460.00</Price>
> </Item>
> <Item ItemNumber="50">
> <ProductId>HT-1101</ProductId>
> <ProductName>Smart Design</ProductName>
> <Category>Software</Category>
> <Quantity>10</Quantity>
> <CurrencyCode>EUR</CurrencyCode>
> <Price>799.00</Price>
> </Item>
> </Items>
> </ns0:PurchaseOrder>
> 
> ```

After applying the Content Filter, the message has the following structure.

> ### Note:  
> In this case, the content was filtered for Software.

> ### Sample Code:  
> ```
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/ContentFilter" PurchaseOrderNumber="99401" OrderDate="2019-05-06">
>     <Address Type="Shipping">
>         <Name>Ellen Adams</Name>
>         <Street>123 Maple Street</Street>
>         <City>Mill Valley</City>
>         <State>CA</State>
>         <Zip>10999</Zip>
>         <Country>USA</Country>
>     </Address>
>     <Address Type="Billing">
>         <Name>Tai Yee</Name>
>         <Street>8 Oak Avenue</Street>
>         <City>Old Town</City>
>         <State>PA</State>
>         <Zip>95819</Zip>
>         <Country>USA</Country>
>     </Address>
>     <DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>
>     <Items>
>         <Item ItemNumber="50">
>             <ProductId>HT-1101</ProductId>
>             <ProductName>Smart Design</ProductName>
>             <Category>Software</Category>
>             <Quantity>10</Quantity>
>             <CurrencyCode>EUR</CurrencyCode>
>            <Price>799.00</Price>
>         </Item>
>     </Items>
> </ns0:PurchaseOrder>
> 
> ```



<a name="loio6fd4a865c9f3456ea452e6b3da4715f6__section_d44_132_5jb"/>

## Implementation

SAP Integration Suite supports a Content Filter step out of the box. You can also implement filtering based on Message Mapping.

**Related Information**  


[Variant: Content Filter Step](variant-content-filter-step-239d8f8.md "In this variant, the filter is used to remove all unnecessary data items from the message. However, the message header is kept.")

[Variant: Message Mapping](variant-message-mapping-85571e2.md "In this variant, Message Mapping is used to remove all unnecessary data items from the message, but the message header is kept.")

