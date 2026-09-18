<!-- loio0714e22be1fa433ea40d581dac09f4d6 -->

# RNIF Adapter

Use the RNIF \(RosettaNet Implementation Framework\) adapter to exchange RosettaNet business messages with trading partners.

The RNIF adapter enables SAP Cloud Integration to exchange RosettaNet business messages with trading partners over HTTPS, in compliance with the RNIF 2.0 specification. The adapter supports both sender \(inbound\) and receiver \(outbound\) channels. You can enter the message processing configuration statically in the integration flow channel or resolve it dynamically at runtime through the Partner Directory. For more information, see [Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md).

> ### Note:  
> The adapter works in Cloud Integration and Edge Integration Cell environments.



## Supported Features

The RNIF adapter implements the transport, packaging, and security model of the RosettaNet Implementation Framework 2.0. The following features are supported:

-   Single-action and two-action synchronous Partner Interface Process \(PIP\) exchanges
-   Digital signing and signature verification of request and response messages
-   Encryption and decryption of payloads or full payload containers
-   Static configuration through the integration flow channel or dynamic configuration through the Partner Directory

**Related Information**  


[Configure the RNIF Sender Adapter](configure-the-rnif-sender-adapter-8dbb4ac.md "Configure the RNIF sender adapter for SAP Cloud Integration to receive RosettaNet messages from a trading partner over HTTPS.")

[Configure the RNIF Receiver Adapter](configure-the-rnif-receiver-adapter-556d7e3.md "Configure the RNIF receiver adapter for SAP Cloud Integration to send RosettaNet messages to a trading partner over HTTPS.")

