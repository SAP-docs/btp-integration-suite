<!-- loio996ce78e334648bd8a1ecf6e0d69ec6a -->

# Access Header and Properties in XPath

Learn how to access header and exchange properties in XPath.



You can use XML Path Language \(XPath\) to navigate through elements of an XML document.

Various elements of SAP Integration Suite support XPath. This section shows you how you can define XPath expressions using header values and exchange properties.



<a name="loio996ce78e334648bd8a1ecf6e0d69ec6a__section_b2f_dd4_smb"/>

## Implementation

To showcase the access to headers and exchange properties using XPath, we’ve implemented a simple integration scenario that is initiated by a sender \(using the HTTPS sender adapter\).

The example integration flow *Modeling Basics - Access Header And Properties In XPATH And Conditions* is designed the following way:

![](images/2008_Accessing-Headers_and_Properties_in_XPath_40e1a24.png)

The integration flow receives a message through an HTTPS adapter. In the message body, a product category and maxPrice are provided. Furthermore, the header `Accept` is provided which is either application/json or application/xml.

In a *Content Modifier* step, 2 exchange properties are defined: `category` and `maxPrice`. Type *XPath* defines that a particular element in the incoming message is retrieved through an XPath expression.  


<table>
<tr>
<td valign="top">

**Action**

</td>
<td valign="top">

**Name**

</td>
<td valign="top">

**Type**

</td>
<td valign="top">

**Data Type**

</td>
<td valign="top">

**Value**

</td>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

category

</td>
<td valign="top">

XPath

</td>
<td valign="top">

java.lang.String

</td>
<td valign="top">

//Category

</td>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

maxPrice

</td>
<td valign="top">

XPath

</td>
<td valign="top">

java.lang.String

</td>
<td valign="top">

//MaxPrice

</td>
</tr>
</table>

In a *Request Reply* step, product data is read from an external source through the OData protocol \(using the OData receiver adapter\). For our scenario, we use the ESPM WebShop, which is based on the Enterprise Sales and Procurement Model \(ESPM\) provided by SAP. The demo application can be accessed at the following address: [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html).

The query is defined as follows:

> ### Sample Code:  
> ```
> $select=ProductId,Category,CategoryName,CurrencyCode,DimensionDepth,DimensionHeight,DimensionUnit,DimensionWidth,LongDescription,Name,PictureUrl,Price,QuantityUnit,ShortDescription,SupplierId,Weight,WeightUnit&$filter=Category eq '${property.category}' 
> ```

The expression `${property.category}` is used to accessing the value of the `category` property at runtime.

In the *Filter* step, message property `maxPrice` is used to remove all unnecessary data items from the message, that is, all products are removed for which the price is higher than the specified max price.

The XPath expression is defined as follows:


<table>
<tr>
<td valign="top">

XPath Expression

</td>
<td valign="top">

//Products/Product\[./Price < $maxPrice\]

</td>
</tr>
<tr>
<td valign="top">

Value Type

</td>
<td valign="top">

Nodelist

</td>
</tr>
</table>

The expression `$maxPrice` is used to accessing the value of the `maxPrice` property.

The Context Modifier step *Body2XML* is necessary to store the message body in an XML structure:

> ### Sample Code:  
> ```
> <Products> 
> ${in.body} 
> </Products> 
> ```

In the next step, the message is routed to the receiver with the following conditions:


<table>
<tr>
<td valign="top">

**Order**

</td>
<td valign="top">

**Route Name**

</td>
<td valign="top">

**Condition Expression**

</td>
<td valign="top">

**Default Route**

</td>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

XML

</td>
<td valign="top">

 

</td>
<td valign="top">

X

</td>
</tr>
<tr>
<td valign="top">

2

</td>
<td valign="top">

JSON

</td>
<td valign="top">

$\{header.Accept\} = 'application/json'

</td>
<td valign="top">

 

</td>
</tr>
</table>

The expression `${header.Accept}` is used to access the value of the `Accept` header.

If the message header `Accept` has the value `application/json`, the message is converted to JSON in the next step.

To access the incoming HTTP header values, enter the HTTP header parameter names into the *Allowed Header\(s\)* field in the *Runtime Configuration* settings of the integration flow.

For more information on how to access the incoming HTTP header in the integration flow, see [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md).

**Related Information**  


[Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md "Specify the runtime properties of the integration flow.")

[Define Router](define-router-d7fddbd.md "")

[About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md "")

