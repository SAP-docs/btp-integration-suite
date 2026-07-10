<!-- loioa0b3712b550a466d859bf9dd0532cc1a -->

# External Callout for API Artifact

The **Request Reply** policy synchronously sends a request to an external service and waits for a response before continuing the execution of the policy model..

Use this policy when your API artifact needs to invoke a backend service, retrieve data, or perform an operation before processing can continue. The Request Reply policy acts as the connection between the policy model and a receiver adapter, which forwards the request to the configured target endpoint.

When you create an API artifact, a **Request Reply** policy is automatically added to the policy model and connected to the default receiver adapter based on the selected service type. For example:

-   **REST** → HTTP receiver adapter
-   **SOAP** → SOAP receiver adapter
-   **OData** → OData receiver adapter

> ### Note:  
> By default, a Request-Reply policy is applied when you create an API artifact. This step connects to the *Target Endpoint*using the adapter corresponding to the selected API type. The initial Request-Reply policy is mandatory and cannot be deleted. See, [Default Adapters for API Artifacts](default-adapters-for-api-artifacts-719d07c.md).
> 
> Here's an example on how it works:
> 
> -   The client sends a request to the HTTP endpoint with the necessary parameters.
> -   The target endpoint receives the request, performs the necessary operations \(e.g., database query\), and sends the response back.
> -   The client receives the response and processes the data accordingly \(e.g., displays user details\).

**How the Request Reply Policy Works**

-   The client sends a request to the API artifact.
-   The request passes through the configured policies in the policy model.
-   The Request Reply policy forwards the request to the connected receiver adapter.
-   The receiver adapter invokes the configured backend service.
-   The backend service returns a response to the Request Reply policy.
-   The policy model continues processing the response and returns it to the client.

> ### Note:  
> The Request Reply policy itself does not define the connection to the backend service. The connected receiver adapter, such as an HTTP, SOAP, or OData receiver adapter, determines how the request is sent to the target endpoint.

**Related Information**  


[Creating Additional Request Reply Policy for API Artifact](creating-additional-request-reply-policy-for-api-artifact-f08b086.md "If you are using Edge Integration Cell or Integration Cell as your runtime profile, you can add an additional request reply policy to an API artifact to call an external HTTP(S) endpoint.")

