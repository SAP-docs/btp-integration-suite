<!-- loio201fd43d4dab4bce9144ebfd9cdfbb20 -->

# Apply the Highest Security Standards

When using SAP Integration Suite , customer data is processed beyond the boundaries of the customer's network. There are various measures taken by SAP to make sure that such data is protected at a maximum level.

> ### Note:  
> For more information, see:
> 
> [Security](../60-Security/security-a58b240.md)

However, a significant part of the responsibility also lies with the integration developer. The integration flow ultimately specifies how a message is processed and which options are applied to protect the content of the messages on the way between the sender and the receiver. Therefore, the integration developer has to make sure that the integration flows are designed in a way that ensures that the highest security standards are applied.

> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Apply Highest Security Standards](https://api.sap.com/package/DesignGuidelinesApplySecurity?section=Overview) 
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

> ### Note:  
> If you don't consider the proposed guidelines during integration design, there's the risk that your scenario is affected in the following way:
> 
> -   Your scenario is exposed to a higher risk for attacks.
> 
> -   Third parties can get access to sensitive data.

> ### Note:  
> It can be the case that you've applied the integration flow design guidelines described in this section to your best knowledge, but you still face issues during the operation of the scenario. For example, you have applied all design rules with regard to performance but still the performance isn't good enough at runtime. In such cases, you can check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).

To apply this design guideline, consider the following rules:

-   [Remove Sensitive or Secret Content Before Logging or Forwarding](remove-sensitive-or-secret-content-before-logging-or-forwarding-4686862.md)

-   [Switch Off Resolving of External Entities](switch-off-resolving-of-external-entities-a990e2c.md)

-   [Encode Dynamic Parameters](encode-dynamic-parameters-d278350.md)

-   [Use CSRF Protection](use-csrf-protection-a0765d5.md)

-   [Use Secure Authentication Methods](use-secure-authentication-methods-3d46d45.md)

-   [Upload WSDLs as Integration Flow Resource](upload-wsdls-as-integration-flow-resource-9c22b39.md)

-   [Apply Message-Level Security](apply-message-level-security-9036c0c.md)

-   [Use Secure Protocols](use-secure-protocols-c9b8cae.md)

-   [Protect Data Integrity](protect-data-integrity-e0ef25c.md)


