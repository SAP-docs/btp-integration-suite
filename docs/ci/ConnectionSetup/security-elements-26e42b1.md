<!-- loio26e42b1d69304ce39b908fd11882e7ab -->

# Security Elements

To set up the secure communication between a tenant and a sender/receiver system, certain security elements have to be created and - in some cases - exchanged between the involved components \(the tenant on the one side and the sender/receiver system on the other side of the communication\).



For example, to set up SSL communication using certificate-based authentication between a tenant and a receiver system, X.509 certificates are required. Those private keys owned by the tenant are to be part of a Java keystore that is to be deployed on the tenant, whereas the private keys owned by the receiver are to be part of the receiver system keystore. To complete the security setup, each keystore also has to contain the public key of the connected partner. In our example, the Java keystore of the tenant has to contain the receiver public key, and the receiver keystore has to contain the tenant public key.

This section provides a summary for each security option of how the required security elements have to be distributed among the involved components \(tenant and sender/receiver systems\).

**Related Information**  


[Security Elements \(Transport-Level Security\)](security-elements-transport-level-security-1f76768.md "Each transport-level security option requires a specific set of security elements.")

[Security Elements \(Message-Level Security\)](security-elements-message-level-security-15ccdf9.md "The configuration of secure message exchange requires the exchange of public keys (or other security-related information) between the involved parties. Each message-level security option requires a specific set of keys to be exchanged.")

