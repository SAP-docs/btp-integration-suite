<!-- loio6d4cdd14953842509907b19175882fea -->

# Integration Flow Configuration Version 2.0

Configure your integration flows to test the end-to-end scenario.

The package **Cloud Integration – Trading Partner Management V2** contains 2.0 version of the necessary artifacts that have to be configured. This integration flow uses the latest AS2 Sender Adapter 1.13 and AS2 MDN Sender Adapter 1.10 that provide you with more dynamic parameters.

The AS2 Adapter has two configuration modes - *Profile* and *Channel*. The Profile mode which uses reusable configurations is the only mode that's compatible with the 2.0 Version.

To know more on how to configure this profile mode, see [Creating a Trading Partner Profile](creating-a-trading-partner-profile-542fb11.md).

If you want to make your active agreement compatible with this version, follow the steps mentioned here .

> ### Note:  
> This is a configure-only package and hence, you cannot edit the integration flows.
> 
> The 2.0 version of the generic integration flow is not compatible with 1.x generic integration flow package.
> 
> The default sender endpoint\(sender URL\) for integration flow 2.0 is the same as integration flow 1.x. If you want to deploy both 1.x and 2.0 versio of the integration flow, then you need to change the default sender endpoints to another value\(by configuring the externalized parameter\) in the 2.0 integration flow during deployment.

Follow the steps below to copy the integration package to your *Design* space.

1.  Login to your tenant.

2.  Under the *Discover* tab, search for and open the package *Cloud Integration - Trading Partner Management V2*.
3.  Choose *Copy*.
4.  Navigate to the *Design* tab.
5.  Choose and open the integration package and navigate to the *Artifacts* tab.
6.  The table belows lists the integration flows in the package and their purpose:

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
    <td valign="top" rowspan="4">
    
    Sender


    
    </td>
    <td valign="top">
    
    Step 1 - Sender AS2 Communication Flow V2


    
    </td>
    <td valign="top">
    
    This integration flow receives and extracts messages sent using AS2 adapter


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1 - Sender AS2 MDN Communication Flow V2


    
    </td>
    <td valign="top">
    
    This integration flow receives and extracts messages sent using AS2 MDN adapter


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1 - Sender IDOC Communication Flow V2


    
    </td>
    <td valign="top">
    
    This integration flow receives and extracts messages sent using IDOC adapter.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Step 1 - Sender SOAP Communication Flow V2


    
    </td>
    <td valign="top">
    
    This integration flow receives and extracts messages sent using SOAP adapter.


    
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
    
    This integration flow transforms the message sent by the sender to the structure expected by the receiver.


    
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
    
    This integration flow gets the final message from the queue and sends it to the receiver


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
     


    
    </td>
    <td valign="top">
    
    Reusable Groovy Scripts V2


    
    </td>
    <td valign="top">
    
    This is the collection of scripts used in the integration flows of the package.


    
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
    > 
    > -   The supported receiver adapters are:
    > 
    >     -   SOAP adapater
    > 
    >     -   AS2 adapter
    >     -   IDoc adapter

7.  Follow the procedure below for configuring the integration flows:
    -   [Sender Communication Flow V2](sender-communication-flow-v2-5b946c5.md)

    -   [Interchange Processing Flow V2](interchange-processing-flow-v2-cd26ea5.md)
    -   [Receiver Communication Flow V2](receiver-communication-flow-v2-3897ded.md)
    -   


