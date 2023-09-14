<!-- loio462a4782db7b485b94ffce5b6fe22c31 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Externalized Parameters of an Integration Flow



## Context

Cloud Integration allows you to configure an integration flow individually or multiple integration flows at once. You can configure the runtime, error configuration and also provide a description about the integration flow.

> ### Note:  
> If you want timer or SuccessFactors sender adapter scheduler to be available in quick configuration, you need to externalize these parameters while creating the integration content.
> 
> If you want SucessFactors sender adapter scheduler to be available in quick configure for existing integration flows, you should externalize the scheduler parameters and republish the integration package.
> 
> You must click on the participant’s name of sender and receiver elements, to view the header and property information. Also, you must drag and drop message flow over the participant's name, to assign communication channels.

> ### Restriction:  
> You cannot use quick configure option for integration flows in *Monitor* and *Discover* tab pages. You can only configure integration flows in your customer workspace \(*Design* tab page\).



## Procedure

1.  Select the integration package that contains the integration flow you want to configure.

2.  Choose *Package content*.

    You see an overview of all the artifacts available in the selected integration package.

3.  In the *Actions* column for the integration flow you want to configure, choose <span class="SAP-icons"></span> and *Configure*.

4.  Select relevant details of externalised components in *Sender, Reciever* or *More*tab.

    > ### Note:  
    > For more information, see [Configure Adapter in Communication Channels](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/1f066330e8314324bf3ebe3b6adc21b2.html).

5.  To view and modify externalised values for integration flow configuration or integration flow steps or local integration process or integration process.

    1.  Select *Type* of component.

        > ### Note:  
        > You can also view all parameters of the component using *All Parameters* option.

    2.  Select *Name\[ID\]* of component.

        You cannot select name for integration flow configuration.


6.  If you want to save this configured integration flow as a version, choose *Save as version* and specify the version details.

7.  If you want to save or deploy this integration flow, choose the appropriate option.

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
    > 
    > 
    > </th>
    > <th valign="top">
    > 
    > Description
    > 
    > 
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
    > 
    > 
    > </td>
    > <td valign="top">
    > 
    > No error handling strategy is used if a message exchange could not be processed .
    > 
    > 
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Raise Exception \(Deprecated\)
    > 
    > 
    > 
    > </td>
    > <td valign="top">
    > 
    > If a message exchange could not be processed and there is an IDoc or SOAP \( SAP RM\) channel in the integration flow, an exception is raised to the sender.
    > 
    > 
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Raise Exception
    > 
    > 
    > 
    > </td>
    > <td valign="top">
    > 
    > If a message exchange could not be processed, an exception is raised to the sender.
    > 
    > 
    > 
    > </td>
    > </tr>
    > </table>


**Related Information**  


[Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md "")

[Define a Timer Start Event](define-a-timer-start-event-ae14ad7.md "You can configure an integration flow to automatically start and run on a particular schedule.")

