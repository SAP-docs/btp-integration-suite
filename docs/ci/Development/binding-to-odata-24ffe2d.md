<!-- loio24ffe2db9c1c4d449716a027ce019853 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Binding to OData



## Prerequisites

You are editing an OData API artifact and you have created an OData model. OData objects in the model are listed in a table on the Service Designer page.



## Context

You can use this procedure to bind function imports and operations of entity sets to the corresponding OData APIs.



## Procedure

1.  Select *ODATA* as the data source for an entity set or function import.

2.  Choose *Bind* \(:link:\) for the function import or operation associated with the entity set that you need to bind. The *Configure OData Data Source* dialog box appears.

3.  Choose *Browse* and select the EDMX file from your file location. You can also select the file from the *Existing Files* list. The *Existing Files* list is populated with EDMX file names used in other bindings in the same OData API artifact.

4.  Select an entity set from the *Entity Sets* dropdown list. This list displays all entity sets from the selected EDMX file.

5.  Enter the Endpoint URI corresponding to the OData API that you are binding to.

6.  Choose *OK*. The Service Designer page appears and the *Action* column for this operation now displays *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and *Delete Binding* \(:wastebasket:\) buttons.

    A predefined integration flow with mapping steps is generated for the operation or function import. For more information, see [Predefined Integration Flows for OData](predefined-integration-flows-for-odata-585b5af.md).

    You can update the integration flow to better suit your business scenario by choosing *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\). For more information, see [Editing an Integration Flow](editing-an-integration-flow-ccd062a.md).

    In case you need to update the binding information, you can do it in one of the following ways:

    -   Choose *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and update the Endpoint URI information in the receiver channel.
    -   Choose *Delete Binding* \(:wastebasket:\) and repeat the binding procedure.

7.  Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


