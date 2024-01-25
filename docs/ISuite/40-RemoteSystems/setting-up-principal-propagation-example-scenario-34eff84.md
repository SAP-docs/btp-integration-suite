<!-- loio34eff846cfb84011b09ad1fb1894ce14 -->

# Setting Up Principal Propagation \(Example Scenario\)

Use principal propagation to forward the principal \(identity of a user\) across several connections in a complex system landscape.

In the following example setup, the principal of the inbound user is forwarded to SAP Cloud Connector, and from there to the back-end receiver system.

![](images/Principal_Propagation_Scenario_5024193.png)

We assume the following:

-   In this example, the authentication option OAuth is used \(using OAuth SAML Bearer Destination\) for inbound communication \(from the sender to SAP BTP\).

-   An on-premise SAP system based on Application Server ABAP is used as the receiver system,.

    The on-premise receiver system is connected to SAP BTP through SAP Cloud Connector.

    > ### Caution:  
    > Using SAP Cloud Connector is a mandatory when configuring principal propagation.

-   The receiver system is associated with an identity provider, which mediates a trust relationship between the sender, SAP BTP, and the receiver.

-   To establish an outbound connection \(from SAP BTP to SAP Cloud Connector\), an adapter that supports principal propagation is used \(for example, the HTTP receiver adapter\).

-   All systems that communicate with each other have to provide the same user. This can be achieved by using an identity provider, as indicated in the figure above as an example setup.


To configure principal propagation for this setup, perform the following steps.

1.  Enable OAuth \(with SAML Bearer Destination\) for the inbound connection from the sender to SAP BTP.

    More information: [OAuth SAML Bearer Destination](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/f93122629816412c911f827a5eb62e5e.html "You can enable principal propagation between different accounts.") :arrow_upper_right:

    > ### Note:  
    > Note that currently only the following \(sender\) adapter types can be used on the inbound side: HTTPS, SOAP \(SOAP 1.x\), SOAP \(SAP RM\), and IDoc.

2.  In the receiver channel of the integration flow, as *Authorization* option, enable *Principal Propagation*.

    More information: [HTTP Receiver Adapter](../50-Development/http-receiver-adapter-2da452e.md)

    > ### Remember:  
    > When you want to use Principal Propagation as the authentication method to connect with an on-premise system, don't pass any authorization headers. Follow the approach recommended by SAP BTP Connectivity. See: [Authentication to the On-Premise System](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/67b0b94f09f2446598787eea0855e56b.html).

3.  Prepare SAP Cloud Connector to support principal propagation with X.509 certificates \(for the communication with the receiver system\).

    You need a certificate chain with at least one intermediate certification authority. The intermediate certification authority signs a short-lived certificate, which is used for principal propagation. Use the user name \(associated with the identity to be propagated\) as the subject common name \(subject CN\) of this certificate.

    SAP Cloud Connector forwards the identity \(to be propagated\) in a short-living X.509 certificate in HTTP header SSL\_CLIENT\_CERT.

    More information: [Configuring a CA Certificate for Principal Propagation](https://help.hana.ondemand.com/help/frameset.htm?d0c4d5675d4f4bc78a5b7a7b8687c841.html)

4.  In SAP Cloud Connector, configure the trust relationship with the SAP BTP application.

    More information: [Cloud Connector](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/cloud-connector)

5.  Configure the receiver system. You need to do the following:

    -   Configure the receiver system to trust the certificate of the SAP Cloud Connector.

    -   Configure the Internet Communication Manager \(ICM\) to trust the system certificate for principal propagation.

    -   Map the short-living certificate \(from SAP Cloud Connector\) to the user \(whose identity is being propagated\).


    More information: [Configuring Principal Propagation to an ABAP System for HTTPS](https://userapps.support.sap.com/sap/support/knowledge/en/2462533)


