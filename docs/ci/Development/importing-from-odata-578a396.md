<!-- loio578a3965639b40a4a7cadd1658d9a89e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing from OData



## Context

You have created an OData API artifact in an integration package. You can use this procedure to create an OData model or build up an existing one by importing the model definition from an existing OData API.



## Procedure

1.  If you are creating a new OData API artifact, proceed to the next step. If you are editing an existing OData API artifact, choose *Edit* on the Service Designer page.

2.  Choose :inbox_tray:.

3.  In the *Select Data Source Type* page, select *ODATA* as data source type.

4.  Choose *Browse* and select the EDMX file from your file system. You can also select the EDMX from the list of existing EDMX files \(if any\) used in the OData API artifact.

    *metadata.edmx* is the file used internally in Cloud Integration Web application to store the OData model definition of the OData API artifact.

    > ### Note:  
    > -   The OData Model Editor supports only OData SAP V2 annotations.
    > -   Only OData models up to 300 KB in size are supported.

    > ### Restriction:  
    > Importing of EDMX files with navigation entities are not supported and also there is size restrictions on EDMX files with large number of complex entities. For more information, see the KBA [2844323](https://me.sap.com/notes/2844323) and read the blog on [When to use an OData API](https://blogs.sap.com/2017/07/17/odata-service-project-vs-integration-project-when-to-use-what-in-cloud-platform-integration/).

5.  Choose *Step 2*. In the *Select Structure* page, you can see entity types and function imports from the EDMX listed in a table. The table also displays the EDM type, primary key and documentation information associated with the OData objects.

    > ### Note:  
    > While importing from any data source using the *Import Wizard*, if the element is of complex type containing a single child element of simple type, the option to deselect only the child element is not supported. In such a scenario, you can select *Flatten* from the *Import As* dropdown for the parent WSDL element. After completing the *Import Wizard*, navigate to the *OData Model Editor* and modify the structure as required.

6.  Select OData objects that you need to add to the model from the *OData Hierarchy* column. You can expand or collapse OData objects to view its properties better.

7.  Choose *Step 3*.

8.  In the *Review and Finish EDMX Structure* page, verify and perform the following additional changes, if required, to the OData model definition:

    -   Rename the OData objects listed under *EDM Name*.
    -   Select another primary key.
    -   Select a different EDM type.
    -   Update the *Documentation* column.
    -   Restore default definition of the OData model by choosing *Restore Default Values*.

9.  Once you have completed all the changes, choose *Finish*. The Service Designer page displays the entity sets and function imports from the OData model in a table.

10. Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


