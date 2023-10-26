<!-- loioe0ef25c8894e45eb8a9e75e0e0bc6944 -->

# Protect Data Integrity

One important security requirement is to protect the integrity of data throughout its path between the components connected by an integration. Data integrity means that you can always ensure that the payload or a part of its content hasn't been changed unintentionally.

SAP Integration Suite comes with the *Message Digest* step type. With this integration flow step, you can define a digest of one or more payload elements.

> ### Tip:  
> A digest \(also referred to as *hash value*\) is an expression with a fixed size calculated from an input value \(which can be of any size\). Performing the same hash algorithm on the same data results in the same digest. However, the inverse operation isn’t possible: The input value can’t be reproduced out of the hash value.

A digest provides a secure way to check if the content of a certain payload element has been changed.

A digest is calculated from an XML element or a set of XML elements using a certain canonicalization method and a digest algorithm.

More information: [Define Message Digest](define-message-digest-e5d2867.md)



<a name="loioe0ef25c8894e45eb8a9e75e0e0bc6944__section_utn_sx4_spb"/>

## Implementation

To illustrate this feature in a simple scenario, you can deploy and run the integration flow *Apply Security - Protect Data Integrity*.

This integration flow is designed in the following way:

![](images/ApplySecurity_ProtectDataIntegrity_94aeb47.png)

The integration flow is called by an HTTP client, for example Postman.

The integration flow performs the following steps.

1.  Content Modifier *Define hash of expected text* stores the hash value of the text element \(as expected in the inbound message\) as property.

    In tab *Exchange Property*, a single property is specified:

    ****


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    ExpectedHash
    
    </td>
    <td valign="top">
    
    Constant
    
    </td>
    <td valign="top">
    
    CBUArpOZ6Wfota6iRcAPlk3YW14=
    
    </td>
    </tr>
    </table>
    
    The hash value has been calculated from the following request body element using the `SHA1` digest algorithm and the `Canonical XML Version 1.0` canonicalization method:

    ```
    <wordGame>
    <text xmlns:a="http://demo.sap.com" a:language="English" a:category="tongue twister">She sells seashells by the seashore</text>
    <rating></rating>
    </wordGame>
    ```

    The request body contains an XML message with:

    -   1 text element that contains as value the citation of a popular tongue twister

    -   1 empty element


    The `ExpectedHash` property is used as reference at a later step: By comparing its value with the message digest derived from the inbound message, Cloud Integration can detect if the latter one has been changed.

2.  The *Message Digest* step is configured in the following way \(*Processing* tab\):

    ****


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Filter \(XPath\)
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Canonicalization Method
    
    </td>
    <td valign="top">
    
    Canonical XML Version 1.0
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Digest Algorithm
    
    </td>
    <td valign="top">
    
    SHA1
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Header
    
    </td>
    <td valign="top">
    
    SAPMessageDigest
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > -   The *Filter \(XPath\)* field is left empty. This means that the whole XML message is taken and processed by this step. This setting has been chosen to show how canonicalization works \(when executing the scenario with different XML messages as request body\).
    > 
    > -   The *Canonicalization Method* parameter allows you to transform the XML content of the message body into a form that makes it possible to compare it with other XML documents \(see [Define Message Digest](define-message-digest-e5d2867.md)\). If you select *Canonical XML Version 1.0*, the message body \(out of which the digest is calculated\) is transformed in such a way that, for example:
    > 
    >     -   Whitespace in start and end tags is normalized.
    > 
    >     -   Empty elements are encoded as start/end pairs.
    > 
    >     -   The sequence of element attributes is normalized.
    > 
    > 
    > -   When you model an integration flow with a *Message Digest* step by yourself, the name *SAPMessageDigest* for the *Target Header* header is proposed by as default value. You can give this header any name, if desired.

    You notice that the same canonicalization method and digest algorithm are specified like used to calculate the digest stored in the `ExpectedHash` property.

3.  A *Router* step creates 2 routes, each containing a Content Modifier with the name *Define response message body*:

    -   The Content Modifier in the *ok* route \(specified as default route\) defines the following message body \(*Message Body* tab\)

        ```
        All good! \n
        The content of the message hasn't been changed.
        
        Digest: ${header.SAPMessageDigest}
        ```

    -   The *not ok* route has the condition:

        `${property.ExpectedHash} != ${header.SAPMessageDigest}`

        That means, this route is taken when the hash value stored in the `ExpectedHash` property isn't equal to the hash value calculated from the inbound message \(which is stored in the `SAPMessageDigest` header\).

        The Content Modifier in the *not ok* route defines the following message body \(*Message Body* tab\)

        ```
        Caution!\n
        The content of the message has been changed.
        
        Digest differs: ${header.SAPMessageDigest} 
        ```





