<!-- loio066850745755490497da2b02783b74e7 -->

# Setting Up SAP Identity Authentication Service as Custom IdP for Basic Authentication

You can set up SAP's custom identity provider \(IdP\) to configure basic inbound authentication for sender systems to call an integration flow or for API clients to access the OData API.

When setting up trust relationships in SAP BTP cockpit, in most cases SAP ID service is used as default identity provider. However, you've the option to define a custom IdP as your default IdP.

This procedure only works for SAP Identity Authentication Service and isn't supported for non-SAP IdPs.

Perform the following steps:

1.  Configure SAP Custom IdP with OpenID Connect.

    More information: [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/161f8f0cfac64c4fa2d973bc5f08a894.html?q=Establish%20Trust%20and%20Federation%20Between%20UAA%20and%20Identity%20Authentication)

2.  Create a service instance for XS user authentication and authorization service \(XSUAA\) under the `apiaccess` plan.

    Furthermore, generate a service key for the service instance, and request an access token from the authorization service associated with the custom IdP \(using the content of the service key when sending the request\).

    More information: [Get API Access](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ebc9113a520e495ea5fb759b9a7929f2.html)

3.  Using the token retrieved from the previous step, perform another HTTP call to perform a patch request at:

    `https://api.authentication.<landscape domain>.hana.ondemand.com/sap/rest/authorization/v2/securitySettings`

    Send the following body along with the request:

    `{ "defaultIdp": "sap.custom" }`


You can now set up basic authentication for users registered by the custom IdP for the following use cases:

-   Sender component calls integration flow endpoint \(see: [Basic Authentication of IdP User for Integration Flow Processing](basic-authentication-of-idp-user-for-integration-flow-processing-5d46e56.md)\).

-   API client calls Cloud Integration OData API \(see: [Basic Authentication of an IdP User for API Clients](basic-authentication-of-an-idp-user-for-api-clients-57f104d.md)\).


