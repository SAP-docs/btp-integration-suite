<!-- loio13b3dc9014a24c249ea04cf4db366f7d -->

# Displaying Properties of a PGP Key

Display properties of a selected PGP key.



## Context

There are the following key types:

-   *Public*

    Public PGP key

-   *Secret*

    Public/secret key pair


See: [How OpenPGP Works](../40-RemoteSystems/how-openpgp-works-29bc188.md)



<a name="loio13b3dc9014a24c249ea04cf4db366f7d__steps_jyx_3j5_cwb"/>

## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  Click a key to show the details.

3.  The *Key Details* tab shows the following attributes for the selected key.


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
    
    *Fingerprint* 
    
    </td>
    <td valign="top">
    
    Character sequence that identifies the public key.

    A fingerprint is generated out of the public key applying a hash function on the public key.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User IDs* 
    
    </td>
    <td valign="top">
    
    User IDs associated with the key.

    In the context of PGP, a user ID indicates the entity that uses the key to perform a dedicated action on the message content.

    The user ID can be a name, an email address, or a combination of both.

    Examples:

    -   A user ID associated with a public PGP key indicates the entity that receives the message encrypted with the public key.

    -   A user ID associated with a secret PGP key indicates the entity that sends the encrypted message that is to be decrypted using the secret key.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PGP Keys* 
    
    </td>
    <td valign="top">
    
    This section shows a set of attributes for the key and \(if defined\) its subkeys.

    The following attributes are displayed:

    -   *ID*

        Key ID that uniquely identifies the key or sub key.

    -   *Type*

        Asymmetric key algorithm.

        Supported values: RSA, DSA, Elgamal

        In particular, elyptic curve algorithms are not supported.

    -   *Strength*

        The length of the key in bits.

    -   *Usage \(Key Flags\)*

        Shows for which activity the key is used, for example, for message encryption.

    -   *Valid From*

    -   *Valid Until*

        Indicates the expiration date.

    -   *Modified On*

        Indicates the date and time the key was last modified.



    
    </td>
    </tr>
    </table>
    

