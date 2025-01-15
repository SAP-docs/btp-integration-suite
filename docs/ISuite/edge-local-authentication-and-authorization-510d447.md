<!-- loio510d447eef554e188b7577c902809416 -->

# Edge Local Authentication and Authorization

Edge Local Authentication and Authorization enables operations of integration flows and API proxies without relying on SAP Business Technology Platform \(SAP BTP\) for authentication and authorization in real time.

Edge Local Authentication and Authorization provides inbound local authentication and authorization for integration flow scenarios and API proxies, removing the real-time dependency on SAP Business Technology Platform. It supports offline authentication and authorization without SAP BTP dependency for client certificate authentication during integration flow processing, and API artifacts invocations.

> ### Note:  
> Edge Local Authentication and Authorization takes the certificate pinning configuration into account. However, disabling pinning still allows both current and previously used certificates \(with older issue dates\) to authenticate successfully. To fully revoke a previous certificate, delete the old service key containing the certificate and create a new one with only the updated certificate. For more information, see [Creating Service Instance and Service Key for Inbound Authentication](40-RemoteSystems/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md).



<a name="loio510d447eef554e188b7577c902809416__section_cys_bzt_zbc"/>

## Operations

Edge Local Authentication and Authorization is designed to operate during periods of temporary connectivity loss to SAP BTP. It operates seamlessly by using real-time service instance and service key data from SAP BTP, and doesn't require additional configuration.

Changes made to service instances and service keys in SAP BTP \(such as *Create*, *Modify*, or *Delete*\) are synchronized to the Edge Runtime Location. This process usually takes a few minutes, but in some cases, for example when there are connectivity issues, it can take up to 170 minutes.

> ### Note:  
> Edge Local Authentication and Authorization doesn't work for Integration flows and API Artifacts running on Edge Integration Cell for service keys of type *Certificate* created before May 17, 2024 \(release 2404\). To resolve this issue, please regenerate those service keys. For more information, see [3472645](https://me.sap.com/notes/3472645).

> ### Caution:  
> During connectivity loss, changes made to service instances and service keys in SAP BTP can't be synchronized to the Edge Runtime Location. Therefore, if you delete a service key or modify/delete a service instance to offboard a partner, the partner can still operate integration flows and API proxies until the changes synchronize to the Edge Runtime Location.

**Related Information**  


[Fix Edge Local Authentication and Authorization Issues](fix-edge-local-authentication-and-authorization-issues-4cddfbe.md "Check and fix issues related to local authentication and authorization.")

