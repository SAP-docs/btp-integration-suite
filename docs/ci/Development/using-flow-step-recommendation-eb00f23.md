<!-- loioeb00f23c6be44da5a1ba75ba0c0f311e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using Flow Step Recommendation

The flow step recommendation in an integration flow development helps you to easily add flow steps. You get the recommendations based on prepackaged SAP integration content.



<a name="loioeb00f23c6be44da5a1ba75ba0c0f311e__prereq_dvt_bg1_cnb"/>

## Prerequisites

-   You’ve created an integration package. For more information, see [Create an Integration Package](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/748968a0f43d442f98d93a9a197cdbd2.html).

-   You've created an integration flow. For more information, see [Creating an Integration Flow](creating-an-integration-flow-da53d93.md).




## Context

With flow step recommendation, there’s no need to find the next flow steps from the palette. You get a dialog with a list of flow steps in the editor itself where you need them. You get a suggestion for next possible flow step at the time of integration scenario development. For example, when you’re adding a content modifier in your integration flow, it comes with a flow step recommendation that helps you select the next flow step without navigating to the palette. The selected flow step automatically gets added to the sequence connector.

You see the following sections in the flow step recommendation dialog:

-   *Recommended Steps*: From an existing flow step or sequence connector, you get recommendations for the next step. The recommendations are made by a machine learning study on the prepackaged SAP integration content.

-   *All Steps*: The dialog also provides a list of all flow steps where you can either scroll or search for the required flow step.




## Procedure

Here's how you can use flow step recommendation for adding flow step in an integration flow.

1.  Choose :pencil2: \(*Design*\) tab to access your workspace.

2.  Choose *Integration Package* \> *Artifacts* \> *Integration Flow* \> *Edit*.

3.  Select an existing flow step or a sequence connector.

4.  Choose :heavy_plus_sign: \(*Add Flow Step*\) button.

    A dialog opens up showing the recommended steps first and then all the steps.

5.  Select a step that is required for your integration flow.

    ![](images/Smart_Editor_675b444.gif)


