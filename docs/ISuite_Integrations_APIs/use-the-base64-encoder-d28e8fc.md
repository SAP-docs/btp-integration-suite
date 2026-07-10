<!-- loiod28e8fcd750c4e95aafb2abad26b7e40 -->

# Use the Base64 Encoder

Learn how to use the Base64 Encoder. 

You use this step to convert any binary data into text data. You can use an encoder if you need to transfer data over a medium that only supports the exchange of textual data.



<a name="loiod28e8fcd750c4e95aafb2abad26b7e40__section_b44_vpk_cnb"/>

## Use Case

Assume that you like to add an image to a product details message and you like to transfer this message to a medium that only works with textual data.



<a name="loiod28e8fcd750c4e95aafb2abad26b7e40__section_vnx_zpk_cnb"/>

## Implementation

The example integration flow *Modeling Basics - Base64 Encoder* is designed in the following way:

![](images/base64_Encoder_Flow_548e89a.png)

The integration flow performs the following steps:

It receives a message containing an image of a product through an HTTPS adapter. Furthermore, the request contains a header including the ProductID.

-   Image: `ProductImage_DVD.jpg`

-   ProductID: `HT-2001` 


The Base64 Encoder step encodes the image.

The Content Modifier stores the encoded image string in the exchange property `productImage` based on the following settings \(tab *Exchange Property*\):


<table>
<tr>
<th valign="top">

Action

</th>
<th valign="top">

Name

</th>
<th valign="top">

Type

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

productImage

</td>
<td valign="top">

Expression

</td>
<td valign="top">

java.lang.String

</td>
<td valign="top">

$\{in.body\}

</td>
</tr>
</table>

Furthermore, the body needs to be assigned the constant *None* because the subsequent OData request does not support an encoded message. Therefore, in tab *Message Body* the following settings are configured:

The *Type* parameter is set to *Constant* and in the *Body* entry field, the string `None` is entered.

In a Request Reply step, product data is read from an external source \(the WebShop component\) through the OData protocol \(using the OData receiver adapter\).

The external data source supports the Open DataProtocol \(OData\). For our scenario, we use the ESPM WebShop, which is based on the Enterprise Sales and Procurement Model \(ESPM\) provided by SAP. The demo application can be accessed at the following address: [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html)

The query is defined as follows:

> ### Sample Code:  
> ```
> $select=ProductId,Category,CategoryName,CurrencyCode,DimensionDepth,DimensionHeight,DimensionUnit,DimensionWidth,LongDescription,Name,Price,QuantityUnit,ShortDescription,SupplierId,Weight,WeightUnit&$filter=ProductId eq '${header.productID}'  
> ```

Finally, in a Message Mapping, the response from the OData request as well as the property *productImage* are mapped to a product structure.

To execute the scenario, perform the following steps:

Import the Postman collection provided with the integration package and select the *Base64Encoder* request in folder *Base64EncoderDecoder*.

**Related Information**  


[Define an Encoder](define-an-encoder-89f8bdd.md "You use this task to encode messages using an encoding scheme to secure any sensitive message content during transfer over the network.")

[Message Mapping](message-mapping-459ccdf.md "")

[Access Header and Properties in Message Mapping](access-header-and-properties-in-message-mapping-4f2a8c9.md "Learn how to access header and exchange properties in a message mapping.")

[Define a Local Script Step](define-a-local-script-step-03b32eb.md "Learn how to use a script step that’s specific to an integration artifact to create custom scripts (JavaScript or Groovy Script).")

