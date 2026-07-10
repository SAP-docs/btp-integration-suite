<!-- loioc6bf239803be452789d7f5ea75e59c7d -->

# Perform an XSLT Mapping

Define an XSLT mapping dynamically based on partner-specific information stored in the Partner Directory.

To illustrate this rule, check out the *Partner Directory - XSLT Mapping* integration flow. It is modeled as shown in the figure.

![](images/Guidelines_Partner_Directory_XSLT_Mapping_604fa33.png)

This integration flow reads binary parameters from the Partner Directory. These parameters are partner-specific. You can use this integration flow for different partners with different mappings and schemas.

The integration flow performs the following steps:

1.  It receives a request from the corresponding Postman collection. This request provides the partner id \(`PartnerA`\) in the request body.

    > ### Sample Code:  
    > ```
    > <?xml version="1.0" encoding="ISO-8859-1"?>
    > <Order>
    >   <Header>
    >     <PID>PartnerA</PID>
    >     <CredentialsName>ReceiverCredentials</CredentialsName>
    >   </Header>
    >   <Customer>
    >     <Name>Jon Doe AG</Name>
    >     <Id>1234567890</Id>
    >     <Mail>jon.doe@sap.com</Mail>
    >     <Telephone>+40 1234 567890</Telephone>
    >   </Customer>
    >   <Items>
    >     <Item>
    >       <ProductId>A111</ProductId>
    >       <Description>Description</Description>
    >       <Price>5.00</Price>
    >       <Qtty>1</Qtty>
    >     </Item>
    >     <Item>
    >       <ProductId>B222</ProductId>
    >       <Description>Description</Description>
    >       <Price>10.00</Price>
    >       <Qtty>1</Qtty>
    >     </Item>
    >     <Item>
    >       <ProductId>C333</ProductId>
    >       <Description>Description</Description>
    >       <Price>20.00</Price>
    >       <Qtty>1</Qtty>
    >     </Item>
    >   </Items>
    > </Order>
    > ```

2.  The Content Modifier *read PartnerId* gets the partner ID \(value of element `PID`\) from the payload \(using the XPath expression `//Header/PID`\) and saves it as property.

3.  The Content Modifier *write Pid in Header* defines the following headers based on information stored in the Partner Directory. The `PartnerId` property defined in the previous step is used to define the following headers:

    ****


    <table>
    <tr>
    <th valign="top">

    Header
    
    </th>
    <th valign="top">

    Expression
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    MyMappingSchema
    
    </td>
    <td valign="top">
    
    `pd:${property.PartnerId}:MyMappingSchema:Binary`
    
    </td>
    <td valign="top">
    
    Mapping schema used by the partner

    With this schema, the relevant binary is stored in the header and can now be used in the subsequent integration flow steps, for example, the XSLT Mapping step.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MyMapping
    
    </td>
    <td valign="top">
    
    `pd:${property.PartnerId}:MyMapping:Binary` 
    
    </td>
    <td valign="top">
    
    Partner-specific mapping
    
    </td>
    </tr>
    </table>
    
4.  The XSLT Mapping step *xslt from PD* uses header `MyMapping` to identify which mapping to process.

5.  The XML Validator step *validate XML* validates the XML based on the partner-specific schema. Which schema to use is specified through the header `MyMappingSchema`.

6.  The Content Modifier *Define context for monitoring purposes* sets the `context` and `receiver` headers for the subsequent *Generic Receiver* integration flow.

    The headers are defined with the following expressions:

    ****


    <table>
    <tr>
    <th valign="top">

    Header
    
    </th>
    <th valign="top">

    Expression
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    context
    
    </td>
    <td valign="top">
    
    `PartnerDirectory-XSLT`
    
    </td>
    <td valign="top">
    
    Defines the Data Store name. In this case, the name reflects this guideline.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    receiver
    
    </td>
    <td valign="top">
    
    `Partner ${property.PartnerId}` 
    
    </td>
    <td valign="top">
    
    Defines the Data Store entry ID. In this case, the value is given by the partner ID from the Partner Directory.
    
    </td>
    </tr>
    </table>
    
7.  Finally, the integration flow calls the *Generic Receiver* integration flow.


To process the integration flow, perform the following steps:

1.  Deploy the integration flows *Partner Directory - XSLT Mapping* and *Generic Receiver*.

2.  Start the Postman Runner and select collection *CPI Partner Directory Example Flows*.

3.  Select folder *XSLT* in the folder structure for the relevant cloud environment \(under *Neo Environment* \> *Integration Flows \(Neo\)* or *CF Environment* \> *Integration Flows \(CF\)*\).

4.  Start the Postman runner for this folder.


On successful processing, the integration flow creates the following Data Store entry:

-   Data Store name: *PartnerDirectory-XSLT*

-   Data Store entry ID: *Partner <PID\>*


