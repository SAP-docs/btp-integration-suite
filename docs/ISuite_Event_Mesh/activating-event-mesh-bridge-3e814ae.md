<!-- loio3e814ae4eca14f9ea6c786398fe1500b -->

# Activating Event Mesh Bridge

Activating the Event Mesh bridge to allow flow of events between Event Mesh capability on SAP Integration Suite to SAP Integration Suite, advanced event mesh.



<a name="loio3e814ae4eca14f9ea6c786398fe1500b__prereq_r4h_qxb_b2c"/>

## Prerequisites

-   You have an active Event Mesh capability on the SAP Integration Suite.
-   You have an active SAP Integration Suite, advanced event mesh subscription with at least one event broker active.
-   You have the Event Mesh Administrator or Event Mesh Developer role assigned to you.

You can watch a short video for the activation process here: 



## Procedure

1.  Log in to SAP Integration Suite.

2.  Navigate from the left panel to *Configure* \> *Event Mesh* \> *Bridge*.

3.  Choose *Create Bridge*.

4.  In the *Bridge to SAP Integration Suite, Advanced Event Mesh* wizard that opens, enter the following details:

    Under *Connect*


    <table>
    <tr>
    <th valign="top">

    Fields
    
    </th>
    <th valign="top">

    User Input
    
    </th>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    *Subscription Details*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Broker Host URL*
    
    </td>
    <td valign="top">
    
    The broker host URL for a broker on the SAP Integration Suite, advanced event mesh. You need to choose the ampq protocol. See[Finding Event Broker Service Connection Details](https://help.pubsub.em.services.cloud.sap/Cloud/cloud-configure-messaging-services.htm#finding-event-broker-service-connection-details).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Subaccount ID*
    
    </td>
    <td valign="top">
    
    The ID of the subaccount from which you've subscribed to SAP Integration Suite, advanced event mesh.
    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    *Authentication*

    > ### Note:  
    > You must configure an event broker service to use client certificate authentication. The public certificate \(MyRootCaCert.pem\) generated must be uploaded to the broker and the client certificate \(.pem\) and client key must be uploaded while configuring the bridge for authentication. See [Configuring an Event Broker Service to use Client Certificate Authentication](https://help.pubsub.em.services.cloud.sap/Cloud/ght_client_certs.htm).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Certificate
    
    </td>
    <td valign="top">
    
    The client certificate \(.pem\) obtained when the event broker in SAP Integration Suite, advanced event mesh is configured to use client certificate authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key
    
    </td>
    <td valign="top">
    
    The key obtained when the event broker in SAP Integration Suite, advanced event mesh is configured to use client certificate authentication.
    
    </td>
    </tr>
    </table>
    
5.  Choose *Test Connection* to check if with the provided credentials, Event mesh in SAP Integration Suite can successfully reach the SAP Integration Suite, advanced event mesh broker. If the connection is successful a status message *Connection Tested* is displayed.

6.  Under *Add Topics* add topics from the Event Mesh capability from which events and messages must be forwarded to SAP Integration Suite, advanced event mesh. Then choose *Review*.

7.  Review the details you've entered, and then choose *Finish*. Once the bridge is successfully created you see the status change to *Ready*.

    You can now forward messages from topics in the Event Mesh capability to SAP Integration Suite, advanced event mesh.

    > ### Note:  
    > If you want to persist the events on the SAP Integration Suite, advanced event mesh, create a queue, and subscribe to the topics added to the bridge.

8.  You can monitor the message rate for all the topics in the bridge by navigating to *Monitor* \> *Event Mesh* \> *Bridge*. You can also view the data for *Spool Size*, *Connections* and *Consumers*.


