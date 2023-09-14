<!-- loio6874eb0061e74a3aa480abf52a5e86e0 -->

# Subscribing to SAP Integration Advisor



<a name="loio6874eb0061e74a3aa480abf52a5e86e0__prereq_qg4_1vd_dmb"/>

## Prerequisites

You have obtained a license for SAP Cloud Integration Enterprise Edition.



## Context

SAP Integration Advisor is available with the Standard edition and Premium edition of Integration Suite. However, you need to provision the application from SAP BTP cockpit. This procedure guides you on subscribing to SAP Integration Advisor application.



## Procedure

1.  Login to your SAP BTP cockpit and navigate to your subaccount in Cloud Foundry Environment.

2.  In the navigation area of the subaccount, choose *Subscriptions*.

    The following information is displayed for the business applications to which your global account is entitled in the Cloud Foundry environment:

    -   The name and short description of the application.

    -   *Subscribed / Not subscribed*: The status of the application, indicating whether the subscription is active in your subaccount in the current region.

3.  Choose the *Integration Suite* tile to open its *Overview* page.

4.  Choose *Subscribe*. Wait for the subscription to complete and once done successfully, you will see the *Integration Suite* tile is shown as *Subscribed*.

    > ### Note:  
    > To login to the SAP Cloud Integration application, you have to assign the relevant roles first.

5.  Choose *Go to Application* to provision the tenant. If this option is not enabled, refer the chapter [Configuring User Access](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/sap.cp.integration.suite/en-US/2c6214a3228e4b4cba207f49fda92ed4.html) and assign the necessary role collection.

6.  In the resulting *Activate Capabilities* dialog, select the checkbox for *Implement Interfaces and Mapping* to activate Integration Advisor and choose *Next*.

7.  Set the necessary values in step 2 *Cloud Integration* and choose *Next*.

8.  Review the summary of the capability and choose *Finish*. This will activate Integration Advisor in your tenant.

    > ### Note:  
    > You can also *Deactivate* the capability when you no longer need the service, but you will lose all the data uploaded and used in this application along with the deactivation.


