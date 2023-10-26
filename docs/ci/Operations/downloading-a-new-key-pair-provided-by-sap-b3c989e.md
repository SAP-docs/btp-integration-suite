<!-- loiob3c989e1f1154b3e934849e7d2a800d6 -->

# Downloading a New Key Pair Provided by SAP

Download a single Key Pair to your local disk.



<a name="loiob3c989e1f1154b3e934849e7d2a800d6__context_drb_kxh_cgb"/>

## Context

You can download a key, a single certificate, a complete certificate chain or a root certificate from the *New SAP Keys* tab.

> ### Note:  
> You can download only public keystore content \(no private keys\).



<a name="loiob3c989e1f1154b3e934849e7d2a800d6__steps_erb_kxh_cgb"/>

## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *New SAP Keys* tab, select a keystore entry.

3.  Choose one of the following options for the selected keystore entry.

    Dowload only supports Key Pair entries in the *New SAP Keys* tab.


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
    



<a name="loiob3c989e1f1154b3e934849e7d2a800d6__postreq_a2v_rq5_xz"/>

## Next Steps

You can import the downloaded files into other keystores and open them using third-party tools \(for example, KeyStore Explorer\).

