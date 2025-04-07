<!-- loiofdf5373c67c64fab8e5b285a61806fd9 -->

# Configure APIs

The *Configure APIs* menu allows you to perform two tasks: creating and updating API proxies, and registering APIs that are not currently proxified. The text is too short to provide a summary.



<a name="loiofdf5373c67c64fab8e5b285a61806fd9__section_yf4_m1k_g1c"/>

## Registering an Externally-Managed API

Unproxified API endpoints, also known as unmanaged or externally managed APIs, are endpoints that do not require an API proxy and are not part of the strictly managed APIs. Registering an unproxified API into the catalog of managed APIs can have several benefits, as it allows for further exposure to developers. To register an unproxified API, an API specification is required. API specifications are based on the OpenAPI \(also known as Swagger\) standard and can be imported as a file or designed using the API Designer tool. For more information, see [Adding Externally Managed APIs](50-Development/adding-externally-managed-apis-523ff94.md).



<a name="loiofdf5373c67c64fab8e5b285a61806fd9__section_j3f_wjy_g1c"/>

## Creating an API Proxy

API proxies are the fundamental components of the API Management feature in SAP Integration Suite. An API proxy acts as a protective layer in front of your service API \(the target endpoint\), offering consumers of your APIs a standardized and properly formatted URL. Additionally, it provides security measures and mediation policies to further safeguard the API. For more information, see [Build API Proxies](50-Development/build-api-proxies-74c042b.md).

There are two ways to create an API proxy for an existing system or service API:

-   You can directly provide the complete service URL when creating the API proxy. For more information, see [Create an API Proxy by Providing a Direct Target Endpoint URL](50-Development/create-an-api-proxy-by-providing-a-direct-target-endpoint-url-d0f5087.md).

-   Alternatively, you can first set up a system descriptor \(host, port\) as an API provider and then provide the service path when creating the API proxy. For more information, see [Create an API Proxy by Referring to an API Provider System](50-Development/create-an-api-proxy-by-referring-to-an-api-provider-system-84628b9.md)


You can create an API proxy based on an existing API proxy. By creating a new API proxy based on an existing one, you can add or modify features to meet your specific requirements. For more information, see[Create an API Proxy Based on an Existing API Proxy](50-Development/create-an-api-proxy-based-on-an-existing-api-proxy-54831ca.md).

If you want to create API proxies for on-premise systems like SAP S/4HANA or ECC, you need to define an API provider first and use it when creating API proxies for its services.

For all other URLs, whether they are cloud-based or "Internet" URLs, API administrators have the option to directly provide the URL during the API creation process or define an API provider.



<a name="loiofdf5373c67c64fab8e5b285a61806fd9__section_rpc_gs2_h1c"/>

## Creating an API Proxy by Providing a Cloud-based URL

Creating an API proxy using a cloud-based URL can enhance the security, scalability, performance, and monitoring capabilities of your API, providing a better experience for both developers and end-users. For more information, see[Create an API Proxy by Providing a Direct Target Endpoint URL](50-Development/create-an-api-proxy-by-providing-a-direct-target-endpoint-url-d0f5087.md).



<a name="loiofdf5373c67c64fab8e5b285a61806fd9__section_yw2_2z2_h1c"/>

## Creating an API Proxy to an on-premise SAP \(OData\) System

The creation of an API Proxy for an on-premise system service involves three key steps:

1.  Setting up a cloud connector to establish a connection between your account and the on-premise system.

2.  Creating a service instance of the API Management connectivity plan to enable the necessary connectivity.

3.  Creating an API provider of the on-premise type to facilitate the integration.


There are two different approaches to this process:

-   Creating an API proxy that authenticates users with principal propagation.

-   Creating an API proxy with transparent authentication.


These steps and variations allow for the effective implementation of an API proxy for an on-premise system service.



### Creating an API Proxy with principal propagation to an on-premise SAP \(OData\) system

The ability to create an API proxy for an on-premise SAP endpoint and to propagate the identity of the caller \(principal propagation\) to this on-premise system is an important feature of API Management SAP Integration Suite. To address this challenge, the following steps need to be taken:

1.  Set up a cloud connector from your account to the on-premise system, using either "X.509 certificate" or "certificate" as the principal type.

2.  Establish a service instance of the API Management connectivity plan. For detailed instructions, see [Accessing On-Premise Systems through API Management](accessing-on-premise-systems-through-api-management-2fc7a5b.md).

3.  Create an API provider of type *on-premise* and set the authentication to *Principal Propagation*. For more informtion, see [Create an API Provider](50-Development/create-an-api-provider-6b263e2.md).

4.  When creating the API proxy, make sure to use the created API provider and specify the path to the API service.




### Creating a transparent API proxy to an on-premise SAP \(OData\) system

Create an API proxy for an on-premise SAP endpoint without applying any authentication in the API proxy. This approach can be useful, for example, if the backend service expects the client to provide a user and password in the form of HTTP headers, which will be passed through the API proxy as-is.

To create an API proxy without authentication:

1.  Set up a cloud connector from your account to the on-premise system, using either "X.509 certificate" or "certificate" as the principal type.

2.  Establish a service instance of the API Management connectivity plan. For detailed instructions, see [Accessing On-Premise Systems through API Management](accessing-on-premise-systems-through-api-management-2fc7a5b.md).

3.  Create an API provider of type *on-premise* and set the authentication to *None*. For more informtion, see [Create an API Provider](50-Development/create-an-api-provider-6b263e2.md).

4.  When creating the API proxy, make sure to use the created API provider and specify the path to the API service.


