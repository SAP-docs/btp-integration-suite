<!-- loiocd26ea55a9994a4787d88202536ecf42 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Interchange Processing Flow V2

This integration flow transforms the message sent by the sending partner to the structure expected by the receiving partner.

Follow the procedure below to configure the integration flow:

1.  In the *Artifacts* tab, choose the *Action* <span class="SAP-icons"></span> button of the integration flow *Step 2 - Interchange Processing Flow V2* and select *Configure*

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
    
    The type of the sender adapter which is set to *JM* by default.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Queue Name


    
    </td>
    <td valign="top">
    
    INBOUND\_Q


    
    </td>
    <td valign="top">
    
    JMS queue where the messages are taken from. These are the incoming messages persisted in step 1 integration flow.

    > ### Note:  
    > This sender queue name must be the same as the receiver queue name in Step 1 integration flow.


    
    </td>
    </tr>
    </table>
    
3.  Choose the *Receiver* tab and maintain the following parameter

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
    
    Receiver


    
    </td>
    <td valign="top">
    
     


    
    </td>
    <td valign="top">
    
    The name of the receiver.


    
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
    
    The type of the sender adapter which is set to *JM* by default.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Queue Name


    
    </td>
    <td valign="top">
    
    OUTBOUND\_Q


    
    </td>
    <td valign="top">
    
    JMS queue where the outgoing messages are persisted before being sent.

    > ### Note:  
    > This receiver queue name must be the same as the sender queue name in Step 3 integration flow.


    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.
5.  Choose *Deploy*.

