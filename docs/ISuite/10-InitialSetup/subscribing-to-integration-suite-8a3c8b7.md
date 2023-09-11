<!-- loio8a3c8b7a6b1c4f249bb81d11644ef806 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Subscribing to Integration Suite

Subscribe to the Integration Suite application from the Subscriptions page in the SAP BTP cockpit.



<a name="loio8a3c8b7a6b1c4f249bb81d11644ef806__prereq_nbs_lth_vlb"/>

## Prerequisites

You’ve created a subaccount in your assigned global account using the SAP BTP cockpit and added the desired service plans for Integration Suite to the subaccount.



## Procedure

1.  In the navigation area of the subaccount, choose *Services* \> *Service Marketplace*.

2.  Search for *Integration Suite* and choose *Create* in the overview page.

3.  In the *New Instance or Subscription* dialog box, select the *Plan* and wait for the subscription to complete successfully.

    Check the status of the submission in subscriptions section on the *Instances and Subscriptions* page. If the subscription is successful, you notice the status of the *Integration Suite* shown as *Subscribed*.

4.  Navigate to the *Security* \> *Users*.

5.  Choose *Create* to add a new user.

    If the user details exist already in the subaccount, you can skip this step and continue from step 7.

6.  Enter the *User Name* and *E-Mail*, and choose *Create*.

7.  Choose the user and select <span class="SAP-icons"></span> under *Role Collections* section and choose *Assign Role Collection*.

    > ### Note:  
    > For Feature Set B customers, *Integration\_Provisioner* role is assigned automatically.

8.  In the resulting dialog box, select the checkbox of the role collection that you want to assign the user and choose *Assign Role Collection*. Choose the *Integration\_Provisioner* role.

    > ### Note:  
    > Clear your web browser cache and cookies before navigating to *Go to Application*.

9.  Choose *Go to Application* to launch the Integration Suite home page. For more information, see [Working with Integration Suite Home](../20-Working_with_SAP_Integration_Suite_Home/working-with-integration-suite-home-a53dce3.md).

    > ### Tip:  
    > To remain informed and receive timely notifications about planned and unplanned downtime, customer communications, and maintenance announcements, we recommend you maintain your contact information via a self-service tool named Cloud System Notification Subscriptions \(CSNS\). For more information, see [Cloud Availability Center & Cloud System Notification Subscriptions](https://support.sap.com/en/my-support/systems-installations/cac.html).


