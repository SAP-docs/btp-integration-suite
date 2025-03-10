<!-- loioc09c2bfcb47e4fbab21b543a91f2733c -->

# Managing Channels and Parameters

A channel represents a single connection to a service instance of Event Mesh in SAP Integration Suite.



<a name="loioc09c2bfcb47e4fbab21b543a91f2733c__prereq_s4b_dlk_52b"/>

## Prerequisites

-   You have the *Enterprise Event Enablement* administrator role.

-   You have created an `SM59` destination. For more information, refer to [Creating SM59 Destination](creating-sm59-destination-5c684ae.md).

-   You have configured an OAuth 2.0 client and you can provide the client ID, client secret and token endpoint of the `amqp10ws` protocol from the messaging client service instance. For more information, refer to [Configuring OAuth 2.0 Account Client](configuring-oauth-2-0-account-client-d445b27.md).




## Procedure

1.  To open the *Channel Configuration*, you have two options:

    -   Execute transaction `/IWXBE/CONFIG`.
    -   1.  Execute transaction `SPRO`.
2.  Press the button *Open SAP Reference IMG*.
3.  Navigate to *SAP Customizing Implementation Guide* \> *ABAP Platform* \> *Enterprise Event Enablement* \> *Administration* \> *Channel Connection Settings*.
4.  Execute *Manage Channels and Parameters*.


2.  Press the button with the tooltip *Create new channel*. Select *SAP Event Mesh* from the drop-down menu.

3.  Enter the *Channel* name.

    The allowed character set is \{A-Z,0-9,'\_'\}.

4.  Enter the *Destination*.

5.  In the *Topic Name* field, enter the namespace derived from the service key of the given instance. The name space is the identifier for events that originate from the same source.

6.  Enter the *Description*.

7.  Make the following entry in the *Parameters* section \(mandatory\):

    *OAuth 2.0 Configuration*: Choose the configuration name created in [Configuring OAuth 2.0 Account Client](configuring-oauth-2-0-account-client-d445b27.md).

8.  You can make entries in the *Optional Parameters* section. The following parameters are available:

    -   *Max Reconnect Attempts*: Define the number of attempts the enterprise event enablement framework executes to reestablish the connection if the connection is lost. If no value is entered or the entered value is 0, the framework tries to connect until a connection is established. If the connection is not established after reaching reconnect attempts, the channel is deactivated.

    -   *Quality of Service*: There are two values.


        <table>
        <tr>
        <th valign="top">

        At Most Once
        
        </th>
        <th valign="top">

        At Least Once
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        The message arrives at the Event Mesh in Integration Suite mostly once.
        
        </td>
        <td valign="top">
        
        QoS=1, this is the default value if no value is entered. This quality of service ensures that the message arrives at the Event Mesh in Integration Suite at least once.
        
        </td>
        </tr>
        </table>
        
    -   *Reconnect Waittime*: The enterprise event enablement framework waits for the mentioned time \(in seconds\) and then tries to reconnect. If the attempts fail, the framework increases the waittime until the maximum reconnect waittime \(1800 seconds\) is reached. The default reconnect waittime is 10 seconds. If the *Max Reconnect Attempts* value is not maintained, the framework tries to reconnect indefinitely until the connection is established. The channel will not be deactivated during this period.


    > ### Note:  
    > In case of connectivity problems, the respective channel is amended with status information visible in transaction `/IWXBE/CONFIG`. However, the channel remains in status *Active* until it is deactivated manually. All events in the queue stay persisted and new events arising at the time of connectivity issues are added to the queue.

9.  Press the *Save configuration* button or press [Enter\].

10. Choose *Active <-\> Deactivate* to activate or deactivate the channel.

    The events are sent only if the channel is active.

11. Choose *Check connection* to perform a connection test.

    If the connection test fails for an active channel, the corresponding error message is displayed. The same applies for an inactive channel.

12. Enable the use of a local proxy.

    By default, the enterprise event enablement framework does not support using a local proxy with a username and password for the channel destination. If you have maintained a local proxy in the channel destination, you will need to enable the local proxy use for your channel. To do so, proceed as follows:

    1.  Right-click on your channel to open the context menu.

    2.  Select *Enable for Local Proxy*.

    3.  Click *Enable* to confirm the pop-up.

        > ### Note:  
        > When you enable the local proxy use for your channel, the path prefix is removed from the channel destination and stored in the channel parameter *Path Prefix*. You can edit the path prefix manually or automatically:
        > 
        > -   Select your channel and press *Edit selected channel* to update the channel parameter.
        > -   Select your channel and press *Edit via Service Key* to update the path prefix with a corresponding service key.

        A success status message is displayed.



**Related Information**  


[Creating SM59 Destination](creating-sm59-destination-5c684ae.md "As an administrator, you create an SM59 destination to connect to the instance created for Event Mesh in SAP Integration Suite.")

[Configuring OAuth 2.0 Account Client](configuring-oauth-2-0-account-client-d445b27.md "You can access an external service provider's (SAP Integration Suite, SAP BTP, Cloud Foundry environment) OAuth 2.0 protected web service from an SAP S/4HANA, on-premise edition system. You need to provide credentials and an OAuth 2.0 client ID in the service provider.")

