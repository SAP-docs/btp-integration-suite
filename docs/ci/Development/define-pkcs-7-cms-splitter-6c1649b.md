<!-- loio6c1649bdd4d04c6ba3baddd490a42e9e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define PKCS\#7/CMS Splitter



## Context

Use a PKCS\#7/CMS Splitter if you want to break down a PKCS7 Signed Data message into two files: one containing the signature and one containing the content.



## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Routing\), then *Splitter* \> *PKCS\#7/CMS Splitter*.

2.  Place the *PKCS\#7/CMS Splitter* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *PKCS\#7/CMS Splitter* element.

4.  On the *Processing* tab, define the attributes of the element based on the descriptions in the following table.


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
    
    *Payload File Name* 
    
    </td>
    <td valign="top">
    
    Name of the file that will contain the payload after the splitting step
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signature File Name* 
    
    </td>
    <td valign="top">
    
    Name of the file \(extension `.sig`\) that will contain the signature after the splitting step
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Wrap by Content Info* 
    
    </td>
    <td valign="top">
    
    Select this option if you want to wrap PKCS\#7 signed data containing the signature into PKCS\#7 content.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PayloadFirst* 
    
    </td>
    <td valign="top">
    
    Select this option if you want the payload to be the first message returned.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *BASE64 Payload* 
    
    </td>
    <td valign="top">
    
    Select this option if you want to encode the payload with the base64 encoding scheme after splitting.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *BASE64 Signature* 
    
    </td>
    <td valign="top">
    
    Select this option if you want to encode the signature using the base64 encoding scheme after splitting.
    
    </td>
    </tr>
    </table>
    

