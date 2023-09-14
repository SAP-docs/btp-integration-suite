<!-- loio4b475eaac3de4ef1a9f434fd13cbb709 -->

# Splitter

If a message contains multiple elements but each element needs to be processed in a different way, you can use the Splitter pattern to break up the message into multiple individual messages according to the number of elements.

There are 2 use cases:

-   Splitting a bulk order message into multiple orders

-   Splitting a single order with multiple items




<a name="loio4b475eaac3de4ef1a9f434fd13cbb709__section_kwy_nk3_sjb"/>

## Use Cases

**Splitting a Bulk Order Message into Multiple Orders**

Let's assume that you have a bulk message that contains multiple orders. The bulk message is broken up into as many individual messages as there are orders.

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?>
> <ns0:PurchaseOrders xmlns:ns0="http://demo.sap.com/eip/splitter">
> 	<ns0:PurchaseOrder PurchaseOrderNumber="99501" OrderDate="2019-10-20">
> 		<Items>
> 			<Item ItemNumber="10">
> 				<ProductId>HT-1000</ProductId>
> 				<ProductName>Notebook Basic 15</ProductName>
> 				<Category>Notebooks</Category>
> 				<Quantity>1</Quantity>
> 				<CurrencyCode>EUR</CurrencyCode>
> 				<Price>956.00</Price>
> 			</Item>
> 			<Item ItemNumber="20">
> 				<ProductId>HT-1001</ProductId>
> 				<ProductName>Notebook Basic 17</ProductName>
> 				<Category>Notebooks</Category>
> 				<Quantity>1</Quantity>
> 				<CurrencyCode>EUR</CurrencyCode>
> 				<Price>1249.00</Price>
> 			</Item>
> 			</Items>
> 	</ns0:PurchaseOrder>
> 	<ns0:PurchaseOrder PurchaseOrderNumber="99502" OrderDate="2019-10-22">
> 			<Items>
> 				<Item ItemNumber="10">
> 					<ProductId>HT-1030</ProductId>
> 					<ProductName>Ergo Screen</ProductName>
> 					<Category>Flat screens</Category>
> 					<Quantity>2</Quantity>
> 					<CurrencyCode>EUR</CurrencyCode>
> 					<Price>460.00</Price>
> 				</Item>
> 				</Items>
> 	</ns0:PurchaseOrder>
> 	<ns0:PurchaseOrder PurchaseOrderNumber="99503" OrderDate="2019-10-22">
> 			<Items>
> 				<Item ItemNumber="10">
> 					<ProductId>HT-1101</ProductId>
> 					<ProductName>Smart Design</ProductName>
> 					<Category>Software</Category>
> 					<Quantity>10</Quantity>
> 					<CurrencyCode>EUR</CurrencyCode>
> 					<Price>799.00</Price>
> 				</Item>
> 				<Item ItemNumber="20">
> 					<ProductId>HT-1103</ProductId>
> 					<ProductName>Smart Multimedia</ProductName>
> 					<Category>Software</Category>
> 					<Quantity>20</Quantity>
> 					<CurrencyCode>EUR</CurrencyCode>
> 					<Price>1540.00</Price>
> 				</Item>
> 				</Items>
> 	</ns0:PurchaseOrder>
> </ns0:PurchaseOrders>
> ```

Resulting messages:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/splitter" PurchaseOrderNumber="99501" OrderDate="2019-10-20">
> 	<Items>
> 		<Item ItemNumber="10">
> 			<ProductId>HT-1000</ProductId>
> 			<ProductName>Notebook Basic 15</ProductName>
> 			<Category>Notebooks</Category>
> 			<Quantity>1</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>956.00</Price>
> 		</Item>
> 		<Item ItemNumber="20">
> 			<ProductId>HT-1001</ProductId>
> 			<ProductName>Notebook Basic 17</ProductName>
> 			<Category>Notebooks</Category>
> 			<Quantity>1</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>1249.00</Price>
> 		</Item>
> 	</Items>
> </ns0:PurchaseOrder>
> ```

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/splitter" PurchaseOrderNumber="99502" OrderDate="2019-10-21">
> 	<Items>
> 		<Item ItemNumber="10">
> 			<ProductId>HT-1030</ProductId>
> 			<ProductName>Ergo Screen</ProductName>
> 			<Category>Flat screens</Category>
> 			<Quantity>2</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>460.00</Price>
> 		</Item>
> 	</Items>
> </ns0:PurchaseOrder>
> ```

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/splitter" PurchaseOrderNumber="99503" OrderDate="2019-10-20">
> 	<Items>
> 		<Item ItemNumber="10">
> 			<ProductId>HT-1101</ProductId>
> 			<ProductName>Smart Design</ProductName>
> 			<Category>Software</Category>
> 			<Quantity>10</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>799.00</Price>
> 		</Item>
> 		<Item ItemNumber="20">
> 			<ProductId>HT-1103</ProductId>
> 			<ProductName>Smart Multimedia</ProductName>
> 			<Category>Software</Category>
> 			<Quantity>20</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>1540.00</Price>
> 		</Item>
> 	</Items>
> </ns0:PurchaseOrder>
> ```

