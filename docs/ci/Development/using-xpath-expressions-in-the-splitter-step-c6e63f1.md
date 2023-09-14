<!-- loioc6e63f1397c74dceb1153ff580268031 -->

# Using XPath Expressions in the Splitter Step



<a name="loioc6e63f1397c74dceb1153ff580268031__section_l23_vjn_gkb"/>

## Relative XPath - Split Point Appears Under the Same Parent Element

Relative paths are only supported if the split point is on the same level and under the same root path.

Assume that the addressed element occurs always under the same parent element.

Example inbound message:

> ### Sample Code:  
> ```
> 
> <root>
> 	<shop>
> 		<customerReview>
> 			<id>3</id>
> 			<id>4</id>
> 		</customerReview>
> 	</shop>
> </root>
> 
> ```

Specifying the relative XPath expression `//id` in the General Splitter leads to the following result messages:

> ### Sample Code:  
> ```
> 
> <root>
> 	<shop>
> 		<customerReview>
> 			<id>3</id>
> 		</customerReview>
> 	</shop>
> </root>
> 
> ```

```

<root>
	<shop>
		<customerReview>
			<id>4</id>
		</customerReview>
	</shop>
</root>

```

This result is straightforward and reflects likely the expected behavior.



<a name="loioc6e63f1397c74dceb1153ff580268031__section_e5m_1kn_gkb"/>

## Relative XPath - Split Point Appears Under Different Parent Elements

The same element occurs under different parent elements in the inbound message.

If a relative XPath points to an element that appears under different parent elements in the inbound message, the *General Splitter* works in the following way.

In the example inbound message, element `id` occurs under 2 different parent elements \(`products` and `customerReview`\):

> ### Sample Code:  
> ```
> 
> <root>
> 	<shop>
> 		<product>
> 			<id>1</id>
> 			<id>2</id>
> 		</product>
> 		<customerReview>
> 			<id>3</id>
> 			<id>4</id>
> 		</customerReview>
> 	</shop>
> </root>
> 
> ```

In this case, it's recommended that in the General Splitter you specify the relative XPath expression that contains the parent element you like to address, for example: `//customerReview/id`. Then, the General Splitter provides the following result messages:

> ### Sample Code:  
> ```
> 
> <root>
> 	<shop>
> 		<product>
> 			<id>1</id>
> 			<id>2</id>
> 		</product>
> 		<customerReview>
> 			<id>3</id>
> 		</customerReview>
> 	</shop>
> </root>
> 
> ```

> ### Sample Code:  
> ```
> 
> <root>
> 	<shop>
> 		<product>
> 			<id>1</id>
> 			<id>2</id>
> 		</product>
> 		<customerReview>
> 			<id>4</id>
> 		</customerReview>
> 	</shop>
> </root>
> 
> ```

The resulting messages are split according to the element for which also 1 parent element is addressed in the relative XPath \(`//customerReview/id`\).

However, in case you specify the relative XPath expression `//id` in the General Splitter, you get 4 result messages:

> ### Sample Code:  
> ```
> <root>
> 	<shop>
> 		<product>
> 			<id>1</id>
> 		</product>
> 	</shop>
> </root>
> ```

> ### Sample Code:  
> ```
> <root>
> 	<shop>
> 		<product>
> 			<id>2</id>
> 		</product>
> 	</shop>
> </root>
> ```

> ### Sample Code:  
> ```
> <root>
> 	<shop>
> 		<product>
> 			<id>3</id>
> 		</product>
> 	</shop>
> </root>
> ```

> ### Sample Code:  
> ```
> <root>
> 	<shop>
> 		<product>
> 			<id>4</id>
> 		</product>
> 	</shop>
> </root>
> ```

In this case, the message is split according to the addressed element, but the split point occurs in certain result messages obviously under an unexpected parent element: Although the inbound message parts `<id>3</id>` and `<id>4</id>` are under the parent element `customerReview`, the General Splitter puts them under the parent element `products`. This result might not correspond to what you expect.



<a name="loioc6e63f1397c74dceb1153ff580268031__section_y1y_nh2_fqb"/>

## Default XML Namespaces

The following inbound message contains the declaration of a default namespace that applies to all elements \(as no prefixes are used\):

> ### Sample Code:  
> ```
> <root xmlns="demo.sap.com">
> 	<shop>
> 		<customerReview>
> 			<id>001</id>
> 			<rating>4</rating>
> 		</customerReview>
> 		<customerReview>
> 			<id>002</id>
> 			<rating>1</rating>
> 		</customerReview>
> 	</shop>
> </root>
> 
> ```

If you want to split the message at the `customerReview` element, make sure to enter the following XPath expression when defining the *Splitter* step:

`/ns1:root/ns1:shop/ns1:customerReview xmlns:ns1="demo.sap.com"`

Note that if you enter the following XPath expression, you get an error when saving the integration flow:

`/root/shop/customerReview xmlns="demo.sap.com"`

You get 2 result messages:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <root xmlns="demo.sap.com">
> 	<shop>
> 		<customerReview>
> 			<id>001</id>
> 			<rating>4</rating>
> 		</customerReview>
> 	</shop>
> </root>
> ```

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?>
> <root xmlns="demo.sap.com">
> 	<shop>
> 		<customerReview>
> 			<id>002</id>
> 			<rating>1</rating>
> 		</customerReview>
> 	</shop>
> </root>
> ```