<a name="loioe0ef25c8894e45eb8a9e75e0e0bc6944__section_e5f_z4f_bqb"/>

## Executing the Scenario

If you use Postman to run the scenario, you can download the Postman collection that comes with the integration package *Integration Flow Design Guidelines - Apply Highest Security Standards* and upload it to your local Postman installation. The predefined requests to run this example scenario are in folder *DataIntegrity*.

This folder contains 1 GET request and 5 POST requests. The GET request *DataIntegrity1* is used to fetch the X-CSRF token for the subsequent POST requests \(see [Use CSRF Protection](use-csrf-protection-a0765d5.md)\). The 5 POST requests differ only in the request body. We propose that you run the requests one after each other to find out in which case the integration flow identifies the inbound message as being changed.

1.  Run the GET request *DataIntegrity\_GetXsrfToken* to fetch the X-CSRF token.

2.  Run the *DataIntegrity - Original payload* request.

    This request uses the message body that also was taken to calculate the reference digest value \(`ExpectedHash` property\). We refer to this message body as the *original message body*:

    ```
    <wordGame>
    <text xmlns:a="http://demo.sap.com" a:language="English" a:category="tongue twister">She sells seashells by the seashore</text>
    <rating></rating>
    </wordGame>
    ```

    Therefore, as expected, you get the following response:

    ```
    All good! 
    
    The content of the message hasn't been changed.
    
    Digest: CBUArpOZ6Wfota6iRcAPlk3YW14=
    ```

3.  Run the *DataIntegrity - Empty element* request.

    This request uses the following message body:

    ```
    <wordGame>
    <text xmlns:a="http://demo.sap.com" a:language="English" a:category="tongue twister">She sells seashells by the seashore</text>
    <rating/>
    </wordGame>
    ```

    You notice that this XML differs from the original one in the following way: The empty element is represented by the expression `<rating/>` instead of a start/end tag pair. When using canonicalization, the corresponding XML is equivalent to the original one.

    Therefore, you get the following response:

    ```
    All good! 
    
    The content of the message hasn't been changed.
    
    Digest: CBUArpOZ6Wfota6iRcAPlk3YW14=
    ```

4.  Run the *DataIntegrity - Order of attributes and namespace* request.

    This request uses the following message body:

    ```
    <wordGame>
    <text a:category="tongue twister" a:language="English" xmlns:a="http://demo.sap.com">She sells seashells by the seashore</text>
    <rating></rating>
    </wordGame>
    ```

    In this XML, the sequence of attributes and namespace in the text element is different as compared to the original message body. When using canonicalization, the corresponding XML is equivalent to the original one.

    Therefore, you get the following response:

    ```
    All good! 
    
    The content of the message hasn't been changed.
    
    Digest: CBUArpOZ6Wfota6iRcAPlk3YW14=
    ```

5.  Run the *DataIntegrity - Comments* request.

    This request uses the following message body:

    ```
    <wordGame>
    <text xmlns:a="http://demo.sap.com" a:language="English" a:category="tongue twister">She sells seashells by the seashore</text>
    <rating><!-- first comment --></rating>
    </wordGame>
    <!-- second comment -->
    ```

    In this XML, comments have been added to the XML. When using canonicalization, the corresponding XML is equivalent to the original one.

    Therefore, you get the following response:

    ```
    All good! 
    
    The content of the message hasn't been changed.
    
    Digest: CBUArpOZ6Wfota6iRcAPlk3YW14=
    ```

6.  Run the *DataIntegrity - Text modified* request.

    This request uses the following message body:

    ```
    <wordGame>
    <text xmlns:a="http://demo.sap.com" a:language="English" a:category="tongue twister">She sells seashells at the seashore</text>
    <rating></rating>
    </wordGame>
    ```

    In this XML, the value of the text element has been changed: The text of the tongue twister is slightly different as compared to the original message and reads: `She sells seashells at the seashore` instead of `She sells seashells by the seashore`. Even when using canonicalization, the corresponding XML different to the original one.

    Therefore, you get the following response:

    ```
    Caution!
    
    The content of the message has been changed.
    
    Digest differs: 32bSWmPbj73onA6gVo9CaUWcoYg=
    ```


