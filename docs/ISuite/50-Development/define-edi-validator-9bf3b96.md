<!-- loio9bf3b965a5c74365b44cd24f473e29e7 -->

# Define EDI Validator

The EDI validator validates the message payload in EDI flat file format against the configured XSD schema.



## Context

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

EDI validator supports UN-EDIFACT, ODETTE and ASC-X12 document types. You use this procedure to assign XSD files to validate the message payload in a process step. The validator checks the message payload against configured XSD schema, and throws an exception in case of discrepancy.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> -   EDI Validator version 1.4 and above supports EDIFACT Syntax version 2 in addition to version 3 and 4.
> -   Contact the Cloud Integration Team to obtain EDI related XSD files.
> -   EDI Validator version 1.5 and above supports LS/LE segments.



<a name="loio9bf3b965a5c74365b44cd24f473e29e7__steps_dyx_lyf_y5"/>

## Procedure

1.  In the palette, choose *Message Validator*.

2.  Position the cursor on the step and click.

3.  Select the *EDI Validator* step.

4.  Select the *EDI Validator* tab in the *Properties* view.

5.  Define the parameters as described below:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter the name of the validator.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Encoding
    
    </td>
    <td valign="top">
    
    Select encoding format for the incoming payload.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Validate Message
    
    </td>
    <td valign="top">
    
    The EDI validator performs validation on incoming message against a defined XSD scheme, and has the following options available during validation:

    -   *Standard Validation*: Validates the incoming payload for the structural violations defined in XSD schema.

    -   *Extended Validation*: Validates the incoming payload for structural violations defined in the XSD schema. It also performs validation for conditional violations that are defined in XSLT constraints found within the XSD schema.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    EDI Schema Definition
    
    </td>
    <td valign="top">
    
    Select the source of schema definition.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Schemas
    
    </td>
    <td valign="top">
    
    If you select `Integration Flow` as *EDI Schema Definition*, then you can see the table *Schemas*, in *Properties* view. Select the valid schemas against which the validation will take place.

    > ### Note:  
    > -   You can add XSD files to the integration flow.
    > 
    > -   The file name of the xml schema for **EDI** payloads should have the following format:
    > 
    >     -   EDIFACT: `UN-EDIFACT_ORDERS_D96A.xsd`
    > 
    >     -   ODETTE: `ODETTE_ORDERR_2.xsd`
    > 
    >     -   ODETTE EDIFACT: `UN-EDIFACT_ORDERS_D96A_A18051.xsd`
    > 
    >     -   EANCOM: `UN-EDIFACT_ORDERS_D96A_EAN008.xsd`
    > 
    > 
    > -   The file name comprises of following three parts separated by '\_':
    > 
    >     -   First part "UN-EDIFACT" refers to the EDI standard with organization name. This value is fixed and cannot be customised.
    >     -   Second part "ORDERS" refers to the message type.
    >     -   Third part "D96A" refers to the version .
    > 
    > -   The file name of the xml schema for **ASC-X12** should have the following format:
    > 
    >     `ASC-X12_810_004010.xsd`
    > 
    >     The file name comprises of following three parts separated by '\_':
    > 
    >     -   First part "ASC-X12" refers to the ASC-X12 standard with organization name. This value is fixed and cannot be customised.
    >     -   Second part "810" refers to the message type.
    >     -   Third part "004010" refers to the version .
    > 
    > -   The above mentioned values should match with schema content.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    HeaderName
    
    </td>
    <td valign="top">
    
    If you select `Header` as *EDI Schema Definition*, then you can see the field *HeaderName*, in *Properties* view. Enter a valid header for the field.

    > ### Note:  
    > This header name is fetched from camel header. The header is added in script element. This script element is added before converter element. You can add value for this header in the script element.
    > 
    > For example, you can add the value, `/xsd/UN-EDIFACT_ORDERS_D96A.xsd` for EDIFACT.
    > 
    > For example, you can add the value, `/xsd/ASC-X12_810_004010.xsd` for ASC-X12.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Prevent Exception on Failure
    
    </td>
    <td valign="top">
    
    If you want to continue the processing even if the system encounters error while validating, then select this parameter. If an exception occurs, then the error payload is added to `SAP_EDIValidationResult` header.
    
    </td>
    </tr>
    </table>
    
    The header content for UN-EDIFACT shown below is validation xml. Similar xml is generated for ASC-X12 but the XPath changes.

    > ### Sample Code:  
    > ```
    > 
    > <Interchange>
    >                 <DocumentStandard>UN-EDIFACT</DocumentStandard>
    >                 <SyntaxVersion>3</SyntaxVersion>
    >                 <InterchangeSender>
    >                                 <Identification></Identification>
    >                                 <Qualifier></Qualifier>
    >                 </InterchangeSender>
    >                 <InterchangeControlNumber></InterchangeControlNumber>
    >                 <InterchangeError>
    >                                 <Error>
    >                                                 <ElementType>CompositeElement</ElementType>
    >                                                 <XPath>/Interchange/S_UNB/C_S003</XPath>
    >                                                 <ErrorCode></ErrorCode>
    >                                                 <ErrorText></ErrorText>
    >                                 </Error>
    >                                 <Error>
    >                                                 <ElementType>DataElement</ElementType>
    >                                                 <XPath>/Interchange/S_UNB/C_S004/D_0019</XPath>
    >                                                 <ErrorCode></ErrorCode>
    >                                                 <ErrorText></ErrorText>
    >                                 </Error>
    >                 </InterchangeError>
    >                 <FunctionalGroup>
    > 						   <GroupControlNumber>1</GroupControlNumber>
    >                                 <Error>
    >                                                  <ElementType>SegmentElement</ElementType>
    >                                                  <XPath>/Interchange/S_UNE</XPath>
    >                                                  <ErrorCode></ErrorCode>
    >                                                  <ErrorText></ErrorText>
    >                 			  </Error>
    > 
    >                                 <MessageError type="" version="">
    >                                                 <MessageControlNumber></MessageControlNumber>
    >                                                 <Error>
    >                                                                 <ElementType>SegmentElement</ElementType>
    >                                                                 <XPath>/Interchange/M_ORDERS/S_BGM</XPath>
    >                                                                 <ErrorCode></ErrorCode>
    >                                                                 <ErrorText></ErrorText>
    >                                                                 <SegmentPosition></SegmentPosition>
    >                                                 </Error>
    >                                                 <Error>
    >                                                                 <ElementType>SegmentElement</ElementType>
    >                                                                 <XPath>/Interchange/M_ORDERS/S_UNS</XPath>
    >                                                                 <ErrorCode></ErrorCode>
    >                                                                 <ErrorText></ErrorText>
    >                                                                 <SegmentPosition></SegmentPosition>
    >                                                 </Error>
    >                                                 <Error>
    >                                                                 <ElementType>DataElement</ElementType>
    >                                                                 <XPath>/Interchange/M_ORDERS/S_UNT</XPath>
    >                                                                 <ErrorCode></ErrorCode>
    >                                                                 <ErrorText></ErrorText>
    >                                                                 <SegmentPosition></SegmentPosition>
    >                                                                 <DataElementPosition></DataElementPosition>
    >                                                                 <DataCompositePosition></DataCompositePosition>
    >                                                 </Error>
    >                                 </MessageError>
    >                 </FunctionalGroup>
    > </Interchange>
    > 
    > ```

    > ### Note:  
    > If a validation exception occurs then you can check the message processing log \(MPL\) attachment.

    The tags are described in the table below:


    <table>
    <tr>
    <th valign="top">

    Tags
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Interchange
    
    </td>
    <td valign="top">
    
    Describes the full message payload.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    DocumentStandard
    
    </td>
    <td valign="top">
    
    Document standard is valid for UN-EDIFACT and ASC-X12.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SyntaxVersion
    
    </td>
    <td valign="top">
    
    The value can be 3 or 4 for UN-EDIFACT.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    InterchangeSender
    
    </td>
    <td valign="top">
    
    Specifies sender identification and sender qualifier information.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    InterchangeReceiver
    
    </td>
    <td valign="top">
    
    Specifies receiver identification and receiver qualifier information.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    InterchangeControlNumber
    
    </td>
    <td valign="top">
    
    Specifies the number that uniquely identifies EDI payload.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    InterchangeError
    
    </td>
    <td valign="top">
    
    Specifies the error applicable for interchange.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Describes the error details like element type, xpath, error code and error text.

    For error code and error text of interchange please refer to the table **Interchange Level**, given below.

    For error code and error text of message please refer to the table **Message Level**, given below.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    FunctionalGroup
    
    </td>
    <td valign="top">
    
    Specifies the error in the functional group.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    GroupControlNumber
    
    </td>
    <td valign="top">
    
    Specifies the number that uniquely identifies functional group.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MessageError type version
    
    </td>
    <td valign="top">
    
    Specifies the message error details. For example, type can be `Invoice` and version can be `96A`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SegmentPosition
    
    </td>
    <td valign="top">
    
    Refers to the erroneous segments position in the payload. It either refers to the line number if the segments in the incoming payload occur in different lines or it refers to the number of segment separator after which the erroneous segment occurs in the payload.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    DataElementPosition
    
    </td>
    <td valign="top">
    
    Specifies the data element position inside the segment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    DataCompositePosition
    
    </td>
    <td valign="top">
    
    Specifies the data composite position inside the segment.
    
    </td>
    </tr>
    </table>
    
    The error codes for UN-EDIFACT are given below:

    **Interchange Level**


    <table>
    <tr>
    <th valign="top">

    Error Code
    
    </th>
    <th valign="top">

    Error text
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    2
    
    </td>
    <td valign="top">
    
    Notifies that the syntax version and/or level is not supported by the recipient.
    
    </td>
    </tr>
    </table>
    
    **Message Level**


    <table>
    <tr>
    <th valign="top">

    Error Code
    
    </th>
    <th valign="top">

    Error Text
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    12
    
    </td>
    <td valign="top">
    
    Notifies that the value of a stand-alone data element, composite data element or component data element does not conform to the relevant specifications for the value.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    13
    
    </td>
    <td valign="top">
    
    Notifies that a mandatory \(or otherwise required\) service or user segment, data element, composite data element or component data element is missing.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    14
    
    </td>
    <td valign="top">
    
    Notifies that the recipient does not support use of the specific value of an identified stand-alone data element, composite data element or component data element in the position where it is used. The value may be valid according to the relevant specifications and may be supported if it is used in another position.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    15
    
    </td>
    <td valign="top">
    
    Notifies that the recipient does not support use of the segment type, stand-alone data element type, composite data element type or component data element type in the identified position.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    16
    
    </td>
    <td valign="top">
    
    Notifies that the identified segment contained too many data elements or that the identified composite data element contained too many component data elements.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    18
    
    </td>
    <td valign="top">
    
    Notifies that an error has been identified, but the nature of the error is not reported.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    19
    
    </td>
    <td valign="top">
    
    Notifies that the character indicated as decimal notation in UNA is invalid, or the decimal notation used in a data element is not consistent with the one indicated in UNA .
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    35
    
    </td>
    <td valign="top">
    
    Notifies that a segment was repeated too many times.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    36
    
    </td>
    <td valign="top">
    
    Notifies that a segment group is repeated to many times.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    37
    
    </td>
    <td valign="top">
    
    Notifies that one or more numeric characters were used in an alphabetic \(component\) data element or that one or more alphabetic characters were used in a numeric \(component\) data element.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    38
    
    </td>
    <td valign="top">
    
    Notifies that a decimal sign is not preceded by one or more digits.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    39
    
    </td>
    <td valign="top">
    
    Notifies that the length of the data element received exceeded the maximum length specified in the data element description.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    40
    
    </td>
    <td valign="top">
    
    Notifies that the length of the data element received is shorter than the minimum length specified in the data element description.
    
    </td>
    </tr>
    </table>
    
    The error codes for ASC-X12 are given below:

    **Functional Group Level**


    <table>
    <tr>
    <th valign="top">

    Error Code
    
    </th>
    <th valign="top">

    Error text
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    3
    
    </td>
    <td valign="top">
    
    Notifies that the functional group trailer is missing.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    4
    
    </td>
    <td valign="top">
    
    Notifies that the group control number in the functional group header and trailer do not match.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    Notifies that the number of included transaction sets does not match actual count .
    
    </td>
    </tr>
    </table>
    
    **Transaction Set Level**


    <table>
    <tr>
    <th valign="top">

    Error Code
    
    </th>
    <th valign="top">

    Error Text
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    1
    
    </td>
    <td valign="top">
    
    Notifies that the transaction set is not supported.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    2
    
    </td>
    <td valign="top">
    
    Notifies that the transaction set trailer is missing.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    3
    
    </td>
    <td valign="top">
    
    Notifies that the transaction set control number in header and trailer do not match.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    4
    
    </td>
    <td valign="top">
    
    Notifies that the number of included segments does not match actual count.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    Notifies that the one or more segments have error.
    
    </td>
    </tr>
    </table>
    
    **Segment Level**


    <table>
    <tr>
    <th valign="top">

    Error Code
    
    </th>
    <th valign="top">

    Error Text
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    1
    
    </td>
    <td valign="top">
    
    Notifies that there is an unrecognized segment ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    2
    
    </td>
    <td valign="top">
    
    Notifies that there is an unexpected segment .
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    3
    
    </td>
    <td valign="top">
    
    Notifies that the mandatory segment is missing .
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    4
    
    </td>
    <td valign="top">
    
    Notifies that the loop occurs over maximum times.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    Notifies that the segment exceeds maximum use.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    6
    
    </td>
    <td valign="top">
    
    Notifies that the segment is not defined in transaction set.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    7
    
    </td>
    <td valign="top">
    
    Notifies that the segment is not in proper sequence.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    8
    
    </td>
    <td valign="top">
    
    Notifies that the segment has data element errors.
    
    </td>
    </tr>
    </table>
    
    **Data Element Level**


    <table>
    <tr>
    <th valign="top">

    Error Code
    
    </th>
    <th valign="top">

    Error Text
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    1
    
    </td>
    <td valign="top">
    
    Notifies that there mandatory data element is missing.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    3
    
    </td>
    <td valign="top">
    
    Notifies that there are too many data elements.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    4
    
    </td>
    <td valign="top">
    
    Notifies that the data element is too short.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    Notifies that the data element is too long.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    6
    
    </td>
    <td valign="top">
    
    Notifies that there is an invalid character in data element .
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    8
    
    </td>
    <td valign="top">
    
    Notifies that the date is invalid.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    9
    
    </td>
    <td valign="top">
    
    Notifies that the time is invalid.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > `SAP_EDI_Document_Number` header contains document number for the incoming EDI file.


