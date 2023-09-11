<!-- loioe53bb5cd1e1745afa7f785e0aff735a1 -->

# WS-Security Configuration for the Sender SOAP 1.x Adapter

You use a sender channel to configure how inbound messages are to be treated at the tenant’s side of the communication.

With regard to WS-Security in a sender channel, you specify the following:

-   How the tenant verifies the payload of an incoming message \(signed by the sender\)
-   How the tenant decrypts the payload of an incoming message \(encrypted by the sender\)

The following figure illustrates the setup of components:

![](../40-RemoteSystems/images/SOAP_1_x_WS_Security_Sender_Channel_6afaf0a.png)

The sender SOAP 1.x adapter allows the following combination of message-level security options:

-   Verifying a payload
-   Verifying and decrypting a payload

For a detailed description of the SOAP adapter WS-Security parameters, check out [Configure the SOAP \(SOAP 1.x\) Sender Adapter](configure-the-soap-soap-1-x-sender-adapter-a178913.md) \(under *WS-Security*\).

