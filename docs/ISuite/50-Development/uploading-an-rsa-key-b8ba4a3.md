<!-- loiob8ba4a3d62054775bb8264f6e31b8d71 -->

# Uploading an RSA Key

Upload an RSA key to the tenant keystore.



<a name="loiob8ba4a3d62054775bb8264f6e31b8d71__context_pfb_ssq_bwb"/>

## Context

You can add an RSA key to the keystore monitor instead of creating one.

Using this action, you cerate a new keystore entry based on an uploaded RSA key file.



<a name="loiob8ba4a3d62054775bb8264f6e31b8d71__steps_udb_ssq_bwb"/>

## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, above the table, choose *Add* \> *RSA Key*.

3.  Choose *Browse* and select the RSA key on your local disk.

    You can only upload PEM-encoded RSA keys in PKCS\#1 format.

    The alias is generated based on the file name.

4.  Select the signature algorithm.

    By default, *SHA-256/RSA* is set.

5.  Enter the required information for the following attributes.

    These attributes represent the coordinates of the organization associated with the certificate \(such like *Organization \(O\)*, *Organizational Unit \(OU\)*, *Country/Region \(C\)*, and so forth\).

    Note that for *Common Name \(CN\)* you need to specify an address \(for example, `myhost.com`\). Which address to specify, depends on the usage of the key pair. For example, if you use the key pair to sign a message, the address of the signing component is to be specified.

    For more information on certificates, see: [X.509 Certificates](../40-RemoteSystems/x-509-certificates-8d38a83.md).

6.  Check the settings vor the validity \(*Valid From* and *Valid Until* fields\) and, if desired, change them \(by default, the validity is set to 10 years\).

7.  Choose *Add* to create the key entry.


