<!-- loioac794e455e4e446a82bb296fb4d48f4f -->

# Managing API Endpoints

The primary purpose of API Management is to manage your API endpoints.

There are two categories of API endpoints:

-   Those that you explicitly want to “proxify” by routing API calls through an API proxy \(referred to as "proxified" endpoints\)

-   Those that should be registered in the list of governed APIs but not proxified \(referred to as "unmanaged APIs" or "externally managed APIs"\)


Both proxified and unproxified API endpoints can be published to developers.



<a name="loioac794e455e4e446a82bb296fb4d48f4f__section_oqx_hbc_g1c"/>

## API Proxies

You proxify your APIs to add an extra layer of security by filtering and validating requests before they reach the API. They can also implement authentication and authorization mechanisms to control access to the API. For more information, see [API Proxy](50-Development/api-proxy-8962643.md).



### Policies

When it comes to API proxies, policies are a set of rules and configurations that are applied to API proxies to control their behavior. It is used to enforce security measures, perform data transformations, apply rate limiting, logging, caching, and more. They provide a way to customize and control the behavior of the API proxy. For more information, see [Policies](50-Development/policies-7e4f3e5.md).



### API Provider

An API provider describes a specific host to whose API services you want to provide access. You specify the host details and any further details that are necessary to establish the connection, for example, proxy settings. This is particularly useful when create API proxies to on-premise \(backend\) OData based systems. See Create an API Provider. For more information, see [API Providers](50-Development/api-providers-42e13b2.md).



<a name="loioac794e455e4e446a82bb296fb4d48f4f__section_wgs_3bc_g1c"/>

## Externally-managed APIs

Unmanaged or externally managed APIs, are endpoints that do not require an API proxy and are not part of the strictly managed APIs. These endpoints may already be managed by another API Gateway or API Management solution, such as one offered by a hyperscaler. Registering such an API into the catalog of managed APIs can be advantageous as it allows developers to easily access and utilize them. However, it's important to note that unproxified API endpoints are not managed or monitored, and they do not have rate plans assigned to them. For more information, see [Externally Managed APIs](50-Development/externally-managed-apis-848015d.md).



<a name="loioac794e455e4e446a82bb296fb4d48f4f__section_gpj_jbc_g1c"/>

## API Artifacts on Edge Integration Cell

The Edge Integration Cell introduces a new type of proxified integration flow, referred to as an API artifact. The API artifacts allowsusers to easily add and configure policies and integration flow steps in a unified manner using the Integration Flow Editor. This type of integration flow conveniently embeds the policies of an API proxy, which can be specified during the design of the integration flow. For more information, see [API Development](50-Development/api-development-94957bc.md).

