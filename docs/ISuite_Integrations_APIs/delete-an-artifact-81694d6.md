<!-- loio81694d6c97214238937ff249310993c0 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Delete an Artifact

Use this procedure to delete an API or an MCP Server artifact from an integration package in the Design workspace.



<a name="loio81694d6c97214238937ff249310993c0__prereq_rnp_v53_b2b"/>

## Prerequisites

You are assigned the *PI\_Integration\_Developer* role.



<a name="loio81694d6c97214238937ff249310993c0__context_snp_v53_b2b"/>

## Context

To delete an API artifact, proceed as follows:



<a name="loio81694d6c97214238937ff249310993c0__steps_tnp_v53_b2b"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *Integrations and APIs*.

3.  Select the *<integration package\>* from where you want to delete the API or the MCP Server artifact.

4.  On the *<integration package\>* details page, choose *Artifacts*.

5.  Choose the <span class="SAP-icons-V5"></span> Action icon against the required artifact and then select the *Delete* option.

6.  In the confirmation dialog, choose *Delete* again to confirm the deletion.

    > ### Note:  
    > You cannot delete an artifact if it is referenced or consumed by another artifact. Remove the existing references or dependencies before deletion.
    > 
    > Deleting an artifact permanently removes it from the integration package.




<a name="loio81694d6c97214238937ff249310993c0__result_av2_h23_31c"/>

## Results

The selected API or MCP Server artifact is deleted from the integration package and is no longer available in the *Design* workspace.

**Related Information**  


[API Artifact](api-artifact-a4f87b1.md "API artifacts are the core building blocks used to design, configure, publish, and manage APIs in SAP Integration Suite, API Management. These artifacts define how APIs behave, how they interact with backend systems, and how they are exposed to consumers.")

[Model Context Protocol \(MCP\)](model-context-protocol-mcp-9eb9239.md "Model Context Protocol (MCP) is an open-source protocol designed to bridge the gap between AI applications or agents and enterprise tools and data. Just as REST APIs connect web applications to data and services, MCP enables AI-native integrations by exposing tools, APIs, and data sources to AI Agents.")

[Deploy an Artifact](deploy-an-artifact-b70e7ec.md "After creating an API or an MCP server artifact, it is necessary to deploy it on the chosen runtime in order to make it executable and ready for use.")

[Copy an Artifact](copy-an-artifact-820c9e8.md "Create a copy of an existing API artifact or an MCP server with all its configurations and policies intact. This can be useful when you want to create a similar artifact but with some modifications or variations.")

