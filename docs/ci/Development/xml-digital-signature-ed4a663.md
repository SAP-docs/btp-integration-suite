<!-- loioed4a66365eef448ea8cdb9441e856639 -->

# XML Digital Signature



The following types of XML digital signatures are supported:

-   **Enveloping XML Signature**: The input message body is signed and embedded within the signature. This means that the message body is wrapped by the *Object* element, where *Object* is a child element of the *Signature* element.

    > ### Example:  
    > A template of the enveloping signature is shown below and describes the structure supported by XML signature implementation. \("?" denotes zero or one occurrence; the brackets \[\] denote variables whose values can vary.\)
    > 
    > ```
    > <Signature>
    >      <SignedInfo>
    >             <CanonicalizationMethod>
    >             <SignatureMethod>
    >             <Reference URI="#[generated object_id]" type="[optional_type_value]">
    >                   <Transform Algorithm="canonicalization method">
    >                   <DigestMethod>
    >                   <DigestValue>
    >             </Reference>
    >             (<Reference URI="#[generated keyinfo_id]">
    >                   <Transform Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315"/>
    >                   <DigestMethod>
    >                   <DigestValue>
    >             </Reference>)?
    >      </SignedInfo>
    >      <SignatureValue>
    >      (<KeyInfo Id="[generated keyinfo_id]">)?
    > 	<--!The Id attribute is only added if there exists a reference-->
    >      <Object Id="[generated object_id]"/>
    > </Signature>
    > 
    > ```

-   **Enveloped XML Signature**: The digital signature is embedded in the XML message to be signed. This means that the XML message contains the *Signature* element as one of its child elements. The *Signature* element contains information such as:

    -   Algorithms to be used to obtain the digest value
    -   Reference with empty URI, which means the entire XML resource
    -   Optional reference to the KeyInfo element \(attribute *Also Sign Key Info*\)
    -   Headers:


        <table>
        <tr>
        <td valign="top">
        
        *CamelXmlSignatureContentReferenceUri*
        
        </td>
        <td valign="top">
        
        Reference URI for the content to be signed.

        Only used in the enveloped case. The value must be a reference to an attribute of type ID, example: \#attribute\_value. The resource schema URI \(see header CamelXmlSignatureSchemaResourceUri\) must also be set because the schema validator will find out which attributes are attributes of type ID. Will be ignored in the enveloping or detached case.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *CamelXmlSignatureSchemaResourceUri*
        
        </td>
        <td valign="top">
        
        Can be set in the enveloped and enveloping case.

        If set, then the XML document is validated with the specified XML schema which must be uploaded as XSD resource into the integration flow. Overwrites the XML Schema File Path set for the detached XML Signature.
        
        </td>
        </tr>
        </table>
        

    > ### Example:  
    > A template of the enveloped signature is shown below and describes the structure supported by XML signature implementation. \("?" denotes zero or one occurrence; the brackets \[\] denote variables whose values can vary\):

    ```
    <[parent element]>
          ...
          <Signature>
              <SignedInfo>
                    <CanonicalizationMethod>
                    <SignatureMethod>
                    <Reference URI="" type="[optional_type_value]">
                          <Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
                          <Transform Algorithm=[canonicalization method]/>
                          <DigestMethod>
                          <DigestValue>
                    </Reference>
                    (<Reference URI="#[generated keyinfo_Id]">
                          <Transform Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315"/>
                          <DigestMethod>
                          <DigestValue>
                    </Reference>)?
             </SignedInfo>
             <SignatureValue>
             (<KeyInfo Id="[generated keyinfo_id]">)?
    		<--!The Id attribute is only added if there exists a reference-->
         </Signature>
    </[parent element]>
    
    ```

-   **Detached XML Signature**: The digital signature is a sibling of the signed element. There can be several XML signatures in one XML document.

    You can sign several elements of the message body. The elements to be signed must have an attribute of type ID. The ID type of the attribute must be defined in the XML schema that is specified during the configuration.

    Additionally, you specify a list of XPath expressions pointing to attributes of type ID. These attributes determine the elements to be signed. For each element, a signature is created as a sibling of the element. The elements are signed with the same private key. Elements with a higher hierarchy level are signed first. This can result in nested signatures.


> ### Example:  
> A template of the detached signature is shown below and describes the structure supported by XML signature implementation. \("?" denotes zero or one occurrence; the brackets \[\] denote variables whose values can vary\):

> ### Sample Code:  
> ```
> (<[signed element] Id="[id_value]">
> <!-- signed element must have an attribute of type ID -->
>       ...
> </[signed element]>
> <other sibling/>* <!-- between the signed element and the corresponding signature element, there can be other siblings -->
> <Signature>
> <!-- signature element becomes the last sibling of the signed element -->
>            <SignedInfo>
>                 <CanonicalizationMethod>
>                 <SignatureMethod>
>                 <Reference URI="#[id_value]" type="[optional_type_value]">
>                 <!-- reference URI contains the ID attribute value of the signed element -->
>                       <Transform Algorithm=[canonicalization method]/>
>                       <DigestMethod>
>                       <DigestValue>
>                 </Reference>
>           </SignedInfo>
>           <SignatureValue> 
>          <!-- The Id attribute is only added if there exists a reference with the corresponding URI -->
> </Signature>)+
> 
> ```

Note that the following elements are generated and cannot be configured with the Integration Designer:

-   Key Info ID
-   Object ID



The sender canonicalizes the XML resource to be signed, based on the specified transform algorithm. Using a digest algorithm on the canonicalized XML resource, a digest value is obtained. This digest value is included within the 'Reference' element of the 'SignedInfo' block. Then, a digest algorithm, as specified in the signature algorithm, is used on the canonicalized SignedInfo. The obtained digest value is encrypted using the sender's private key.

> ### Note:  
> Canonicalization transforms the XML document to a standardized format, for example, canonicalization removes white spaces within tags, uses particular character encoding, sorts namespace references and eliminates redundant ones, removes XML and DOCTYPE declarations, and transforms relative URIs into absolute URIs. The representation of the XML data is used to determine if two XML documents are identical. Even a slight variation in white spaces results in a different digest for an XML document.

