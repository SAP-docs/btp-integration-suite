<!-- loioa74cddceacb34abb958e817c1f6782d2 -->

# Activating Enterprise Messaging

Activate SAP Event Mesh.



<a name="loioa74cddceacb34abb958e817c1f6782d2__prereq_lrc_w23_1gb"/>

## Prerequisites

> ### Note:  
> This procedure is only relevant when you use SAP Cloud Integration in the Neo and Cloud Foundry environment. JMS queues are included in SAP Integration Suite without the need for an additional license, except in Basic Edition \(where the feature is not supported\).

-   You must have purchased a minimum of 10 SKUs of SAP Event Mesh, in which five SKUs are consumed by Message Monitor and remaining five SKUs are used to activate JMS capabilities.

-   Contact your Account Executive for more details and for purchasing additional SKUs for SAP Event Mesh.




## Context

Use procedure to activate SAP Event Mesh for consuming JMS capabilities.



## Procedure

1.  The following steps are executed by a global account administrator:

    1.  Log into the accounts cockpit \(SAP BTP cockpit\).

    2.  Choose a global account.

    3.  Navigate to the *Subaccounts* tab.

    4.  Choose a subaccount.

    5.  Navigate to the *Entitlements* page.

    6.  Choose *Edit* to assign the required quota to a relevant subaccount in the *Event Mesh* section.

        > ### Note:  
        > The quota must be in 1:5 ratio, where one messaging queue on Cloud Integration corresponds to five quotas.

    7.  Saves the changes before modifying the quota for other subaccounts.


2.  Execute following steps to assign tenant administrator role:

    1.  Navigate to the *Subscription* tab.

    2.  Choose *Provision* application for *hcisvc* provider account.

    3.  Navigate to *Roles* tab.

    4.  Assign *AuthGroup.Administrator* authgroup to activate the application.


3.  The following steps are executed by Tenant Administrator to activate SAP Event Mesh and to modify the messaging queues:

    1.  Navigate to the account cockpit.

    2.  Navigate to *Services* tab.

    3.  Choose the *Process Integration* tile.

    4.  Choose the *Configure Process Integration* link under *Take Action*.

    5.  Choose the *Event Mesh* tab, and then choose *Activate* to start the service.

        > ### Note:  
        > -   **Google Chrome**, **Firefox** and **Safari** web browsers support provisioning application.
        > -   Choose *Deactivate* to deactivate the messaging service.


    Perform the steps here to increase the SAP Event Mesh queues for a specific subaccount.

    1.  Communicate with the Global Account Administrator to increase the quota to the relevant subaccount.

    2.  In the *Cloud Integration* application, select *Event Mesh* tab.

    3.  Choose *Edit* to increase the message queues.


    Perform the steps here to decrease the SAP Event Mesh queues for a specific subaccount.

    1.  Decrease the message queues by selecting *Event Mesh* and choose *Edit* to decrease the message queues.

        > ### Note:  
        > You must remove unused JMS queues from your tenant before decreasing the message queues. For more information, see [Managing Message Queues](managing-message-queues-cdcce24.md).

    2.  Communicate with the Global Account Administrator to decrease the quota to the relevant subaccount in the *Entitlements* page of the account cockpit.


    For more information, read the blog on [Activating and Managing Enterprise Messaging Capabilities](https://blogs.sap.com/2018/12/12/cloud-integration-activating-and-managing-enterprise-messaging-capabilities-as2-jms-and-xi-adapters/).


