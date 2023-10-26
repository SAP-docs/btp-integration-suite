<!-- loio7c5e114c0f6d4690a2a8c25b163520d8 -->

# Use the JSON to XML and XML to JSON Converter

Learn how to transform a JSON file into an XML format and an XML into a JSON file.

This section shows you how you can configure the JSON to XML and XML to JSON converter.



<a name="loio7c5e114c0f6d4690a2a8c25b163520d8__section_k3s_qsn_5mb"/>

## Implementation

To showcase the capabilities of the JSON to XML and XML to JSON converter, we’ve implemented a simple integration scenario that is initiated by a sender \(using the HTTPS sender adapter\).

The example integration flow *Modeling Basics - JSON to XML Converter And XML to JSON Converter* is designed in the following way.

![](images/Converter_JSON_f0c6711.png)

The inbound message provided in JSON format is converted into an XML message. It has a simple structure and contains a root element with a product item. The Product item just contains a product ID. Furthermore, the XML Root Element “Products” is added to the message body.

The following settings are defined in the JSON to XML Converter under *Processing Settings*:


<table>
<tr>
<td valign="top">

**Attribute**

</td>
<td valign="top">

**Value**

</td>
</tr>
<tr>
<td valign="top">

Use Namespace Mapping

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

JSON Prefix Separator

</td>
<td valign="top">

Colon\(:\)

</td>
</tr>
<tr>
<td valign="top">

Add XML Root Element

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Products

</td>
</tr>
</table>

Message payload after *JSON to XML Converter* step:

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?> 
> 
> <Products> 
> 
>     <Product> 
> 
>         <ProductId>HT-8001</ProductId> 
> 
>     </Product> 
> 
> </Products> 
> ```

In the next step, the *Content Enricher* reads the data from the Webshop and appends the additional information to the original message. For our scenario, we use the ESPM WebShop, which is based on the Enterprise Sales and Procurement Model \(ESPM\) provided by SAP. The demo application can be accessed at the following address: [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html.](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html.)

The following settings are defined in the OData receiver adapter under *Processing Settings*:


<table>
<tr>
<td valign="top">

**Attribute**

</td>
<td valign="top">

**Value**

</td>
</tr>
<tr>
<td valign="top">

Operation Details

</td>
<td valign="top">

Query \(GET\)

</td>
</tr>
<tr>
<td valign="top">

Resource Path

</td>
<td valign="top">

Products

</td>
</tr>
<tr>
<td valign="top">

Query Options

</td>
<td valign="top">

$select=ProductId,Price,Category,QuantityUnit,ShortDescription,Name,CurrencyCode

</td>
</tr>
</table>

For *Aggregation Algorithm*, the *Enrich* option is chosen.

Under *ORIGINAL MESSAGE*, the following settings are defined:


<table>
<tr>
<td valign="top">

**Attribute**

</td>
<td valign="top">

**Value**

</td>
</tr>
<tr>
<td valign="top">

Path to Node

</td>
<td valign="top">

Products

</td>
</tr>
<tr>
<td valign="top">

Key Element

</td>
<td valign="top">

ProductId

</td>
</tr>
</table>

After having been processed by the *Content Enricher*, the message has the following structure and content:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8'?> 
> 
> <Products> 
> 
>     <Product> 
> 
>         <ProductId>HT-8001</ProductId> 
> 
>         <Product> 
> 
>             <CurrencyCode>EUR</CurrencyCode> 
> 
>             <Category>Notebooks</Category> 
> 
>             <Price>999.000</Price> 
> 
>             <ProductId>HT-8001</ProductId> 
> 
>             <QuantityUnit>EA</QuantityUnit> 
> 
>             <ShortDescription>1,6 Ghz, dual core, 60 GB HDD, Windows Vista Home Basic, 512 MB RAM+</ShortDescription> 
> 
>             <Name>ITelO FlexTop I6300c</Name> 
> 
>         </Product> 
> 
>     </Product> 
> 
> </Products> 
> ```

In an additional *Mapping* step, the redundant fields are removed.

After the Mapping step, the message has the following structure:

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?> 
> 
> <Products> 
> 
>     <Product> 
> 
>         <Category>Notebooks</Category> 
> 
>         <ProductId>HT-8001</ProductId> 
> 
>         <Price>999.000</Price> 
> 
>         <Name>ITelO FlexTop I6300c</Name> 
> 
>         <ShortDescription>1,6 Ghz, dual core, 60 GB HDD, Windows Vista Home Basic, 512 MB RAM+</ShortDescription> 
> 
>         <CurrencyCode>EUR</CurrencyCode> 
> 
>         <QuantityUnit>EA</QuantityUnit> 
> 
>     </Product> 
> 
> </Products> 
> ```

The following settings are defined in the *XML to JSON Converter* under *Processing Settings*:


<table>
<tr>
<td valign="top">

**Attribute**

</td>
<td valign="top">

**Value**

</td>
</tr>
<tr>
<td valign="top">

JSON Prefix Separator

</td>
<td valign="top">

Colon\(:\)

</td>
</tr>
<tr>
<td valign="top">

JSON Output Encoding

</td>
<td valign="top">

From Header or Property

</td>
</tr>
</table>

The output message has the following structure:

**JSON**:

> ### Sample Code:  
> ```
> { 
> 
>     "Products": { 
> 
>         "Product": { 
> 
>             "Category": "Notebooks", 
> 
>             "ProductId": "HT-8001", 
> 
>             "Price": "999.000", 
> 
>             "Name": "ITelO FlexTop I6300c", 
> 
>             "ShortDescription": "1,6 Ghz, dual core, 60 GB HDD, Windows Vista Home Basic, 512 MB RAM+", 
> 
>             "CurrencyCode": "EUR", 
> 
>             "QuantityUnit": "EA" 
> 
>         } 
> 
>     } 
> 
> } 
> 
>  
> ```

**Related Information**  


[Define JSON to XML Converter](define-json-to-xml-converter-5a7c0cd.md "The JSON to XML converter enables you to transform messages in JSON format to XML format.")

[Define XML to JSON Converter](define-xml-to-json-converter-a60a282.md "The XML to JSON converter enables you to transform messages in XML format to JSON format.")

[Access Header and Properties in XPath](access-header-and-properties-in-xpath-996ce78.md "Learn how to access header and exchange properties in XPath.")

[Creating Message Mapping as a Flow Step](creating-message-mapping-as-a-flow-step-3d5cb7f.md "")

