<!-- loio8962643388fc4df6b7a165baa14475d9 -->

# API Proxy

An API is exposed in API Management as an API proxy. An API proxy is a discrete representation of an API. It is implemented as a set of configuration files, policies, and code snippets that rely on the resource information provided by API Management.

The API proxy decouples an API from any backend changes. This provides flexibility to application developers to continue calling the same API.

**Supported Service Types** 

Broadly API Proxies can be exposed as REST, ODATA, and SOAP APIs. For example, a backend RESTful service can be exposed directly as REST AP. An ODATA service can be exposed either as an ODATA API or even a REST API. A SOAP service can be exposed as a pass-through SOAP API directly. The benefit of exposing a service as an ODATA API is that the exposed API will comply with ODATA-specific operations \(like metadata fetch, navigating through associations and so on\). You have the flexibility of exposing an ODATA service also as a RESTful API. But in doing so, you also need to ensure that the REST resource is mapped correctly to the ODATA resource. When you expose a SOAP service as a SOAP API, there is no strict notion of an API resource as SOAP services work directly on the endpoint. Every operation-type on the SOAP service is as per the WSDL contract and does not directly map to the exposed resource.

API proxies handle request and response messages as a processing pipeline. In an API proxy configuration, there are two types of endpoints: Proxy Endpoint and Target Endpoint.



## Proxy Endpoint

The proxy endpoint defines the settings for the inbound connections for an API proxy. When you configure a proxy endpoint, you define how the client applications should invoke the API proxy. The main purpose of this configuration object is to manage interactions with consumers of the API. An API proxy must contain a proxy endpoint.



## Target Endpoint

The Target endpoint defines the outbound connections for an API proxy. The main purpose of this object is to manage interactions to the actual backend service endpoint on behalf of consumer applications. An API proxy can contain zero or many target endpoints.

