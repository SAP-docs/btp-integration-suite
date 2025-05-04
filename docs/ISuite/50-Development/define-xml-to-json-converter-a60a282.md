<!-- loioa60a282ce3b44927989388dc31d35263 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define XML to JSON Converter

The XML to JSON converter enables you to transform messages in XML format to JSON format.



<a name="loioa60a282ce3b44927989388dc31d35263__prereq_s5n_p1t_5fb"/>

## Prerequisites

-   You are familiar with the conversion rules for XML to JSON conversion.

    For more information see [Conversion Rules for XML to JSON Conversion](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778aed733e3140cea0435f4615d53812.html "To ensure a successful conversion from XML format to JSON format, you should make yourself familiar with the conversion rules.") :arrow_upper_right:.

-   You are familiar with the limitations for XML to JSON conversion.

    For more information see [Limitations for XML-to-JSON Conversion](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/a5b4641c393f406bb544987497c90a72.html "To ensure a successful conversion form XML to JSON format you have to know the limitations for this conversion.") :arrow_upper_right:.

-   You are familiar with streaming for XML to JSON conversion.

    For more information see [How Streaming in the XML-to-JSON Converter Works](how-streaming-in-the-xml-to-json-converter-works-4e05044.md).

-   You are editing the integration flow in the editor.




## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span>*Transformation* \> *Converter* \> *XML to JSON Converter*.

2.  Insert the converter at the desired position in your integration process.

    The converter appears as a graphical element in your integration process.

    The properties tab page for the XML to JSON-Converter opens.

3.  Define the parameters for your conversion, see table below.


    <table>
    <tr>
    <th valign="top">

    Option
    
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
    
    JSON Output Encoding
    
    </td>
    <td valign="top">
    
    Enter the JSON output encoding. The default value is *from header or property*.

    If you select *from header or property*, the converter tries to read the encoding from the message header or exchange property `CamelCharsetName`. If there is no value defined, UTF-8 is used.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    XML Namespace \(only if the option *Namespace Mapping* is selected\)
    
    </td>
    <td valign="top">
    
    If you select from header or property, the converter tries to read the encoding from the message header or exchange property CamelCharsetName. If there is no value defined, UTF-8 is used.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    JSON Prefix Separator \(only if the option *Namespace Mapping* is selected\)
    
    </td>
    <td valign="top">
    
    Enter the JSON prefix separator to be used to separate the JSON prefix from the local part. The value used must not be used in the JSON prefix or local name.

    The following characters are allowed: colon\(:\), comma\(,\), dot\(.\), pipe\(|\), semicolon\(;\), and space.
    
    </td>
    </tr>
    </table>
    
4.  Specify whether to enable *Streaming* or not.

    With streaming you can specify whether the whole XML document or only specified XML elements are to be presented by JSON arrays.


    <table>
    <tr>
    <td valign="top">
    
    All
    
    </td>
    <td valign="top">
    
    All elements are presented as JSON arrays.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Specific Ones
    
    </td>
    <td valign="top">
    
    Only the specified elements will be represented as JSON arrays, the others as JSON objects.

    > ### Note:  
    > A JSON object is an unordered set of name/value pairs that begins with `{` and ends with `}`. Each name is followed by `:` and the name/value pairs are separated by `,`.
    > 
    > A JSON array is an ordered collection of values. An array begins with `[` and ends with `]`. Values are separated by`,`.

    Enter the absolute paths to the XML elements to be converted to JSON arrays. Specify all elements with a multiplicity larger than one. Otherwise, it cannot be ensured that streaming will result in a valid JSON document.

    Familiarize yourself with streaming in the XML-to-JSON converter, as documented in a separate topic.
    
    </td>
    </tr>
    </table>
    
5.  If you want to continue editing the integration package without exiting, choose *Save*.

6.  If you want to retain your changes as a variant, choose *Save as version* to retain a copy of the current artifact.

7.  If you want to terminate the creation of package, choose *Cancel* before saving it.


