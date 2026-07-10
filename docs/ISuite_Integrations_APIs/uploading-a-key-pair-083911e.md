<!-- loio083911ea02864f02a17bd24318b25cf9 -->

# Uploading a Key Pair

Upload a private/public key pair to the tenant keystore.



## Context

> ### Note:  
> You cannot import a key pair for a keystore entry with an alias starting with `sap_` or `hcicertificate` \(as these entries are owned by SAP\).



<a name="loio083911ea02864f02a17bd24318b25cf9__steps_w42_mbk_bdb"/>

## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, above the table, choose *Add* \> *Key Pair*.

3.  Enter the alias \(*Alias* field\).

    > ### Note:  
    > You cannot import a key pair with an alias starting with \(as this namespace is reserved for SAP-owned keystore entries\). You cannot import a key pair with an alias starting with `sap_`You cannot import a key pair with an alias starting with \(as this namespace is reserved for SAP-owned keystore entries\). You cannot import a key pair with an alias starting with
    > 
    > Make sure you don't enter an alias that is already used by an existing keystore entry.

4.  Choose *Browse* and select the key pair on your local disk.

    You can also upload files with the extension `.pfx` and `.p12`.

    > ### Caution:  
    > Note that a `.pfx` or `.p12` file can contain one or more keys. In case the file contains only one key, you can upload it as single key pair with this feature. If the file contains more than one key, it is recommended to upload it as keystore \(via *Add* \> *Keystore*\). The reason is: If you try to upload a `.pfx` or `.p12` file that contains more than one key via *Add* \> *Key Pair*, the system will only upload one key and ignore the others.

5.  Enter the password associated with the private key.

6.  Choose *Add*.

    > ### Note:  
    > If there is already an entry with this alias in the keystore, an error message is shown.
    > 
    > Currently, the size limit for uploading key pairs to the keystore is at 30720 bytes.
    > 
    > If the system cannot verify the trustworthiness of the key pair \(for example, if it is self-signed\), a warning message is displayed, which also contains the fingerprints.
    > 
    > A fingerprint is generated out of the public key applying a hash function to it. You can check the trustworthiness of the public key by comparing the fingerprint with a fingerprint for the public key provided by your communication partner via a trustworthy channel \(phone, signed e-mail\).


