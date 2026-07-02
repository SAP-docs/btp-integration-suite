<!-- loio478632d30d9e4082b62f39c7dc29eeec -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Editing an OData Model



## Context

You have created an integration package and added an OData API artifact to the package.

You can use this procedure to create an OData model from the ground up. You can also use it to edit an existing OData model.



## Procedure

1.  If you are creating a new OData API artifact, proceed to the next step. If you are editing an existing OData API artifact, choose *Edit* on the Service Designer page.

2.  Choose *OData Model Editor* \(<span class="SAP-icons-V5"></span>\) on the Service Designer page.

    If you are creating an OData model from the ground up, the OData Model Editor opens a predefined structure based on the selected OData version. The root is a **Schema** element. Below the root, subelements such as **EntityType**, **ComplexType**, **Association**, **EntityContainer**, and so on, can be added if required.

    > ### Note:  
    > -   In the case of an existing OData API artifact, you can only view the OData model in the OData Model Editor unless you explicitly choose *Edit* on the Service Designer page.
    > 
    >     For more information on the features of the OData Model Editor, see [OData Model Editor Features](odata-model-editor-features-7d298e2.md).
    > 
    > 
    > -   Only OData models up to 300 KB in size are supported.

3.  Once you have finished editing the OData model, choose *OK*.

4.  Choose *Back* \(<span class="SAP-icons-V5"></span>\) to get back to the Service Designer page.

5.  Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


