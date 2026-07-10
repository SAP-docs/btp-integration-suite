<!-- loio462a4782db7b485b94ffce5b6fe22c31 -->

# Configure Externalized Parameters of an Integration Flow



## Context

Cloud Integration supports runtime-aware configuration, enabling you to configure integration flows across one or more runtime profiles in a centralized way. This capability is critical for organizations operating across different runtime profiles, as it allows you to:

-   Apply common configurations across multiple runtime profiles
-   Enable runtime-specific overrides without duplicating configurations
-   Ensure consistent behavior across runtimes with controlled flexibility
-   Eliminate redundant configuration efforts, hence saving time, operational cost, and maintenance effort
-   Reduce manual errors caused by repeated configurations

> ### Remember:  
> When you configure an externalized parameter, it is possible that you are allowed to provide a value for another dependent parameter which isn't externalized. In such cases, don't configure the dependent parameter. Configuration is supported only for externalized parameters. Even if you provide a value for an unexternalized parameter, it is ignored after you save your changes.

<a name="task_wmp_wr2_njc"/>

<!-- task\_wmp\_wr2\_njc -->

## Configure an Integration Flow across Single or Multiple Runtime Profile



## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  On the *Integration Package* details page, choose *Artifacts*.

3.  Open the integration flow.

4.  Choose *Configure*.

    The externalized parameters are displayed in various tabs like *Timer*, *Sender*, *Receiver* or *More*. See [Configure Adapter in Communication Channels](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/1f066330e8314324bf3ebe3b6adc21b2.html) 

5.  From the *Runtime Profile* drop down, choose the specific runtime profile in which you want to configure the parameters. All the runtime profiles applicable for the selected artifact are listed. See [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md)

    > ### Note:  
    > If you wish to apply shared configurations across multiple runtime profiles, choose *All*. In case of different configurations in *All* and specific runtime, the specific runtime configuration will take precedence.

    For example, you selected *All* from *Runtime Profile* drop down and for *Receiver* tab’s *Address* field you assigned `https://example.com`. Then, for Cloud Integration runtime profile you assigned `https://cloud_integration_example.com`

    So, while deployment the latter will take precedence for Cloud Integration runtime profile.

6.  Assign the configuration values for the parameters.

7.  Choose *Save*.

    You must save the configurations before adding values for another runtime profile.

8.  *Save* or *Deploy* this integration flow.

    > ### Note:  
    > You can use error configuration to handle errors when message processing fails at runtime. You select an error handling strategy based on the descriptions below:
    > 
    > **Error Handler Strategies**
    > 
    > 
    > <table>
    > <tr>
    > <th valign="top">
    > 
    > Option
    > 
    > </th>
    > <th valign="top">
    > 
    > Description
    > 
    > </th>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > None
    > 
    > \(default setting\)
    > 
    > </td>
    > <td valign="top">
    > 
    > No error handling strategy is used if a message exchange could not be processed .
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Raise Exception \(Deprecated\)
    > 
    > </td>
    > <td valign="top">
    > 
    > If a message exchange could not be processed and there is an IDoc or SOAP \( SAP RM\) channel in the integration flow, an exception is raised to the sender.
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Raise Exception
    > 
    > </td>
    > <td valign="top">
    > 
    > If a message exchange could not be processed, an exception is raised to the sender.
    > 
    > </td>
    > </tr>
    > </table>


<a name="task_rqq_ypd_njc"/>

<!-- task\_rqq\_ypd\_njc -->

## Configure Multiple Integration Flows across Single or Multiple Runtime Profile



## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  On the *Integration Package* details page, choose *Artifacts*.

3.  Select the integration flows that you wish to configure.

4.  Choose *Configure*.

    A list of selected integration flows appears at the left hand-side pane and the respective externalized parameters for each integration flow are displayed in various tabs *Timer*, *Sender*, *Receiver* or *More*. See [Configure Adapter in Communication Channels](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/1f066330e8314324bf3ebe3b6adc21b2.html) 

5.  Select an integration flow to configure.

6.  From the *Runtime Profile* drop down, choose the specific runtime profile in which you want to configure the parameters. All the runtime profiles applicable for the selected artifact are listed. See [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md)

    > ### Note:  
    > If you wish to apply shared configurations across multiple runtimes, choose *All*. In case of different configurations in *All* and specific runtime, the specific runtime will take precedence.

    For example, you selected *All* from *Runtime Profile* drop down and for *Receiver* tab’s *Address* field you assigned `https://example.com`. Then, for Cloud Integration runtime profile you assigned `https://cloud_integration_example.com`

    So, while deployment the later will take precedence for Cloud Integration.

7.  Assign the configuration values for the parameters and configure all the integration flows in the similar fashion.

8.  Choose *Save All* or *Deploy All*.

    You can check the deployment status in Monitoring view. See [Monitor Message Processing](monitor-message-processing-314df3f.md) 


**Related Information**  


[Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md "")

[Define a Timer Start Event](define-a-timer-start-event-ae14ad7.md "You can configure an integration flow to automatically start and run on a particular schedule.")

