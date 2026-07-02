<!-- loiof7d228c6402f44b7b8f01204e9b759e3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing from SOAP



## Context

You have created an OData API artifact in an integration package. You can use this procedure to create an OData model or build up an existing one by importing the model definition from SOAP web services.



## Procedure

1.  If you are creating a new OData APIOData API artifact, proceed to the next step. If you are editing an existing OData API artifact, choose *Edit* on the Service Designer page.

2.  Choose *Import Model Wizard* \(<span class="SAP-icons-V5"></span>\).

3.  In the *Select Data Source Type* page, select *SOAP* as data source type.

4.  Choose *Browse* and select the WSDL file from your file system. You can also select the WSDL from the list of existing WSDL files \(if any\) used in the OData API artifact.

    > ### Note:  
    > Composite WSDLs that are flattened are supported. However, multipart WSDLs and other file types are not supported.

5.  Choose *Step 2*. In the *Select Structure* page, you can see the elements from the WSDL listed in a table.

6.  Select elements that you want to add to the OData model from the *WSDL Hierarchy* column. You can expand or collapse WSDL elements to view the hierarchy better.

7.  Deselect any child element that you do not want to include in the OData model. You can see that the corresponding parent elements are in a mixed state \(neither checked nor unchecked\), if they have other child elements that are selected.

    > ### Note:  
    > While importing from any data source using the *Import Wizard*, if the element is of complex type containing a single child element of simple type, the option to deselect only the child element is not supported. In such a scenario, you can select *Flatten* from the *Import As* dropdown for the parent WSDL element. After completing the *Import Wizard*, navigate to the *OData Model Editor* and modify the structure as required.

8.  Select the OData type that each WSDL element has to be converted to in the OData model. To see options available for various types of WSDL elements, refer the following table:


    <table>
    <tr>
    <th valign="top">

    WSDL Type
    
    </th>
    <th valign="top">

    OData Type
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    Operation
    
    </td>
    <td valign="top">
    
    Complex Type
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Entity Type
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Function Import
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Complex Type
    
    </td>
    <td valign="top">
    
    Complex Type
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Input Message
    
    </td>
    <td valign="top">
    
    Complex Type
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Output Message
    
    </td>
    <td valign="top">
    
    Complex Type
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Part
    
    </td>
    <td valign="top">
    
    Complex Type
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You can select *Flatten* from the *Import As* dropdown for all WSDL types other than *Operation*. *Flatten* is not an OData type that a WSDL element can be converted to. It is an instruction to the system to skip importing the specified WSDL element into the OData model without affecting the import of its children in the hierarchy.

9.  Choose *Step 3*. You can review the mapping of WSDL elements to OData objects in this step.

10. In the *Review and Finish EDMX Structure* page, select a primary key from the properties of entity types.

11. Verify and perform the following additional changes, if required, to the OData model definition:

    -   Rename the OData objects listed under *EDM Name*.
    -   Select a different EDM type.
    -   Update the *Documentation* column.
    -   Restore default definition of the OData model by choosing *Restore Default Values*.

12. Once you have completed all the changes, choose *Finish*. The Service Designer page displays the entity sets and function imports from the OData model in a table.

13. Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