**Splitting a Single Order with Multiple Items**

Let's assume that you have an order with multiple line items. The order needs to be broken up into as many individual messages as there are line items. The difference from the first use case is that the header information of the order needs to be duplicated for each individual message.

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?>
> <ns0:PurchaseOrder PurchaseOrderNumber="99401" OrderDate="2019-10-21" xmlns:ns0="http://demo.sap.com/eip/splitter">
> 	<Items>
> 		<Item ItemNumber="10">
> 			<ProductId>HT-1000</ProductId>
> 			<ProductName>Notebook Basic 15</ProductName>
> 			<Category>Notebooks</Category>
> 			<Quantity>1</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>956.00</Price>
> 		</Item>
> 		<Item ItemNumber="20">
> 			<ProductId>HT-1030</ProductId>
> 			<ProductName>Ergo Screen</ProductName>
> 			<Category>Flat screens</Category>
> 			<Quantity>2</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>460.00</Price>
> 		</Item>
> 		<Item ItemNumber="30">
> 			<ProductId>HT-1101</ProductId>
> 			<ProductName>Smart Design</ProductName>
> 			<Category>Software</Category>
> 			<Quantity>10</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>799.00</Price>
> 		</Item>
> 	</Items>
> </ns0:PurchaseOrder>
> ```

Resulting messages:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/splitter" PurchaseOrderNumber="99401" OrderDate="2019-10-21">
> 	<Items>
> 		<Item ItemNumber="10">
> 			<ProductId>HT-1000</ProductId>
> 			<ProductName>Notebook Basic 15</ProductName>
> 			<Category>Notebooks</Category>
> 			<Quantity>1</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>956.00</Price>		
> 		</Item>
> 	</Items>
> </ns0:PurchaseOrder>
> ```

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/splitter" PurchaseOrderNumber="99401" OrderDate="2019-10-21">
> 	<Items>
> 		<Item ItemNumber="20">
> 			<ProductId>HT-1030</ProductId>
> 			<ProductName>Ergo Screen</ProductName>
> 			<Category>Flat screens</Category>
> 			<Quantity>2</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>460.00</Price>
> 		</Item>
> 	</Items>
> </ns0:PurchaseOrder>
> ```

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <ns0:PurchaseOrder xmlns:ns0="http://demo.sap.com/eip/splitter" PurchaseOrderNumber="99401" OrderDate="2019-10-21">
> 	<Items>
> 		<Item ItemNumber="30">
> 			<ProductId>HT-1101</ProductId>
> 			<ProductName>Smart Design</ProductName>
> 			<Category>Software</Category>
> 			<Quantity>10</Quantity>
> 			<CurrencyCode>EUR</CurrencyCode>
> 			<Price>799.00</Price>
> 		</Item>
> 	</Items>
> </ns0:PurchaseOrder>
> ```



<a name="loio4b475eaac3de4ef1a9f434fd13cbb709__section_rwg_mk3_sjb"/>

## Implementation

SAP Cloud Integration supports 2 different Splitter flow steps out of the box: Iterating Splitter and General Splitter. You can also split messages using a multimessage mapping. All of these options are discussed in this section.

**Related Information**  


[Variant with Iterating Splitter](variant-with-iterating-splitter-24f9f29.md "")

[Variant with General Splitter](variant-with-general-splitter-cba1ecb.md "")

[Variant with Message Mapping](variant-with-message-mapping-f6bb2b7.md "")

