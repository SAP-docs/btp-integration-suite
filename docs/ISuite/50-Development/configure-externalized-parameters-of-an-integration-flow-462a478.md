<!-- loio462a4782db7b485b94ffce5b6fe22c31 -->

# Configure Externalized Parameters of an Integration Flow



## Context

Cloud Integration allows you to configure an integration flow individually or multiple integration flows at once. You can configure the runtime, error configuration and also provide a description about the integration flow.

> ### Remember:  
> When you configure an externalized parameter, it is possible that you are allowed to provide a value for another dependent parameter which isn't externalized. In such cases, don't configure the dependent parameter. Configuration is supported only for externalized parameters. Even if you provide a value for an unexternalized parameter, it is ignored after you save your changes.



## Procedure

1.  Open the integration flow..

2.  Choose *Configure*.

    > ### Note:  
    > You can also view the additional information added during parameter externalization, see [Externalized Parameters View](externalized-parameters-view-27a0216.md).

3.  Select relevant details of externalised components in *Sender, Reciever* or *More*tab.

    > ### Note:  
    > For more information, see [Configure Adapter in Communication Channels](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/1f066330e8314324bf3ebe3b6adc21b2.html).

4.  To view and modify externalised values for integration flow configuration or integration flow steps or local integration process or integration process.

    1.  Select *Type* of component.

        > ### Note:  
        > You can also view all parameters of the component using *All Parameters* option.

    2.  Select *Name\[ID\]* of component.

        You cannot select name for integration flow configuration.


5.  If you want to save this configured integration flow as a version, choose *Save as version* and specify the version details.

6.  If you want to save or deploy this integration flow, choose the appropriate option.

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


**Related Information**  


[Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md "")

[Define a Timer Start Event](define-a-timer-start-event-ae14ad7.md "You can configure an integration flow to automatically start and run on a particular schedule.")

