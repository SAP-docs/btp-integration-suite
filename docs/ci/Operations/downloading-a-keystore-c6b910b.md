<!-- loioc6b910b305944a59b11e0f3d55ea150a -->

# Downloading a Keystore

Download a keystore to your local disk.



## Context

When you've downloaded the keystore file, you can, for example, open it with an external tool.



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, choose *Download* \(above the table\).




<a name="loioc6b910b305944a59b11e0f3d55ea150a__postreq_em3_bq5_xz"/>

## Next Steps

The public part of the keystore is downloaded \(in a file with the name `PublicContentKeystore.jks`\).

The file is not password protected. You can open it with a third-party keystore editor \(for example, KeyStore Explorer\).

For private key entries, the certificate chains are resolved into single entries. The alias of the public key certificate is the same as the alias of the original key-pair entry. The intermediate certificate gets an additional suffix `_1` in the alias name. The root certificate gets an additional suffix `_2`.

