<!-- loio914f57e52c8945f5b3ef97a79548aeec -->

# Create an API Artifact Using a Target URL or an OpenAPI Specification

Create API artifacts by using either an endpoint-based or a specification-driven approach.



<a name="loio914f57e52c8945f5b3ef97a79548aeec__prereq_qtk_13k_qwb"/>

## Prerequisites

The *PI\_Integration\_Developer* role collection should be assigned to you.

Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).

-   To deploy API artifacts to an*Integration Cell* runtime, complete the following prerequisites:

    -   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

    -   Activate Integration Cell runtime. [Activate Integration Cell](activate-integration-cell-1a627da.md).

    -   *PI\_Integration\_Developer* role collection should be assigned to you.



-   To deploy API artifacts to an *Edge Integration Cell* runtime, complete the following prerequisites:

    -   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

    -   Activate Cloud Integration capability. See, [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?version=CLOUD).

    -   Activate Edge Integration Cell runtime. See, [Activate Edge Integration Cell](https://help.sap.com/docs/integration-suite/sap-integration-suite/activate-edge-integration-cell?version=CLOUD&q=Activate+Edge+Inte)





<a name="loio914f57e52c8945f5b3ef97a79548aeec__context_b4x_hdk_dgc"/>

## Context

You can create an API artifact by providing the target backend endpoint URL directly, importing an API Specification file, or uploading an API bundle. These options help you quickly create and configure APIs based on existing backend services or predefined API definitions.

When you use the endpoint-based approach, you provide the target URL of your backend service, for example, `https://backend.mycompany.com/service`. API Management uses this URL to route incoming API requests to the backend service and acts as a gateway between API consumers and the underlying service. You deploy the API on a virtual host, which serves as the public-facing entry point and defines the hostname and base path through which consumers access the API. For example, a backend service hosted at https://backend.mycompany.com/service can be exposed externally as `https://api.example.com/v1/service`. This abstraction helps protect internal endpoints while improving security and architectural flexibility.

The specification-driven approach allows you to quickly create an API artifact by importing an existing API specification or API bundle. This method is useful when you want to reuse an existing API definition or move an API artifact between environments, such as from development to production. For example, you can create an API artifact in a development environment, download it in `.zip` format, and then import it into the production environment to recreate or deploy the same API artifact. Supported import file formats include `.yaml` and `.edmx`.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Add API* dialog opens.

5.  Select the *Runtime Profile* based on your deployment requirements:

    **Integration Cell** for SAP-managed cloud deployments, or **Edge Integration Cell** for customer-managed private cloud and on-premise deployments.

6.  Select *URL or Specification* as the source type and choose *Next*.

7.  In the *Provide API Details* step, choose either *Create* or *Upload* and provide the API details:

    > ### Note:  
    > After filling in the API details in the *Create API* dialog \(name, ID, URL, base path, etc.\), you can generate an OpenAPI specification using AI assistance. To enable this feature, make sure the *OpenAPI Specification Generator* is activated in *Settings* \> *Artificial Intelligence*. Please note that this feature is accessible only with the Premium and Enhanced editions. For detailed guidance and best practices for generating OpenAPI specifications with AI assistance, see [Generate OpenAPI Specification with AI Assistance](generate-openapi-specification-with-ai-assistance-5ec68db.md).
    > 
    > Once activated, the *Next* button will appear instead of *Add*, allowing you to go to the page where you can describe your API and generate the OpenAPI specification automatically. This helps streamline the specification process, ensures consistency, and applies best practices for request/response schemas, CRUD operations, and security policies.

    -   *Create*: Lets you create a new API artifact by manually by entering the following API details:

        **API Details**


        <table>
        <tr>
        <th valign="top">

        API Details
        
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
        
        Enter an intuitive name. The name must start with a letter or underscore \(\_\), and may include letters, numbers, spaces, periods \(.\), or hyphens \(-\). It must not end with a period \(.\).
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ID
        
        </td>
        <td valign="top">
        
        APIs are identified by their IDs on the home screen. You can use space and special characters in an ID.Provide an intuitive name in lowercase. Avoid using space, special characters, and forward slash \(/\).
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        The HTTPS endpoint URL of the service. For example, https://<host\>:<port\>/SFlight..

        > ### Note:  
        > In a REST API, it is recommended not to include query parameters in the URL field. For example, the URL should be in the format `https://abc.org/anything` instead of `https://abc.org/anything?$format=json`. Including query parameters in the URL can cause the validation of the artifact to fail during deployment.
        > 
        > If you need to use query parameters, it is best to append them during the execution of the API rather than including them in the URL field.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Service Type
        
        </td>
        <td valign="top">
        
        API artifacts can be exposed as REST, ODATA, and SOAP.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        API Base Path
        
        </td>
        <td valign="top">
        
        Enter the path prefix for the API. For example, `v1/SFlight`.

        > ### Note:  
        > The base path shouldn't be left empty or set to only "/".


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        API State
        
        </td>
        <td valign="top">
        
        API state is used only for demarcation and not used to govern the lifecycle of the API. Choose Alpha if the version of an API is used for exploratory purposes, Beta if the API isn’t meant for productive use, and Active if the API is meant for productive use.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        API Version
        
        </td>
        <td valign="top">
        
        Add a version if you want to improve, upgrade, or customize the functional behavior of an existing API artifact. Versioning allows the creation and management of multiple concurrent versions of an API. See, [API Artifact Versioning](api-artifact-versioning-3f2e06b.md).
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Runtime Profile
        
        </td>
        <td valign="top">
        
        The runtime node on which the API artifact will be deployed.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Virtual Host
        
        </td>
        <td valign="top">
        
        You can view the *Virtual Host URL* for the selected runtime profile from this page. The virtual host defines the public-facing hostname and base path through which your API is exposed.

        For example, even if your backend service is hosted at https://internal.services.local/orders, you can expose it externally as `https://api.yourdomain.com/v1/orders` using a virtual host.

        This helps in proxification of the internal URL, improving security and allowing for more flexible deployment configurations. See, [Configuring Additional Virtual Host](configuring-additional-virtual-host-26c7416.md).
        
        </td>
        </tr>
        </table>
        
        After you provide the API details, the subsequent steps depend on whether the *OpenAPI Specification Generator* is enabled in *Settings* \> *Artificial Intelligence*

        > ### Note:  
        > AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).

        > ### Note:  
        > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

    -   *Upload*: Lets you create the API artifact by importing an existing API definition or an API bundle. You can upload supported file types such as `.json`, `.yaml`, `.edmx`, and `.zip`. Depending on your selection, you can either use a configured *Destination* or specify a target *URL* directly for the backend service.

        > ### Note:  
        > For the **Edge Integration Cell** runtime profile, only the **URL** option is currently supported.

        > ### Note:  
        > If you upload a .zip bundle, the service type specified in the bundle is automatically populated in the *Service Type* field and cannot be edited.

        When the *Runtime Profile* is set to *Integration Cell*, you can choose one of the following target configuration options:

        -   *Destination*: Use this option when you want to connect through a configured destination. This approach is recommended when backend connectivity, authentication, or endpoint configuration is managed centrally using destinations.

            Provide the following details:

            -   **Target** – Select the configured destination.
            -   **Relative URL** – Specify the relative path that should be appended to the destination URL.

        -   *URL*: Use this option when you want to directly specify the backend service endpoint.

            Provide the following details:

            -   **URL** – Enter the target backend service URL.
            -   **ID** – Enter a unique identifier for the API artifact.



    All other API details remain the same for both options. To learn more about the common fields, refer to the [Table 1](create-an-api-artifact-using-a-target-url-or-an-openapi-specification-914f57e.md#loio914f57e52c8945f5b3ef97a79548aeec__table_checkID) table.

    > ### Note:  
    > If you upload a reusable API, only the relevant fields are displayed based on the uploaded API definition or bundle. Fields such as *File Name*, *Name*, *ID*, *API Base Path*, *API Version*, and *Runtime Profile* are automatically populated from the uploaded reusable API. You can review and modify these values before creating the API artifact.

8.  Once the required details are filled, choose one of the following options: .

    -   *Add*: Creates the API artifact, which is then displayed under the *Artifacts* tab of the integration package.
    -   *Add and Open in API Designer*: Creates the API artifact and opens it in API Designer for further configuration and editing.
    -   *Previous*: Returns to the previous step to modify the selected method or runtime profile.
    -   *Cancel*: Closes the wizard without creating the API artifact.

    After adding the API artifact, you can further configure and manage it as needed. For information, see [Govern and Manage an API Artifact](govern-and-manage-an-api-artifact-79aee17.md).


