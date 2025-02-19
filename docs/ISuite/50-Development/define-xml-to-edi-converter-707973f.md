<!-- loio707973f9bfb1419eb80628755494b962 -->

# Define XML to EDI Converter

The XML to EDI converter transforms a single XML message from XML format to EDI format.



## Context

Use the converter to convert XML message either to EDIFACT, ODETTE, TRADACOMS, or ASC-X12 format.

XML to EDI Converter version 2.0 and above supports the TRADACOMS standard \(*TRADACOMS* tab; available only for dedicated service plans, see [2903776](https://me.sap.com/notes/2903776)\).

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loio707973f9bfb1419eb80628755494b962__steps_i3z_mpn_35"/>

## Procedure

1.  In the graphical editor of integration flow, choose the *XML to EDI Converter* element.

2.  Define the parameters to convert the XML data format to EDI data format.

    > ### Note:  
    > -   Use *EDIFACT* tab to convert XML file to ODETTE document. XML to EDI Converter version 1.2 and above supports EDIFACT Syntax versions 2, 3, and 4, while version 2.5 and above additionally supports EDIFACT Syntax versions 1 and x.
    > 
    > -   For X12 format, XML to EDI converter v1.3.0 and v2.1.0 onwards support same group name with different definition in XSD.


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
    <td valign="top" colspan="2">
    
    **General**
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter a name for the flow step.
    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    **EDIFACT**
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Encoding
    
    </td>
    <td valign="top">
    
    Select encoding format for the incoming payload. The following encoding formats are available:

    -   UTF-8
    -   ISO-8859-1


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Encoding
    
    </td>
    <td valign="top">
    
    Select encoding format for the outgoing payload. If you select 'Dynamic', you must define either of the following values in SAP\_XMLTOEDI\_EDIFACT\_TARGET\_ENCODING exchange header:

    -   UTF-8
    -   ISO-8859-1 to ISO-8859-9
    -   fromIncomingPayload


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    EDI Schema Definition
    
    </td>
    <td valign="top">
    
    Select the source of schema definition. To specify the schema definition, there are the following options:

    -   Integration Flow

    -   Header


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Schemas
    
    </td>
    <td valign="top">
    
    If you select `Integration Flow` as *EDI Schema Definition*, then you can see the table *Schemas*, in *Properties* view. Choose *Add* \> *Select* to select the valid schemas against which the conversion will take place.

    > ### Note:  
    > -   You can add XSD files to the integration flow. For more details, please refer to the topic **Validating Message Payload against XML Schema**, in developer's guide.
    > 
    > -   The file name of the xml schema for **EDIFACT/ODETTE** should have the following format:
    > 
    >     -   EDIFACT: `UN-EDIFACT_ORDERS_D96A.xsd`
    > 
    >     -   ODETTE: `ODETTE_ORDERR_2.xsd`
    > 
    >     -   ODETTE EDIFACT: `UN-EDIFACT_ORDERS_D96A_A18051.xsd`
    > 
    > 
    >     Consider the EDIFACT filename as a sample to understand its constituents. The file name comprises of following parts separated by '\_':
    > 
    >     -   First part "UN-EDIFACT" refers to the EDI standard with organization name. This value is fixed and cannot be customised.
    >     -   Second part "ORDERS" refers to the message type.
    >     -   Third part "D96A" refers to the version .


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    HeaderName
    
    </td>
    <td valign="top">
    
    If you select Header as *EDI Schema Definition*, then you can see the field *HeaderName*. Enter a valid header name for the field.

    > ### Note:  
    > This header name is fetched from Camel header. The header is added in script element. This script element is added before the converter element. You can add value for this header in the script element.
    > 
    > For example, you can add the value, `/xsd/UN-EDIFACT_ORDERS_D96A.xsd`.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Use Custom Separators
    
    </td>
    <td valign="top">
    
    Select this option if you want to specify which separators are to be used in the converted message. You can select the characters available in the dropdown list for each separator type:

    -   *Segment Terminator*: This character is used to indicate the end of a segment.
    -   *Composite Separator*: This is a separator between component data elements within a composite data element.
    -   *Data Element Separator*: This is a separator between two simple or composite data element.
    -   *Escape Character*: This is used when one of the separator characters is to be used within a data element or to restore separator and terminator signs to their normal meaning.
    -   *Decimal Character*: This is used to determine decimal character of outgoing payload. You can choose the value as *Comma \(,\)*, *Dot \(.\)* or *Dynamic* for the converted message. If you select 'Dynamic', you must define the hexadecimal value ‘\#x2e’ for dot or ‘\#x2c’ for comma in `SAP_XMLTOEDI_DECIMAL_CHARACTER` header.

    > ### Note:  
    > You can also manually specify the custom separator.
    > 
    > -   Enter the hexadecimal value for the separator you want to use in the respective field. For example, enter `#x2b` to use *\+* as the separator.
    > -   Enter the header value to fetch the sepatator from header. For example, `${header.HEADER_NAME}`


    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    **X12**
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Encoding
    
    </td>
    <td valign="top">
    
    Select encoding format for the incoming payload. The following encoding formats are available:

    -   UTF-8
    -   ISO-8859-1


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    EDI Schema Definition
    
    </td>
    <td valign="top">
    
    Select the source of schema definition. To specify the schema definition, there are the following options:

    -   Integration Flow
    -   Header


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Schemas
    
    </td>
    <td valign="top">
    
    If you select Integration Flow as *EDI Schema Definition*, then you can see the table *Schemas*, in *Properties* view. Choose *Add* \> *Select* to select the valid schemas against which the conversion will take place.

    > ### Note:  
    > -   You can add XSD files to the integration flow. For more details, please refer to the topic *Validating Message Payload against XML Schema*, in developer's guide.
    > -   The file name of the xml schema for ASC-X12 should have the format, *ASC-X12\_810\_004010.xsd*. It contains three parts separated by *\_*:
    >     -   First part *ASC-X12* refers to the ASC-X12 standard with organization name. This value is fixed and cannot be customised.
    >     -   Second part *810* refers to the message type.
    >     -   Third part *004010* refers to the version.
    > 
    > -   The aforementioned values should match with the schema content.
    > -   During runtime only XSD’s from Integration Advisor \(IA\) are supported.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Header Name
    
    </td>
    <td valign="top">
    
    If you select Header as *EDI Schema Definition*, then you can see the field *HeaderName*. Enter a valid header name for the field.

    > ### Note:  
    > This header name is fetched from camel header. The header is added in script element. This script element is added before converter element. You can add value for this header in the script element.
    > 
    > For example, you can add the value, `/xsd/ASC-X12_810_004010.xsd`.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Use Custom Separators
    
    </td>
    <td valign="top">
    
    Select this option if you want to specify which separators are to be used in the converted message. You can select the characters available in the dropdown list for each separator.

    > ### Note:  
    > You can also manually specify the custom separator.
    > 
    > -   Enter the hexadecimal value for the separator you want to use in the respective field. For example, enter `#x2b` to use *\+* as the separator.
    > -   Enter the header value to fetch the sepatator from header. For example, `${header.HEADER_NAME}`


    
    </td>
    </tr>
    </table>
    
    **TRADACOMS**

    > ### Note:  
    > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).


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
    
    Source Encoding
    
    </td>
    <td valign="top">
    
    Use the appropriate encoding format of the inbound TRADACOMS interchange.

    The following encoding formats are available:

    -   UTF-8

    -   ISO-8859-1

    -   Dynamic

        If selected, the encoding format is set dynamically at runtime using the header `SAP_XMLTOEDI_TRADACOMS_SOURCE_ENCODING` \(possible values: `UTF-8`, `ISO-8859-1`\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Conversion Preference
    
    </td>
    <td valign="top">
    
    Specify the conversion preference for the TRADACOMS EDI message.

    There are the following options:

    -   No

    -   Yes

    -   Dynamic

        If selected, this parameter is set dynamically at runtime using the header `SAP_XMLTOEDI_TRADACOMS_CONVERSION_PREFERENCE` \(possible values: `No`, `Yes`\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    EDI Schema Definition
    
    </td>
    <td valign="top">
    
    Validates an EDI interchange against the XSD schema for the conversion.

    To specify the schema definition, there are the following options:

    -   Dynamic

        If selected, this parameter is set dynamically at runtime based on the value of the header `SAP_XMLTOEDI_TRADACOMS_SCHEMA_SOURCE` \(possible values: `Header`, `IntegrationProject`\).

    -   Header

        If selected, the location of the schema definition is set at runtime based on the value of a header \(header name to be defined using the *Header Name* parameter\).

    -   Integration Flow

        If selected, the schema definition is specified from a resource file of the integration flow \(use the parameter *Schemas* to choose the schema\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Header Name

    \(only available if for *EDI Schema Definition* the option *Header* is selected\)
    
    </td>
    <td valign="top">
    
    Define the name of the header that contains the location of the EDI schema definition.

    > ### Note:  
    > You can define the header in a Script step that is to be added before the EDI Converter step of your integration flow.
    > 
    > For example, you can add the following header value:
    > 
    > `/xsd/TRADACOMS_ORDHDR_FILE_9.xsd for TRADACOMS`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Schemas

    \(only available if for *EDI Schema Definition* the option *Integration Flow* is selected\)
    
    </td>
    <td valign="top">
    
    Select the schema definition from an XSD file added as resource to the integration flow.

    Perform the following steps:

    1.  Choose *Add*.

    2.  Choose *Select* to add a file from the XSD folder found in the same integration project.

        Only XSD files from Integration Advisor are supported at runtime.


    > ### Note:  
    > Apply the following naming convention for the file name of the XML schema:
    > 
    > `TRADACOMS: TRADACOMS_ORDHDR_FILE_9.xsd`


    
    </td>
    </tr>
    </table>
    
3.  If you want to continue editing the integration package without exiting, choose *Save*.

4.  Choose *Save as version* to retain a copy of the current artifact.

5.  If you want to terminate the creation of package, choose *Cancel* before saving it.

    > ### Note:  
    > -   Any EDIFACT message is an interchange. An interchange can have multiple groups. And each group consists of message types. For EDIFACT message, the EDI elements in SAP Cloud Integration support only 1 message type per interchange but does not support any group segment \(GS\) per interchange segment.
    > -   Any ASC-X12 message is an interchange. An interchange can have multiple groups. And each group consists of transaction sets. For ASC-X12 message, the EDI elements in SAP Cloud Integration support only 1 group segment \(GS\) per interchange segment and only 1 transaction set \(ST\) per group segment.
    > -   SAP Cloud Integration does not support repetition characters. Repetition character is a single character which separates the instances of a repeating data element. For example, *^* \(caret sign\) is a repetition character.
    > -   SAP Cloud Integration generates EDI file which uses the following separators for EDIFACT message:
    >     -   Data Element separator *\+* 
    >     -   Component Data Element separator *:*
    >     -   Segment separator *‘* 
    > 
    > -   SAP Cloud Integration generates EDI file which uses the following separators for ASC-X12 message:
    >     -   Data Element separator *\** 
    >     -   Component Data Element separator *:*
    >     -   Segment separator *~* 
    > 
    > -   The file name of the XSD schema for **EDIFACT/ODETTE** should have the following format:
    > 
    >     -   EDIFACT: `UN-EDIFACT_ORDERS_D96A.xsd`
    > 
    >     -   ODETTE: `ODETTE_ORDERR_2.xsd`
    > 
    >     -   ODETTE EDIFACT: `UN-EDIFACT_ORDERS_D96A_A18051.xsd`
    > 
    > 
    > -   During runtime only XSD’s from Integration Advisor \(IA\) are supported.

    > ### Note:  
    > `SAP_EDI_Document_Number` header contains document number for the single incoming EDI file.

    -   The following example shows the transformation from *XML to EDI* format of EDIFACT message.

        Input sample EDIFACT XML Message

        ```
        
        <?xml version="1.0" encoding="UTF-8"?><Interchange>
            <S_UNA>:+.? '</S_UNA>
            <S_UNB>
                <C_S001>
                    <D_0001>UNOC</D_0001>
                    <D_0002>3</D_0002>
                </C_S001>
                <C_S002>
                    <D_0004>SENDERABC</D_0004>
                    <D_0007>14</D_0007>
                    <D_0008>XXXX</D_0008>
                </C_S002>
                <C_S003>
                    <D_0010>ReceiverXYZ</D_0010>
                    <D_0007>14</D_0007>
                    <D_0014>YYYYY</D_0014>
                </C_S003>
                <C_S004>
                    <D_0017>150831</D_0017>
                    <D_0019>1530</D_0019>
                </C_S004>
                <D_0020>1</D_0020>
                <C_S005>
                    <D_0022>HELLO WORLD</D_0022>
                </C_S005>
                <D_0029>A</D_0029>
                <D_0035>1</D_0035>
            </S_UNB>
            <M_ORDERS>
                <S_UNH>
                    <D_0062>1</D_0062>
                    <C_S009>
                        <D_0065>ORDERS</D_0065>
                        <D_0052>D</D_0052>
                        <D_0054>96A</D_0054>
                        <D_0051>UN</D_0051>
                    </C_S009>
                    <C_S010>
                        <D_0070>2</D_0070>
                    </C_S010>
                </S_UNH>
                <S_BGM>
                    <C_C002>
                        <D_1001>220</D_1001>
                    </C_C002>
                    <D_1004>MY_ID</D_1004>
                    <D_1225>9</D_1225>
                    <D_4343>NA</D_4343>
                </S_BGM>
                <S_DTM>
                    <C_C507>
                        <D_2005>137</D_2005>
                        <D_2380>201507311500</D_2380>
                        <D_2379>203</D_2379>
                    </C_C507>
                </S_DTM>
                <S_DTM>
                    <C_C507>
                        <D_2005>2</D_2005>
                        <D_2380>201508010930</D_2380>
                        <D_2379>203</D_2379>
                    </C_C507>
                </S_DTM>
                <S_CNT>
                    <C_C270>
                        <D_6069>16</D_6069>
                        <D_6066>10</D_6066>
                    </C_C270>
                </S_CNT>
                <S_UNT>
                    <D_0074>5</D_0074>
                    <D_0062>1</D_0062>
                </S_UNT>
            </M_ORDERS>
            <S_UNZ>
                <D_0036>1</D_0036>
                <D_0020>1</D_0020>
            </S_UNZ>
        </Interchange>
        
        
        ```

        Output sample EDIFACT EDI Message

        ```
        
        UNA:+.? '
        UNB+UNOC:3+SENDERABC:14:XXXX+ReceiverXYZ:14:YYYYY+150831:1530+1+HELLO WORLD++A+++1'
        UNH+1+ORDERS:D:96A:UN++2'
        BGM+220+MY_ID+9+NA'
        DTM+137:201507311500:203'
        DTM+2:201508010930:203'
        CNT+16:10'
        UNT+5+1'
        UNZ+1+1'
        
        ```

    -   The following example shows the transformation from *XML to EDI* format of ASC-X12 message.

        Input sample ASC-X12 XML Message

        ```
        
        <?xml version="1.0" encoding="UTF-8"?><ns0:Interchange xmlns:ns0="urn:sap.com:typesystem:b2b:116:asc-x12:850:004010">
            <S_ISA>
                <D_I01>00</D_I01>
                <D_I02>          </D_I02>
                <D_I03>00</D_I03>
                <D_I04>          </D_I04>
                <D_I05_1>01</D_I05_1>
                <D_I06>784849291      </D_I06>
                <D_I05_2>01</D_I05_2>
                <D_I07>315029991      </D_I07>
                <D_I08>051007</D_I08>
                <D_I09>0928</D_I09>
                <D_I10>/</D_I10>
                <D_I11>4010 </D_I11>
                <D_I12>000000001</D_I12>
                <D_I13>0</D_I13>
                <D_I14>P</D_I14>
                <D_I15>^</D_I15>
            </S_ISA>
            <S_GS>
                <D_479>PO</D_479>
                <D_142>784849291</D_142>
                <D_124>315029991</D_124>
                <D_373>20051007</D_373>
                <D_337>0928</D_337>
                <D_28>1</D_28>
                <D_455>U</D_455>
                <D_480>004010</D_480>
            </S_GS>
            <M_850>
                <S_ST>
                    <D_143>850</D_143>
                    <D_329>10001</D_329>
                </S_ST>
                <S_BEG>
                    <D_353>00</D_353>
                    <D_92>NE</D_92>
                    <D_324>228914</D_324>
                    <D_373>20051006</D_373>
                </S_BEG>
                <S_CUR>
                    <D_98_1>BY</D_98_1>
                    <D_100_1>EUR</D_100_1>
                    <D_280>0100</D_280>
                </S_CUR>
                <G_N1>
                    <S_N1>
                        <D_98_1>SF</D_98_1>
                        <D_93>BEHR SERVICE GMBH</D_93>
                        <D_66>92</D_66>
                        <D_67>1939</D_67>
                    </S_N1>
                </G_N1>
                <G_N1>
                    <S_N1>
                        <D_98_1>ST</D_98_1>
                        <D_93>BEHR SERVICE AMERICA</D_93>
                        <D_66>92</D_66>
                        <D_67>1939</D_67>
                    </S_N1>
                </G_N1>
                <G_PO1>
                    <S_PO1>
                        <D_350>10000</D_350>
                        <D_330>17</D_330>
                        <D_355>EA</D_355>
                        <D_212>91.8074</D_212>
                        <D_639>EA</D_639>
                        <D_235_1>BP</D_235_1>
                        <D_234_1>2112910003</D_234_1>
                        <D_235_2>PD</D_235_2>
                        <D_234_2>Radiator</D_234_2>
                    </S_PO1>
                    <S_LIN>
                        <D_235_1>MF</D_235_1>
                        <D_234_1>2109308</D_234_1>
                    </S_LIN>
                    <G_SCH>
                        <S_SCH>
                            <D_380>17</D_380>
                            <D_355>EA</D_355>
                            <D_374_1>002</D_374_1>
                            <D_373_1>20060401</D_373_1>
                        </S_SCH>
                    </G_SCH>
                </G_PO1>
                <G_CTT>
                    <S_CTT>
                        <D_354>1</D_354>
                    </S_CTT>
                </G_CTT>
                <S_SE>
                    <D_96>10</D_96>
                    <D_329>10001</D_329>
                </S_SE>
            </M_850>
            <S_GE>
                <D_97>1</D_97>
                <D_28>1</D_28>
            </S_GE>
            <S_IEA>
                <D_I16>1</D_I16>
                <D_I12>000000001</D_I12>
            </S_IEA>
        </ns0:Interchange>
        
        
        
        ```

        Output sample ASC-X12 EDI Message

        ```
        
        ISA*00*          *00*          *01*784849291      *01*315029991      *051007*0928*/*4010 *000000001*0*P*^~
        GS*PO*784849291*315029991*20051007*0928*1*U*004010~
        ST*850*10001~
        BEG*00*NE*228914**20051006~
        CUR*BY*EUR*0100~
        N1*SF*BEHR SERVICE GMBH*92*1939~
        N1*ST*BEHR SERVICE AMERICA*92*1939~
        PO1*10000*17*EA*91.8074*EA*BP*2112910003*PD*Radiator~
        LIN**MF*2109308~
        SCH*17*EA***002*20060401~
        CTT*1~
        SE*10*10001~
        GE*1*1~
        IEA*1*000000001~
        
        
        ```





## Example

**EANCOM Document Standard**

The following segments are part of message payload of EANCOM, and the table below mentions the headers and values for the given payload.

UNB+UNOC:3+**4006501000002**:**14**+**5790000016839**:**14**+100818:0028+**0650**+++++XXXXX'

UNH+1+**INVOIC**:**D**:**96A**:**EN:EAN008**'

**Value for EANCOM Document Standard**


<table>
<tr>
<th valign="top">

Header Name

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Document\_Standard

</td>
<td valign="top">

UN-EDIFACT

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Interchange\_Control\_Number

</td>
<td valign="top">

1

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Association\_Assign\_Code

</td>
<td valign="top">

EAN008

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Control\_Number

</td>
<td valign="top">

1

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Controlling\_Agency

</td>
<td valign="top">

UN

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Release

</td>
<td valign="top">

96A

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Type

</td>
<td valign="top">

ORDERS

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Version

</td>
<td valign="top">

D

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Payload\_Format

</td>
<td valign="top">

EDI\_FLAT

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Processing\_Priority\_Code

</td>
<td valign="top">

A

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_ID

</td>
<td valign="top">

RECIPIENT ID

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_Routing\_Address

</td>
<td valign="top">

INT ROUT

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Recipient\_Reference\_Password

</td>
<td valign="top">

PASSWORD RCV

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_ID\_Qualifier

</td>
<td valign="top">

14

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Sender\_ID

</td>
<td valign="top">

SENDER ID

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Sender\_ID\_Qualifier

</td>
<td valign="top">

14

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Sender\_Reverse\_Routing\_Address

</td>
<td valign="top">

REV ROUT

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Syntax\_Identifier

</td>
<td valign="top">

UNOC

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Syntax\_Version\_Number

</td>
<td valign="top">

3

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Test\_Indicator

</td>
<td valign="top">

1

</td>
</tr>
</table>

**EDIFACT Document Standard**

The element creates camel headers and populates it with respective extracted values. For example, if following segments are part of message payload of EDIFACT, then respective headers and values for the same are given in the table below.

UNB+UNOC:3+**4006501000002**:**14**+**5790000016839**:**14**+100818:0028+**0650**+++++XXXXX'

UNH+1+**INVOIC**:**D**:**96A**:**UN**'

**Value for EDIFACT Document Standard**


<table>
<tr>
<th valign="top">

Header Name

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Payload\_Format

</td>
<td valign="top">

XML or Flat-File

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Document\_Standard

</td>
<td valign="top">

UN-EDIFACT

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Sender\_ID

</td>
<td valign="top">

4006501000002

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Sender\_ID\_Qualifier

</td>
<td valign="top">

14

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_ID

</td>
<td valign="top">

5790000016839

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_ID\_Qualifier

</td>
<td valign="top">

14

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Interchange\_Control\_Number

</td>
<td valign="top">

0650

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Type

</td>
<td valign="top">

INVOIC

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Version

</td>
<td valign="top">

D

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Release

</td>
<td valign="top">

96A

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Controlling\_Agency

</td>
<td valign="top">

UN

</td>
</tr>
</table>

**ASC-X12 Document Standard**

If following segments are part of message payload of ASC-X12 , then respective headers and values for the same are given in the table below.

ISA\*00\* \*00\* \***ZZ**\***WWRESNDR** \***ZZ**\***WWRERCVR** \*020709\*0816\*U\*00401\***000046668**\*0\*P\*:~

GS\*IN\*GSRESNDR\*GSRERCVR\*20030709\*0816\*12345\*X\***004010**~

**810**\*0001~

**Value for ASC-X12 Document Standard**


<table>
<tr>
<th valign="top">

Header Name

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Payload\_Format

</td>
<td valign="top">

XML or Flat-File

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Document\_Standard

</td>
<td valign="top">

ASC-X12

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Sender\_ID

</td>
<td valign="top">

WWRESNDR

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Sender\_ID\_Qualifier

</td>
<td valign="top">

ZZ

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_ID

</td>
<td valign="top">

WWRERCVR

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_ID\_Qualifier

</td>
<td valign="top">

ZZ

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Interchange\_Control\_Number

</td>
<td valign="top">

000046668

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Type

</td>
<td valign="top">

810

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Message\_Version

</td>
<td valign="top">

004010

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_GS\_Sender\_ID

</td>
<td valign="top">

GSRESNDR

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Receiver\_ID

</td>
<td valign="top">

GSRERCVR

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_GS\_Control\_Number

</td>
<td valign="top">

12345

</td>
</tr>
<tr>
<td valign="top">

SAP\_GS\_Functional\_Id\_Code

</td>
<td valign="top">

IN

</td>
</tr>
<tr>
<td valign="top">

SAP\_GS\_Responsible\_Agency\_Code

</td>
<td valign="top">

X

</td>
</tr>
<tr>
<td valign="top">

SAP\_ISA\_Acknowledgment\_Requested

</td>
<td valign="top">

0

</td>
</tr>
<tr>
<td valign="top">

SAP\_ISA\_Auth\_Information\_Qualifier

</td>
<td valign="top">

00

</td>
</tr>
<tr>
<td valign="top">

SAP\_ISA\_Control\_Standards\_Identifier

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

SAP\_ ISA\_Security\_Information\_Qualifier

</td>
<td valign="top">

00

</td>
</tr>
<tr>
<td valign="top">

SAP\_ISA\_Usage\_Indicator

</td>
<td valign="top">

P

</td>
</tr>
<tr>
<td valign="top">

SAP\_ISA\_Version\_Number

</td>
<td valign="top">

004010

</td>
</tr>
<tr>
<td valign="top">

SAP\_MessageProcessingLogID

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

SAP\_ST\_Control\_Number

</td>
<td valign="top">



</td>
</tr>
</table>

