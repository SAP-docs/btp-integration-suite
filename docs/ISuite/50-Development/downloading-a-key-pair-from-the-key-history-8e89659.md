<!-- loio8e896591313e49ee9489fc58943251d9 -->

# Downloading a Key Pair from the Key History

Download a key pair from the *SAP Key History* tab.



## Context

You can download a key, a complete certificate, a certificate chain, or a root certificate from the *SAP Key History* tab.

> ### Note:  
> You can download only public keystore content \(no private keys\).



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *SAP Key History* tab, select a keystore entry.

3.  Choose one of the following options for the selected keystore entry.


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
    
    *Key Pair* entry
    
    </td>
    <td valign="top">
    
    You can download the public key \(X.509 format\).

    -   *Download Certificate*

        A file with the name `<alias>.cer` is downloaded.

    -   *Download Certificate Chain*

        A file with the name `<alias>.p7b` is downloaded.

        The file contains the whole certificate chain.

    -   *Download Root Certificate*

        A file with the name `<alias>_rootCA.cer` is downloaded.



    
    </td>
    </tr>
    </table>
    



<a name="loio8e896591313e49ee9489fc58943251d9__postreq_a2v_rq5_xz"/>

## Next Steps

You can import the downloaded files into other keystores and open them using third-party tools \(for example, KeyStore Explorer\).

**Related Information**  


[Restoring a Key Pair from the Key History](restoring-a-key-pair-from-the-key-history-43965e7.md "Restore a key pair from the SAP Key History.")

