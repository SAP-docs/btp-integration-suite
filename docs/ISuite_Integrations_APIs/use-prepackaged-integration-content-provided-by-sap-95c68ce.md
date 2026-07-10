<!-- loio95c68ce417e2476d994f082b9301a98d -->

# Use Prepackaged Integration Content Provided by SAP

SAP delivers prepackaged integration content out of the box that enables integration developers to get started quickly. These integration packages are created for some of the commonly used business processes.

SAP Integration Suite allows you to extend the capabilities of prepackaged integration content provided by SAP. This approach allows you to design custom integration logic without changing the content provided by SAP. To adapt the content to custom business requirements, you as the integration developer can edit and modify the related integration flows contained in the standard integration package. However, further updates to the standard integration content in the SAP Business Accelerator Hub can't be applied to the modified content in your design workspace. Copying the updated standard package from the SAP Business Accelerator Hub to the *Design* workspace of the tenant overwrites all your changes made to that package.

> ### Note:  
> If you don't consider the proposed guidelines during integration design, there's the risk that your scenario is affected in the following way:
> 
> -   You run into problems that others already have solved.

> ### Note:  
> It can be the case that you've applied the integration flow design guidelines described in this section to your best knowledge, but you still face issues during the operation of the scenario. For example, you have applied all design rules with regard to performance but still the performance isn't good enough at runtime. In such cases, you can check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).

To apply this design guideline, consider the following rules:

-   [Keep Modifications Separate from Prepackaged Integration Content](keep-modifications-separate-from-prepackaged-integration-content-1f4c046.md)

-   [Subscribe Only a Single Tenant to SAP Business Accelerator Hub](subscribe-only-a-single-tenant-to-sap-business-accelerator-hub-185a52a.md)


See also: [Adapting Standard Integration Content to Your Requirements](adapting-standard-integration-content-to-your-requirements-35b53da.md)

