<!-- loio2cb1d31f227947e98e02fd0ede360c8c -->

# Copying the Integration Package and Deploying the Integration Flows



To work with the example integration flows, you need to perform the following steps:

1.  Copy the integration package that contains the example integration flows for the guideline into your workspace.

    > ### Note:  
    > For more information, try out the tutorial [Getting Started with Integration Flow Design Guidelines - Timer Initiated Scenario](https://developers.sap.com/tutorials/btp-integration-suite-design-guidelines.html).

    The integration flows are published in dedicated integration packages on SAP Business Accelerator Hub. For each guideline category \(for example, [Handle Errors Gracefully](handle-errors-gracefully-42c95f7.md)\), you can find a dedicated integration package as summarized in the following table:


    <table>
    <tr>
    <th valign="top">

    Guideline Category and Documentation
    
    </th>
    <th valign="top">

    Integration Package Name
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    [Learn the Basics](learn-the-basics-ebc6034.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Learn the Basics](https://api.sap.com/package/DesignGuidelinesModelingBasics/integrationflow) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Run an Integration Flow Under Well-Defined Boundary Conditions](run-an-integration-flow-under-well-defined-boundary-conditions-f8cf974.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Run an Integration Flow Under Well-Defined Boundary Conditions](https://api.sap.com/package/DesignGuidelinesManageResources?section=Overview) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Relax Dependencies to External Components](relax-dependencies-to-external-components-3ea1e33.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Relax Dependencies to External Components](https://api.sap.com/package/DesignGuidelinesRelaxDependenciestoExternalComponents?section=Overview) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Keep Readability in Mind](keep-readability-in-mind-578fa77.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Keep Readability in Mind](https://api.sap.com/package/DesignGuidelinesKeepReadabilityinMind?section=Overview) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Handle Errors Gracefully](handle-errors-gracefully-42c95f7.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Handle Errors Gracefully](https://api.sap.com/package/DesignGuidelinesHandleErrors?section=Overview) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Use Prepackaged Integration Content Provided by SAP](use-prepackaged-integration-content-provided-by-sap-95c68ce.md) 
    
    </td>
    <td valign="top">
    
    \(no integration package available\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Apply the Highest Security Standards](apply-the-highest-security-standards-201fd43.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Apply Highest Security Standards](https://api.sap.com/package/DesignGuidelinesApplySecurity?section=Overview) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Use the Partner Directory Appropriately](use-the-partner-directory-appropriately-6e00412.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Use the Partner Directory Appropriately](https://api.sap.com/package/IntegrationFlowDesignGuidelinesPartnerDirectoryGuidelines?section=Overview) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Scripting Guidelines](https://api.sap.com/package/IntegrationFlowDesignGuidelinesScriptingGuidelines/integrationflow) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    [Guidelines to Implement Specific Integration Patterns](guidelines-to-implement-specific-integration-patterns-eaf929e.md) 
    
    </td>
    <td valign="top">
    
    [Integration Flow Design Guidelines - Enterprise Integration Patterns](https://api.sap.com/package/DesignGuidelinesPatterns?section=Overview) 
    
    </td>
    </tr>
    </table>
    
2.  Open the package it in the *Design* section of the Web UI.

    The integration flows are in the *Artifacts* tab and the Postman collections are in the *Documents* tab.

3.  Search for the integration flows that belong to the guideline that you want to explore.

    The integration flow names follow the naming pattern *<Category\> - <Guideline\> - <extension\>*.

4.  Deploy each required integration flow.

    Make sure that the *Generic Receiver* integration flow is also deployed. This integration flow serves as a common receiver mock up for all the integration flows.

    For more information, see [Generic Receiver](generic-receiver-83a6970.md).


