<!-- loio74465607b6684749aa6ad1eee270378d -->

# Configure Governance Settings

Configure and manage governance levels in Developer Hub to control developer access, product subscription permissions, and approval workflows.



<a name="loio74465607b6684749aa6ad1eee270378d__prereq_dls_sq3_dgc"/>

## Prerequisites

-   The *AuthGroup.API.Admin* role collection should be assigned to you.



## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage Governance Settings* and select the *Subscriptions* tab.

3.  Choose *Edit*.

4.  Select the appropriate approval process from the list below:

    -   *Auto Approval*: Subscriptions created and edited by developers are automatically approved by the system without requiring manual intervention.
    -   *Manage Approval Outside Developer Hub*: To create or modify subscriptions, developers must obtain approval outside of Developer Hub.

    > ### Note:  
    > As a Developer Hub administrator, keep the following in mind when modifying governance settings:
    > 
    > -   Any new subscription requests made after the changes will follow the updated governance settings.
    > -   If there are pending subscription approvals, you must either delete them or wait for their approval or rejection before modifying the governance settings.

5.  Choose *Save*, and then choose *Yes* in the confirmation dialog to apply the new governance settings to your subscriptions.

    > ### Note:  
    > As a Developer Hub administrator, when you set governance to *Manage Approval Outside Developer Hub*, the responsibility for handling subscription approvals shifts to the external application instead of being managed within Developer Hub.
    > 
    > In this setup, the customer subaccount administrator must implement the Service Provider Interface \(SPI\). See step 2 *Complete the Prerequisites* in [Setting Up External Governance](setting-up-external-governance-8b4f848.md).
    > 
    > Once the SPI implementation is completed, the subaccount administrator must configure a destination in the SAP BTP Cockpit with the SPI details. This destination enables Developer Hub to route subscription requests to the external service for approval. See, [Create a Destination for Approving and Rejecting Subscriptions](create-a-destination-for-approving-and-rejecting-subscriptions-71230dc.md).
    > 
    > Now, when a developer requests a subscription, Developer Hub triggers this interface to seek approval. The service can then approve or reject the request via an API.

    > ### Note:  
    > If there are any subscriptions pending approval for an application, you must either delete them or wait for their approval or rejection before changing the governance settings to *Auto Approval*.


