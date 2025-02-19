<!-- loiocd26ea55a9994a4787d88202536ecf42 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Interchange Processing Flow V2

This integration flow transforms the message sent by the sending partner to the structure expected by the receiving partner.

Follow the procedure below to configure the integration flow:

1.  In the *Artifacts* tab, choose the *Action* <span class="SAP-icons-V5"></span> button of the integration flow *Step 2 - Interchange Processing Flow V2* and select *Configure*

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
    
    JMS-Receiver-Q

    If you want to use dead letter queue to collect messages that failed after retries, select the drop-down <span class="SAP-icons-V5"></span> button in this field and choose *Step2-DeadLetterQueue*.

    To enable the dead letter queue for this integration flow, you need to make changes to the retry configuration. To know more, see [Configuration Manager](configuration-manager-7daf06c.md) .
    
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
    
    *OUTBOUND\_Q* is the standard value.

    The value **COM\_PROCESSING\_OUTBOUND\_DEAD\_LETTER\_Q** is displayed if you chose dead letter queue for the *Receiver* field.
    
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

    > ### Note:  
    > To know how to set maximum retries for failed integration flows, see [Configuration Manager](configuration-manager-7daf06c.md).




<a name="loiocd26ea55a9994a4787d88202536ecf42__section_u22_1rq_32c"/>

## Retry using Idempotent Process Call

The retry mechanism has been enhanced with Idempotent process to ensure seamless processing of large payloads with multiple sub-payloads. This mechanism is designed to minimize the impact of failures and ensure data consistency.

Previously, when a large payload with multiple sub-payloads was processed, a failure in one sub-payload would trigger a retry of the entire payload. This led to unwanted reprocessing of successfully processed sub-payloads. To resolve this, idempotent process call has been implemented. With this feature:

-   **Duplicate IDs are checked:** Before processing a sub-payload, the system checks for its unique ID. If the ID is already present, the sub-payload is skipped, ensuring that it's not retried unnecessarily.
-   **Individual sub-payloads are retried:** When a sub-payload fails, only that specific sub-payload is retried, rather than the entire payload.

Through this feature, we can reduce reprocessing of successfully processed sub-payloads.



### Backward Compatibility and Configuration

To maintain backward compatibility, a new property called `SAP_TPM_Quality_Of_Service` is set in the computed PID. This property allows you to configure the retry behavior.

Here's how it works:

-   **Default Behavior:** If no `SAP_TPM_Quality_Of_Service` property is present, the system defaults to `DuplicateRetries=Allowed`. This means that the interchange will bypass the Idempotent Process and proceed to the next sub-process.
-   **Duplicate Retries Allowed:** If the `SAP_TPM_Quality_Of_Service` property is set to `DuplicateRetries=Allowed`, the interchange will bypass the Idempotent Process. Manual restart will be enabled for this interchange.
-   **Duplicate Retries Prevented:** If the `SAP_TPM_Quality_Of_Service` property is set to **DuplicateRetries=Prevent**, the interchange will go through the Idempotent Process. Manual restart will be disabled for this interchange.

