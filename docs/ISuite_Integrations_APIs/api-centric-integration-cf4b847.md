<!-- loiocf4b847a25de47cdb8e0d98f3985f1b7 -->

# API-Centric Integration

SAP Integration Suite provides a unified platform to design, manage, and monitor APIs and integrations, enabling organizations to expose data and services securely across hybrid and cloud environments. API-centric Integration enables you to design API artifacts that combine security, traffic management, and integration logic within a single model.

This unified approach allows you to apply governance, control traffic, and embed integration processing within the same artifact, regardless of the deployment landscape.



## When to Use API-Centric Integration

API-centric Integration allows you to encapsulate integration logic directly within an API artifact, together with security and traffic management policies.

Use API-centric Integration with integration steps when your API must perform processing beyond simple exposure.

Typical scenarios include:

-   Securing access to backend services through authentication and authorization policies
-   Managing API traffic and protecting backend services by applying IP filtering, quota, and surge protection policies
-   Aggregating data from multiple backend systems
-   Transforming or mapping payload formats between consumers and providers
-   Orchestrating calls to multiple services in sequence or conditionally
-   Validating and enriching requests before forwarding them

In these scenarios, supported integration steps are added during API modeling to define the execution flow. The API artifact coordinates backend interactions and applies security and traffic management policies as part of a single design. For a detailed list and description of supported integration steps, see [Working with Policies and Mediation Steps](working-with-policies-and-mediation-steps-c744df5.md).

Here, the API acts as both a controlled gateway and an integration component.



## When to Use Simple Governed APIs

If a backend service already performs the necessary business processing, you can simply create a proxy of the backend API in the form of an API artifact for governed access. The API artifact then acts as a managed entry point that focuses solely on:

If a backend service already performs the necessary business processing, the API can focus solely on:

-   Security management
-   Traffic management
-   Monitoring and analytics
-   Lifecycle governance

In this case, the API artifact securely exposes the backend capability while applying enterprise governance controls. This approach is ideal when the backend service is already well-designed, stable, and directly consumable by client applications — the proxy simply adds a governance and security layer on top.

