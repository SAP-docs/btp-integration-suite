<!-- loio0a383737f6cd4abfb3f1c58680747152 -->

# Update Service Instance that Contains Deprecated client\_x509 Grant Type

This information is relevant for you when you operate scenarios using Cloud Integration inbound authentication with client certificates and service instances with `client_x509` grant type.

The `client_x509` grant type will reach its end of life in January 2026. It will be replaced by the `client_credentials`grant type. Instances currently using `client_x509` must be updated to the new grant type. Instructions for updating the service instance are provided below.

> ### Caution:  
> If the `client_x509` grant type is configured for affected service instances, updates will fail, and new service keys cannot be created. To prevent these issues, make sure to update the grant type to `client_credentials`.



<a name="loio0a383737f6cd4abfb3f1c58680747152__section_osh_w33_rcc"/>

## Updating Affected Service Instances

To find out if a service instance is affected, perform the following steps:

1.  SAP BTP cockpit and select *Services* \> *Instances and Subscriptions* \> *.* 

2.  Select a service instance.

    > ### Note:  
    > Only service instances with service *Process Integration Runtime* are relevant.

3.  Select *View Parameters*.

    ![](images/grant-type-01_20fac43.png)

4.  In the popup, choose the *JSON* tab.

5.  If under *Grant-types* there is the entry *client\_x509*, this service instance is affected.

    ![](images/grant-type-02_0e87127.png)

6.  Replace the entry `client_x509` by `client_credentials`.

7.  Update instance.


See also: [Cloud Integration on CF - How to Setup Secure HTTP Inbound Connection with Client Certificates](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-on-cf-how-to-setup-secure-http-inbound-connection-with/ba-p/13393777) \(SAP Community blog\)

