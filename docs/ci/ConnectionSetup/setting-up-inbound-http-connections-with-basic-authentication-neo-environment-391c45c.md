<!-- loio391c45cfcd0f4435952ab085283b7f7d -->

# Setting Up Inbound HTTP Connections \(with Basic Authentication\), Neo Environment



## Context

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

> ### Note:  
> This option is **not** recommended for productive scenarios.

The following figure shows the components and the involved security artifacts:

![](images/CF_Basic_IdP_0046872.png)

The table provides an overview of the required digital keys and their purpose in the authentication process, and summarizes the required configuration steps. Note that when setting up secure communication of different systems, typically administrators associated with the different systems need to accomplish configuration tasks in a coordinated way and to exchange public keys.


<table>
<tr>
<th valign="top">

Security Artifact



</th>
<th valign="top">

Used to ...



</th>
<th valign="top">

Configuration Steps



</th>
</tr>
<tr>
<td valign="top">

Load balancer server root certificate



</td>
<td valign="top">

Make the sender trust the load balancer.



</td>
<td valign="top">

Sender administrator:

Get certificate using the Cloud Integration *Connectivity Test* \(pointing to endpoint address of integration flow\).



</td>
</tr>
<tr>
<td valign="top">

Load balancer server certificate \(including certificate chain\)



</td>
<td valign="top">

Qualify load balancer as trusted component \(for senders that like to connect to it\).



</td>
<td valign="top">

No action required as this artifact is maintained by the operator of the cloud infrastructure.



</td>
</tr>
</table>



## Procedure

1.  Configure the **sender system**.

    This detailed procedure depends on the type of sender system and will not be covered here.

    However, make sure to take care of the following:

    -   To enable the sender for this authentication option, a communication user has to be created for the sender system.

    -   The keystore of the sender needs to contain the load balancer server root certificate \(which identifies the certification authority that has signed the load balancer server certificate\).

        Only with such a setup, the sender \(client\) can trust the load balancer's server certificate and, that way, establish a trust relationship to the load balancer \(as required for HTTPS communication\).

    -   Make sure that the message sent from the sender to the tenant contains this user in the message header.


2.  Authorize the communication user of the sender system user to process messages on the runtime node.

    You perform user and authorization management using SAP BTP Cockpit. You have the following options:

    -   Assign to the user the role `ESBMessaging.send` \(predefined by SAP to define permission to process messages on the runtime node\)

    -   Define a custom role for the runtime node.


3.  Configure the related integration flow.

    To open the design tool for integration flows, open a browser and enter the *Web UI URL* you have received from SAP in the mail that informs you that your tenant has been provided.

    To create and design integration flows, go to the *Design* tab.

    1.  Create a sender channel \(with adapter type that supports this authentication option\) and click the connection for the associated sender adapter.

    2.  As *Authorization* choose *User Role* and specify the role \(either keep the role name *ESBmessaging.send* pre-entered by default in the *User Role* field, or enter a custom role \(in case it is available\).

    3.  After you have finished configuring the integration flow \(including the processing steps for your scenario\), deploy the integration flow on the tenant.



**Related Information**  


[Developing Integration Content with SAP Cloud Integration](../Development/developing-integration-content-with-sap-cloud-integration-e6b43b4.md "You can use SAP Cloud Integration to access and design integration content.")

[Defining Permissions for Senders to Process Messages on a Runtime Node](../Operations/defining-permissions-for-senders-to-process-messages-on-a-runtime-node-24585cc.md "")

