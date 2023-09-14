<!-- loioed4a66365eef448ea8cdb9441e856639 -->

# XML Digital Signature



The sender canonicalizes the XML resource to be signed, based on the specified transform algorithm. Using a digest algorithm on the canonicalized XML resource, a digest value is obtained. This digest value is included within the 'Reference' element of the 'SignedInfo' block. Then, a digest algorithm, as specified in the signature algorithm, is used on the canonicalized SignedInfo. The obtained digest value is encrypted using the sender's private key.

> ### Note:  
> Canonicalization transforms the XML document to a standardized format, for example, canonicalization removes white spaces within tags, uses particular character encoding, sorts namespace references and eliminates redundant ones, removes XML and DOCTYPE declarations, and transforms relative URIs into absolute URIs. The representation of the XML data is used to determine if two XML documents are identical. Even a slight variation in white spaces results in a different digest for an XML document.

