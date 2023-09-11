<!-- copy2a19480024bc456887c64f3f850616f3 -->

# Requesting a Signed Certificate from a Certification Authority

To enable the tenant to communicate as client with the customer system, you have to import a client certificate to the tenant client keystore. This certificate has to be signed by a certification authority \(CA\).



## Prerequisites

You have created a certificate signing request \(CSR\). Using this CSR, you request a signed certificate from a certification authority \(CA\).

Each CA has its own processes for performing these steps. Check out the website of the CA for more information.



## Context

Note that usually only authorized people can directly order a signed certificate from a CA as costs are involved.



<a name="copy2a19480024bc456887c64f3f850616f3__postreq_kmt_4vf_gfb"/>

## Next Steps

Upload the signing response that you receive from the CA to the keystore.

**Related Information**  


[Updating a Key Pair with a Signing Response](../50-Development/updating-a-key-pair-with-a-signing-response-4242f01.md "Upload a signing response from a certification authority and use it to update the key pair in your keystore, keeping the alias of the keystore entry unchanged.")

