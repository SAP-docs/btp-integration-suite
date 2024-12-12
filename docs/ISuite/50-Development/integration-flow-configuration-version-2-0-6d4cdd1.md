<!-- loio6d4cdd14953842509907b19175882fea -->

# Integration Flow Configuration Version 2.0

Configure your integration flows to test the end-to-end scenario.

The package **Cloud Integration – Trading Partner Management V2** contains 2.0 version of the necessary artifacts that have to be configured. This integration flow uses the latest AS2 Sender Adapter 1.13 and AS2 MDN Sender Adapter 1.10 that provide you with more dynamic parameters.

The AS2 Adapter has two configuration modes - *Profile* and *Channel*. The Profile mode which uses reusable configurations is the only mode that's compatible with the 2.0 Version.

To know more on how to configure this profile mode, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md).

If you want to make your active agreement compatible with this version, follow the steps mentioned here [Migration Steps for 2.0 Compatibility](migration-steps-for-2-0-compatibility-8631960.md).

> ### Note:  
> This is a configure-only package and hence, you cannot edit the integration flows.
> 
> The 2.0 version of the generic integration flow is not compatible with 1.x generic integration flow package.
> 
> The default sender endpoint\(sender URL\) for integration flow 2.0 is the same as integration flow 1.x. If you want to deploy both 1.x and 2.0 versio of the integration flow, then you need to change the default sender endpoints to another value\(by configuring the externalized parameter\) in the 2.0 integration flow during deployment.
> 
> Few pointers to consider while using ProcessDirect sender and receiver adapters:
> 
> -   The groovy scripts provided in the integration package is reserved for *SAP* and it is not recommended to apply the groovy code to custom integration flows.
> 
> -   The newly added integration flow *Step 1b - Write Message to Message Queue* is for internal use and not configurable. This integration flow can be called only through *Step 1 - Sender Process Direct Communication Flow V2* and the Step 1 integration flow will pass the actual type system in the camel header **SAP\_EDI\_Document\_Standard** with the following values:
>     -   UN-EDIFACT
> 
>     -   ASC-X12
>     -   SAP\_IDoc
>     -   SAP\_S4HANA\_Cloud\_SOA
>     -   GS1-XML
> 
> -   You can handover all the camel headers that are defined in your custom integration flows to Process Direct Step 1, and it is recommended not to use camel header property name with prefix *SAP\_* as the property value might get overwritten by generic integration flow.
> -   The computed Partner Directory ID can be used in both Step 2 Process Direct and Step 3 Process Direct integration flows. You can access the computed PID's content by calling PID *SAP\_TPM\_ACTIVITYPARTNER\_ID* in your groovy scripts.

Follow the steps below to copy the integration package to your *Design* space.

1.  Login to your tenant.

2.  Under the *Discover* tab, search for and open the package *Cloud Integration - Trading Partner Management V2*.
3.  Choose *Copy*.
4.  Navigate to the *Design* tab.
5.  Choose and open the integration package and navigate to the *Artifacts* tab.
6.  The table belows lists the integration flows in the package and their purpose:

    > ### Note:  
    > To know more about the integration flow step in detail, see [Cloud Integration - Trading Partner Management V2 | SAP Business Accelerator Hub](https://api.sap.com/package/CloudIntegrationTradingPartnerManagementV2/documents)

    **Cloud Integration - Trading Partner Management V2**


    <table>
    <tr>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Integration Flow
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="7">
    
    Sender
    
    </td>
    <td valign="top">
    
    Step 1 - Sender AS2 Communication Flow V2
    
    </td>
    <td valign="top">
    
    Receives and extracts messages sent using AS2 adapter
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1 - Sender AS2 MDN Communication Flow V2
    
    </td>
    <td valign="top">
    
    Receives and extracts messages sent using AS2 MDN adapter
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1 - Sender IDOC Communication Flow V2
    
    </td>
    <td valign="top">
    
    Receives and extracts messages sent using IDOC adapter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1 - Sender SOAP Communication Flow V2
    
    </td>
    <td valign="top">
    
    Receives and extracts messages sent using SOAP adapter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1 - Sender Process Direct Communication Flow V2
    
    </td>
    <td valign="top">
    
    Receives and extracts messages sent using ProcessDirect adapter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1a - Sender Communication Flow V2 \(Internal\)
    
    </td>
    <td valign="top">
    
    Receives Restart and Retry messages via HTTP protocol.

    > ### Note:  
    > This flow step is for internal purposes only. Do not configure or send payloads to this step.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1b - Write Message to Message Queue
    
    </td>
    <td valign="top">
    
    Helps write the incoming message to the message queue.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Interchange
    
    </td>
    <td valign="top">
    
    Step 2 - Interchange Processing Flow V2
    
    </td>
    <td valign="top">
    
    Transforms the message sent by the sender to the structure expected by the receiver.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Receiver
    
    </td>
    <td valign="top">
    
    Step 3 - Receiver Communication Flow V2
    
    </td>
    <td valign="top">
    
    Receives the final message from the queue and sends it to the receiver
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Reusable Groovy Scripts V2
    
    </td>
    <td valign="top">
    
    Collection of scripts used in the integration flows of the package.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > -   The supported sender adapters are:
    > 
    >     -   SOAP
    > 
    >     -   AS2
    >     -   AS2 MDN
    >     -   IDoc
    >     -   ProcessDirect
    > 
    > -   The supported receiver adapters are:
    > 
    >     -   SOAP adapater
    > 
    >     -   AS2 adapter
    >     -   IDoc adapter
    >     -   ProcessDirect

7.  Follow the procedure below for configuring the integration flows:
    -   [Sender Communication Flow V2](sender-communication-flow-v2-5b946c5.md)

    -   [Interchange Processing Flow V2](interchange-processing-flow-v2-cd26ea5.md)
    -   [Receiver Communication Flow V2](receiver-communication-flow-v2-3897ded.md)


