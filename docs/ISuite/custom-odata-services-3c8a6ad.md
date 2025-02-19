<!-- copy3c8a6adea9814c7383beb43f59c29197 -->

# Custom OData Services

In addition to connecting to SAP business systems, you can set up a custom datasource that supports OData protocol to enable Graph to communicate with your API service.

As an administrator of your OData API service, you need to configure the communication between Graph and your business system.



<a name="copy3c8a6adea9814c7383beb43f59c29197__section_llc_tnt_xxb"/>

## Setup Connectivity

Make sure your OData API service is publicly accessible. All the necessary setup should be considered for your custom API service, such as secure communication.



<a name="copy3c8a6adea9814c7383beb43f59c29197__section_dgp_wnt_xxb"/>

## Create Destinations

Create a destination to enable the communication between your business system and Graph. As the SAP BTP administrator, you need to create an HTTP destination to be able to make calls to OData APIs from Graph. The authentication type is based on your setup for that specific business system.

You can create destinations to your API service using BasicAuthentication, or even using NoAuthentication for public services \(mainly for testing purposes and not recommended for production\).

Destinations to services that require special HTTP headers can be defined with additional URL.headers. Use XXX properties for this purpose. For more information, see [HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/http-destinations?version=Cloud).

