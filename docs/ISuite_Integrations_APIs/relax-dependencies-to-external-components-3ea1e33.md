<!-- loio3ea1e33606c24c27ad097d60b57b6e4e -->

# Relax Dependencies to External Components

Calls to external components must be closely controlled. When you specify outbound processing of a message, anticipate a temporary unavailability of the called external component.

> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Relax Dependencies to External Components](https://api.sap.com/package/DesignGuidelinesRelaxDependenciestoExternalComponents?section=Overview)
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

> ### Note:  
> If you don't consider the proposed guidelines during integration design, there's the risk that your scenario is affected in the following way:
> 
> -   In case of temporary issues, errors are propagated back to the sender system \(sender system needs to enable restart of scenario\).
> 
> -   Too many failures occur due to unavailability or overload of target system.

> ### Note:  
> It can be the case that you've applied the integration flow design guidelines described in this section to your best knowledge, but you still face issues during the operation of the scenario. For example, you have applied all design rules with regard to performance but still the performance isn't good enough at runtime. In such cases, you can check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).

To apply this design guideline, consider the following rules:

-   [Apply the Retry Pattern](apply-the-retry-pattern-97789c9.md)

-   [Set a Proper Timeout](set-a-proper-timeout-3535f15.md)

-   [Validate Incoming Messages](validate-incoming-messages-f421c07.md)

-   [Perform OData Batch Requests](perform-odata-batch-requests-b0372d4.md)

-   [Reduce Size of OData Content Enricher Response](reduce-size-of-odata-content-enricher-response-8a76692.md)


