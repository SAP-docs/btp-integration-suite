<!-- loio992512e5bec0405b8e0791f86216908c -->

# Setting Up External Governance

This topic describes how to configure an external governance process in which subscription requests raised by developers in Developer Hub are approved or rejected through an external system.

The process begins by selecting the *Manage Approval Outside Developer Hub* option in Developer Hub However, enabling this setting alone is not sufficient — several prerequisites must first be fulfilled.

In this section, we’ll take you step by step through the configuration process.



## Configuring External Governance

1.  **Governance Settings in Developer Hub** 

    The Developer Hub administrator \(with the AuthGroup.API.Admin role\), navigates to the *Governance Settings* page on Developer Hub and selects the *Manage Approval Outside Developer Hub* option. For more information, see [Configure Governance Settings](configure-governance-settings-7446560.md).

2.  **Complete the Prerequisites** 
    1.  **Implement the Service Provider Interface \(SPI\)**: The subaccount administrator of the external governance system should ensure that the Service Provider Interface \(SPI\) is implemented in their landscape, which also takes care of redirecting the subscription request to an external system. This ensures that all the subscription request raised in Developer Hub will reach the external system. This external system can be a workflow, UI application, backend service, or an automated service.

        The SPI specifications are published on SAP Business Accelerator Hub, see [Developer Hub - Service Provider Interface](https://api.sap.com/api/DevPortal_ExternalGovernanceSPI_CF/overview). These specifications include interface details such as name, input/output parameters, and other technical requirements.

        > ### Note:  
        > It is recommended to use SAP Integration Suite API Management to implement the Service Provider Interface \(SPI\), and leverage SAP Build Process Automation to design the external governance workflow. For more information on SAP Build Process Automation, see [SAP Process Automation | SAP Learning](https://learning.sap.com/products/sap-build/process-automation). However, you can implement the Service Provider Interface \(SPI\) and the external governance workflow using any other method that suits your requirements.

    2.  **Create a Destination in SAP BTP Cockpit**: After implementing the Service Provider Interface \(SPI\), the customer subaccount administrator creates a destination in their SAP BTP subaccount pointing to the SPI endpoint.

        This destination must include:

        -   The SPI service URL
        -   Authentication details \(such as OAuth2, Basic Auth, and Client Certificate\)

        This destination allows Developer Hub to forward subscription requests to the customer’s external governance system. For more information, see [Create a Destination for Approving and Rejecting Subscriptions](create-a-destination-for-approving-and-rejecting-subscriptions-71230dc.md).

    3.  **Update Developer Hub with the governance decisions**: Once a subscription request is approved or rejected externally, the decision must be communicated back to Developer Hub.

        The external governance system calls the API [Developer Hub - External Governance \(CF\)](https://api.sap.com/api/DevPortal_ExternalGovernance_CF/overview) published on SAP Business Accelerator Hub, using credentials of the *AuthGroup.External.Reviewer* role collection. This ensures that Developer Hub reflects the final decision from the external system.


3.  **Governance Setting takes Effect**

    Once all prerequisites are fulfilled, the *Manage Approval Outside Developer Hub* setting takes effect.

    From this point onward, new subscription requests raised by developers are automatically routed through the customer’s external governance workflow for approval or rejection.

    > ### Note:  
    > If the governance settings are changed but the required prerequisites are not completed, the external governance will not function as expected. In such cases, subscription requests from developers will fail. To ensure proper operation, verify that all prerequisites are correctly configured before enabling external governance.

4.  **Subscription Process After Setup**

    Once the setup is complete:

    1.  **Developer Submits a Subscription Request**
        -   The application developer subscribes to a product from the Developer Hub catalog and submits the subscription request for approval.
        -   If the governance setting is configured as *Manage Approval Outside Developer Hub*, the subscription request is sent to the external governance system for manual approval.

    2.  **External Administrator Reviews and Acts on the Request**
        -   The external administrator logs into the external approval system \(for example, a workflow built using SAP Build Process Automation\) to review the pending subscription request.
        -   The administrator can then approve or reject the request based on the business rules or criteria defined in the external workflow.

            > ### Note:  
            > The external administrator has read-only access to the Developer Hub, which allows them to view detailed information about the products related to subscription requests. This can be done either by logging into the Developer Hub directly or by using the API Management APIs available on the SAP Business Accelerator Hub.


    3.  **Developer Receives the Decision**
        -   The application developer waits for the subscription request to be approved by the external administrator before performing any further actions \(such as editing or testing APIs\).
        -   When the request is approved, the developer receives an email notification containing a link to the approved subscription. The developer can then access and consume the APIs.
        -   If the request is rejected, the developer receives an email notification, and the subscription \(which was in Pending Approval state\) is automatically deleted.
        -   Until the decision is made, the developer can check the status of the request under *My Workspace* \> *Subscriptions* \> *Pending Approval in Developer Hub*.





## Managing Governance for Internally and Externally Managed Products

Once external governance is enabled, subscription requests are processed differently depending on how products and APIs are managed:

-   **Governance for products managed by SAP API Management**

    In this model, products are internally managed within the SAP ecosystem. Their APIs are exposed and governed using SAP’s internal API Management system. Application developers can subscribe to these products directly and the governance setting selected would be applicable.

-   **Governance for products managed by external API Management systems**

    In this model, products are managed outside of SAP, and their APIs are maintained and governed by an external API management system. However, these APIs can still be cataloged in Developer Hub by manually uploading their API specification in a product, allowing developers to discover them in the catalog.

    -   **Publishing APIs from External Systems**: The content administrator \(assigned the AuthGroup.Content.Admin role collection\) imports APIs from the external gateway, adds them to a product, and publishes the product in Developer Hub. For detailed instructions, see[Make APIs Imported from External Gateways Available in Developer Hub](make-apis-imported-from-external-gateways-available-in-developer-hub-961d39e.md).
    -   During this process, the content administrator must mark the product as subscribable by selecting the *Allow Subscription* checkbox.

        This can be done either during product creation, or later, by editing the product details.

        Depending on your organizations's governance needs, there are two common scenarios to allow subscriptions:

        -   **Governance Only**: Used to track which developers are using which products. This ensures visibility and control, even if API keys or credentials are shared outside of Developer Hub.
        -   **Governance and Credential Distribution**: In addition to tracking subscriptions, some organizations also share API credentials directly through Developer Hub. This allows for both governance tracking and automatic credential sharing with developers. When the Developer Hub is updated with governance decisions, the corresponding credentials to access the products are also sent automatically.

        > ### Note:  
        > Application developers cannot directly subscribe to these products through the SAP system.
        > 
        > Optionally, the approver \(external administrator\) can provide developers with API keys from the external gateway to enable access to the subscribed APIs.

    -   **Configuration Requirements for External Governance**: To ensure external governance functions correctly, verify the following configurations:

        -   The Developer Hub administrator has set the governance option to *Manage Approval Outside Developer Hub* in the governance settings.
        -   The product is marked as externally subscribable by selecting the*Allow Subscription* checkbox.

        > ### Caution:  
        > Both settings are mandatory for external subscription approvals to work correctly.

    -   **Product Management Considerations**
        -   You cannot disable subscriptions or remove a product from the catalog if it has any pending or approved subscriptions associated with it.
        -   After making any configuration changes, you must republish the product to apply those changes.

            > ### Note:  
            > Any changes to a published product in Developer Hub cannot be made directly. To apply updates, you must first bring the product into draft, make the necessary changes, and then publish it again. This ensures that all changes are properly applied to the product.

            Products managed by external API management systems can be published and subscribed to via Developer Hub, with all approvals handled by the external governance system. This setup ensures that external APIs are visible to developers while keeping approval and access fully controlled outside of SAP systems.




