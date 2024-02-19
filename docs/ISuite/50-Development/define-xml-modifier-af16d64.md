<!-- loioaf16d64a4a1a4d23a4169ce1a6feee67 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define XML Modifier

Use the XML Modifier flow step to remove External DTDs and/or to remove XML Declarations.



<a name="loioaf16d64a4a1a4d23a4169ce1a6feee67__prereq_mjd_gyq_25b"/>

## Prerequisites

You're editing the integration flow in the editor.



## Context

With the help of the XML Modifier, users can modify the incoming xml message. The XML Modifier allows you to modify an xml message by removing the XML declaration and/or removing DTDs with external references to avoid issues during message processing as DTDs with external references aren't supported.

> ### Note:  
> XML declarations and DTDs are removed from < to \>. In the case of DTDs, the entire DTD is deleted if it entails an external reference.
> 
> Also, characters following after the \> character \(like line breaks etc.\) remain part of the message \(as shown in the examples below\).



## Procedure

1.  If the *XML Modifier* step is present in the integration flow, select it to edit the properties.

2.  If you want to add *XML Modifier* step to the integration flow, perform the following substeps:

    1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Transformers\)and then choose :envelope:

    2.  Place *XML Modifier* step in the integration process.


3.  Select the *XML Modifier* step, go to the *General* tab define the parameters as follows:

    **XML Modifier – General Tab**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Enter a name for the flow step.
    
    </td>
    </tr>
    </table>
    
4.  Go to the *Processing* tab and define the parameters as follows:

    **XML Modifier – Processing Tab**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Remove External DTDs* \(deactivated by default\)
    
    </td>
    <td valign="top">
    
    Select this option, to remove DTDs with external references from the XML payload.

    > ### Note:  
    > If your payload contains DTDs with external references, the message processing can fail during XML operations.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Remove XML Declaration* \(deactivated by default\)
    
    </td>
    <td valign="top">
    
    Select this option, to remove the XML declaration from the XML payload.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Invalid XML Character Handling*
    
    </td>
    <td valign="top">
    
    Select how to handle XML documents containing characters that are not valid in XML version 1.0/1.1. Depending on the XML version of the source message, the adapter checks the characters against the respective range allowed. Choose between the following options:

    -   *None*: No removal or substitution of invalid XML characters.

    -   *Remove*: Invalid characters are removed.

    -   *Substitute*: Invalid characters are substituted by \#.


    If this configuration option isn't available \(because your are using an older version, for example\), there will be no removal or substitution of invalid XML characters.

    > ### Note:  
    > A character is considered valid, if it's part of the range listed here:
    > 
    > -   *Character Range for XML 1.0*:
    > 
    >     `#x9 | #xA | #xD | [#x20-#xD7FF] | [#xE000-#xFFFD] | [#x10000-#x10FFFF]`*/\* any Unicode character, excluding the surrogate blocks, FFFE, and FFFF. \*/*
    > 
    >     See also: [https://www.w3.org/TR/2008/REC-xml-20081126/\#charsets](https://www.w3.org/TR/2008/REC-xml-20081126/#charsets).
    > 
    > -   *Character Range for XML 1.1*:
    > 
    >     `[#x1-#xD7FF] | [#xE000-#xFFFD] | [#x10000-#x10FFFF]` */\* any Unicode character, excluding the surrogate blocks, FFFE, and FFFF. \*/*
    > 
    >     See also: [https://www.w3.org/TR/2006/REC-xml11-20060816/\#charsets](https://www.w3.org/TR/2006/REC-xml11-20060816/#charsets).
    > 
    >     Restricted characters will be escaped automatically when *Remove* or *Substitute* is used: `[#x1-#x8] | [#xB-#xC] | [#xE-#x1F] | [#x7F-#x84] | [#x86-#x9F]`.


    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the changes.




## Example

*Remove External DTDs*: For our first example, suppose the incoming payload has the following information:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8' ?>
> <!DOCTYPE request SYSTEM "external.dtd">
> <request>This is an example</request>
> 
> ```

After processing, the payload has the following information:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8' ?>
> 
> <request>This is an example</request>
> 
> ```

Similarly, the following happens to the payload in the second example:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8' ?>
> <!DOCTYPE request [
> <!ELEMENT request (#PCDATA)>
> <!ENTITY test SYSTEM "external.dtd">
> ]>
> <request>This is an example</request>
> 
> ```

After processing, the payload has the following information:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8' ?>
> 
> <request>This is an example</request>
> 
> ```

*Remove XML Declaration*: Suppose the incoming payload has the following information:

> ### Sample Code:  
> ```
> <?xml version='1.0' encoding='UTF-8' ?>
> <request>This is an example</request>
> 
> ```

After processing, the payload has the following information:

> ### Sample Code:  
> ```
> 
> 
> <request>This is an example</request>
> ```

