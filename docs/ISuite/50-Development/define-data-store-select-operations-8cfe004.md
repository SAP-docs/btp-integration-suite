<!-- loio8cfe004231bd45d9bdf497eced857cc9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Data Store Select Operations

This step selects entries from a transient data store and creates a bulk message containing the data store entries.



## Context

A data store operations step has to be triggered explicitly, for example, by a Timer event.

> ### Note:  
> A data store can be created during message processing using the following options:
> 
> -   Process a data store Write operation
> 
> -   Create a data store in an XI adapter \(the option *Data Store* must be selected in the *Temporary Storage* parameter\)

> ### Tip:  
> For more information about the data store component and guidelines when to use it, see:
> 
> -   [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md)
> 
> -   [Data Store/Variables Versus Header/Properties: When to Use Which Option?](data-store-variables-versus-header-properties-when-to-use-which-option-61f4045.md)
> 
> -   [Data Store, Variables, and JMS Queues: When to Use Which Option?](data-store-variables-and-jms-queues-when-to-use-which-option-6bc21cb.md)
> 
> 
> For examples, see: [Examples](examples-c8ba267.md)

> ### Caution:  
> This step overwrites the body of the input message.

This step selects messages from the data store and provides as output a bulk message with all entries, according to the specified value of the parameter *Number of Polled Messages*.



<a name="loio8cfe004231bd45d9bdf497eced857cc9__steps_rsl_lyx_wx"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Persistence\), then *Data Store Operations* \> *Select*.

2.  Place the *Select* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *Select* operation.

