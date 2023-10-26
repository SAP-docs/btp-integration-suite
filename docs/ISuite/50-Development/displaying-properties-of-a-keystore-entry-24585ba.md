<!-- loio24585bafb39b42d6a1856e05ad2b428a -->

# Displaying Properties of a Keystore Entry

Display properties of a selected keystore entry.



## Context

There are the following entry types:

-   *Key Pair* entry

    Consists of a private key and its X.509 certificate chain.

    All private keys of a keystore are encrypted with the same password. This password is also used as the keystore password \(for checking the integrity of the keystore\). The keystore is never stored in the same database as the encrypted/signed application data. The password is stored in a separate database.

    The certificate chain typically consists of the public key certificate and the intermediate certification authority \(CA\) certificate with which the signature of the public key certificate can be verified.

-   *Certificate* entry

    In many cases this is an X.509 root certificate.




## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  Click the alias of a keystore entry to show the details.

3.  The following attributes are shown for the selected keystore entry.

    In case, the keystore entry is part of a certificate chain, the certificate chain is displayed as a hierarchy tree at left.

    The following details are displayed for the selected keystore entry. When you click a certain element in the certificate chain, the details are adapted to show the details of this element.

    -   The *Keystore* attribute indicates if the displayed entry is part of the currently active keystore \(*Current*\) or of the backed-up keystore \(*Backup*\).

    -   The *Alias* is used to refer to a specific public key from a keystore.

    -   The *Owner* can either by *SAP* or *Tenant Administrator*.


    **Administration Attributes**


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Created By* 
    
    </td>
    <td valign="top">
    
    User who created the certificate
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Created On* 
    
    </td>
    <td valign="top">
    
    Time when certificate has been created
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Last Modified By* 
    
    </td>
    <td valign="top">
    
    User that modified the keystore entry at the latest
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Last Modified On* 
    
    </td>
    <td valign="top">
    
    Time when the keystore entry has been modified at the latest
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The user shown in *Last Modified By* is anonymized \(the string *SAP* is shown\) in case the keystore is owned by SAP.

    **General Attributes**


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Type* 
    
    </td>
    <td valign="top">
    
    -   *Key Pair*

        Consists of a private key and its X.509 certificate chain.

    -   *Certificate*

        In many cases this is an X.509 root certificate.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Version* 
    
    </td>
    <td valign="top">
    
    Certificate version
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Serial Number* 
    
    </td>
    <td valign="top">
    
    Serial number of certificate as provided by the issuer
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Subject DN* 
    
    </td>
    <td valign="top">
    
    Distinguished name of the entity associated with the public key of the certificate
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Issuer DN* 
    
    </td>
    <td valign="top">
    
    Distinguished name of the issuer \(the certification authority that issued and signed the certificate\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Type* 
    
    </td>
    <td valign="top">
    
    Cryptographic standard the keystore entry is using \(for example, RSA\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Size* 
    
    </td>
    <td valign="top">
    
    Number of bits \(also referred to as *Key Length*\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signature Algorithm* 
    
    </td>
    <td valign="top">
    
    Algorithm used to create the signature of the key entry \(for example, `SHA-512`\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Valid From* 
    
    </td>
    <td valign="top">
    
    Start of validity period
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Valid Until* 
    
    </td>
    <td valign="top">
    
    End of validity period
    
    </td>
    </tr>
    </table>
    
    The section *Fingerprints* shows different sequences defined to identify the public key. A fingerprint is generated out of the public key applying a hash function on the public key. For each fingerprint, the hash algorithm is also displayed \(for example, `SHA-512`\).




<a name="loio24585bafb39b42d6a1856e05ad2b428a__postreq_jqk_ysd_lbb"/>

## Next Steps

The following functions are available:

-   You can delete the keystore entry in case it is owned by the Tenant Administrator.

-   You can download the keystore entry.

-   You can change the alias of the keystore entry in case it is owned by the Tenant Administrator.


**Related Information**  


[Changing the Alias of a Keystore Entry](changing-the-alias-of-a-keystore-entry-72b0f88.md "")

