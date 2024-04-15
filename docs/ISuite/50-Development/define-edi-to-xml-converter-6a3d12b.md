<!-- loio6a3d12b4075a424080aee47d256c41b5 -->

# Define EDI to XML Converter

The EDI to XML converter enables you to transform single incoming EDI messages from EDI to XML format.



<a name="loio6a3d12b4075a424080aee47d256c41b5__prereq_ffz_jpk_zdb"/>

## Prerequisites

> ### Note:  
> This information is relevant only when you use the Cloud Integration capability as a part of SAP Integration Suite. Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

EDI to XML Converter version 2.0 and above supports the TRADACOMS standard \(*TRADACOMS* tab; available only for dedicated service plans, see [2903776](https://me.sap.com/notes/2903776)\).

You are editing the integration flow in the editor.



## Context

Use this procedure to convert EDIFACT, ODETTE, TRADACOMS, and ASC-X12 format into XML format.

> ### Note:  
> -   Any EDIFACT message is an interchange. An interchange can have multiple groups. And each group consists of message types. For EDIFACT messages, the EDI elements in Cloud Integration support only 1 message type per interchange but does not support any group segment \(GS\) per interchange segment.
> 
>     EDI to XML converter version 1.5 and above supports EDIFACT Syntax version 2 in addition to version 3 and 4.
> 
> -   Any ASC-X12 message is an interchange. An interchange can have multiple groups. And each group consists of transaction sets. For ASC-X12 message, the EDI elements in Cloud Integration support only 1 group segment \(GS\) per interchange segment and only 1 transaction set \(ST\) per group segment.
> -   EDI to XML converter version 1.6 and above supports LS/LE segments.
> -   Cloud Integration does not support repetition characters. Repetition character is a single character which separates the instances of a repeating data element. For example, *^* \(caret sign\) is a repetition character.
> -   For X12 format, EDI to XML converter v1.8.0 and v2.2.0 onwards support same group name with different definition in XSD.



## Procedure

1.  In the graphical editor of integration flow, choose the *EDI to XML Converter* element..

2.  Define the parameters to convert the EDI data format to XML data format.

    Use *EDIFACT* tab to convert the ODETTE payload to XML format.


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
    
    Enter the name of the converter.
    
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
    
    Target Encoding
    
    </td>
    <td valign="top">
    
    Select encoding format for the outgoing payload. If you select 'Dynamic', you must define the value 'UTF-8' or 'ISO-8859-1' in SAP\_EDITOXML\_EDIFACT\_TARGET\_ENCODING exchange header.
    
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
    
    If exchange headeryou select `Integration Flow` as *EDI Schema Definition*, then you can see the table *Schemas*, in *Properties* view. Select the valid schemas against which the conversion will take place.

    > ### Note:  
    > -   You can add XSD files to the integration flow. For more details, please refer to [Validating Message Payload against XML Schema](validating-message-payload-against-xml-schema-360dc70.md).
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
    > 
    > -   During runtime only XSD’s from Integration Advisor are supported.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    HeaderName
    
    </td>
    <td valign="top">
    
    If you select `Header` as *EDI Schema Definition*, then you can see the field *HeaderName*, in *Properties* view. Enter a valid header name for the field.

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
    
    Exclude Interchange and Group envelopes
    
    </td>
    <td valign="top">
    
    If selected the feature notifies the converter to exclude the interchange and group envelopes found in an EDI document.
    
    </td>
    </tr>
    </table>
    
    **TRADACOMS**

    > ### Note:  
    > This information is relevant only when you use the Cloud Integration capability as a part of SAP Integration Suite. Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).


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

        If selected, the encoding format is set dynamically at runtime using the header `SAP_EDITOXML_TRADACOMS_SOURCE_ENCODING` \(possible values: `UTF-8`, `ISO-8859-1`\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Conversion Preference
    
    </td>
    <td valign="top">
    
    Specify the conversion preference for the TRADACOMS message.

    There are the following options:

    -   No

    -   Yes

    -   Dynamic

        If selected, this parameter is set dynamically at runtime using the header `SAP_EDITOXML_TRADACOMS_CONVERSION_PREFERENCE` \(possible values: `No`, `Yes`\).



    
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

        If selected, this parameter is set dynamically at runtime based on the value of the header `SAP_EDITOXML_TRADACOMS_SCHEMA_SOURCE` \(possible values: `Header`, `IntegrationProject`\).

    -   Header

        If selected, the location of the schema definition is set at runtime based on the value of a header \(header name to be defined using the *Header Name* parameter\).

    -   Integration Flow

        If selected, the schema definition is specified from a resource file of the integration flow \(use the parameter *Schemas* to choose the schema\).


    > ### Note:  
    > During runtime only XSD’s from Integration Advisor are supported.


    
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

        Only XSD files from Integration Advisor are supported.


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
    > -   `SAP_EDI_Document_Number` header contains document number for the single incoming EDI file.
    > 
    > -   In a ODETTE message payload, provide the value for *SAP\_EDI\_Document\_Standard* header as `ODETTE`.
    > -   From EDI to XML Converter version 1.4 onwards for EANCOM payloads, use `UN-EDIFACT` as the value for `SAP_EDI_Document_Standard` header. For earlier version of the converter, you can provide the value for the header as `EANCOM`.




## Example

-   The following example shows the transformation from *EDI to XML* format of EDIFACT message.

    Input sample EDIFACT EDI Message

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

    Output sample EDIFACT XML Message

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

-   The following example shows the transformation from *EDI to XML* format of ASC-X12 message.

    Input sample ASC-X12 EDI Message

    > ### Sample Code:  
    > ```
    > 
    > ISA*00*          *00*          *01*784849291      *01*315029991      *051007*0928*/*4010 *000000001*0*P*^~
    > GS*PO*784849291*315029991*20051007*0928*1*U*004010~
    > ST*850*10001~
    > BEG*00*NE*228914**20051006~
    > CUR*BY*EUR*0100~
    > N1*SF*BEHR SERVICE GMBH*92*1939~
    > N1*ST*BEHR SERVICE AMERICA*92*1939~
    > PO1*10000*17*EA*91.8074*EA*BP*2112910003*PD*Radiator~
    > LIN**MF*2109308~
    > SCH*17*EA***002*20060401~
    > CTT*1~
    > SE*10*10001~
    > GE*1*1~
    > IEA*1*000000001~
    > 
    > 
    > ```

    Output sample ASC-X12 XML Message

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


