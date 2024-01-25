<!-- loio5f7fa93d25344808af53ee2ab888e9d7 -->

# Special Use Cases: SAP RM vs XI vs IDoc

The scenarios provided in this section show how to guarantee end-to-end Exactly Once delivery between systems integrated via SAP Integration Suite for special use cases where the receiver protocol supports idempotency. We focus here on the receiver adapters SAP RM, XI, and IDoc.

The following table shows what settings are required to ensure guaranteed delivery depending on different situations.

> ### Note:  
> For the scenarios where the sender handles retry, we assume that the sender passes the header `SapMessageIdEx` to the integration flow.

> ### Note:  
> For all adapters, you can choose between the three options *Generate*, *Reuse* and *Map* to determine the message ID. Whereas for the SAP RM adapter and the XI adapter the header `SapMessageIdEx` is used for duplicate handling in the backend, the IDoc adapter uses the header `SapMessageId`.


<table>
<tr>
<th valign="top">

Boundary Conditions

</th>
<th valign="top">

SAP-RM

</th>
<th valign="top">

XI

</th>
<th valign="top">

IDoc

</th>
</tr>
<tr>
<td valign="top">

Sender handles retry providing unique message ID

</td>
<td valign="top">

-   Adapter Processing settings
    -   SAP RM Message ID determination: *Reuse* 


See: [Sender and Receiver with SAP RM Protocol](sender-and-receiver-with-sap-rm-protocol-9f3e2b6.md)

</td>
<td valign="top">

-   Adapter Delivery Assurance settings
    -   XI Message ID determination: *Reuse*
    -   Quality Of Service:*Exactly Once*
    -   Temporary Storage: any


See: [XI Receiver Handles Duplicates](xi-receiver-handles-duplicates-fcf026b.md)

</td>
<td valign="top">

-   Adapter Connection settings
    -   IDoc Content Type:*Application/x-sap.idoc*

-   Adapter Processing settings
    -   SAP Message ID Determination:*Map*
    -   Source for SAP Message ID: header *SapMessageIdEx*



See: [IDoc Receiver Handles Duplicates](idoc-receiver-handles-duplicates-8f8feea.md)

</td>
</tr>
<tr>
<td valign="top">

Sender handles retry providing unique ID in payload

</td>
<td valign="top">

-   Adapter Processing settings
    -   SAP RM Message ID determination: *Map* 
    -   Source for SAP RM Message ID: *unique ID* in payload


See: [Sender and Receiver with SOAP Protocol](sender-and-receiver-with-soap-protocol-cd4c6e0.md)

</td>
<td valign="top">

-   Adapter Delivery Assurance settings
    -   XI Message ID determination: *Map* 
    -   Source for XI Message ID: *unique ID* in payload
    -   Quality Of Service: *Exactly Once* 
    -   Temporary Storage: any


See: [XI Receiver Handles Duplicates \(based on unique ID in payload\)](xi-receiver-handles-duplicates-based-on-unique-id-in-payload-3add2bf.md)

</td>
<td valign="top">

-   Adapter Connection settings
    -   IDoc Content Type:*Application/x-sap.idoc*

-   Adapter Processing settings
    -   SAP Message ID Determination:*Map*
    -   Source for SAP Message ID: unique ID in payload



See:[IDoc Receiver Handles Duplicates \(based on unique ID in payload\)](idoc-receiver-handles-duplicates-based-on-unique-id-in-payload-bb441a9.md) 

</td>
</tr>
<tr>
<td valign="top">

Sender cannot retry \(decoupling via JMS queues\)

</td>
<td valign="top">

-   Adapter Processing settings
    -   SAP RM Message ID determination: *Map* 
    -   Source for SAP RM Message ID: header*SAP\_MessageProcessingLogID* 


See: [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md)

</td>
<td valign="top">

-   Adapter Delivery Assurance settings
    -   XI Message ID determination: *Map* 
    -   Source for XI Message ID: header*SAP\_MessageProcessingLogID*
    -   Quality Of Service:*Exactly Once* 
    -   Temporary Storage:*JMS Queue* 


