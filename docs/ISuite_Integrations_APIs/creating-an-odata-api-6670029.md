<!-- loio6670029b44bd43868216787a9adb648d -->

# Creating an OData API

Use this procedure to create an integration package that contains an OData API artifact.



## Context

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).



<a name="loio6670029b44bd43868216787a9adb648d__steps_o4s_p1h_py"/>

## Procedure

1.  Choose *Design* \> *Integrations and APIs*.

2.  Choose *Create*.

3.  Enter the required data for the integration package. See [Creating an Integration Package](creating-an-integration-package-9126d79.md).

4.  In the *Artifacts* tab, choose *Add* \> *OData API*.

5.  In the *Add OData API* dialog box, choose one of the following options:

    -   *Create Using Wizard* – to create a new OData API artifact that you can further develop based on your requirements.

    -   *Upload* – to create a new OData API artifact by uploading the necessary resources from your local file directory.


    > ### Note:  
    > The *Create Using Template* option is targeted for low code API development.

6.  Enter the OData API details as listed in the following table.


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Name of the OData API.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Namespace \(for Create Using Wizard\)
    
    </td>
    <td valign="top">
    
    Logical grouping of the OData API. Default is *SAP*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ID \(for Create Using Wizard\)
    
    </td>
    <td valign="top">
    
    Uniquely identifies the OData API and is a combination of the name and namespace of the OData API in the format <name\>\_<namespace\>\_1. This field isn’t editable.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Description of the OData API and its purpose.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OData API \(only for uploading the artifact\)
    
    </td>
    <td valign="top">
    
    Upload a ZIP file containing the OData API artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OData Version
    
    </td>
    <td valign="top">
    
    Currently, OData V2 is the only supported OData version.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You can edit some of the OData API details such as Name, Description, and Namespace after the service is created. For more information, see .

7.  Choose *Create*.

    You can further develop the OData API by:

    1.  [Creating an OData mode](create-an-odata-model-35fe18a.md)
    2.  [Binding to a data source](bind-to-data-source-2b6e865.md)
    3.  [Editing an Integration Flow](editing-an-integration-flow-ccd062a.md)

8.  Deploy the OData API. For more information, see [Deploying an OData API](deploying-an-odata-api-5f59721.md).

9.  Save the integration package.

    After the iFlow template generation, ensure that the Sender channel is always of type *OData*; for the other types, the tracing functionality won’t capture the details of the sender.


**Related Information**  


[Packaging Integration Content in SAP Integration Suite](packaging-integration-content-in-sap-integration-suite-89da0a2.md "")

