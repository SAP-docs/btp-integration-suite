<!-- loio2ecdaf9ada514e5292af9996974ac38c -->

# Importing from ODC



## Prerequisites

You have created an OData API artifact in an integration package.



## Context

SAP Cloud Integration helps you import a model definition from an OData API, which is created on an on-premise SAP Gateway system. SAP Gateway has a component called Backend Provisioning Component or IW\_BEP. This component resides on SAP Business Suite and is used to build OData APIs from data sources like RFCs, BAPIs, and so on. SAP Cloud Integration communicates with the IW\_BEP component in SAP Gateway through OData Channel or ODC protocol, which is an SAP proprietary protocol.

> ### Note:  
> SAP Cloud Integration does not support connecting to an SAP Gateway system based on SAP NetWeaver 7.02 where the IW\_BEP component version is SP 06 or lower.
> 
> SAP Cloud Integration also does not support connecting to an SAP Gateway system based on SAP NetWeaver 7.40 where the SAP\_GWFND component is SP 02 or lower.

You can use this procedure to create an OData model or build up an existing one by importing the model definition from an OData API created in IW\_BEP \(ODC\).



## Procedure

1.  If you are creating a new OData API artifact, proceed to the next step. If you are editing an existing OData API artifact, choose *Edit* on the Service Designer page.

2.  Choose *Import Model Wizard* \(![](images/Import_Model_e262810.png)\).

3.  In the *Select Data Source Type* page, select *ODC* as data source type.

4.  Enter the connection details as listed in the following table.

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

        This option is only available if you have chosen Cloud Integration as the runtime profile.

        If you select this option, the *Address* field of the adapter refers to a virtual address that has to be configured in the SAP Cloud Connector settings.



    
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
    
5.  Choose *Step 2*.

    > ### Note:  
    > While importing from any data source using the *Import Wizard*, if the element is of complex type containing a single child element of simple type, the option to deselect only the child element is not supported. In such a scenario, you can select *Flatten* from the *Import As* dropdown for the parent WSDL element. After completing the *Import Wizard*, navigate to the *OData Model Editor* and modify the structure as required.

    In the *Select Structure* page, you can see entity types and function imports from the EDMX listed in a table. The table also displays the associated EDM type, primary key, and documentation information.

6.  Select entity types and function imports that you need to add to the model from the *OData Hierarchy* column. You can expand or collapse entity types and function imports to view its properties better.

7.  Choose *Step 3*.

8.  In the *Review and Finish EDMX Structure* page, verify and perform the following additional changes, if required, to the OData model definition:

    -   Rename the OData objects listed under *EDM Name*.
    -   Select a different EDM type.
    -   Select another primary key.
    -   Update the *Documentation* column.
    -   Restore default definition of the OData model by choosing *Restore Default Values*.

9.  Once you have completed all the changes, choose *Finish*. The Service Designer page displays the entity sets and function imports from the OData model in a table.

10. Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


