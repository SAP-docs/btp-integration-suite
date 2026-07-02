<!-- loio8315ca7cd37f4ac3b9548753be025983 -->

# Creating Channels Using a Service Key



## Prerequisites

-   You have the *Enterprise Event Enablement* administrator role.
-   You have a subaccount in SAP BTP, Cloud Foundry environment. For more information, refer to [Getting Started with a Customer Account: Workflow in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/56440ab2380041e092c29baf2893ef97.html).
-   You have created a service instance for Event Mesh in SAP Integration Suite. See[Configure a Message Client](https://help.sap.com/docs/integration-suite/sap-integration-suite/configure-message-client?version=CLOUD).

    > ### Note:  
    > You can also create a channel manually without a service key. This procedure is described in [Creating and Managing Channels](creating-and-managing-channels-1e8d242.md).




## Context

The service key, created in Event Mesh in SAP Integration Suite, contains all information required to establish a connection. This information is extracted and used to create a destination and an OAuth 2.0 configuration. By using the service key while creating a channel, the administrator saves manual steps on the SAP S/4HANA system. These required configurations are created automatically by the enterprise event enablement framework.

If there is already a channel you want to use, skip the steps below and proceed with the configuration of the outbound bindings.



## Procedure

1.  Execute transaction `/IWXBE/CONFIG`.

2.  Press the *via Service Key* \(Create new channel via Service\) button. Select *SAP Event Mesh* from the dropdown menu.

3.  Enter the following.

    -   Channel
    -   Description
    -   Destination \(Enter your preferred `SM59` destination name.\)
    -   OAuth 2.0 Configuration \(Enter your preferred name. The name must not have been used yet.\)
    -   Daemon User

        > ### Note:  
        > The daemon user denotes the user under which the daemon sessions are running. The daemon sessions are responsible for keeping the connection open and for processing the events. You can use the role `SAP_IWXBE_RT_XBE_DAEMON`, which has all the required authorizations.


4.  Enter the service key and click *Save*.

    > ### Note:  
    > **Optional:** You have to maintain proxy options for the SM59 destination and the OAuth 2.0 configuration manually afterwards, as described in [Creating SM59 Destination](creating-sm59-destination-5c684ae.md) and [Configuring OAuth 2.0 Account Client](configuring-oauth-2-0-account-client-d445b27.md).

5.  Choose *Active <-\> Deactivate* to activate or deactivate the channel.

    The events are sent only if the channel is active.

6.  Choose *Check connection* to perform a connection test.

    If the connection test fails for an active channel, the corresponding error message is displayed. The same applies for an inactive channel.




## Results

Your newly created channel is listed in the channel list.



## Next Steps

-   If the destination or the OAuth 2.0 Configuration name is not available, random names will be generated.

-   After saving, you can still change optional parameters.


**Related Information**  


[Creating and Managing Channels](creating-and-managing-channels-1e8d242.md "")

[Managing Channels and Parameters](managing-channels-and-parameters-c09c2bf.md "A channel represents a single connection to a service instance of Event Mesh in SAP Integration Suite.")

