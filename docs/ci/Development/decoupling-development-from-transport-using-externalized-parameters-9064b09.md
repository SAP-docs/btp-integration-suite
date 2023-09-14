<!-- loio9064b0960b5146fd8c7fef7557584df2 -->

# Decoupling Development from Transport Using Externalized Parameters

Consider decoupling development from transport when designing integration content.

When designing integration content, there are certain configurations that depend on the landscape where the content is deployed.

Let us assume that you design an integration flow that calls an external system \(with OAuth authentication\). Let us furthermore assume that you design the integration flow first on a development tenant and, in a subsequent step, transport it to a production tenant.

In such a case, you can assume that the URL used to address the external system and the OAuth credentials differ in the development and the production environment.

If you specify the URL of the external system for the development environment in the related receiver adapter, the integration scenario doesn't work anymore after you've transported it to the production tenant.

To overcome this issue, you or another integration developer need to edit the integration flow on the production tenant after content transport and deploy it again. Such an activity leads to inconsistencies in the transport mechanism. Furthermore, this activity also decreases productivity, as additional steps are needed before deployment.

To avoid this behavior, the best practice is to use externalized parameters. If you've designed your integration flows using externalized parameters, you benefit from the following advantages:

-   After you've transported the integration flow and before deploying it on the target tenant, you only need to configure the externalized parameters. You don't have to do any changes in the integration flow model at all.

-   Configuring the externalized parameters after transport is usually a one-time activity. After subsequent transports, you don't need to configure these parameters again if the values remain the same \(as the initially configured values aren't overwritten\).


**Related Information**  


[Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md "")

[Externalize Volatile Configurations](externalize-volatile-configurations-300277d.md "Externalize volatile configurations in an integration flow.")

