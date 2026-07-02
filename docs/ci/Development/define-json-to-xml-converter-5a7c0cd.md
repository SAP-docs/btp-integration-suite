<!-- loio5a7c0cd2a3e8497c89ffcda41787477f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define JSON to XML Converter

The JSON to XML converter enables you to transform messages in JSON format to XML format.



<a name="loio5a7c0cd2a3e8497c89ffcda41787477f__prereq_fnn_w1t_5fb"/>

## Prerequisites

-   You are familiar with the conversion rules for JSON to XML conversion.

    For more information, see [Conversion Rules for JSON to XML Conversion](conversion-rules-for-json-to-xml-conversion-232a9cf.md).

-   You are familiar with the limitations for JSON to XML conversion.

    See [Limitations for JSON to XML Conversion](limitations-for-json-to-xml-conversion-3a02829.md).

-   You are editing the integration flow in the editor.




## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span>, then choose *Transformation* \> *Converter* \> *JSON to XML Converter*.

2.  Insert the converter at the desired position in your integration process.

    The converter appears as a graphical element in your integration process.

    The properties tab page for the XML to JSON Converter opens.

3.  Define the parameters for your conversion, see table below.


    <table>
    <tr>
    <th valign="top">

    Tab
    
    </th>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    General
    
    </td>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter the name of the converter.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="5">
    
    Processing
    
    </td>
    <td valign="top">
    
    JSON Prefix \(only if the option *Use Namespace Mapping* is selected\)
    
    </td>
    <td valign="top">
    
    Enter the mapping of the JSON prefix to the XML namespace. The JSON namespace/prefix must begin with a letter and can contain aA-zZ and 0-9.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    JSON Prefix Separator
    
    </td>
    <td valign="top">
    
    Enter the JSON prefix separator to be used to separate the JSON prefix from the local part. The value used must not be used in the JSON prefix or local name.

    The following characters are allowed: colon\(:\), comma\(,\), dot\(.\), pipe\(|\), semicolon\(;\), and space.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Add XML Root Element
    
    </td>
    <td valign="top">
    
    Select this option to convert JSON documents with an XML root element
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Name \(only if the option *Add XML Root Element* is selected\)
    
    </td>
    <td valign="top">
    
    Enter the name of the XML root element. The name must comply with the NCName rules:

    -   The name must begin with a letter or an underscore.
    -   The valid characters for the remainder of the name are:
        -   Letters
        -   Digits
        -   Period
        -   Hyphen
        -   Underscore



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Namespace Mapping \(only if the option *Add XML Root Element* is selected\)
    
    </td>
    <td valign="top">
    
    Enter the namespace of the XML root element that you have configured in the integration flow.
    
    </td>
    </tr>
    </table>
    
4.  If you want to continue editing the integration package without exiting, choose *Save*.

5.  If you want to retain your changes as a variant, choose *Save as version* to retain a copy of the current artifact.

6.  If you want to terminate the creation of package, choose *Cancel* before saving it.


**Related Information**  


[Define XML to JSON Converter](define-xml-to-json-converter-a60a282.md "The XML to JSON converter enables you to transform messages in XML format to JSON format.")

[Define Message Transformer Steps](define-message-transformer-steps-e223071.md "Message transformers convert messages in one format to another.")

