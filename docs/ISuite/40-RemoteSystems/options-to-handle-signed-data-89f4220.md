<!-- loio89f4220ae4f84305af5fe6fe3134ecd2 -->

# Options to Handle Signed Data

To enable the receiver \(using the PKCS7 Signature Verifyer\) to verify the siged message, there needs to be a standard way to pass on the information required to verify the message signature from the sender to the receiver. This is where PKCS\#7 Signed Data comes into play. Signed Data is a specific format that can be used to transfer this information from the sender to the receiver.

The *PKCS7/CMS Signer* step supports different ways to handle Signed Data.

-   Signed Data can be transferred together with the message content as part of the message body. To configure this option, in the *PKCS7/CMS Signer* step select the option *Include Content in Signed Data*.

-   Signed Data can be transferred in an Exchange property \(`SapCmsSignedData`\). To enable this option, in the *PKCS7/CMS Signer* step deselect the option *Include Content in Signed Data*.

    Note that the signer provides no option any more to automatically store the Signed Data object in a header – for reasons of security: If stored in a header, the Signed Data object is by default sent together with the message content to a receiver, if no other measures are taken.

    Up to version 1.2 of the *PKCS\#7/CMS Signer* you can choose to include the signed data in the *SapCmsSignedData* header. From version 1.3 of the *PKCS\#7/CMS Signer* onwards, you can include the signed data in the *SapCmsSignedData* property.

    However, if you still like to use a header on purpose to transfer the Signed Data object to another component, you can define this header in a dedicated step, for example, a content modifier.


As an additional option, you can base64-encode the Signed Data object \(independent of the option you have chosen for *Include Content in Signed Data*\). To do this, select the option *Encode Signed Data with Base64*.

Likewise, the *PKCS7 Signature Verifyer* step can handle the Signed Data object \(received from the sender\) in different ways. Depending on how the verifier expects to receive the Signed Data object, you can select one of the following options when configuring the *PKCS7 Signature Verifyer* step:


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

*Header/Property is Base64-Encoded* 

</td>
<td valign="top">

Select this option of you expect that the Signed Data object is transferred to the receiver that verifies the message either in a header or a property \(with the name SapCmsSignedData\) and, additionally, the value is base64-encoded.

</td>
</tr>
<tr>
<td valign="top">

*Body is Base64-Encoded* 

</td>
<td valign="top">

Select this option of you expect that the message body contains either the Signed Data object including the content or the content alone base64-encoded.

</td>
</tr>
</table>

