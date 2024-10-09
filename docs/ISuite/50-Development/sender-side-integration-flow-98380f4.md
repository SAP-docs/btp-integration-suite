<!-- loio98380f4122a24b8ab56304660a463885 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Sender Side Integration Flow

The integration flows receive and extract messages sent using the AS2, AS2 MDN, IDoc and SOAP adapter.

Follow the procedure below to configure these integration flows.

> ### Note:  
> If you have a custom integration flow calling the sender side integration flow, it has to hand over the type system in header, and avoid using the header name reserved by the application\(TPM\).



<a name="loio98380f4122a24b8ab56304660a463885__section_u3w_vld_mrb"/>

## Sender AS2 Communication Flow

1.  In the *Artifacts* tab, choose *Action* <span class="SAP-icons-V5"></span> of the integration flow *Step 1 - Sender AS2 Communication Flow* and select *Configure*.

2.  Under the *Sender* tab, maintain the following parameters.

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
    
    Address
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Address of the endpoint to start the integration flow
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Role
    
    </td>
    <td valign="top">
    
    ESBMessaging.send
    
    </td>
    <td valign="top">
    
    Role authorisation needed to trigger the integration flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message ID Left Part
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Left part of the message ID from the incoming message.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message ID Right Part
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Right part of the message ID from the incoming message.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Partner AS2 ID
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Partner ID \(sender\) from the incoming message expected in the sender AS2 channel.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Own AS2 ID
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Own company ID \(receiver\) from the incoming message expected in the sender AS2 channel.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message Subject
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Subject from the incoming message expected in the sender AS2 channel.
    
    </td>
    </tr>
    </table>
    
3.  Select the *Receiver* tab and maintain the following parameter:

    **Receiver Parameter**


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
    
    Queue Name
    
    </td>
    <td valign="top">
    
    INBOUND\_Q
    
    </td>
    <td valign="top">
    
    JMS queue where the incoming message is persisted.
    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.
5.  Choose *Deploy*.



<a name="loio98380f4122a24b8ab56304660a463885__section_svz_mw3_2vb"/>

## Sender AS2 MDN Flow

This integration flow is used to capture the Technical Acknowledgement through the AS2 adapter. You can also review the Technical Acknowledgement in the *B2B Monitoring* tab.

1.  In the *Artifacts* tab, choose *Action* <span class="SAP-icons-V5"></span> of the integration flow *Step 1 - Sender AS2 MDN Flow* and select *Deploy*.




<a name="loio98380f4122a24b8ab56304660a463885__section_kwk_cmd_mrb"/>

## Sender IDOC Communication Flow

1.  In the *Artifacts* tab, choose *Action* <span class="SAP-icons-V5"></span> of the integration flow *Step 1 - Sender IDOC Communication Flow* and select *Configure*

2.  Under the *Sender* tab, maintain the following parameters

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
    
    Address
    
    </td>
    <td valign="top">
    
    /tpm/b2b/idoc/
    
    </td>
    <td valign="top">
    
    Address of the endpoint to start the integration flow
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Role
    
    </td>
    <td valign="top">
    
    ESBMessaging.send
    
    </td>
    <td valign="top">
    
    Role authorisation needed to trigger the integration flow.
    
    </td>
    </tr>
    </table>
    
3.  Choose the *Receiver* tab and maintain the following parameter:

    **Receiver Parameter**


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
    
    Queue Name
    
    </td>
    <td valign="top">
    
    INBOUND\_Q
    
    </td>
    <td valign="top">
    
    JMS queue where the incoming message is persisted.
    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.
5.  Choose *Deploy*.



<a name="loio98380f4122a24b8ab56304660a463885__section_dlc_qmd_mrb"/>

## Sender SOAP Communication Flow

1.  In the *Artifacts* tab, choose the *Action* <span class="SAP-icons-V5"></span> button of the integration flow *Step 1 - Sender IDOC Communication Flow* and select *Configure*

2.  Under the *Sender* tab, maintain the following parameters

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
    
    Address
    
    </td>
    <td valign="top">
    
    /tpm/b2b/soap/
    
    </td>
    <td valign="top">
    
    Address of the endpoint to start the integration flow
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Role
    
    </td>
    <td valign="top">
    
    ESBMessaging.send
    
    </td>
    <td valign="top">
    
    Role authorisation needed to trigger the integration flow.
    
    </td>
    </tr>
    </table>
    
3.  Choose the *Receiver* tab and maintain the following parameter.

    **Receiver Parameter**


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
    
    Queue Name
    
    </td>
    <td valign="top">
    
    INBOUND\_Q
    
    </td>
    <td valign="top">
    
    JMS queue where the incoming message is persisted.
    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.
5.  Choose *Deploy*.



To know about the integration process involved, see [Integration Process Flow](integration-process-flow-8e9f6bf.md)

**Related Information**  


[Interchange Processing Flow](interchange-processing-flow-7d3bce9.md "This integration flow transforms the message sent by the sending partner to the structure expected by the receiving partner.")

[Receiver Communication Flow](receiver-communication-flow-cd233d1.md "This integration flow gets the final message from the queue and sends it to the receiver.")

[Update Agreements](update-agreements-b5e1fc9.md "Update Agreement properties and MIG/MAG information.")

