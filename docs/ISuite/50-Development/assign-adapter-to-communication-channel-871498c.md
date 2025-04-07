<!-- loio871498c12fe94b5395526bd5b55a9ca9 -->

# Assign Adapter to Communication Channel



## Prerequisites

You are editing an integration flow.



## Context

You must create a communication channel between SAP Cloud Integration and the sender/receiver system to facilitate communication between them.

> ### Note:  
> You must select on the participant’s name of sender and receiver elements, to access the header and property information. Also, you must drag and drop message flow over the participant's name, to assign communication channels.

You use this procedure if you want to change the adapter assigned to the communication channel in integration flows.



## Procedure

1.  Choose *Design* \> *Integrations and APIs*.

2.  Select the integration package that contains the integration flow or create a new one.

3.  Select the integration flow and choose *Edit*.

    > ### Note:  
    > In the case of OData API artifacts in integration packages, you have to edit the OData API artifact in order to edit the required integration flow.

4.  If you want to define a sender channel, choose *Sender*, select the arrow icon, and drag to *Start*.

    > ### Note:  
    > In the case of integration flows in OData API artifacts, you cannot change the OData sender adapter.

5.  If you want to define receiver channel, choose *End*, select the arrow icon, and drag to *Receiver*.

6.  In *Adapter Type* dialog, select the adapter you want to assign. Choose the message protocol that you want to use, if prompted.

7.  Save or deploy the changes after configuring the adapter and other integration flow elements.

    > ### Note:  
    > In the case of integration flows in OData API artifacts, you can save the integration flow and deploy the OData API.


