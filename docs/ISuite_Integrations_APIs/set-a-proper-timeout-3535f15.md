<!-- loio3535f157bfa84ea2a886ae538dcfe8b3 -->

# Set a Proper Timeout

When configuring an adapter, set a proper timeout value tailored to the needs of the connected external component.

In most cases, it isn't possible to predict how long a call to an external component will take. It might not even return at all. The timeout is a setting that defines when the call is interrupted to handle the situation.



<a name="loio3535f157bfa84ea2a886ae538dcfe8b3__section_zkm_ykw_ljb"/>

## Implementation

In SAP Integration Suite , various adapters allow you to configure a timeout for the call to the external component.

For example, the following adapters support this feature:

-   [Configure the OData V2 Receiver Adapter](configure-the-odata-v2-receiver-adapter-c5c2e38.md)

-   [Configure the SOAP \(SOAP 1.x\) Receiver Adapter](configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md)

-   [Configure the SuccessFactors OData V2 Receiver Adapter](configure-the-successfactors-odata-v2-receiver-adapter-d16dd12.md)

-   [HTTP Receiver Adapter](http-receiver-adapter-2da452e.md)


To illustrate this rule, you can consult the integration flow *Manage Resources - Size Integration Flow* \(in the *Integration Flow Design Guidelines - Run an Integration Flow Under Well-Defined Boundary Conditions* integration package\) that is described in [Manage Large Batch Sizes](manage-large-batch-sizes-825d2cf.md).

In the example integration flow, a timeout of 10 minutes is configured for the OData receiver adapter \(in the *Timeout* parameter in the *Processing* tab\).

