<!-- loio691301a251954b8195db484449c5d2d6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Binding to SOAP



## Prerequisites

You are editing an OData API artifact and you have created an OData model. OData objects in the model are listed in a table on the Service Designer page.



## Context

You can use this procedure to bind function imports and operations of entity sets to the corresponding SOAP Web service operations.



## Procedure

1.  Select *SOAP* as the data source for an entity set or function import.

2.  Choose *Bind* \(:link:\) for the operation associated with the entity set or function import that you need to bind. The *Configure SOAP Data Source* dialog box appears.

3.  Choose *Browse* and select the WSDL file from your file location. If the OData model was imported from a WSDL file, the corresponding file name appears by default. You can change this to any other file name as required.

    > ### Note:  
    > Composite WSDLs that are flattened are supported. However, multipart WSDLs and other file types are not supported.

4.  Select an operation. If the OData model was imported from a WSDL file, operations defined in the WSDL appear in the dropdown list.

5.  Enter the Endpoint URI where the operation is located. If the OData model was imported from a WSDL file and an operation was selected from this WSDL, the corresponding Endpoint URI is auto-populated.

6.  Choose *OK*. The Service Designer page appears and the *Action* column for this operation now displays *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and *Delete Binding* \(:wastebasket:\) buttons.

    A predefined integration flow with mapping steps is generated for the operation. For more information, see [Predefined Integration Flows for SOAP](predefined-integration-flows-for-soap-383f7d1.md).

    You can update the integration flow to better suit your business scenario by choosing *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\). For more information, see [Editing an Integration Flow](editing-an-integration-flow-ccd062a.md).

    In case you need to update the binding information, you can do it in one of the following ways:

    -   Choose *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and update the Endpoint URI information in the receiver channel.
    -   Choose *Delete Binding* \(:wastebasket:\) and repeat the binding procedure.

7.  Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


