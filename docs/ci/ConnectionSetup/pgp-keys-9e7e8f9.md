<!-- loio9e7e8f999b2d4ea88b1183eaa19e4ea9 -->

# PGP Keys

PGP public and secret keys \(the latter containing a private key\) can be uploaded to the tenant via separate keyrings. The PGP Public Keyring contains Transferable Public Keys as defined in section 11.1 of the Open PGP specification \([https://tools.ietf.org/html/rfc4880](https://tools.ietf.org/html/rfc4880)\) and the secret keyring contains Transferable Secret Keys as defined in section 11.2.

PGP keys are used in the PGP Encryptor and Decryptor step. You should only add PGP Public keys to thePGP public Keyring if you trust this key. Typically you check the fingerprint of the public key. The same security measures must be taken for the secret keys that you use in the secret keyring. The encryption and signing steps do also work with expired certificates.

For the PGP Secret Keyring, the same precautions as for the X.509 keystore must be taken because it contains private keys.

