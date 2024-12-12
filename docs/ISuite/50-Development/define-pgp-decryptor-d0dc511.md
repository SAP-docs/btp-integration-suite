<!-- loiod0dc511970b04f9bb4a844bcc3d5b89e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define PGP Decryptor



## Context

You use the PGP Decryptor to decrypt a message using OpenPGP standards.

To decrypt a message, the decryptor step requires a private key that must be deployed on the tenant \(as part of a PGP Secret Keyring\). The PGP Secret Keyring can contain multiple private keys.

To make sure that the right private key is used for decryption, the encrypted message \(processed by the decryptor\) contains a reference that enables the system to uniquely identify the right key.



## Procedure

1.  In the palette, choose :lock:, then choose ** \> *Decryptor* \> *PGP Decryptor*.

2.  Place *PGP Decryptor* in integration process and define the message path.

3.  Define the following parameters in the *General* tab.


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
    
    Enter a name for the decryptor.
    
    </td>
    </tr>
    </table>
    
4.  Define the following parameters in the *Processing* tab.


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
    
    *Signatures* 
    
    </td>
    <td valign="top">
    
    -   *None Expected*: If selected, no inbound messages must contain any signature\(s\) at all.

    -   *Optional*: A signature is optional. If signature\(s\) is/are available, at least one of them must be verifiable.

    -   *Required*: If selected, inbound messages must contain at least one signature. One of the signatures must be verifiable.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signer User ID of Key\(s\) from Public Keyring*

    \(only if for *Signatures* the option *Optional* or *Required* has been selected\)
    
    </td>
    <td valign="top">
    
    Enter the public key user IDs \(or parts of them\) from all expected senders. The system picks up all public keys associated with User IDs containing this value from PGP public keyring and uses them for verifying the signatures \(see [Inbound: Message-Level Security with OpenPGP](../40-RemoteSystems/inbound-message-level-security-with-openpgp-d2acb9f.md)\).

    You can enter `${header.headername`\} or `${property.propertyname}` to read the signer user ID dynamically from a header or exchange property.

    > ### Note:  
    > Consider the security implications when deriving information from header attributes as it can be influenced by inbound adapters or exported/published by outbound adapters. It is more secure to use \(exchange\) properties for this purpose.
    > 
    > More information: [About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md)


    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the configuration.


**Related Information**  


[How OpenPGP Works](../40-RemoteSystems/how-openpgp-works-29bc188.md "You can use Open Pretty Good Privacy (Open PGP) to digitally sign and encrypt messages.")

[Deploying a PGP Public Keyring](deploying-a-pgp-public-keyring-7f04458.md "This artifact contains the public key that enables the tenant to encrypt or verify messages using the Pretty Good Privacy (PGP) standard.")

[Inbound: Message-Level Security with OpenPGP](../40-RemoteSystems/inbound-message-level-security-with-openpgp-d2acb9f.md "")

