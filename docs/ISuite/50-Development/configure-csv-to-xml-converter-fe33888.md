<!-- loiofe338881f2fc4ea094c334b18e63a015 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure CSV to XML Converter



<a name="loiofe338881f2fc4ea094c334b18e63a015__prereq_n5z_gyq_25b"/>

## Prerequisites

You’re editing the integration flow in the editor.



## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span>, then navigate to *Converter* \> *CSV to XML Converter*.

2.  Place the *CSV to XML converter* shape in the integration process and define the message path.

3.  Choose *CSV to XML Converter* and provide values in fields based on description in table.


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
    
    XML Schema
    
    </td>
    <td valign="top">
    
    Choose *Browse*. Select the XML schema you want to use.

    Optionally, you can also upload the XML schema from your local file system by choosing *Upload from File System*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Path to Target Element in XSD
    
    </td>
    <td valign="top">
    
    XPath in the XML schema file where you want to place the content from CSV file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Record Marker in CSV
    
    </td>
    <td valign="top">
    
    The record in CSV file that indicates the entry that the converter has to consider as the starting point of the content.

    > ### Note:  
    > If you don’t provide a value for this field, the converter considers all the records in the CSV file for conversion.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Field Separator in CSV
    
    </td>
    <td valign="top">
    
    Select the character from dropdown list that is used as the field separator in CSV file.

    > ### Tip:  
    > If you want to use a field separator that isn’t available in the dropdown list, manually enter the character.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Exclude First Line Header
    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to use the header information from the first line of CSV file to map the column to the corresponding xsd attributes.

    > ### Note:  
    > If you don't select the checkbox, then the converter maps the attributes of the CSV file to the order of occurrence in the XSD.
    > 
    > To use this option, the CSV and XSD must share the same header-attribute names. If the header names don't match or the same header name is used multiple times in the first line of the CSV, it leads to ambiguity that the converter can resolve as it's an unsupported XML specification.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The CSV to XML flow step, version 1.4 and above, supports dynamic configurations for fields such as XML Schema, Path to Target Element in XSD, and Record Marker in CSV. For a header or property, the accepted format is "$\{header.<headername\>\}" or "$\{property.<propertyname\>\}". For the partner directory, the accepted format is "pd:<partnerId\>:<parameterId\>".
    > 
    > In addition to the above, for XML Schema, you now have the ability to consume an XSD file from the partner directory in binary form. For this, the accepted format for the partner directory is "pd:<partnerId\>:<parameterId\>:binary".

4.  Save or deploy the configuration.


