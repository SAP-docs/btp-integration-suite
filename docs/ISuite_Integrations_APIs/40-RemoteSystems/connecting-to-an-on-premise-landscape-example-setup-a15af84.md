<!-- loioa15af84aa3364f39b484c8ba2e2395b8 -->

# Connecting to an On-Premise Landscape \(Example Setup\)

To give you an idea of what the technical landscape behind a real life integration scenario looks like, here's an example for the SAP Cloud for Customer \(C4C\)-to-SAP ERP integration scenario. In this scenario, SAP’s own cloud solution SAP Cloud for Customer \(C4C\) is connected with an on-premise SAP Enterprise Resource Planning \(ERP\) system through Cloud Integration.

The following figure shows a typical setup of components:

![See following text for explanation.](images/Cloud_Technical_Landscape_SAP_Cloud_Connector_be397c6.png)

The left side of the figure covers the communication of Cloud Integration with the on-premise system in the customer landscape.

The setup contains components that all are connected by HTTPS communication. Typical adapters are the IDoc adapter for the connection between the on-premise system and Cloud Integration, and the SOAP adapter for the connection between SAP Cloud for Customer and Cloud Integration \(within the SAP Cloud\).

The lower path shows the connection from Cloud Integration to the on-premise system, which is located in the customer landscape. This is the outbound communication from the perspective of the integration platform, but is an inbound connection from the perspective of the customer landscape. Therefore, to protect the components in the customer landscape from remote calls from the Internet, a load balancer component is required – which is either a Web Dispatcher component or the SAP Cloud Connector.

The upper path shows the connection from the on-premise system to Cloud Integration. From the *perspective* of Cloud Integration, this is an inbound connection and, therefore, again a load balancer is required to protect the tenant that actually processes the message against remote calls. This is the BIG-IP load balancer, which is involved in all HTTPS inbound requests by default, and isn't shown in the figure for the sake of simplicity. Also, this component is preconfigured by SAP and doesn't require any further configuration for such a scenario.