4.  On the *Processing* tab, define the attributes of the data store operation based on the descriptions in the following table. The set of attributes depends on the chosen operation.


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Data Store Name* 
    
    </td>
    <td valign="top">
    
    Specifies the name of the data store \(no white spaces\).

    The maximum length allowed for the data store name is 40 characters. If you enter a longer string, a validation error is raised. Note that this length restriction applies to the value that is used for this parameter at runtime. Therefore, if you configure this parameter dynamically, make sure that the expected header or property value does not exceed this length restriction. Otherwise, a runtime error will be raised.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Visibility* 
    
    </td>
    <td valign="top">
    
    Defines whether the data store is shared by all integration flows \(deployed on the tenant\) or only by one specific integration flow.

    -   *Global*: Data store is shared across all integration flows deployed on the tenant.

    -   *Integration Flow*: Data store is used by one integration flow. A data store configured with this setting is also referred to as local data store.


    For more information and guidelines how to use this parameter, see [Anticipate Message Throughput When Choosing a Storage Option](anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Number of Polled Messages* 
    
    </td>
    <td valign="top">
    
    Specifies the maximum number of messages to be fetched from the data store within one poll \(default is 1\).

    If the number of messages fetched per poll is specified in the header `SapDataStoreMaxResults`, the header takes the precedence.

    You can also configure this property in such a way that the number of fetched messages per poll is dynamically evaluated at runtime based on the incoming message. To do this, you can enter the following expressions:

    -   `${header.headername}`, to dynamically retrieve the number of fetched messages per poll from the message header

    -   `${xpath.<xpath>}`, to dynamically retrieve the number of fetched messages per poll from an element in the message indicated by an xPath expression



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Delete on Completion* 
    
    </td>
    <td valign="top">
    
    Select this option to delete a message from the data store after having successfully processed the message.
    
    </td>
    </tr>
    </table>
    
5.  Save the changes.




<a name="loio8cfe004231bd45d9bdf497eced857cc9__result_ogy_jys_lz"/>

## Results

This step provides an output message with a structure as defined by the following DTD content.

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?>
> <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
> 	<xs:element name="messages">
> 		<xs:complexType>
> 			<xs:sequence minOccurs="0" maxOccurs="unbounded">
> 				<xs:element name="message" type="messageType" />
> 			</xs:sequence>
> 		</xs:complexType>
> 	</xs:element>
> 	<xs:complexType name="messageType" mixed="true">
> 		<xs:sequence minOccurs="0" maxOccurs="unbounded">
> 			<xs:any namespace="##any" processContents="lax" />
> 		</xs:sequence>
> 		<xs:attribute name="id" type="idType" use="required" />
> 	</xs:complexType>
> 	<xs:simpleType name="idType">
> 		<xs:restriction base="xs:string">
> 			<xs:maxLength value="255" />
> 		</xs:restriction>
> 	</xs:simpleType>
> </xs:schema>
> 
> ```

Example structure for the case when two messages are retrieved from the data store:

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?>
> <messages>
>     <message id="<ID of first message>">
>         <content of first message>
>     </message>
>     <message id="<ID of second message>">
> 
>         <content of second message>
>     </message>
> <messages>
> ```

There is no in-order processing of data store entries. In other words, the sequence of data store entries selected with a `Select` operation is random and non-deterministic. If you have restricted the number of entries to be fetched \(with the *Number of Polled Messages* attribute\), the selection of retrieved entries is also random.



<a name="loio8cfe004231bd45d9bdf497eced857cc9__postreq_gwy_yqx_tfb"/>

## Next Steps

To find out how a data store Select operation works, you can enhance the sample integration flow *Timer-Initiated Scenario with a Mail Receiver* with a few clicks.

More information on the sample integration flow: [Timer-Initiated Scenario with a Mail Receiver](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/bfee17e150de43c9a1b363746c5a7e72.html "Create a simple integration scenario that is initiated by a timer, retrieves data from an external source, and sends the result to an e-mail account (as the receiver system).") :arrow_upper_right:

Enhance the sample integration flow in the following way:

-   Add a data store Write step after the Request Reply step.

-   Add a data store Select step after the data store Write step.


![](images/Data_Store_Select_Example_4ab1fec.png)

When you deploy and run the integration flow once, the received message looks like this \(example settings\):

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?>
> <messages>
> <message id="9197e678-345e-4e3b-ae51-3bfaa8990918">
> <Products>
>     <Product>
>       <WeightUnit>KG</WeightUnit>
>       <CategoryName>Scanners</CategoryName>
>       <DimensionHeight>0.07</DimensionHeight>
>       <DimensionUnit>m</DimensionUnit>
>       <CurrencyCode>EUR</CurrencyCode>
>       <ProductId>HT-1081</ProductId>
>       <ShortDescription>Flatbed scanner - 1200 dpi x 1200 dpi - 216 x 297 mm - Hi-Speed USB  - Bluetooth Ver. 1.2</ShortDescription>
>       <Name>Power Scan</Name>
>       <Category>Scanners</Category>
>       <LongDescription>Flatbed scanner - 1200 dpi x 1200 dpi - 216 x 297 mm - Hi-Speed USB  - Bluetooth Ver. 1.2</LongDescription>
>       <QuantityUnit>EA</QuantityUnit>
>       <Weight>2.4</Weight>
>       <DimensionWidth>0.31</DimensionWidth>
>       <Price>89.0</Price>
>       <PictureUrl>HT-1081.jpg</PictureUrl>
>       <DimensionDepth>0.43</DimensionDepth>
>       <SupplierId>100000049</SupplierId>
>     </Product>
>   </Products>
> </message>
> </messages>
> ```

In the data store Select step, specify a value bigger than `1` for the parameter *Number of Polled Messages*. Then, in the first content modifier \(on the *Body* tab\), specify a different value for the element `productIdentifier` than for the first message processing run. When you deploy and run the integration flow again, the resulting message \(after the integration flow has been processed\) should look like this:

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8"?>
> <messages>
> <message id="9197e678-345e-4e3b-ae51-3bfaa8990918">
> <Products>
>     <Product>
>       <WeightUnit>KG</WeightUnit>
>       <CategoryName>Scanners</CategoryName>
>       <DimensionHeight>0.07</DimensionHeight>
>       <DimensionUnit>m</DimensionUnit>
>       <CurrencyCode>EUR</CurrencyCode>
>       <ProductId>HT-1081</ProductId>
>       <ShortDescription>Flatbed scanner - 1200 dpi x 1200 dpi - 216 x 297 mm - Hi-Speed USB  - Bluetooth Ver. 1.2</ShortDescription>
>       <Name>Power Scan</Name>
>       <Category>Scanners</Category>
>       <LongDescription>Flatbed scanner - 1200 dpi x 1200 dpi - 216 x 297 mm - Hi-Speed USB  - Bluetooth Ver. 1.2</LongDescription>
>       <QuantityUnit>EA</QuantityUnit>
>       <Weight>2.4</Weight>
>       <DimensionWidth>0.31</DimensionWidth>
>       <Price>89.0</Price>
>       <PictureUrl>HT-1081.jpg</PictureUrl>
>       <DimensionDepth>0.43</DimensionDepth>
>       <SupplierId>100000049</SupplierId>
>     </Product>
>   </Products>
> </message>
> <message id="b4c0f332-ec8e-4edf-81d8-3a64f374123c">
> <Products>
>     <Product>
>       <WeightUnit>KG</WeightUnit>
>       <CategoryName>Scanners</CategoryName>
>       <DimensionHeight>0.05</DimensionHeight>
>       <DimensionUnit>m</DimensionUnit>
>       <CurrencyCode>EUR</CurrencyCode>
>       <ProductId>HT-1080</ProductId>
>       <ShortDescription>Flatbed scanner - 1200 dpi x 1000 dpi - 216 x 297 mm - Hi-Speed USB  - Bluetooth Ver. 1.2</ShortDescription>
>       <Name>Photo Scan</Name>
>       <Category>Scanners</Category>
>       <LongDescription>Flatbed scanner - 1200 dpi x 1000 dpi - 216 x 297 mm - Hi-Speed USB  - Bluetooth Ver. 1.2</LongDescription>
>       <QuantityUnit>EA</QuantityUnit>
>       <Weight>2.3</Weight>
>       <DimensionWidth>0.34</DimensionWidth>
>       <Price>51.0</Price>
>       <PictureUrl>HT-1080.jpg</PictureUrl>
>       <DimensionDepth>0.48</DimensionDepth>
>       <SupplierId>100000041</SupplierId>
>     </Product>
>   </Products>
> </message>
> </messages>
> ```

You can monitor the content of the data store in the *Monitor* section. Under *Manage Stores*, choose the *Data Stores* tile. For more information, see [Managing Data Stores](managing-data-stores-ac39f1d.md).

