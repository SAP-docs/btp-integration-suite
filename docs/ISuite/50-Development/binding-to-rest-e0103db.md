<!-- loioe0103db1c7214156bd0612850bafa36d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Binding to REST



## Prerequisites

You are editing an OData API artifact and you have created an OData model. OData objects in the model are listed in a table on the Service Designer page.



## Context

You can use this procedure to bind function imports and operations of entity sets to the corresponding REST services.



## Procedure

1.  Select *REST* as the data source for an entity set or function import.

2.  Choose *Bind* \(:link:\) for the function import or operation associated with the entity set that you need to bind. The *Configure REST Data Source* dialog box appears.

3.  Enter the Endpoint URI corresponding to the REST service that you are binding to.

4.  Choose *OK*. The Service Designer page appears and the *Action* column for this operation or function import now displays *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and *Delete Binding* \(:wastebasket:\) buttons.

    A predefined integration flow with mapping steps is generated for the operation or function import. For more information, see [Predefined Integration Flows for REST](predefined-integration-flows-for-rest-f86d30e.md).

    You can update the integration flow to better suit your business scenario by choosing *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\). For more information, see [Editing an Integration Flow](editing-an-integration-flow-ccd062a.md).

    In case you need to update the binding information, you can do it in one of the following ways:

    -   Choose *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and update the Endpoint URI information in the receiver channel.
    -   Choose *Delete Binding* \(:wastebasket:\) and repeat the binding procedure.

5.  Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


