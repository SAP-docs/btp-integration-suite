<!-- loio460e1727bf5f4eb3b69e6945b5758c6b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Binding to ODC



## Prerequisites

You are editing an OData API artifact and you have created an OData model. OData objects in the model are listed in a table on the Service Designer page.



## Context

Cloud Integration helps you bind or connect to an OData APIOData API, which is created on an on-premise SAP Gateway system. SAP Gateway has a component called Backend Provisioning Component or IW\_BEP. This component resides on SAP Business Suite and is used to build OData APIs from data sources like RFCs, BAPIs, and so on. Cloud Integration communicates with the IW\_BEP component in SAP Gateway through OData Channel or ODC protocol, which is an SAP proprietary protocol.

> ### Note:  
> Cloud Integration does not support connecting to an SAP Gateway system based on SAP NetWeaver 7.02 where the IW\_BEP component version is SP 06 or lower.
> 
> Cloud Integration also does not support connecting to an SAP Gateway system based on SAP NetWeaver 7.40 where the SAP\_GWFND component is SP 02 or lower.

You can use this procedure to bind function imports and operations of entity sets to the corresponding OData APIs created in IW\_BEP \(ODC\).



## Procedure

1.  Select *ODC* as the data source for an entity set or function import.

2.  Choose *Bind* \(:link:\) for the function import or operation associated with the entity set that you want to bind.

    The *Configure ODC Data Source* dialog box appears. The entity set and CRUDQ operation information is prepopulated.

3.  Enter the following information related to the ODC destination.

    ****


    <table>
    <tr>
    <th valign="top">

    Connection Details
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Entity Sets
    
    </td>
    <td valign="top">
    
    A list of entity sets that is populated from the ODC source when importing the OData model. If you have coded the OData model, then the list is populated directly from your model.

    Select an entity set that you want to bind to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Address
    
    </td>
    <td valign="top">
    
    Endpoint URI of the target system
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client
    
    </td>
    <td valign="top">
    
    Client of the target system
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Namespace
    
    </td>
    <td valign="top">
    
    Logical grouping of the service implementation
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Service Name
    
    </td>
    <td valign="top">
    
    Name of the service implementation
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Version
    
    </td>
    <td valign="top">
    
    Version of the service implementation
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    The type of proxy that you are using to connect to the target system:

    -   Select *On-Premise* if you are connecting to an on-premise system using the SAP Cloud Connector.

        This option is only available if you have chosen *HANA Cloud Integration* as the product profile.

        If you select this option, the *Address* field of the adapter refers to a virtual address, which has to be configured in the SAP Cloud Connector settings.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Select *Basic* if you want to use user credentials to connect to the target system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Credential Name
    
    </td>
    <td valign="top">
    
    Name of the user credentials artifact deployed on the tenant
    
    </td>
    </tr>
    </table>
    
4.  Choose *OK*. The Service Designer page appears and the *Action* column for this operation now displays *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and *Delete Binding* \(:wastebasket:\) buttons.

    A predefined integration flow with mapping steps is generated for the operation or function import. For more information, see [Predefined Integration Flows for ODC](predefined-integration-flows-for-odc-677fcba.md).

    You can update the integration flow to better suit your business scenario by choosing *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\). For more information, see [Editing an Integration Flow](editing-an-integration-flow-ccd062a.md).

    If you want to update the binding information, you can do it in one of the following ways:

    -   Choose *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) and update the Endpoint URI information in the receiver channel.
    -   Choose *Delete Binding* \(:wastebasket:\) and repeat the binding procedure.

5.  Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


