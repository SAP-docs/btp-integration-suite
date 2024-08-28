<!-- loioe5d2867ed03c4e5f89002817180b9037 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Message Digest

This integration flow step is used to calculate a digest of the payload or parts of it and store the result in a message header.



## Context

In detail, the *Message Digest* integration flow step transforms a message into a canonical XML document. From this document, a digest \(hash value\) is calculated and written to the message header.

> ### Tip:  
> A digest \(also referred to as *hash value*\) is an expression with a fixed size calculated from an input value \(which can be of any size\). Performing the same hash algorithm on the same data results in the same digest. However, the inverse operation isn’t possible: The input value can’t be reproduced out of the hash value.

You can use this feature to implement scenarios like the following ones:

-   Instead of a signature, you can send the digest along with a certain value in a message. That way, you enable the receiver to check if the value has been changed during processing.

-   Instead of a certain value, you can store its digest. You can check for the value's digest to find out if it has changed during message processing.


> ### Note:  
> This step can only process XML content.

> ### Tip:  
> To learn how to quickly check if a response message from an external data source has been changed between 2 message processing runs, see [Simple Integration Flow Using a Message Digest Step](simple-integration-flow-using-a-message-digest-step-8b5a7ce.md).



## Procedure

1.  If the *Message Digest* step is present in the integration flow, select it to edit the properties.

2.  If you want to add a *Message Digest* step to the integration flow, perform the following substeps:

    1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Transformers\)and then choose <span class="SAP-icons-V5"></span> \(Message Digest\).

    2.  Place *Content Modifier* step in the integration process.


3.  Specify the following attributes for the step.


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
    
    **Filter \(XPath\)**
    
    </td>
    <td valign="top">
    
    If you only want to transform part of the message, enter an XPath expression to specify the part \(optional attribute\).

    You can also define a prefix namespace mapping.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Canonicalization Method**
    
    </td>
    <td valign="top">
    
    Canonicalization transforms an XML document into a form \(the canonical form\) that makes it possible to compare it with other XML documents. With the *Message Digest* integration flow step, you can apply canonicalization to a message or to parts of a message, calculate a digest out of the transformed message, and add the digest to the message header.

    In simple terms, canonicalization skips nonsignificant elements from an XML document. To give some examples, the following changes are applied during the canonicalization of an XML document: Unification of quotation marks and blanks, or encoding of empty elements as start/end pairs. The original message remains unchanged.

    You can choose between the following methods:

    -   *Canonical XML Version 1.0*

        More information: [http://www.w3.org/TR/2001/REC-xml-c14n-20010315](http://www.w3.org/TR/2001/REC-xml-c14n-20010315)

    -   *Canonical XML with Comments Version 1.0*

        More information: [http://www.w3.org/TR/2001/REC-xml-c14n-20010315\#WithComments](http://www.w3.org/TR/2001/REC-xml-c14n-20010315#WithComments)

    -   *Exclusive XML Canonicalization Version 1.0*

        More information: [http://www.w3.org/2001/10/xml-exc-c14n](http://www.w3.org/2001/10/xml-exc-c14n)

    -   *Exclusive XML Canonicalization with Comments Version 1.0*

        More information: [http://www.w3.org/2001/10/xml-exc-c14n\#WithComments](http://www.w3.org/2001/10/xml-exc-c14n#WithComments)

    -   *XML Canonicalization Version 1.1*

        More information: [http://www.w3.org/2006/12/xml-c14n11](http://www.w3.org/2006/12/xml-c14n11)

    -   *XML Canonicalization with Comments Version 1.1*

        More information: [http://www.w3.org/2006/12/xml-c14n11\#WithComments](http://www.w3.org/2006/12/xml-c14n11#WithComments)

    -   *None*



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Digest Algorithm**
    
    </td>
    <td valign="top">
    
    Select the hash algorithm to be used to calculate the digest \(mandatory attribute\).

    You can choose between the following hash algorithms:

    -   *MD5*
    -   *SHA1* 
    -   *SHA256* 
    -   *SHA384* 
    -   *SHA512* 

    Default value: SHA512

    > ### Caution:  
    > Algorithms starting with SHA1, MD2, or MD5 are still supported for compatibility reasons, but they no longer meet today's security requirements. Therefore, we recommend using stronger algorithms where possible. Check with your security experts or authorities like NIST for more detailed security recommendations.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Target Header Name**
    
    </td>
    <td valign="top">
    
    Enter the name of the target header element, which is to contain the hash value \(mandatory attribute\).

    The value of this header contains the base64-encoded message digest.

    By default, the header has the name `SAPMessageDigest`, but you can also define another header name.
    
    </td>
    </tr>
    </table>
    

