<!-- loio3897dedf791143a6a862308a6ada50f2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Receiver Communication Flow V2

This integration flow gets the final message from the queue and sends it to the receiver.

Follow the procedure below to configure the integration flow.

> ### Note:  
> If the receiver side integration flow is calling a custom integration flow, only the computed Partner Directory ID header will be handed over by the receiver integration flow to the custom integration flow.

1.  In the *Artifacts* tab, choose the *Action* <span class="SAP-icons-V5"></span> button of the integration flow *Step 3 - Receiver Communication Flow V2* and select *Configure*

2.  Under the *Sender* tab, maintain the following parameter.

    **Parameters for Configuration**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Default Value
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Sender
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    The name of the sender.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter Type
    
    </td>
    <td valign="top">
    
    JMS
    
    </td>
    <td valign="top">
    
    The type of the sender adapter which is set to *JMS* by default.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Queue Name
    
    </td>
    <td valign="top">
    
    SAP\_TPM\_OUTBOUND\_Q
    
    </td>
    <td valign="top">
    
    JMS queue where the messages are taken from. These are the outgoing messages persisted in the interchange step.
    
    </td>
    </tr>
    </table>
    
3.  Choose the *Receiver* tab and maintain the following:

    > ### Note:  
    > You only need to maintain this tab if you have enabled dead letter queue in your agreement for the receiver interchange. To know more, see [Trading Partner Agreement](trading-partner-agreement-9bd43c9.md).

    :

    **Parameters for Configuration**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Default Value
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Receiver
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    The name of the sender.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter Type
    
    </td>
    <td valign="top">
    
    JMS
    
    </td>
    <td valign="top">
    
    The type of the sender adapter which is set to *JMS* by default.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Queue Name
    
    </td>
    <td valign="top">
    
    COM\_RECEIVER\_OUTOUND\_DEAD\_LETTER\_Q
    
    </td>
    <td valign="top">
    
    Dead letter queue where the failed messages after retries are collected.

    To enable the dead letter queue for this integration flow, you need to make changes to the retry configuration. To know more, see [Configuration Manager](configuration-manager-7daf06c.md) .
    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*
5.  Choose *Deploy*.

    > ### Note:  
    > To know how to set maximum retries for failed integration flows, see [Configuration Manager](configuration-manager-7daf06c.md).


