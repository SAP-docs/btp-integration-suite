<!-- loioca8a663d0f944251ae250f479e1c4947 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Downloading Single Keystore Entries

Download a single keystore entry to your local disk.



## Context

You can download a key, a single certificate, a complete certificate chain, a root certificate, or a signing request \(depending on the keystore entry type\).

> ### Note:  
> You can download only public keystore content \(no private keys\).



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, select a keystore entry.

3.  Choose the <span class="SAP-icons-V5"></span> \(Actions\) icon, then select one of the options listed in table below. Alternatively, you can click the keystore entry alias to open the details, and then choose the option under *Download*.

    The options available depend on the type of keystore entry you have selected.


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

    -   *Download Public OpenSSH Key*

        Downloads the public key in OpenSSH format.

        You can store the downloaded `<alias>.pub` file on the connected SFTP server to enable public key authentication on the server.

        > ### Note:  
        > To configure public key authentication on certain SFTP servers, public keys need to be available in OpenSSH format.
        > 
        > In such cases, use this download option.

        > ### Tip:  
        > Want to know how to get an SSH2 public key for the id\_rsa/id\_dsa key-pair of the tenant keystore?
        > 
        > You can use ssh-keygen for this purpose \(to be installed on Windows via Cygwin, for example\).
        > 
        > In ssh-keygen, perform the following command:
        > 
        > `$ ssh-keygen -e -f id_rsa.pub -m RFC4716 > id_rsa.pub_ssh2`
        > 
        > Example result file:
        > 
        > ```
        > ---- BEGIN SSH2 PUBLIC KEY ----
        > Comment: "1024-bit RSA, converted by d023101@WDFN33785618A from OpenSS"
        > AAAAB3NzaC1yc2EAAAADAQABAAAAgQCRB+UOPmnPF9W4cqn6h1z3V5izPFAOTCXSF4cfnw
        > ZivjhV8ZAcKq6QwV/SyOXkXWp/wObjKgTXtiHngdJ0kyOQ+66Eleq/yhO4NDJ0QM3Vzv15
        > IhL+eLYBtynk1ddF5l6kDLgSz1evA9F988wWKiz/vpI8DVjbY8HJjlQbE8wOSQ==
        > ---- END SSH2 PUBLIC KEY ----
        > 
        > ```

    -   *Download Root Certificate*

        A file with the name `<alias>_rootCA.cer` is downloaded.

        > ### Note:  
        > If the key pair is self-signed, this action performs the same function as *Download Certificate*.

    -   *Download Signing Request*

        A file with the name `<alias>.csr` is downloaded.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Certificate* entry
    
    </td>
    <td valign="top">
    
    *Download*

    A file with the name `<alias>.cer` is downloaded.

    It contains the base64-encoded certificate.
    
    </td>
    </tr>
    </table>
    
    For keystore entries owned by SAP, a restricted set of options is available. For an SAP key you can, for example, not download any signing request.




<a name="loioca8a663d0f944251ae250f479e1c4947__postreq_a2v_rq5_xz"/>

## Next Steps

You can import the downloaded files into other keystores and open them using third-party tools \(for example, KeyStore Explorer\).

