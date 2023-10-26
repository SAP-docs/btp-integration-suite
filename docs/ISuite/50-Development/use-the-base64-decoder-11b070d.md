<!-- loio11b070ddb79c42d0ba22476cbf45f426 -->

# Use the Base64 Decoder

Learn how to use the Base64 Decoder.

You use encoding and decoding if you need to transfer data over a medium that only supports the exchange of textual data.



<a name="loio11b070ddb79c42d0ba22476cbf45f426__section_wkl_v5k_cnb"/>

## Implementation

To showcase the Base64 Decoder, we exchange product information, including a product image that is Base64-encoded.

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?> 
> 
> <Product> 
> 
>     <ProductId>HT-2001</ProductId> 
> 
>     <Category>Portable Players</Category> 
> 
>     <CategoryName>Portable Players</CategoryName> 
> 
>     <CurrencyCode>EUR</CurrencyCode> 
> 
>     <DimensionDepth>0.1950</DimensionDepth> 
> 
>     <DimensionHeight>0.2900</DimensionHeight> 
> 
>     <DimensionUnit>m</DimensionUnit> 
> 
>     <DimensionWidth>0.2400</DimensionWidth> 
> 
>     <LongDescription>10 inch LCD Screen, storage battery holds up to 8 hours</LongDescription> 
> 
>     <Name>10 inch Portable DVD player</Name> 
> 
>     <Price>449.900</Price> 
> 
>     <QuantityUnit>EA</QuantityUnit> 
> 
>     <ShortDescription>10 inch LCD Screen, storage battery holds up to 8 hours</ShortDescription> 
> 
>     <SupplierId>100000043</SupplierId> 
> 
>     <Weight>0.840</Weight> 
> 
>     <WeightUnit>KG</WeightUnit>                  
> 
>     <ProductImage>iVBORw0KGgoAAAANSUhEUgAAAK4AAACYCAIAAADyTUUJAAAAAXNSR0IArs4c6QAAAA 
>      RnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAGhjSURBVHhe7X0HfBVV+rarQHrvvfee3N6 
>      Sm95775U0QkIakJBC 
> 
>      …. 
> 
>      Y8K98DiHhXugcU9KtwDi3tUuAcW96hwDyzuUeEeWNyjwj2wuEeFe2Bxjwr3wOIeFe6Bwbff/j8UG8q8KHi6vgAAA 
>      ABJRU5ErkJggg==</ProductImage> 
> 
> </Product> 
> ```

The example integration flow *Modeling Basics - Base64 Decoder* is designed in the following way:

![](images/Base64_Decoder_Flow_9b55f28.png)

The integration flow performs the following steps:

It receives a message through an HTTPS adapter. The message body is an XML document that contains product information and a product image. The latter one is encoded using Base64.

The scenario works that way that it separates the product image from the message, decodes it, and transmits it to the receiver system.

The Content Modifier *Define Properties* stores the base64-encoded image string in the exchange property `productImage` using the following settings \(tab *Exchange Property*\):


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

XPath

</td>
<td valign="top">

java.lang.String

</td>
<td valign="top">

//ProductImage

</td>
</tr>
</table>

The same step overwrites the payload with the property value `${property.productImage}` using the following settings \(in tab *Message Body*\):

The *Type* parameter is set to *Expression* and in the *Body* entry field, the string `${property.productImage}` is entered.

After this step, the message body contains the encoded image.

In the next step, the message body is decoded using the Base64 Decoder.

Finally, the message is sent to the *Generic Receiver* and stored in the Data Store \(from where you can download the image\).

To execute the scenario, perform the following steps:

Import the Postman collection provided with the integration package and select the *Base64Decoder* request in folder *Base64EncoderDecoder*.

After the message processing run, you find the final message in the Data Store *ModelingBasics-Base64Decoding*.

**Related Information**  


[Define a Decoder](define-a-decoder-c95697a.md "You use this task to decode the message received over the network to retrieve original data.")

