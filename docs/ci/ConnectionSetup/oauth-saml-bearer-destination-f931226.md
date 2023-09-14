<!-- loiof93122629816412c911f827a5eb62e5e -->

# OAuth SAML Bearer Destination

You can enable principal propagation between different accounts.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

If you have chosen this option, the identity of the user associated with the sender \(client\) application is forwarded from the sender account to the receiver account. It is a prerequisite for this scenario that the authentication method *OAuth 2.0* is used, in particular, the OAuth 2.0 SAML bearer assertion flow.

A Security Assertion Markup Language \(SAML\) 2.0 Bearer Assertion is used to authenticate the client as well as to request the OAuth 2.0 access token from an OAuth 2.0 authorization server \(hosted in the SAP cloud\).

To configure the scenario, an OAuth2SAMLBearerAssertion destination has to be specified on the sender account.

More information:

[SAML Assertion Authentication](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/saml-assertion-authentication?state=DRAFT&q=assertion%20authentication)

[Principal Propagation to OAuth-Protected Applications](https://help.sap.com/docs/btp/sap-btp-neo-environment/principal-propagation-to-oauth-protected-applications?version=Cloud)

> ### Note:  
> This option is supported for the following sender adapter types: SOAP \(SOAP 1.x\), SOAP \(SAP RM\), HTTPS, and OData.



## Create Connection of Sender and Receiver Account with Trusted Identity Providers

Make sure that the settings for SAML communication between SAP BTP and a trusted identity provider are specified. This communication has to be established for both the sender and receiver account.

In this way you establish a trust relationship between the sender and receiver account.

> ### Note:  
> Note the following remarks related to the identity providers of the sender and receiver account:
> 
> -   You can assign different identity providers to sender and receiver accounts.
> 
> -   Sender account: You must **not** assign the default SAP ID Service as the identity provider.
> 
> -   Receiver account: You can assign the default SAP ID Service for testing purposes. This identity provider is configured by default and has a landscape-dependent *Local Service Provider* name.

Perform the following steps for both the sender and receiver account:

To configure the settings, go to SAP BTP cockpit and choose *Security* \> *Trust*.

Proceed as described under ID Federation with the Corporate Identity Provider[Application Identity Provider](https://help.sap.com/docs/btp/sap-btp-neo-environment/application-identity-provider?version=Cloud#loiob6cfc4bb4bff4ace90afc71b0962fcb5).



## Configure OAuth in Receiver Account

Configure the OAuth settings for the receiver account. In this way, you register the client application as the OAuth client.

Go to SAP BTP cockpit and choose *Security* \> *OAuth* \(*Clients* tab\).

Proceed as described under Configuring OAuth 2.0[OAuth 2.0 Configuration](https://help.sap.com/docs/btp/sap-btp-neo-environment/oauth-2-0-configuration?version=Cloud).

Note the following specific settings:

-   As *Subscription*, select the VM name of the runtime node \(that ends with the node type, for example, `….iflmap`\).

    You can only register applications for node type `iflmap` or `hcioem`.

-   Enter a client ID.

    You can either get a client ID from the client or you can choose one \(you then have to forward this ID to the client\).

-   As *Authorization Grant*, choose *Client Credentials*.

-   Enter a secret \(as assigned to the client application\).

-   Specify a *Token Lifetime* to increase the security level.




## Configure Trust to Sender Local Service Provider in the Receiver Account

In the receiver account, configure a trust relationship to the sender’s local service provider.

Note that here the local service provider of the sender account takes the role of an additional trusted entity provider for the receiver account.

To configure the settings, go to the SAP BTP cockpit and choose *Security* \> *Trust* \(*Trusted Entity Provider* tab\).

Proceed as described under

Proceed as described under [Application Identity Provider](https://help.sap.com/docs/btp/sap-btp-neo-environment/application-identity-provider?version=Cloud#loiob6cfc4bb4bff4ace90afc71b0962fcb5).

\(subsection **Configure Trust to the SAML Identity Provider**\).

As *Name*, enter the *Local Service Provider* name from the sender account.

Enter the *Signing Certificate* as specified for the sender’s local service provider.



## Specify User Group in Receiver Account and Enable User Group to Process Message on Runtime Node

In the receiver account, perform the following tasks:

1.  Create a user group.

    To configure the settings, go to theSAP BTP cockpit and choose *Security* \> *Authorizations*. On the *Groups* tab, create a new group.

2.  Create a mapping of the user group to the local sender service provider.

    You have the following options:

    -   Specify a default group, which means that all users logged in via the sender's local service provider are assigned to this user group.

        To configure the settings for the default group, go to the SAP BTP cockpit and choose *Security* \> *Trust*. On the *Trusted Identity Provider* tab, go to the identity provider specified previously. On the *Groups* tab, choose *Add Default Group* and enter the name of the newly created user group.

    -   Define mapping rules based on the user attributes \(such as e-mail address\).


3.  Assign the user group to the `ESBMessaging.send` role.

    You perform this step to enable all users that are assigned to the user group created to execute integration flows on the runtime node application.

    To configure the settings, go to the SAP BTP cockpit and choose *Security* \> *Authorizations*. On the *Groups* tab, select the group defined previously and choose *Assign*. Select the role `ESBMessaging.send`.

    More information: [Defining Authorizations for Integration Team Members](../Operations/defining-authorizations-for-integration-team-members-3ec7679.md)




## Create OAuth2SAMLBearerAssertion Destination in the Sender Account

To configure the settings, go to the SAP BTP cockpit and choose *Destinations*.

-   As *Type* select *HTTP*.

-   As *Proxy Type* select *Internet*.

-   As *Authentication* select *OAuth2SAMLBearerAssertion*.

-   As *Audience* enter the *Local Provider Name* of the receiver account.

-   As *Client Key* specify the key that identifies the consumer to the authorization server. This key must contain the ID of the client created above.

-   As *Token Service URL* enter the *OAuth token URL* for the receiver account. You can find the value to be entered in the receiver account, SAP BTP cockpit, under *Security* \> *OAuth*. On the *Branding* tab in section *OAuth URLs*, the URL is displayed under *Token Endpoint*.

-   As *Token Service User* specify the user for basic authentication for the OAuth server \(if required\). This entry must contain the ID of the client created above.

-   As *Token Service Password* specify the *Password for Token Service User* \(if required\). This entry must contain the secret of the confidential client.

-   As *Additional Property* add the property `authnContextClassRef` with the following value: `urn:oasis:names:tc:SAML:2.0:ac:classes:X509`.


**Related Information**  


[Setting Up Principal Propagation \(Example Scenario\)](setting-up-principal-propagation-example-scenario-34eff84.md "Use principal propagation to forward the principal (identity of a user) across several connections in a complex system landscape.")

