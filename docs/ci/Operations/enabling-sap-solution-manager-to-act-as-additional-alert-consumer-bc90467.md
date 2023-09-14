<!-- loiobc90467576554d82a8b297f7105c509a -->

# Enabling SAP Solution Manager to Act as Additional Alert Consumer

You can enable SAP Solution Manager to display alerts.



## Context

Currently, alerts are supported that are raised if no receiver can be determined during routing.

To set up this scenario, the SaaS administrator and the administrators of the involved SAP Solution Manager systems have to perform the following steps.

> ### Note:  
> For more information on the tasks of the administrator of the SAP Solution Manager systems, see the documentation for SAP Solution Manager.



## Procedure

1.  Provide the administrator of the SAP Solution Manager system with the tenant management node URL.

    The tenant management node URL is contained in the email that is sent out to the customer after the tenant provisioning process.

2.  Create a user that enables the SAP Solution Manager system to connect to the integration platform as a client.

3.  Assign the following role to this user: `IntegrationOperationServer.consumealerts`.

4.  Provide the administrator of the SAP Solution Manager system with this user.

5.  Make sure that the SAP Solution Manager system is registered as an alert consumer.

    To request this feature, create a ticket on component `LOD-HCI-PI-ET-OP`.




## Results

Once the connected SAP Solution Manager systems and tenants have been configured accordingly, alerts of the above-mentioned type are displayed in the Exception Management inbox of the involved SAP Solution Manager systems.

