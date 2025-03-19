<!-- loio23df43b091a24c7ea38f81d4bb7f42b7 -->

# Creating an Event Mesh Message Client Using the Cloud Foundry Command Line Interface

If you want to work outside of the SAP BTP cockpit, you can create an Event Mesh service instance using the Cloud Foundry Command Line Interface \(cf CLI\).



<a name="loio23df43b091a24c7ea38f81d4bb7f42b7__prereq_vwz_gzk_xcb"/>

## Prerequisites

-   You have the administrator role for your global account.
-   You have access to a Cloud Foundry space.
-   You have added and activated the Event Mesh capability in SAP Integration Suite.



## Procedure

1.  Log on to the Cloud Foundry environment using the Command Line Interface.

    For more information, refer to [Log On to the Cloud Foundry Environment Using the Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7a37d66c2e7d401db4980db0cd74aa6b.html).

2.  Choose your organization and the Cloud Foundry space.

3.  Enter `cf marketplace` to verify the availability of the SAP Integration Suite, Event Mesh service in the service marketplace.

4.  Access an SAP Integration Suite, Event Mesh service instance using one of the following methods:

    -   To create a new service instance enter `cf create-service event-mesh-message-client message-client`. Follow the [Service Descriptor Syntax](service-descriptor-syntax-b70eaad.md).

        > ### Example:  
        > ```
        > cf create-service event-mesh-message-client message-client <yourmessageclientname> -c 
        > '{
        >     "emname": "<yourmessageclientname>",
        >     "namespace": "<yourorgname>/<yourmessageclientname>/<uniqueID>",
        >     "version": "1.1.0",
        >    
        >     "rules": {
        >         "queueRules": {
        >             "publishFilter": [
        >                 "${namespace}/*"
        >             ],
        >             "subscribeFilter": [
        >                 "${namespace}/*"
        >             ]
        >         },
        >         "topicRules": {
        >             "publishFilter": [
        >                 "${namespace}/*"
        >             ],
        >             "subscribeFilter": [
        >                 "${namespace}/*"
        >             ]
        >         }
        >     },
        >     "resources" : {
        >     "units" : "10"
        >   },
        >     "xs-security": { //optional//
        >         "oauth2-configuration": { 
        >         "credential-types": [
        >         "binding-secret",
        >         "x509"
        >       ]
        >     }
        >   }
        > }'
        > ```

        > ### Note:  
        > We recommend that you use the same value for `service instance name` and `emname`.

    -   If the application is deployed in the same space, you can use an existing service instance. Enter `cf services` to find existing instances of the service in your space. To update an existing service instance, enter `cf update-service <service-instance-name> -c 'service-descriptor.json'`

        > ### Example:  
        > ```
        > cf update-service <yourmessageclientname> -c 
        > '{
        >     "emname": "<yourmessageclientname>",
        >     "namespace": "<yourorgname>/<yourmessageclientname>/<uniqueID>",
        >     "version": "1.1.0",
        >    
        >     },
        >      "rules": {
        >         "queueRules": {
        >             "publishFilter": [
        >                 "${namespace}/*"
        >             ],
        >             "subscribeFilter": [
        >                 "${namespace}/*"
        >             ]
        >         },
        >         "topicRules": {
        >             "publishFilter": [
        >                 "${namespace}/*"
        >             ],
        >             "subscribeFilter": [
        >                 "${namespace}/*"
        >             ]
        >         }
        >     },
        >     "resources" : {
        >     "units" : "25"
        >   },
        >     "xs-security": { //optional//
        >         "oauth2-configuration": { 
        >         "credential-types": [
        >         "binding-secret",
        >         "x509"
        >       ]
        >     }
        >   }
        > }'
        > ```



