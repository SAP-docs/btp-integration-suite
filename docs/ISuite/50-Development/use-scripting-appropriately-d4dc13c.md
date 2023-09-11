<!-- loiod4dc13c927b044b2a38e458f4cea9da5 -->

# Use Scripting Appropriately

You can use the Script step to apply script operations on the message content.



<a name="loiod4dc13c927b044b2a38e458f4cea9da5__section_o52_5xb_hqb"/>

## About the Script Step

The Script step type supports the following script languages:

-   Groovy

-   JavaScript


For more information on this feature, see [Define a Local Script Step](define-a-local-script-step-03b32eb.md).

For general guidelines when using the *Script* step, see [General Scripting Guidelines](general-scripting-guidelines-fcbf0f2.md).

For specific integration flow design guidelines when using the *Script* step, see:

-   [Access Secure Parameters in Scripts](access-secure-parameters-in-scripts-fdf4ce3.md)

-   [Access Headers and Properties in Scripts](access-headers-and-properties-in-scripts-6bc5ed1.md)

-   [Create MPL Attachments in Scripts](create-mpl-attachments-in-scripts-17dba92.md)

-   [Access Value Mappings in Scripts](access-value-mappings-in-scripts-12536ee.md)

-   [Use Custom Header Properties to Search for Message Processing Logs](use-custom-header-properties-to-search-for-message-processing-logs-d4b5839.md)

-   [Access URL Paths in Scripts](access-url-paths-in-scripts-f0620cb.md)

-   [Access URL Get Parameters in Scripts](access-url-get-parameters-in-scripts-7ad2ac9.md)

-   [Parse JSON](parse-json-af0da64.md)


> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Scripting Guidelines](https://api.sap.com/package/IntegrationFlowDesignGuidelinesScriptingGuidelines/integrationflow)
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

If you don't consider the proposed guidelines during integration design, there's the risk that your scenario is affected in the following way:

-   The scenario runs into an out of memory situation.

-   It's hard for the integration expert to understand the logic of the integration flow.

-   Your scenario runs into compatibility issues if there are Java upgrades or Cloud Integration updates.


> ### Note:  
> It can be the case that you've applied the integration flow design guidelines described in this section to your best knowledge, but you still face issues during the operation of the scenario. For example, you have applied all design rules with regard to performance but still the performance isn't good enough at runtime. In such cases, you can check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).



<a name="loiod4dc13c927b044b2a38e458f4cea9da5__section_jbx_dnx_vqb"/>

## Script Collection

A script collection is a bundle of scripts which can be used by all the integration artifacts belonging to the same integration package. See [Developing Script and Script Collection](developing-script-and-script-collection-e60f706.md) for information on how to create and use a script collection.

The advantages of using script collections instead of local scripts are:

-   Reuse

-   Reduced Maintenance Efforts

-   Reduce File Size and Memory Usage

-   Avoid Duplicates


The script collection *Scripting – Script Collection* contains the scripts needed by the integration flows in the integration package *Integration Flow Design Guidelines – Scripting Guidelines*. The integration flows explained in the next chapters use references to the corresponding scripts of the collection instead of local scripts. Only the integration flow *Scripting – Mapping Functions* uses a local script, as UDFs in Mappings are not supported yet in script collections.

