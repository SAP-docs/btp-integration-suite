<!-- loio510d447eef554e188b7577c902809416 -->

# Edge Local Authentication and Authorization

Edge Local Authentication and Authorization enables operations of integration flows and API proxies without relying on SAP Business Technology Platform \(SAP BTP\) for authentication and authorization in real time.

Edge Local Authentication and Authorization provides inbound local authentication and authorization for integration flow scenarios and API proxies, removing the real-time dependency on SAP Business Technology Platform. It supports offline authentication and authorization without SAP BTP dependency for client certificate and basic authentication \(clientId and clientsecret\) during integration flow processing, and API artifacts invocations.



<a name="loio510d447eef554e188b7577c902809416__section_cys_bzt_zbc"/>

## Operations

Edge Local Authentication and Authorization is designed to operate during periods of temporary connectivity loss to SAP BTP. It operates seamlessly by using real-time service instance and service key data from SAP BTP, and doesn't require additional configuration.

Changes to service instances and service keys in SAP BTP \(such as *Create*, *Modify*, or *Delete*\) are synchronized to the Edge Runtime Location in a matter of minutes through event-based updates.  Additionally, every 170 minutes a snapshot synchronization job runs to ensure the consistency of the security material between cloud and Edge Integration Cell. This guarantees updates from cloud to the edge location.

> ### Caution:  
> During connectivity loss, changes made to service instances and service keys in SAP BTP can't be synchronized to the Edge Runtime Location. Therefore, if you delete a service key or modify/delete a service instance to offboard a partner, the partner can still operate integration flows and API proxies until the changes synchronize to the Edge Runtime Location.

**Related Information**  


[Fix Edge Local Authentication and Authorization Issues](fix-edge-local-authentication-and-authorization-issues-4cddfbe.md "Check and fix issues related to local authentication and authorization.")

