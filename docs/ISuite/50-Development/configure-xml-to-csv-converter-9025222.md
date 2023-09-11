<!-- loio902522209e7546f89c3c52ad018603d1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure XML to CSV Converter



<a name="loio902522209e7546f89c3c52ad018603d1__prereq_r4q_gyq_25b"/>

## Prerequisites

You are editing the integration flow in the editor.



## Context

The XML to CSV converter converts content in XML format into CSV format.

> ### Note:  
> Note that for the schema of the source XML document only simple type is supported.

You use this procedure to configure XML to CSV converter.



<a name="loio902522209e7546f89c3c52ad018603d1__steps_hcr_bnx_jr"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons"></span>, then ** \> *Converter* \> *XML to CSV Converter*.

2.  Place the *XML to CSV converter* in the integration process and define the message path.

3.  Choose *XML to CSV Converter* and provide values in fields based on description in table.


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
    
    Path to Source Element in XSD


    
    </td>
    <td valign="top">
    
    Path to the source element in the XSD file


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Field Separator in CSV


    
    </td>
    <td valign="top">
    
    Select the character that you want to use as the field separator in CSV file from dropdown list

    > ### Tip:  
    > If you want to use a field separator that is not available in the dropdown list, manually enter the character.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Include Field Name as Headers


    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to use the field names as the headers in CSV file


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Include Parent Element


    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to include the parent element of the XML file in CSV file


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Include Attribute Values


    
    </td>
    <td valign="top">
    
    Select this checkbox if you want to include attribute values in the CSV file


    
    </td>
    </tr>
    </table>
    
4.  Save or deploy the configuration.

    > ### Note:  
    > -   The converter doesn't support XML values with newline characters.
    > 
    > -   The CSV format will contain the values in the same order of occurrence of header and row tags in the XML.
    > -   When optional fields exists in the XML, the ordering is maintained in the order when a tag is encountered.
    > -   If there are namespaces declared in the schema file, the same has to be declared at the integration flow level and the namespace prefixes can be used in the XPATH expression.


