<!-- loio06594b982e86462ab371993fb66c3a37 -->

# Recipient List

Let's assume that you want to send an order to a number of suppliers to find the best quote. However, the order isn't expected to go to all of the suppliers; it depends on the product that you want to order.

Therefore, the particular suppliers are dynamically determined based on the respective goods. Other than for the content-based router, the message, or to be precise a copy of the message, is sent to multiple receivers.



<a name="loio06594b982e86462ab371993fb66c3a37__section_rqz_ykx_sjb"/>

## Use Case

An order is sent to multiple receivers depending on the product category. Assuming that you have an order with multiple items and hence different product categories, you usually would combine the recipient list pattern with the splitter pattern. That means that you first split the multiple items, eventually group the items by category, and then apply the recipient list pattern. For demo purposes, we stick to one single item within the order.

> ### Sample Code:  
> ```
> <?xml version="1.0"?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/recipient-list" PurchaseOrderNumber="99202" OrderDate="2019-05-06">
> 	<Item PartNumber="922-YC">
> 		<ProductName>Name</ProductName>
> 		<ProductCategory>Software</ProductCategory>
> 		<Quantity>1</Quantity>
> 		<Price>119.99</Price>
> 	</Item>
> </ns0:PurchaseOrder>
> ```

In this example, the routing rules are defined as follows:

-   Send any item with the category `Software` to both Supplier1 and Supplier2.

-   Send any item with the category `Notebooks` to Supplier3, Supplier4 and Supplier5.

-   Send any item with the category `Keyboards` to Supplier4 and Supplier5.




<a name="loio06594b982e86462ab371993fb66c3a37__section_yjg_4lx_sjb"/>

## Implementation

We distinguish between 2 different options to implement the Receiver List pattern:

-   Static routing with XPath conditions

-   Dynamic routing using mapping to determine the receivers


**Related Information**  


[Variant: Static Routing](variant-static-routing-b71529f.md "")

[Variant: Dynamic Routing](variant-dynamic-routing-d241c77.md "The dynamic routing variant uses message mapping to determine the list of receivers.")

