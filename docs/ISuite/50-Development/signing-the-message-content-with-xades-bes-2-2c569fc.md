<!-- loio2c569fce9f844bb5b9752d3c6b457605 -->

# Signing the Message Content with XAdES-BES \(2\)

This option allows you to add further contextual information to the signature, like, for example, the place where the signature has been created, or the type of commitment assured by the signer when creating the signature.



## Context

For more information on XAdES, see:

-   [Signing the Message Content with XML Advanced Electronic Signature](signing-the-message-content-with-xml-advanced-electronic-signature-874e032.md)

-   [http://uri.etsi.org/01903/v1.3.2/ts\_101903v010302p.pdf](http://uri.etsi.org/01903/v1.3.2/ts_101903v010302p.pdf)

-   [Limitations](limitations-08d4522.md)

-   [Message Headers](message-headers-e26ab8c.md)




## Procedure

1.  Under *Production Place* enter information on the purported place where the signer claims to have produced the signature \(City, State/Province, Postal Code, and Country Name\).

2.  Specify the commitment to be undertaken by the signer \(for example, proof of origin, proof of receipt, proof of creation\).


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
    
    *Commitment* 
    
    </td>
    <td valign="top">
    
    Specify the commitment. You can select one of the following values:

    -   `Proof of origin` 

        Indicates that the signer recognizes to have created, approved and sent the signed data object.

        The URI for this commitment is: [http://uri.etsi.org/01903/v1.2.2\#ProofOfOrigin](http://uri.etsi.org/01903/v1.2.2#ProofOfOrigin).

    -   `Proof of receipt` 

        Indicates that signer recognizes to have received the content of the signed data object.

        The URI for this commitment is: [http://uri.etsi.org/01903/v1.2.2\#ProofOfReceipt](http://uri.etsi.org/01903/v1.2.2#ProofOfReceipt).

    -   `Proof of delivery` 

        Indicates that the trusted service provider \(TSP\) providing that indication has delivered a signed data object in a local store accessible to the recipient of the signed data object.

        The URI for this commitment is: [http://uri.etsi.org/01903/v1.2.2\#ProofOfDelivery](http://uri.etsi.org/01903/v1.2.2#ProofOfDelivery).

    -   `Proof of sender` 

        Indicates that the entity providing that indication has sent the signed data object \(but not necessarily created it\).

        The URI for this commitment is: [http://uri.etsi.org/01903/v1.2.2\#ProofOfSender](http://uri.etsi.org/01903/v1.2.2#ProofOfSender).

    -   `Proof of approval` 

        Indicates that the signer has approved the content of the signed data object.

        The URI for this commitment is: [http://uri.etsi.org/01903/v1.2.2\#ProofOfApproval](http://uri.etsi.org/01903/v1.2.2#ProofOfApproval).

    -   `Proof of creation` 

        Indicates that the signer has created the signed data object \(but not necessarily approved, nor sent it\).

        The URI for this commitment is: [http://uri.etsi.org/01903/v1.2.2\#ProofOfCreation](http://uri.etsi.org/01903/v1.2.2#ProofOfCreation).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Enter a free text description of the commitment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Documentation Reference*
    
    </td>
    <td valign="top">
    
    Enter references \(URIs\) to one or more documents where the commitment is described.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Commitment Qualifier*
    
    </td>
    <td valign="top">
    
    Enter additional qualifying information on the commitment made by the signer.

    Enter a text or an XML fragment with the root element *CommitmentTypeQualifier*.
    
    </td>
    </tr>
    </table>
    
    Adding these properties helps to avoid legal disputes as the commitment undertaken by the signer can be compared with the commitment made in the context of an applied signature policy.

3.  Under *XML Document Parameters*, select the namespace of the XAdES version and enter a namespace prefix.


