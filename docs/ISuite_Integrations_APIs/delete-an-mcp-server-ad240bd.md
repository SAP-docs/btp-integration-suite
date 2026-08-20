<!-- loioad240bde994e48f3b4a03d31402c0b8e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Delete an MCP Server

Use this procedure to delete an MCP server artifact from an integration package in the Design workspace.



<a name="loioad240bde994e48f3b4a03d31402c0b8e__prereq_rnp_v53_b2b"/>

## Prerequisites

You are assigned the *PI\_Integration\_Developer* role.



<a name="loioad240bde994e48f3b4a03d31402c0b8e__context_snp_v53_b2b"/>

## Context

To delete an MCP server artifact, proceed as follows:



<a name="loioad240bde994e48f3b4a03d31402c0b8e__steps_tnp_v53_b2b"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *Integrations and APIs*.

3.  Select the *<integration package\>* from where you want to delete the MCP server artifact.

4.  On the *<integration package\>* details page, choose *Artifacts*.

5.  Choose the <span class="SAP-icons-V5"></span> Action icon against the required artifact and then select the *Delete* option.

6.  In the confirmation dialog, choose *Delete* again to confirm the deletion.

    > ### Note:  
    > You cannot delete an artifact if it is referenced or consumed by another artifact. Remove the existing references or dependencies before deletion.
    > 
    > Deleting an artifact permanently removes it from the integration package.




<a name="loioad240bde994e48f3b4a03d31402c0b8e__result_av2_h23_31c"/>

## Results

The selected MCP server artifact is deleted from the integration package and is no longer available in the *Design* workspace.

