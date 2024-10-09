<!-- loiocd233d11900b45248c062e8b57f1991f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Receiver Communication Flow

This integration flow gets the final message from the queue and sends it to the receiver.

Follow the procedure below to configure the integration flow.

> ### Note:  
> If the receiver side integration flow is calling a custom integration flow, only the computed Partner Directory ID header will be handed over by the receiver integration flow to the custom integration flow.

1.  In the *Artifacts* tab, choose the *Action* <span class="SAP-icons-V5"></span> button of the integration flow *Step 3 - Receiver Communication Flow* and select *Configure*

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
    
    OUTBOUND\_Q
    
    </td>
    <td valign="top">
    
    JMS queue where the messages are taken from. These are the outgoing messages persisted in the interchange step.
    
    </td>
    </tr>
    </table>
    
3.  Choose *More* tab and set the value of the field *Maximum Retries Number*. By default the value is set to 1.

    > ### Note:  
    > This denotes the maximum number of retries in case of errors.

4.  Choose *Save*
5.  Choose *Deploy*.

The integration flow process is explained below

**Receiver Communication Flow**


<table>
<tr>
<th valign="top">

Component

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Adapter Type Selection

</td>
<td valign="top">

This router checks the receiver adapter type. The message is sent depending on the adapter type to the receiver according to the properties and headers retrieved in PD Lookup in the interchange step. The supported adapter types are:

-   AS2
-   SOAP
-   IDOC
-   SOAP 1.x



</td>
</tr>
<tr>
<td valign="top">

B2B Monitoring - Business Document Sent Event

</td>
<td valign="top">

The script `InterchangeSendEvent.groovy` updates the interchange of the *B2B Monitor* with the status *COMPLETED* and the event *BUSINESSDOCUMENT\_SEND\_EVENT*

</td>
</tr>
</table>

The Retry Configuration integration process is explained below

**Retry Configuration**


<table>
<tr>
<th valign="top">

Component

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Max Retries Number

</td>
<td valign="top">

This content modifier sets the maximum number of retries in case of an error. *Number of Retries* is an externalized parameter.

</td>
</tr>
<tr>
<td valign="top">

Router

</td>
<td valign="top">

This router checks if the maximum number of retries is reached.

-   *B2B Monitoring - Interchange Error Event*: If yes, the script`InterchangeErrorEvent.groovy` updates the corresponding interchange with status *ERROR* in the *B2B Monitor*.

    -   *End Event*: The local process ends with an end event, so that the calling process ends with an escalation event.


-   *B2B Monitoring - Interchange Retry Event*: If not, the script`InterchangeRetryEvent.groovy` updates the corresponding interchange with status *RETRY* in the *B2B Monitor*.
    -   *Escalation End*: If the maximum number of retries is not yet reached, the local process ends with an error event, so that the message remains in the JMS queue for reprocessing.





</td>
</tr>
</table>

**Related Information**  


[Update Agreements](update-agreements-b5e1fc9.md "Update Agreement properties and MIG/MAG information.")

