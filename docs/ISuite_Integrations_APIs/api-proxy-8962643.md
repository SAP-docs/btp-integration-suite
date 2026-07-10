<!-- loio8962643388fc4df6b7a165baa14475d9 -->

# API Proxy

An API is exposed in SAP Integration Suite as an API proxy. An API proxy is a discrete representation of an API. It is implemented as a set of configuration files, policies, and code snippets that rely on the resource information provided by Integration Suite.

The API proxy decouples an API from any backend changes. This provides flexibility to application developers to continue calling the same API.

API proxies enforces the following:

-   **Security**: API proxies can enforce authentication and authorization mechanisms, ensuring that only authorized clients can access the API. They can also implement rate limiting, throttling, and other security measures to protect the backend services from malicious attacks.

-   **Scalability**: API proxies can handle the scaling of backend services by distributing incoming requests across multiple instances. They can also cache responses and reduce the load on backend services, improving overall performance and scalability.

-   **Flexibility**: API proxies can modify or transform requests and responses, allowing clients to interact with the API in a standardized way. They can add or remove headers, modify payloads, or even aggregate data from multiple backend services into a single response.

-   **Monitoring and analytics**: API proxies can collect and analyze data about incoming requests and responses, providing insights into API usage, performance, and potential issues. This information can be used to optimize the API and improve the overall developer experience.

-   **Revisioning and backward compatibility**: API proxies can handle versioning of the API, allowing clients to use different versions of the API without impacting the backend services. This enables developers to introduce changes and updates to the API while ensuring backward compatibility for existing clients.


**Supported Service Types** 

Broadly API Proxies can be exposed as REST, ODATA, and SOAP APIs. For example, a backend RESTful service can be exposed directly as REST AP. An ODATA service can be exposed either as an ODATA API or even a REST API. A SOAP service can be exposed as a pass-through SOAP API directly. The benefit of exposing a service as an ODATA API is that the exposed API will comply with ODATA-specific operations \(like metadata fetch, navigating through associations and so on\). You have the flexibility of exposing an ODATA service also as a RESTful API. But in doing so, you also need to ensure that the REST resource is mapped correctly to the ODATA resource. When you expose a SOAP service as a SOAP API, there is no strict notion of an API resource as SOAP services work directly on the endpoint. Every operation-type on the SOAP service is as per the WSDL contract and does not directly map to the exposed resource.

API proxies handle request and response messages as a processing pipeline. In an API proxy configuration, there are two types of endpoints: Proxy Endpoint and Target Endpoint.



## Proxy Endpoint

The proxy endpoint defines the settings for the inbound connections for an API proxy. When you configure a proxy endpoint, you define how the client applications should invoke the API proxy. The main purpose of this configuration object is to manage interactions with consumers of the API. An API proxy must contain a proxy endpoint.



## Target Endpoint

The Target endpoint defines the outbound connections for an API proxy. The main purpose of this object is to manage interactions to the actual backend service endpoint on behalf of consumer applications. An API proxy can contain zero or many target endpoints.

**Related Information**  


[Different Methods of Creating an API Proxy](different-methods-of-creating-an-api-proxy-4ac0431.md "An API proxy is the data object that contains all the functionality to be executed when an external user wants to access the backend service.")

[Policies](policies-7e4f3e5.md "Policy definition and types of policies supported by SAP Integration Suite.")

[API Providers](api-providers-42e13b2.md "An API provider defines the connection details for services running on specific hosts whose details you want to access.")

