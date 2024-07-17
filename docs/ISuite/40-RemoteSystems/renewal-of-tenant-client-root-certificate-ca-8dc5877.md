<!-- loio8dc5877895c84b85af60fea70d15d640 -->

# Renewal of Tenant Client Root Certificate \(CA\)

In this use case, the tenant client certificate is exchanged by a new one signed from a different certification authority \(CA\).

The following figure illustrates the communication path that is relevant for this use case.

![](images/SAP_HCI_Security_Renewal_-_HTTPS_Certificate_Outbound_HCI_Tenant_36ffd91.png)



## Receiver Accepts Different Certificates at the same Time

Certificate renewal has to be performed in the following sequence:

1.  Tenant administrator: Creates new certificate with a new key pair and gets the certificate signed by another CA than the old one.
2.  Tenant administrator: Provides receiver administrator with the new certificate and root certificate \(the latter one because the CA had changed\).
3.  Receiver administrator: Configures receiver \(server\) that way that the old and the new client certificate are accepted by the server.

    Because the receiver administrator also has received a new **root certificate**, this root certificate also has to be imported into the server keystore.

4.  Receiver administrator: Informs the tenant administrator that the receiver system \(server\) now accepts both the old and the new client certificate.
5.  Tenant administrator: Exchanges the old key pair/certificate with the new key pair/certificate - keeping the old alias in the tenant client keystore.

    This is done by importing the new signed certificate into the tenant client keystore.

6.  Tenant administrator: Informs the integration developer that the integration flow can be restarted.
7.  Integration developer: Restarts the integration flow which sends data via HTTPS to the receiver system.

    This is necessary because the SSL socket caches the keystore for 24 hours.

    If your tenant cluster contains multiple runtime nodes, make sure that you restart your integration flow on all nodes. If you start the integration flow on only one runtime node, message processing might fail on the other nodes.

8.  Tenant administrator: Informs the receiver administrator that a new client certificate \(signed by another CA than the old one\) is now used.
9.  Receiver administrator: Removes the old client certificate and also the old root certificate \(assumed that it is not longer used in any other communication\).

Let us assume, the customer landscape is composed as described under *Connecting a Customer System to Cloud Integration*, section *Technical Landscape for On Premise-On Demand Integration*. In that case, SAP Web Dispatcher is used to receive incoming calls from the cloud. SAP Web Dispatcher \(as reverse proxy\) is the entry point for HTTPS requests into the customer system landscape. The configuration of the receiver \(server\) as indicated in step 2 in the list above comprises the following tasks for that example case:

-   Make sure that the reverse proxy trusts the new CA. A restart is required to finalize the related configuration steps.
-   Map the new certificate in AS ABAP back-end for authentication purpose
-   Edit the new CA in Web Dispatcher farm.

    This step is performed by SAP IT.

-   Upload the new CA in workcenter under *Edit Certificate Trust List*.
-   Update the communication arrangements credentials such way that the new certificate is mapped to the inbound technical user.



## Receiver does not Accept Different Certificates at the same Time

Certificate renewal has to be performed in the following sequence:

1.  Tenant administrator: Creates new certificate with a new key pair and gets the certificate signed by another CA than the old one.
2.  Tenant administrator and Receiver administrator: Aggree on a downtime window.
3.  At start of the downtim window, the tenant administrator informs the integration developer that the integration flow which uses the client certificate for outbound HTTPS communication has to be stopped.
4.  Integration developer: Stops the integration flow.
5.  Integration developer: Informs the tenant administrator that the integration flow has been stopped.
6.  Tenant administrator: Exchanges key pair/certificate in the keystore keeping the old alias.

    This is done by importing the new signed certificate into the tenant client keystore.

7.  Tenant administrator: Provides receiver administrator with the new certificate and the root \(CA\) certificate.

    The tenant administrator informs the receiver administrator that the HTTPS client has been stopped.

8.  Receiver administrator: Exchanges the certificate and imports the new root \(CA\) certificate into the truststore.
9.  Receiver administrator: Informs the tenant administrator that the certificate has been exchanged.
10. Tenant administrator: Informs the integration developer that the integration flow can be restarted.
11. Integration developer: Restarts the integration flow which sends data via HTTPS to the receiver system.

    This is necessary because the SSL socket caches the keystore for 24 hours.

    If your tenant cluster contains multiple runtime nodes, make sure that you restart your integration flow on all nodes. If you start the integration flow on only one runtime node, message processing might fail on the other nodes.


> ### Note:  
> It is not expected that this case occurs very often.

**Related Information**  


[Technical Landscape for On Premise-On Demand Integration](technical-landscape-for-on-premise-on-demand-integration-f69e177.md "As one example for certificate-based connectivity, customer intends to connect a customer-based SAP on-premise system (based on SAP Application Server ABAP with Cloud Integration).")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

