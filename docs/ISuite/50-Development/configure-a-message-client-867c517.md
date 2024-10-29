<!-- loio867c517256d74cc2ad9eab3dd22eb916 -->

# Configure A Message Client

Understand how to create a message client.



## Context

The service instance *SAP Integration Suite, Event Mesh* on the SAP BTP cockpit provides access to the message client of Event Mesh's capability.

By creating a service instance on the SAP BTP cockpit, you trigger the creation of a message client and bind it to the Event Mesh capability. By binding the service instance, you enable the automatic delivery of credentials needed to access the service instance from the Event Mesh capability. Later, all the events publishing and consuming applications are authenticated via OAuth client credentials for all technical commnications.

Configuring a message client is a two-step process. First, you create a service instance and then create a binding to the Event Mesh capability.



## Procedure

Create a service instance:

1.  In the SAP BTP cockpit, choose *Instances and Subscriptions* \> *Create*.

2.  Select the service plan *SAP Integration Suite, Event Mesh*.

3.  Provide a name for the instance.

4.  Choose *Create*.

    A service instance with the name you provided is created under the section *Instances*.


Create a service binding:

5.  From the context menu of the created service instance, choose *Create Service Binding*.

6.  Provide a name for the service binding.

7.  Choose *Create*.

    A binding of the service instance is created to the Event Mesh capability.

    You can also view the message client in the Integration Suite UI. Navigate to *Configure* \> *Event Mesh* to view all the associated message clients.


