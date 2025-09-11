<!-- loioc2fe62c32855435f8b64e0fd10c8507e -->

# Create an API Artifact

Create an API artifact to securely expose backend services, apply consistent governance by adding security and traffic management policies, and gain better visibility and control over how your APIs are accessed and used.



<a name="loioc2fe62c32855435f8b64e0fd10c8507e__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).
-   Activate Cloud Integration capability. See, [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?version=CLOUD).

-   Activate API Management capability. See, [Activate and Configure the API Management Capability and Access Developer Hub](../activate-and-configure-the-api-management-capability-and-access-developer-hub-f6eb433.md).

-   Activate Edge Integration Cell runtime. See, [Activate Edge Integration Cell](https://help.sap.com/docs/integration-suite/sap-integration-suite/activate-edge-integration-cell?version=CLOUD&q=Activate+Edge+Inte)




## Context

SAP Integration Suite provides several methods to model API artifact to be deployed on Integration Cell. When creating an API artifact, you can choose from the following options:

-   *URL*: Create an API artifact by directly specifying the backend system’s HTTP endpoint URL. It’s a good option when:

    -   You have a specific endpoint URL available.


    For more information, see [Create an API Artifact Using a Target URL](create-an-api-artifact-using-a-target-url-914f57e.md).

-   *Import*: You can use the import method when you already have an API definition in formats such as .json, or .zip. This is ideal when:

    -   You want to build quickly from an OpenAPI specification file or an existing API artifact zip bundle.

    For more information, see [Create an API Artifact by Importing an OpenAPI Specification](create-an-api-artifact-by-importing-an-openapi-specification-fb99a7d.md).

-   *API Specification*: Handcraft an API artifact using the OpenAPI Specification editor.. This method is useful when:

    -   You want to define the API using a spec-driven approach.
    -   You have an OpenAPI specification that you want to paste into the OpenAPI Specification editor for review or modification..

    See, [Create an API Artifact Using an API Specification](create-an-api-artifact-using-an-api-specification-39c2b30.md).

-   *Reusable API Artifact*: The reusable API artifact feature enables you to encapsulate a standardized set of API policies and mediation logic—such as authentication, transformation, and validation—into modular units that can be centrally defined and invoked across multiple API artifacts. For more information, see [Create a Reusable API Artifact](create-a-reusable-api-artifact-0112688.md).

**Related Information**  


[Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md "Add a resource to refer to individual endpoints or services.")

[Copy an API Artifact](copy-an-api-artifact-820c9e8.md "You may want to create a copy of an existing API artifact with all its configurations and policies intact. This can be useful when you want to create a similar API artifact but with some modifications or variations.")

[Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md "You can define the behavior of an API by using policies.")

[Deploy an API Artifact](deploy-an-api-artifact-b70e7ec.md "After creating an API artifact, it is necessary to deploy it on the chosen runtime in order to make it executable and ready for use.")

[Externalize Parameter for API Artifact](externalize-parameter-for-api-artifact-ce0a468.md "You can use the externalization feature to define API policies and integration flows that can retrieve externalized configuration values during runtime. These parameters can be utilized later without modifying the standard API artifact.")

