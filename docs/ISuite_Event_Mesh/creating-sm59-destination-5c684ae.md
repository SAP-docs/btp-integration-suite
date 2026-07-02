<!-- loio5c684ae10453430ba360c4d37fab7c9f -->

# Creating SM59 Destination

As an administrator, you create an `SM59` destination to connect to the instance created for Event Mesh in SAP Integration Suite.



<a name="loio5c684ae10453430ba360c4d37fab7c9f__prereq_mwv_ptl_l2b"/>

## Prerequisites

-   You have the *Enterprise Event Enablement* administrator role.
-   You have a subaccount in SAP BTP, Cloud Foundry environment. For more information, refer to [Getting Started with a Customer Account: Workflow in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/56440ab2380041e092c29baf2893ef97.html).
-   You have created a service instance for Event Mesh in SAP Integration Suite. See [Configure a Message Client](https://help.sap.com/docs/integration-suite/sap-integration-suite/configure-message-client?version=CLOUD).



## Procedure

Import certificates

1.  To get certificates from SAP BTP, Cloud Foundry environment, proceed as follows:

    1.  Launch the token endpoint URL `https://<messaging client url>/oauth/token` that you receive from the service instance of Event Mesh in SAP Integration Suite in your browser.

    2.  Export all certificates from the certificates path.


2.  Logon to the SAP S/4HANA, on premise system that has the `SAP_GWFND` component.

3.  Execute transaction `STRUST`.

4.  Select the node *SSL client SSL Client \(Anonymous\)*.

5.  Press the button on the bottom of the screen with the tooltip *Import certificate* to import all certificates.


Clear cache

6.  To clear the cache, go to transaction `SMICM`.

7.  Choose *Administration* \> *ICM* \> *Exit Soft* \> *Local*.

8.  Execute transaction `SPRO`.

9.  Press the button *Open SAP Reference IMG*.

10. Navigate to *SAP Customizing Implementation Guide* \> *ABAP Platform* \> *Enterprise Event Enablement* \> *Administration* \> *Channel Connection Settings*.

11. Execute *Manage RFC Destination*.

12. Choose the button with the tooltip *create*.

13. Enter the `SM59` *Destination* name.

14. Enter the *Connection Type* with *G* \(HTTP connection to external server\).

15. Enter a description.

16. Save your entries.

17. Choose the tab *Technical Settings*.

    1.  In the *Target System Setting* section, in the *Host* field, enter the domain name of the `<app-url>` given in the URI.

        For example `wss://<app-url>/protocols/amqp10ws` of the service instance key in the `amqp10ws` protocol.

    2.  Enter the *Path Prefix*.

        For example `/protocols/amqp10ws`.

    3.  \(Optional\) In the *HTTP Proxy Options* section, enter the proxy details.


18. Choose the tab *Logon & Security*.

    1.  In the *Security Options* section, enable *SSL* as *Active*.

    2.  Select the imported SSL Certificate from the node list of the certificate list.


19. Save your entries.


**Related Information**  


[Configuring OAuth 2.0 Account Client](configuring-oauth-2-0-account-client-d445b27.md "You can access an external service provider's (SAP Integration Suite, SAP BTP, Cloud Foundry environment) OAuth 2.0 protected web service from an SAP S/4HANA, on-premise edition system. You need to provide credentials and an OAuth 2.0 client ID in the service provider.")

[Managing Channels and Parameters](managing-channels-and-parameters-c09c2bf.md "A channel represents a single connection to a service instance of Event Mesh in SAP Integration Suite.")

