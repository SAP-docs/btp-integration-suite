<!-- loioe6b43b4c5a5042fda30a9dfdab97eff3 -->

# Developing Integration Content with SAP Cloud Integration

You can use SAP Cloud Integration to access and design integration content.



<a name="loioe6b43b4c5a5042fda30a9dfdab97eff3__section_pfdb_xw4_b41_cgb"/>

## Use

SAP Cloud Integration provides you with an interface for accessing and managing integration content. You can either directly use the prepackaged integration content from the catalog or upload it to your workspace to adapt it to your requirements.

You can use the artifacts available in integration packages to solve the integration challenges of your scenario. Optionally, you can also upload integration packages from your local folder and use them. You can use the integration flows available in packages by configuring and deploying them. You can also edit the integration flows by adding or removing elements, before you configure and deploy them.

The application consists of the following components which allow you to perform different tasks:


<table>
<tr>
<th valign="top">

Component



</th>
<th valign="top">

Allows you to...



</th>
</tr>
<tr>
<td valign="top">

*Discover* 



</td>
<td valign="top">

View all available integration packages.

Which integration packages are available to you depends on the permissions for the user \(which has logged-in to SAP Cloud Integration\). You can view the description of integration packages and copy integration packages to your customer workspace \(see *Design* tab below\).

This component is also known as *catalog*.



</td>
</tr>
<tr>
<td valign="top">

*Design* 



</td>
<td valign="top">

Configure or model integration flows.

After completing this task, you can save the changes, save as a version or deploy the integration flow.

This component is also known as *customer workspace*.



</td>
</tr>
<tr>
<td valign="top">

*Monitor* 



</td>
<td valign="top">

Monitor the message processing and manage integration artifacts such as integration flows, value mappings and security-related artifacts.

You can check the status of messages and integration artifacts for your tenant cluster.

You can also access the dedicated message monitor and integration content monitor to view more information.



</td>
</tr>
<tr>
<td valign="top">

*Settings* 



</td>
<td valign="top">

Select the runtime profile to specify the target runtime for your content.



</td>
</tr>
</table>

**Related Information**  


[Basic Concepts of Integration Design](basic-concepts-of-integration-design-ca0f6f7.md "")

[Working with Integration Packages](working-with-integration-packages-45423ba.md "")

[Content Transport](content-transport-e3c79d6.md "Reuse content across multiple tenants. Export integration content from one (source) tenant and import it on another (target) tenant.")

[Creating an Integration Flow](creating-an-integration-flow-da53d93.md "Add an integration flow to an integration package.")

[Using Flow Step Recommendation](using-flow-step-recommendation-eb00f23.md "The flow step recommendation in an integration flow development helps you to easily add flow steps. You get the recommendations based on prepackaged SAP integration content.")

[Integration Flow Extension](integration-flow-extension-d374172.md "SAP Cloud Integration allows you to extend the capabilities of standard integration content provided by SAP. This approach allows you to implement specific integration scenarios relevant to your business use case without changing the content provided by SAP.")

[Importing Custom Integration Adapter, Cloud Foundry Environment](importing-custom-integration-adapter-cloud-foundry-environment-482286e.md "Use the integration-adapter artifact type to import custom integration adapter in your integration package.")

[Configure Integration Flow Components](configure-integration-flow-components-3171795.md "Cloud Integration allows you to configure integration flow components in an editor.")

[Simulation of an Integration Flow](simulation-of-an-integration-flow-2e2210b.md "The simulation feature allows you to test an integration flow or its subset and see if you can get the desired outcome even before you deploy the integration flow. Based on the simulation result, you can decide whether to continue and deploy the integration flow or changes the same. You can also resolve if there are any errors.")

[Deploying Data Flows](deploying-data-flows-c3a913e.md "")

[Unlocking Integration Packages and Artifacts](unlocking-integration-packages-and-artifacts-739a536.md "When you edit an integration package or an artifact, it is locked and cannot be edited by other users simultaneously. In case you close your browser without saving the changes or there is a session timeout, the package or artifact remains locked, until you unlock it.")

[Monitor](../Operations/monitor-05446d0.md "Check the status of messages and integration content artifacts for a tenant cluster.")

