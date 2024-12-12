<!-- loio7d3bce9478974229af1abf9121fe47e6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Interchange Processing Flow

This integration flow transforms the message sent by the sending partner to the structure expected by the receiving partner.

Follow the procedure below to configure the integration flow:

1.  In the *Artifacts* tab, choose *Action* <span class="SAP-icons-V5"></span> of the integration flow *Step 2 - Interchange Processing Flow* and select *Configure*.

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



<a name="loio7d3bce9478974229af1abf9121fe47e6__section_mtw_jdg_nrb"/>

## Integration Flow Process

The integration process flow picks up the incoming payload from the Step 1 integration flow and validates the payload based on the corresponding XSD schema. This validation is done only if the payload validation is enabled in the agreement for the sender and receiver interchanges. To know more, see .

The process flow then converts the payload using the MIG and MAG ifnromation provided in the agreement. The application also allows you to use your own custom integration flow for the mapping step. To know more, see

After conversion, the process flow assembles the payload as an evelope and and sends the envelope to the JMS outbound queue in Step 3 integration flow.

**Related Information**  


[Receiver Communication Flow](receiver-communication-flow-cd233d1.md "This integration flow gets the final message from the queue and sends it to the receiver.")

[Update Agreements](update-agreements-b5e1fc9.md "Update Agreement properties and MIG/MAG information.")

