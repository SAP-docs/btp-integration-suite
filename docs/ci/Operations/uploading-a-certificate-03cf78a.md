<!-- loio03cf78a217574e7abd75bfbba990c085 -->

# Uploading a Certificate

Upload a single certificate to the tenant keystore.



## Context



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, above the table, choose *Add*, then *Certificate*.

3.  Enter the alias \(*Alias* field\).

    > ### Note:  
    > You cannot import a certificate with an alias starting with `sap_` \(as this namespace is reserved for SAP-owned keystore entries\).
    > 
    > Make sure you don't enter an alias that is already used by an existing keystore entry.

4.  Choose *Browse* and select the certificate on your local disk.

5.  Choose *Add*.

    > ### Note:  
    > If there is already an entry with this alias in the keystore, an error message is shown.
    > 
    > Currently, the size limit for uploading certificates to the keystore is at 10240 bytes.
    > 
    > If the system cannot verify the trustworthiness of the certificate \(for example, it cannot verify its signature\), a warning message is displayed, which also contains the fingerprints.
    > 
    > A fingerprint is generated out of the public key applying a hash function to it. You can check the trustworthiness of the public key by comparing the fingerprint with a fingerprint for the public key provided by your communication partner via a trustworthy channel \(phone, signed e-mail\).


