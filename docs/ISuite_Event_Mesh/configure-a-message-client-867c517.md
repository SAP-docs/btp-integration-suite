<!-- loio867c517256d74cc2ad9eab3dd22eb916 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configure A Message Client

Understand how to create a message client to communicate with the message broker.



<a name="loio867c517256d74cc2ad9eab3dd22eb916__prereq_iq3_4nd_yfc"/>

## Prerequisites

-   You have a subaccount on the SAP BTP cockpit. See [Create a Subaccount in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/05280a123d3044ae97457a25b3013918.html).
-   You’ve created a space within the subaccount in which Cloud Foundry is enabled. See [Managing Orgs and Spaces Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c4c25cc63ac845779f76202360f98694.html).
-   You've subscribed to the SAP Integration Suite, and activated the Event Mesh capability.
-   You've initiated the message broker. See [Initiating the Message Broker](https://help.sap.com/docs/integration-suite/isuite-event-mesh/initiating-message-broker?version=CLOUD)
-   The entitlements for the message-client plan have been added to your subaccount in the SAP BTP cockpit.



## Context

The service instance *Event Mesh Message Client* on the SAP BTP cockpit provides access to the message client of Event Mesh's capability.

By creating a service instance on the SAP BTP cockpit, you trigger the creation of a message client and bind it to the Event Mesh capability. By binding the service instance, you enable the automatic delivery of credentials needed to access the service instance from the Event Mesh capability. Later, all the events publishing and consuming applications are authenticated via OAuth client credentials for all technical communications.

Configuring a message client is a two-step process. First, you create a service instance and then create a binding to the Event Mesh capability.



## Procedure

Create a service instance:

1.  In the SAP BTP cockpit, in your subaccount, from the left panel, navigate to *Services*, then choose *Instances and Subscriptions* \> *Create*.

2.  In the *New Instance or Subscription* dialog box, select the *SAP Integration Suite, Event Mesh* service.

3.  Choose the *message-client* plan, and then choose *Next*

4.  Provide a name for the instance.

5.  Choose *Next*

6.  Specify parameters using a JSON file. You can provide additional parameters such as the namespace and connection rules for a message client. Follow the [Service Descriptor Syntax](service-descriptor-syntax-b70eaad.md).

    > ### Sample Code:  
    > ```
    > {
    >   "rules": {
    >     "topicRules": {
    >       "publishFilter": [
    >         "${namespace}/*"
    >       ],
    >       "subscribeFilter": [
    >         "${namespace}/*"
    >       ]
    >     },
    >     "queueRules": {
    >       "publishFilter": [
    >         "${namespace}/*"
    >       ],
    >       "subscribeFilter": [
    >         "${namespace}/*"
    >       ]
    >     }
    >   },
    >   "namespace": "sap/em/opshealthcheck",
    >   "resources": {
    >     "units": 10
    >   }
    > }
    > 
    > ```

    > ### Note:  
    > -   Refer to [Service Descriptor Syntax](service-descriptor-syntax-b70eaad.md) to understand the different parameters that you can provide in the example.
    > -   We recommend that you use the same value for `service instance name` and `emname`.
    > -   If you create a message client without a `namespace` it can observe, publish to, and consume from the queues of other clients. We recommend creating a `namespace` for each message client you create.

7.  Choose *Create*.

    A service instance with the name you provided is created under the section *Instances*.


Create a service binding:

8.  From the context menu of the created service instance, choose *Create Service Binding*.

9.  Provide a name for the service binding.

10. Choose *Create*.

    **Binding Credential Types**

    When you create a binding request without specifying parameters, the system uses the default credential type `binding-secret`. The resulting binding contains the following fields:

    -   `credential-type`: `binding-secret`
    -   `clientId`
    -   `clientSecret`

    **Creating an X.509 Certificate Binding**

    To create an X.509 certificate-based binding, include the following parameters in your request:

    ```
    {
        "credential-type": "x509",
        "x509": {
            "key-length": 4096,
            "validity": 90,
            "validity-type": "DAYS"
        }
    }
    
    ```

    You can adjust the `key-length` and `validity` values according to your security requirements.

    The resulting X.509 binding contains these fields instead of `clientId` and `clientSecret`:

    -   `credential-type`: `x509`
    -   `certificate`
    -   `key`

    A binding of the service instance is created to the Event Mesh capability.

    You can also view the message client in the SAP Integration Suite UI. Navigate to *Configure* \> *Event Mesh* to view all the associated message clients.

    > ### Remember:  
    > -   If you delete a message client, the associated webhook subscriptions are deleted, but the associated queues are not. You must manually delete each queue. You can do this by:
    > 
    >     -   Before deleting the message client, navigate to *Configure* \> *Event Mesh* \> *Overview* \> *Message Client* \> *Queues*. For each queue, choose<span class="SAP-icons-V5"></span> Actions and then choose :wastebasket: .
    >     -   After deleting the message client, navigate to*Configure* \> *Event Mesh* \> *Queues*. Search for the queue, and for each queue, choose<span class="SAP-icons-V5"></span> Actions and then choose :wastebasket: .
    > 
    > -   If you deactivate the Event Mesh capability in SAP Integration Suite, the associated message clients are not automatically deleted. You must delete the service instances created in BTP cockpit.




<a name="loio867c517256d74cc2ad9eab3dd22eb916__postreq_pgt_y1z_sdc"/>

## Next Steps

[Configure Event Mesh](configure-event-mesh-77e213c.md)