See: [XI Receiver Handles Duplicates \(with decoupling via JMS Queue\)](xi-receiver-handles-duplicates-with-decoupling-via-jms-queue-bd19abf.md)

</td>
<td valign="top">

-   Adapter Connection settings
    -   IDoc Content Type:*Application/x-sap.idoc*

-   Adapter Processing settings
    -   SAP Message ID Determination:*Map*
    -   Source for SAP Message ID: header SAP\_*MessageProcessingLogID*



See: [IDoc Receiver Handles Duplicates \(with decoupling via JMS Queue\)](idoc-receiver-handles-duplicates-with-decoupling-via-jms-queue-776b640.md)

</td>
</tr>
<tr>
<td valign="top">

Splitter scenario where sender handles retry providing unique message ID \(sequential processing\)

</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: combination of header *SapMessageIdEx* and header *CamelSplitIndex* 
    -   Target Header Name: *SapMessageIdEx* 
    -   Context: any


-   Adapter Processing settings
    -   SAP RM Message ID determination: *Reuse* 


See: [ID Mapping \(with Splitter\)](id-mapping-with-splitter-441e51d.md)

</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: combination of header *SapMessageIdEx* and header *CamelSplitIndex* 
    -   Target Header Name: *SapMessageIdEx* 
    -   Context: any


-   Adapter Delivery Assurance settings
    -   XI Message ID determination: *Reuse* 
    -   Quality Of Service:*Exactly Once* 
    -   Temporary Storage: either *Data Store* or *JMS Queue* 


-   Transaction Handling: either*Required for JDBC* or*Required for JMS* depending on the temporary storage settings



</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: combination of header *SapMessageIdEx* and header *CamelSplitIndex* 
    -   Target Header Name: *SapMessageId* 
    -   Context: any


-   Adapter Connection settings
    -   IDoc Content Type:*Application/x-sap.idoc*

-   Adapter Processing settings
    -   SAP Message ID Determination: *Reuse*





</td>
</tr>
<tr>
<td valign="top">

Splitter scenario where sender handles retry providing unique ID in payload \(parallel processing\)

</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: *unique ID of split item*, e.g., combination of order ID and line item number
    -   Target Header Name: *SapMessageIdEx* 
    -   Context: any


-   Adapter Processing settings
    -   SAP RM Message ID determination: *Reuse* 




</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: *unique ID of split item*, e.g., combination of order ID and line item number
    -   Target Header Name: *SapMessageIdEx* 
    -   Context: any


-   Adapter Delivery Assurance settings
    -   XI Message ID determination: *Reuse* 
    -   Quality Of Service: *Exactly Once* 
    -   Temporary Storage: any




</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: *unique ID of split item*, e.g., combination of order ID and line item number
    -   Target Header Name: *SapMessageId* 
    -   Context: any


-   Adapter Connection settings
    -   IDoc Content Type:*Application/x-sap.idoc* 

-   Adapter Processing settings
    -   SAP Message ID Determination: *Reuse*





</td>
</tr>
<tr>
<td valign="top">

Splitter scenario where sender cannot retry \(decoupling via JMS queues, splitter with sequential processing\)

</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: combination of header*SAP\_MessageProcessingLogID* and header *CamelSplitIndex* 
    -   Target Header Name: *SapMessageIdEx* 
    -   Context: any


-   Adapter Processing settings
    -   SAP RM Message ID determination: *Reuse* 




</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: combination of header*SAP\_MessageProcessingLogID* and header *CamelSplitIndex* 
    -   Target Header Name: *SapMessageIdEx* 
    -   Context: any


-   Adapter Delivery Assurance settings
    -   XI Message ID determination: *Reuse* 
    -   Quality Of Service: *Exactly Once* 
    -   Temporary Storage: *JMS Queue* 




</td>
<td valign="top">

-   ID Mapper with
    -   Source Message ID: combination of header*SAP\_MessageProcessingLogID* and header *CamelSplitIndex* 
    -   Target Header Name: *SapMessageId* 
    -   Context: any


-   Adapter Connection settings

    -   IDoc Content Type:*Application/x-sap.idoc* 

-   Adapter Processing settings

    -   SAP Message ID Determination: *Reuse*





</td>
</tr>
</table>

