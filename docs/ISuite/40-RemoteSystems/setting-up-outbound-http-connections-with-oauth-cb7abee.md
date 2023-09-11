<!-- loiocb7abee348c84de984565fbcac152464 -->

# Setting Up Outbound HTTP Connections \(with OAuth\)

Using this option, authentication of Cloud Integration calling a receiver is performed using OAuth.



## Context

You can configure different OAuth grant types.

For detailed information on the supported grant types and the involved components, check out [OAuth 2.0](oauth-2-0-3823134.md#loio382313443b8d4453b0fd536b82b9e15d).

The set of supported OAuth grant types depends on the receiver adapter type. Therefore, a step-by-step description of the required configuration steps can only be provided for a particular use case with a dedicated receiver adapter type involved.

Nevertheless, the general sequence of steps to configure this authentication option is:



## Procedure

1.  Get the details for OAuth connection from the receiver system to be connected. This includes, for example, the address of the token service that issues the OAuth access token on behalf of the receiver.

2.  Depending on the receiver adapter type and the desired OAuth grant type to implement, create one of the following artifacts. To do that, go to the *Monitor* \> *Integrations* \> ** section and select the *Security Material* tile under *Manage Security*.

    -   *OAuth2 Client Credentials* \(see [Deploying an OAuth2 Client Credentials Artifact](../50-Development/deploying-an-oauth2-client-credentials-artifact-801b106.md)\)

    -   *OAuth2 SAML Bearer Assertion* \(see [Deploying an OAuth2 SAML Bearer Assertion](../50-Development/deploying-an-oauth2-saml-bearer-assertion-3ee6582.md)\)

    -   *OAuth2 Authorization Code* \(see [Deploying an OAuth2 Authorization Code](../50-Development/deploying-an-oauth2-authorization-code-081bfd7.md)\)


3.  In the receiver adapter of the related integration flow, choose the corresponding *Authentication* option and specify the *Credential Name* \(to pint to the artifact from step 2\).




## Example

Check out the following SAP Community blogs to find detailed instructions how to set up scenarios with a given receiver adapter and OAuth grant type:

-   [SAP Cloud Integration – OAuth2 Client Credentials Support in OData V2 Adapter](https://blogs.sap.com/2018/07/31/sap-cloud-platform-integration-oauth2-client-credentials-support-in-odata-v2-adapter/)

-   [SAP Cloud Integration – OAuth2 SAML Bearer/X.509 Certificate Authentication Support in SuccessFactors Connector](https://blogs.sap.com/2021/03/26/sap-cloud-integration-oauth2-saml-bearer-x.509-certificate-authentication-support-in-successfactors-connector/)

-   [Cloud Integration – Call Microsoft Graph API with OAuth 2.0 Authorization Code](https://blogs.sap.com/2021/01/11/cloud-integration-call-microsoft-graph-api-with-oauth-2.0-authorization-code/)


