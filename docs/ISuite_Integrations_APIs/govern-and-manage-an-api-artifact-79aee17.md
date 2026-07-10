<!-- loio79aee17a40c8434f9bc1ba8bf05eb469 -->

# Govern and Manage an API Artifact

After creating the API artifact, you can configure it further based on your requirements. For example, you can add API resources, configure policies, and update the target endpoint or API metadata. This helps you define how the API behaves, how requests are routed, and how security and traffic management are enforced.



## Procedure

1.  Log on to SAP Integration Suite.
2.  From the left navigation pane, choose *Design* \> *Integrations and APIs*.
3.  Select the integration package containing the API artifact and choose *Edit*.
4.  Open the *Artifacts* tab.
5.  Select the required API artifact and choose **Edit**.

    The API artifact editor opens with the following tabs:

    -   **Overview**

        Use the *Overview* tab to view and maintain the general details of the API artifact. You can update information such as:

        -   API name and ID
        -   Short text and description
        -   Service type
        -   API base path
        -   API state
        -   Runtime profile
        -   Virtual host

        The overview information helps identify and configure the API artifact and defines how the API is exposed.

    -   **Target EndPoint**

        Use the *Target EndPoint* tab to configure the backend service URL to which the API requests are routed. The target endpoint defines the destination system or service that processes incoming API requests.

        You can update the target endpoint URL/Destination at any time based on your backend configuration requirements.

    -   **Resources**

        Use the **Resources** tab to add and manage API resources. Resources define the paths and operations exposed by the API and determine how incoming requests are handled.

        From this tab, you can:

        -   Add new resources
        -   Edit existing resources
        -   Delete resources

        For more information, see [Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md).

        You can also add, edit, and delete resources directly in the OpenAPI Specification editors. See, [OpenAPI Specification Editors](openapi-specification-editors-2bf94eb.md).

    -   **Policies**

        Use the *Policies* tab to configure and manage policies for the API artifact. Policies help you control API behavior and enforce security and traffic management requirements.

        You can use policies for:

        -   Authentication and authorization
        -   Request and response transformation
        -   Traffic management
        -   Routing and mediation
        -   Error handling

        The policy model provides a visual interface for adding and arranging policies within the API artifact.

        For more information, see [Working with Policies and Mediation Steps](working-with-policies-and-mediation-steps-c744df5.md) and [Add Policies to Artifacts](add-policies-to-artifacts-c2b3e56.md).


6.  After you finish configuring the API artifact, you can choose one of the following actions:


    <table>
    <tr>
    <th valign="top">

    Action
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Save**
    
    </td>
    <td valign="top">
    
    Save the API artifact as a draft version.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Save as Version**
    
    </td>
    <td valign="top">
    
    Create a new version of the API artifact. In the **Version Information** dialog, specify the version number. You can also add comments to provide additional context or details about the version for future reference. See [API Artifact Versioning](api-artifact-versioning-3f2e06b.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Deploy**
    
    </td>
    <td valign="top">
    
    Deploy the API artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Delete**
    
    </td>
    <td valign="top">
    
    Delete the API artifact and remove it from the package.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Cancel**
    
    </td>
    <td valign="top">
    
    End the editing session without saving the changes.
    
    </td>
    </tr>
    </table>
    

**Related Information**  


[Different Methods for Creating an API Artifact](different-methods-for-creating-an-api-artifact-c2fe62c.md "API artifacts can be created using different methods depending on your integration scenario and deployment requirements.")

