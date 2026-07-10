<!-- loiofe4b35a356004670ad4a2ad021fb29f1 -->

# Working with Service Interface

Service interfaces in SAP Integration Suite provide a platform- and language-independent way to define how systems communicate and what data they exchange with communication partners. They form the foundation for enabling cross-system communication via SAP Integration Suite.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

A service interface describes, at a conceptual level, the operations required for later implementation in an application system. This allows you to design integrations without being tied to a specific technology or programming language.

Depending on the role of the service interface, the following use cases apply:

-   *Inbound \(Provider Role\)*: Implement a service in an application system that can be invoked by external consumers.

-   *Outbound \(Consumer Role\)*: Call a service provided by an external system. In this case, you use an outbound service interface that corresponds to the inbound interface of the provider.

-   *Abstract*: Exchange messages with integration process. See [Define Integration Processes](define-integration-processes-d704f5c.md)


To implement these interfaces in the system, you must generate proxy. See [Generating ABAP Proxy](generating-abap-proxy-c6fcf31.md)

> ### Note:  
> Proxy generation is not supported for Abstract category of service interface.

