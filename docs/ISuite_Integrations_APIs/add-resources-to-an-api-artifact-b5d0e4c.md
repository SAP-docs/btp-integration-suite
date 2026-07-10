<!-- loiob5d0e4c587cb4bb1b40ffbddb04c08bb -->

# Add Resources to an API Artifact

Add a resource to refer to individual endpoints or services.



<a name="loiob5d0e4c587cb4bb1b40ffbddb04c08bb__context_k3p_2vj_dgc"/>

## Context

Resources are added to an API to define the individual endpoints or functional units that clients can interact with. Each resource represents a specific piece of data or functionality that the API exposes. For example, in a sales order API, common resources might include customers, products, and orders. Each resource is accessed via a specific endpoint—such as /orders to retrieve a list of sales orders or /customers/\{id\} to view details of a specific customer. By defining these resources, the API becomes easier to understand, maintain, and scale, as each resource handles specific operations using standard HTTP methods like GET, POST, PUT, and DELETE. This structure not only improves clarity and usability but also supports better security and modular development.



## Procedure

1.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  To add a resource to an API artifact, choose the *<integration package\>* and select the API artifact to which you want to add a resource.

3.  Choose *Edit*.

4.  To add resources to the API artifact, execute the following steps:

    -   Adding a resource for a *REST* service:

        1.  Choose + \(*Add*\).

        2.  In the popup, enter a title and path prefix for the resource.

        3.  Select the methods that need to be supported for this resource.

        4.  Add descriptions in the editor and choose *Add*.

            The added resource appears on the *Resources* tab.

        5.  Choose *Add* to add more resources to the same API.


    -   Adding a resource for a *OData* service:

        For a given OData-based API artifact, you can import an .edmx file to update the API artifact with the latest resources. Importing an .edmx file will overwrite the existing list of resources in the API artifact. However, the description for each resource will still be maintained and not be changed.

        > ### Note:  
        > Importing the .edmx file will convert the API artifact to OpenAPI Specification 3.0.0. Please review the changes carefully before saving the API artifact.

        For an OData service, select the methods that the application developer can perform:

        -   *Get*: Read an entity.
        -   *Post*: Create an entity.
        -   *Put*: Update an entity.
        -   *Delete*: Delete an entity.

        > ### Note:  
        > Only the supported methods for each resource appear on the UI. By default, only permitted methods are selected.

    -   To add a resource to a SOAP-based API artifact:

        1.  Choose + \(*Add*\).

        2.  Enter a title and specify the SOAP operation name in the path prefix.

        3.  Use the editor to enter the relevant API documentation in the description field, and choose *Add*.

            The added resource appears on the *Resources* tab. By default, only the *POST* operation is selected.

        4.  Choose *Add* to add more resources to the same API.



    For a given resource, choose *Show/Hide* to view the list of properties and their associated API documentation. You can add descriptions for each resource in the editor.

5.  Choose *Save* after making the necessary changes.


