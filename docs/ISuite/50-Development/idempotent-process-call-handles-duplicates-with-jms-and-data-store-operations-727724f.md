<!-- loio727724f8ab8341829a07fea68bad3f7c -->

# Idempotent Process Call Handles Duplicates \(with JMS and Data Store Operations\)

The scenario described in this topic is similar to the scenario [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md) where purchase orders are filtered based on a particular product category. A JMS queue is used to handle the retry of the message delivery if an error occurs. In addition, the number of messages that are exchanged through the integration flow is counted. This number is stored in the tenant’s database. Furthermore, Cloud Integration uses this number to overwrite the purchase order number.

JMS and database operations can't be executed in one single transaction \(see [Transaction Handling Guidelines](transaction-handling-guidelines-52e3f67.md)\). Let's assume that message delivery to the receiver failed. In this case, the database transaction was already committed. However, the message remains in the JMS queue and is retried from the queue. When retried, the counter is incremented again. This behavior leads to a wrong number of overall exchanged messages.

To overcome this issue and to ensure correct numbers, the increment of the counter needs to run in an idempotent process call.

The *Pattern Quality Of Service - Scenario 06* integration flow illustrates this scenario.

![](images/Integration_flow_06_JMS_and_Data_Store_Options_9c26ced.png)

Cloud Integration stores the counter in the local variable `QoS_Counter` using the *Write counter* write variables step.

> ### Note:  
> The *Write counter* is contained in the *Local Integration Process: Increment message counter* subprocess.

The main integration process *Integration Process Scenario 06 with side effects: read from JMS queue* reads the messages from the JMS queue and performs the following steps:

1.  The *Get counter* content modifier step reads the value of the local variable and stores it in the exchange property with name `counter`. It uses the following parameters:

    ****


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Setting
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Action
    
    </td>
    <td valign="top">
    
    Create
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    counter
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Type
    
    </td>
    <td valign="top">
    
    Local Variable
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Value
    
    </td>
    <td valign="top">
    
    QoS\_Counter
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Default Value
    
    </td>
    <td valign="top">
    
    0
    
    </td>
    </tr>
    </table>
    
    On the 1st run of the scenario, the variable doesn't exist yet. For that reason, default value 0 is assigned to the exchange property.

2.  The *Idempotent Process Call* step sends the message to the local integration process \(*Local Integration Process: Increment message counter*\) using the following idempotent conditions:

    ****


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Setting
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Message ID
    
    </td>
    <td valign="top">
    
    $\{header.SAP\_MessageProcessingLogID\}
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Skip Process Call for Duplicates
    
    </td>
    <td valign="top">
    
    Selected
    
    </td>
    </tr>
    </table>
    
    If there’s an error during message processing, the message remains in the JMS queue and is retried based on the retry configuration in the JMS sender adapter. When retried, the same ID is passed on to the local integration process. As the *Skip Process Call for Duplicates* flag is selected, the local integration process is called only once.

3.  In the subsequent integration flow steps of the main integration process, the purchase order is filtered based on a particular product category. Finally, the counter is mapped to the purchase order number.


In the local integration process *Local Integration Process: Increment message counter*, Cloud Integration increments the counter using a content modifier with the following parameter settings:

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Setting

</th>
</tr>
<tr>
<td valign="top">

Action

</td>
<td valign="top">

Create

</td>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

counter

</td>
</tr>
<tr>
<td valign="top">

Source Type

</td>
<td valign="top">

Expression

</td>
</tr>
<tr>
<td valign="top">

Source Value

</td>
<td valign="top">

$\{property.counter\}++

</td>
</tr>
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

Integer

</td>
</tr>
</table>

These settings guarantee the correct increment of the counter.

The *Write counter* step overwrites the local variable `QoS_Counter` with the incremented value of property `counter`. This step uses the following settings \(see the *Processing* tab\):

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Setting

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

QoS\_Counter

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Expression

</td>
</tr>
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

Integer

</td>
</tr>
<tr>
<td valign="top">

Value

</td>
<td valign="top">

$\{property.counter\}

</td>
</tr>
<tr>
<td valign="top">

Global Scope

</td>
<td valign="top">

Deselected

</td>
</tr>
</table>

To test the scenario, perform the following steps:

1.  Set up inbound *Basic* authentication for integration flow endpoints.

    See:

    [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

    [Setting Up Inbound HTTP Connections (with Basic Authentication), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/391c45cfcd0f4435952ab085283b7f7d.html "") :arrow_upper_right:

2.  Deploy a *User Credentials* artifact with the following parameters using the *Monitor* application \(*Security Material* tile under *Manage Security*\).


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Setting
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    `OWN`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User*
    
    </td>
    <td valign="top">
    
    Enter the user as specified when setting up inbound basic authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Enter the password as specified when setting up inbound basic authentication.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 06*, you notice that the receiver adapters refer to a *User Credentials* artifact with the name *OWN*.
    > 
    > Both integration flows operate on the same tenant and use the same user credentials for outbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 06*.
4.  In the Postman client, open the *QualityOfService* folder of the Postman collection that has been provided with the *Integration Flow Design Guidelines - Enterprise Integration Patterns* package. Execute the *QualityOfService – Scenario 06* request.
5.  Check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > You see only 1 entry with an entry ID that is automatically generated by the data store write operation. Double-check the payload of the data store entry. If the scenario was processed as expected, the correct purchase order number is assigned.

6.  Optionally, check the local variable *QoS\_Counter* \(open the *Monitor* application and select the *Variables* tile under *Manage Stores*\).

    > ### Note:  
    > Verify that the counter value has been increased by 1.

7.  Before rerunning the test, clean up the data store but don’t remove the variable.

> ### Note:  
> Optionally, you can enforce a delivery error by performing the following steps:
> 
> 1.  Undeploy the *Generic Receiver* integration flow.
> 
> 2.  Switch on the trace to be able to verify the overall behavior.
> 
> 3.  Rerun the request.
> 
>     Message processing ends with an error.
> 
> 4.  Wait for a while until the message has been retried.
> 
> 5.  Check the trace to confirm that for the retried messages the idempotent local integration process is bypassed.
> 
> 6.  Redeploy the *Generic Receiver* integration flow and wait until the message has been successfully processed after retry.
> 
> 7.  Confirm that the purchase order number of the new data store entry in the data store *Pattern-QualityOfService* or the value of the local variable `QoS_Counter` has been incremented by 1 only.

**Related Information**  


[Transaction Handling Guidelines](transaction-handling-guidelines-52e3f67.md "")

[Define Idempotent Process Call](define-idempotent-process-call-84c85d7.md "Execute a process call step to check if an incoming message was already processed, and skip the processing of this message.")

