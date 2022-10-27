<!-- loio2d808e76e639447cb15cc4b716db7807 -->

# Setting Up Outbound HTTP Connections \(with Basic Authentication\)



## Context

This option was referred to as *basic authentication* in former releases. It is based on user credentials.



## Procedure

1.  Create and deploy a tenant keystore that contains the receiver server root certificate.

    This certificate is required to identify \(authenticate\) the receiver system as trusted server.

2.  Create and deploy the credentials on the tenant.

    These are user name and password that are used to authenticate the tenant calling the receiver system.

    1.  Use the same URL like for the integration flow design tool and choose the *Monitor* \> *Integrations* \> ** section.

    2.  Click the *Security Material* tile under *Manage Security*.

    3.  To create a new *User Credentials* artifact or edit an existing one for the tenant, choose *Add*.

    4.  On the *Add User Credentials* page, enter the attributes \(*Credential Name*, *User* and *Password*\) and choose *OK*.


3.  Configure the security-specific settings in the related integration flow.

    1.  Open the SAP Integration Suite design section for integration flows.

    2.  To create and design integration flows, go to the *Design* \> *Integrations* \> ** section.

    3.  Open the related receiver adapter \(that is used to specify the connection of the tenant with the receiver system\) and as Authentication choose *Basic*; then enter the credential name.

        This is the name of the *User Credentials* artifact that you have deployed on the tenant in a previous step.


4.  Configure the receiver keystore.

    The keystore needs to contain a certificate that is signed by a certification authority \(CA\) which is also contained in the tenant keystore.

    More information:

    [Creating X.509 Keys](creating-x-509-keys-ec605c7.md)


**Related Information**  


[Basic Authentication](basic-authentication-a5d77b1.md "Basic authentication allows a the tenant to authenticate itself against the receiver through credentials (user name and password).")

[Deploying a User Credentials Artifact](../50-Development/deploying-a-user-credentials-artifact-6912d63.md "To set up a connection using basic authentication or username token authentication, you have to specify the required attributes (for example, user name and password).")

