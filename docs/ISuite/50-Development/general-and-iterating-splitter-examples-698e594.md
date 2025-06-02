<!-- loio698e594132b144178a4eb4795316947a -->

# General and Iterating Splitter \(Examples\)



<a name="loio698e594132b144178a4eb4795316947a__SplitterExamplesLineBreak"/>

## Example for General Splitter and Iterating \(Non-XML Message\)

If you expect a non-XML file as the input message and, as a result, select *Line Break* in the *Expression Type* field, General Splitter and Iterative Splitter process the message differently, as shown for the following example.

Let's assume the input message has the following content:

> ### Sample Code:  
> ```
> "Customer Number", "No of Ordered Articles", "Price"
> "0001", "100", "1000 EUR"
> "0009", "1", "10000 EUR"
> "0011", "20", "999 EUR"
> ```

The *General Splitter* transforms the inbound message into the following **three** messages:

```
"Customer Number", "No of Ordered Articles", "Price"
"0001", "100", "1000 EUR"

```

```
"Customer Number", "No of Ordered Articles", "Price"
"0009", "1", "10000 EUR"

```

```
"Customer Number", "No of Ordered Articles", "Price"
"0011", "20", "999 EUR"
```

> ### Note:  
> The *General Splitter* interprets the first line of the inbound message as header or root element.

The *Iterating Splitter* transforms the inbound message into the following **four** messages:

```
"Customer Number", "No of Ordered Articles", "Price"

```

```
"0001", "100", "1000 EUR"

```

```
"0009", "1", "10000 EUR"

```

```
"0011", "20", "999 EUR"
```

> ### Note:  
> The *Iterating Splitter* handles the first line of the inbound message in the same way like the other lines. The first line is not interpreted as a root element.

A line break can also be defined by an escape character \(`\n` or `\r`\).

Let's assume the input message has the following content:

> ### Sample Code:  
> ```
> "Customer Number", "No of Ordered Articles", "Price"\n"0001", "100", "1000 EUR"\n"0009", "1", "10000 EUR"\n"0011", "20", "999 EUR"
> ```

The *General Splitter* and the *Iterating Splitter* transforms the inbound message into the same messages like in the example above.



<a name="loio698e594132b144178a4eb4795316947a__SplitterExamplesXPathGeneralSplitter"/>

## Example for General Splitter \(XML Message\)

Assume you expect an XML message and like to address elements with *Expression Type* set to *XPath*. This is an example for an input message representing items ordered by a certain customer.

```
<customer xmlns="http://myCustomer.com">
    <customerNumber>0001</customerNumber>
    <customerName>Paul Smith</customerName>
    <order id="100">
        <items>
            <item>Shirt</item>
            <item>Shoe</item>
        </items>
    </order>                             
    <order id="101">
        <items>
            <item>Shoe</item>
            <item>Car</item>
            <item>Watch</item>
        </items>
    </order>             
</customer>

```

To split this message, you need to define a namespace mapping \(of a prefix and a namespace\) for the integration flow \(under *Runtime Configuration*\), for example: `xmlns:n1=http://myCustomer.com`.

When configuring the *General Splitter* and wanting to address the message element with an XPath expression, make sure that you refer to the namespace prefix by using the following XPath expression: `/n1:customer/n1:order`.

Aditonally, you can also use a reference to a header or property instead of a fixed value for XPath Expression, for example: `${header.expression}`.

> ### Note:  
> Namespaces are inherited from parent to child element. This is why you need to indicate the namespace explicitly in the XPath expression.

Then, the message is split with the *General Splitter* into the following two chunks:

```
<customer xmlns="http://myCustomer.com">
    <customerNumber>0001</customerNumber>
    <customerName>Paul Smith</customerName>
    <order id="100">
        <items>
            <item>Shirt</item>
            <item>Shoe</item>
        </items>
    </order>             
</customer>

```

```
<customer xmlns="http://myCustomer.com">
    <customerNumber>0001</customerNumber>
    <customerName>Paul Smith</customerName>           
    <order id="101">
        <items>
            <item>Shoe</item>
            <item>Car</item>
            <item>Watch</item>
        </items>
    </order>             
</customer>

```



<a name="loio698e594132b144178a4eb4795316947a__section_xjh_cbm_v1b"/>

## Example for Iterating Splitter \(XML Message\)

This is an example for an input message representing orders from different customers.

```
<customerList xmlns="http://myCustomer.com">
    <customers>
        <customerNumber>0001</customerNumber>
        <customerName>Paul Smith</customerName>
	</customers>
    <customers>
        <customerNumber>0002</customerNumber>
        <customerName>Seena Kumar</customerName>
    </customers>
</customerList>
```

To split this message, you need to define a namespace mapping \(of a prefix and a namespace\) for the integration flow \(under *Runtime Configuration*\), for example: `xmlns:n2=http://myCustomer.com`.

Use the following XPath expression: `/n2:customerList/n2:customers`, or enter a reference to a header or property instead of a fixed value for XPath Expression.

The *Iterating Splitter* splits the message into the following two chunks:

```
<customers xmlns="http://myCustomer.com>
    <customerNumber>0001</customerNumber>
    <customerName>Paul Smith</customerName>
</customers>

```

```
<customers xmlns="http://myCustomer.com">
    <customerNumber>0002</customerNumber>
    <customerName>Seena Kumar</customerName>
</customers>

```



<a name="loio698e594132b144178a4eb4795316947a__section_wvw_22y_2mb"/>

## Example for Iterating Splitter \(XML Message and Token Expression Type\)

This is an example for an input message representing orders from different customers.

```
<customerList>
    <customers>
        <customerNumber>0001</customerNumber>
        <customerName>Paul Smith</customerName>
	</customers>
    <customers>
        <customerNumber>0002</customerNumber>
        <customerName>Seena Kumar</customerName>
    </customers>
</customerList>
```

In the Iterating Splitter, as *Expression Type* select *Token* and in field *Token* enter `customers`.

The *Iterating Splitter* splits the message into the following two chunks:

```
<customers xmlns="http://myCustomer.com>
    <customerNumber>0001</customerNumber>
    <customerName>Paul Smith</customerName>
</customers>

```

```
<customers>
        <customerNumber>0002</customerNumber>
        <customerName>Seena Kumar</customerName>
</customers>
```

In the Iterating Splitter, as *Expression Type* select *Token* and in field *Token* enter `customerName`.

The *Iterating Splitter* splits the message into the following two chunks:

```
<customerName>Paul Smith</customerName>
```

```
<customerName>Seena Kumar</customerName>
```



For more examples, see the following SAP Community blog: [SAP Cloud Integration – Splitter](https://blogs.sap.com/2019/11/08/sap-cloud-platform-integration-splitter/).

**Related Information**  


[Using XPath Expressions in the Splitter Step](using-xpath-expressions-in-the-splitter-step-c6e63f1.md "")

