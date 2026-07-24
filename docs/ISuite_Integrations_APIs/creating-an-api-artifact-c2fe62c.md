<!-- loioc2fe62c32855435f8b64e0fd10c8507e -->

# Creating an API Artifact

API artifacts can be created using different methods depending on your integration scenario and deployment requirements.

SAP Integration Suite provides different methods to create API artifacts depending on the selected runtime profile. API artifacts can be deployed either to the Edge Integration Cell runtime or the Integration Cell runtime based on your deployment requirements.

When creating an API artifact, first select the runtime profile and then choose one of the available creation methods. The available methods depend on the selected runtime profile.

> ### Note:  
> API artifact deployments are runtime-specific. After an API artifact is created on a specific runtime, you cannot change its runtime profile either by editing the artifact or during deployment. For example, an API artifact created for the Integration Cell runtime cannot later be deployed to the Edge Integration Cell runtime, and vice versa.
> 
> The only exception applies to API artifacts created with the Edge Integration Cell runtime profile, where you can select or change the target Edge Integration Cell node during editing or deployment.

-   *URL or Specification*:

    -   Specify the backend system’s HTTP endpoint URL directly when you already have a backend endpoint URL available. For more information, see [Create an API Artifact Using a Target URL or an OpenAPI Specification](create-an-api-artifact-using-a-target-url-or-an-openapi-specification-914f57e.md).
    -   Upload an OpenAPI specification when you already have an API definition in formats such as .json, yaml, edmx, or .zip. This is ideal when you want to build quickly from an OpenAPI specification file or an existing API artifact zip bundle.
    -   Create or modify an API definition using the OpenAPI Specification editor when you want to follow a specification-driven approach for API design and modeling. For more information, see [OpenAPI Specification Editors](openapi-specification-editors-2bf94eb.md).

-   *API Provider*: This method allows you to create an API artifact based on a configured business system or a SAP BTP destination:

    > ### Note:  
    > The API Provider method is currently available only for the Integration Cell runtime and is not supported for the Edge Integration Cell \(EIC\) runtime.

    -   *Discover a System*: Discover APIs and their metadata from pre-configured business systems \(e.g., SAP S/4HANA Cloud and SAP Gateway system\). For more information, see [Create an API Artifact Using a Discoverable System](create-an-api-artifact-using-a-discoverable-system-bd5c1f4.md).

        This option is best when:

        -   You have registered business systems.
        -   You want to leverage system-level integration and automated discovery.
        -   You need governance, security, and lifecycle management aligned with business systems.

    -   *Select a Destination*: Manually choose a destination from a list of SAP BTP destinations. See, [Create an API Artifact Using a Destination](create-an-api-artifact-using-a-destination-a0bdfd4.md).This method is useful when you have a pre-configured destinations on SAP BTP Cockpit.

-   *Reusable API Artifact*: The reusable API artifact feature enables you to encapsulate a standardized set of API policies and mediation logic—such as authentication, transformation, and validation—into modular units that can be centrally defined and invoked across multiple API artifacts. For more information, see [Create a Reusable API Artifact](create-a-reusable-api-artifact-0112688.md).

**Related Information**  


[Service Types for API Artifacts](service-types-for-api-artifacts-4dd2dde.md "Service types define the communication protocol for an API artifact and determine the default sender and receiver adapters and the generated policy model.")

