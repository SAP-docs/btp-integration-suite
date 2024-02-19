<!-- loio8a8aa384a19c49afb8636a014bf939eb -->

# Guidelines and Best Practices for Content Transport

Cloud Integration offers different options to transport integration content. There are certain criteria that help you to decide which option to choose for your integration project.

To find out more about the different content transport options, see [Content Transport](content-transport-e3c79d6.md).

The mentioned options allow you to transport always complete integration packages and their content. Integration artifacts transported with an integration package are:

-   Integration flows

-   Value mappings

-   OData APIs

-   REST APIs

-   SOAP APIs

-   API


> ### Note:  
> However, additional artifacts are required to use integration content on a tenant that cannot be transported along with integration content.
> 
> For example, to run an integration flow that uses authentication to a receiver system based on OAuth2 client credentials grant, you also need to deploy an *OAuth2 Client Credentials* artifact on the tenant and refer to the artifact alias in the integration flow.
> 
> After you have transported an integration flow using this authentication type, you need to separately deploy a new *OAuth2 Client Credentials* artifact on the target tenant \(ideally with the same alias as used on the source tenant\).

Other examples for non-transportable content are keystore entries \(key pairs and certificates\).

For more information on objects that cannot be transported and how to deal with them in a transport scenario, see [Handling Integration Artifacts When Reusing an Integration Flow on Multiple Tenants](handling-integration-artifacts-when-reusing-an-integration-flow-on-multiple-tenants-2a1d598.md).

**Related Information**  


[Decision Help for Choosing the Right Content Transport Option](decision-help-for-choosing-the-right-content-transport-option-19e0e73.md "There are different criteria that help you to decide on a transport option.")

[Decoupling Development from Transport Using Externalized Parameters](decoupling-development-from-transport-using-externalized-parameters-9064b09.md "Consider decoupling development from transport when designing integration content.")

[Guidelines on Role Assignments](guidelines-on-role-assignments-fc409e8.md "")

[Content Transport - Sequence of Steps \(Example\)](content-transport-sequence-of-steps-example-1ca3d1e.md "")

