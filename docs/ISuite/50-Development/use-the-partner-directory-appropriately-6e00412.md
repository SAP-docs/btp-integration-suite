<!-- loio6e00412aebd549f8b5771c9397c08c5d -->

# Use the Partner Directory Appropriately

When designing business-to-business scenarios, you can use the Partner Directory to store information on business partners that are connected to the tenant in the context of a larger business network.

The Partner Directory contains information on partners that are connected to a tenant in the context of a larger business partner network. The information stored in the Partner Directory can be used to parameterize integration flows.

> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Use the Partner Directory Appropriately](https://api.sap.com/package/IntegrationFlowDesignGuidelinesPartnerDirectoryGuidelines?section=Overview)
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

> ### Note:  
> For more information on the Partner Directory, see: [Parameterizing Integration Flows Using the Partner Directory](parameterizing-integration-flows-using-the-partner-directory-b7812a5.md).
> 
> For more information on the Partner Directory APIs, see: [Partner Directory](partner-directory-0fe80dc.md).

1.  Import the required Postman collections, see: [First Steps - Import the Postman Collections](first-steps-import-the-postman-collections-0f4cf38.md).

2.  Initially create the required Partner Directory entities, see: [First Steps - Create Entities in the Partner Directory](first-steps-create-entities-in-the-partner-directory-d32359a.md).


After you've performed these steps, you can execute the example integration flows covering the different rules.

> ### Note:  
> If you don't consider the proposed guidelines during integration design, there's the risk that your scenario is affected in the following way:
> 
> -   You need to develop a high number of specific integration flows in order to implement your scenario.
> 
> -   You need to implement more logic within your integration flows. This implies integration flow modifications if objects/configurations related to a specific partner are changed.
> 
> -   You expect a high maintenance effort if there are updates or bug fixes.

> ### Note:  
> It can be the case that you've applied the integration flow design guidelines described in this section to your best knowledge, but you still face issues during the operation of the scenario. For example, you have applied all design rules with regard to performance but still the performance isn't good enough at runtime. In such cases, you can check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).

To apply this design guideline, consider the following rules:

-   [Dynamically Address Receivers](dynamically-address-receivers-dde6b3a.md)

-   [Perform an XSLT Mapping](perform-an-xslt-mapping-c6bf239.md)

-   [Use an Alternative Partner Id to Retrieve Partner Information](use-an-alternative-partner-id-to-retrieve-partner-information-01a784c.md)

-   [Fetch the Partner Info from the Partner Directory](fetch-the-partner-info-from-the-partner-directory-a44a1f9.md)

-   [Use the AS2 Adapter with Dynamic Encryption and Signature Verification](use-the-as2-adapter-with-dynamic-encryption-and-signature-verification-2cd252c.md)


**Related Information**  


[Managing Partner Directory Entries](managing-partner-directory-entries-3d6eee7.md "Manage Partner Directory entries that can be used to parameterize integration flows.")

