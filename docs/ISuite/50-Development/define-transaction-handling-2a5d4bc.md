<!-- loio2a5d4bc3b5da46df84b26ac96450587b -->

# Define Transaction Handling

You can configure transaction handling on integration process or local integration process level.



## Context

Transactional processing means that the message \(as defined by the steps contained in a process\) is processed within one transaction.

For example, consider a process with a Data Store Write operation. If transaction handling is activated, the Data Store entry is only committed if the whole process is executed successfully. In an error case, the transaction is rolled back and the Data Store entry isn't written. If transaction handling is deactivated, the Data Store entry is committed directly when the integration flow step is executed. In an error case, the Data Store entry is nevertheless persisted \(and not removed or rolled back\).

> ### Tip:  
> To learn more on how to define transaction handling, check out the corresponding integration flow design guidelines at: [Define Proper Transaction Handling](define-proper-transaction-handling-1c31963.md) and the [blog](https://blogs.sap.com/2017/05/31/cloud-integration-how-to-configure-transaction-handling-in-integration-flow/).
> 
> You also find predefined sample integration flows that are designed in such a way that each integration flow focuses on the transaction handling topic that makes it easy for you to understand. Each integration flow can be deployed and executed with minimum effort. That way, you can test each guideline on your own.

> ### Tip:  
> In the 1.0 version of Integration Process and Local Integration Process, transaction handling was enabled implicitly if persistence-related steps were modeled in the integration flow \(for example, a Data Store Get step\). However, you couldn't explicitly configure transactional behavior for this integration flow element.
> 
> With the 1.1 version or higher of Integration Process and Local Integration Process, you can configure transaction handling explicitly. If not needed, you can disable transaction handling to improve the processing performance.
> 
> If your integration flow still contains the old version of Integration Process pool, migrate it to a new version to be able to disable transactional behavior. For more information, see [Migrate an Integration Flow Component to a New Version](migrate-an-integration-flow-component-to-a-new-version-61bf6a2.md).

> ### Remember:  
> From 1.2 version of Integration Process, the default value for *Transaction Handling* is set to *Not Required*. This design in turn, improves the processing performance. If necessary for your integration use case, you can change the value as mentioned in the following table.
> 
> -   After the 1.2 version of Integration Process is made available, when you attempt to deploy your integration flow with a lower version of Integration Process, you must provide your consent if you've configured *Transaction Handling* with the value *Required for JDBC*. The consent is to avoid improper or uninformed configuration that leads to performance issues. The consent dialog comes up when you attempt to deploy either from the Integration Flow Editor or the Package view.
> 
>     For Integration process version 1.2 onwards, there's no consent required before deployment.
> 
> -   After you export the same integration flow \(with lower version of Integration Process\) from one tenant to another and trigger deployment in the target tenant, you must provide consent again.
> 
> -   The same is the experience when you attempt to migrate from lower to higher version – that is, you must provide consent to migrate if you have configured *Transaction Handling* with the value *Required for JDBC*.
> 
> -   Irrespective of the version of the Integration Process pool that you use, if you've configured *Transaction Handling* with the value *Required for JDBC*, you see a message strip in the property sheet that reminds that you've defined a transaction for the process.
> 
> 
> For design guidelines, see: [Define Proper Transaction Handling](define-proper-transaction-handling-1c31963.md).

Note the following limitations and recommendations related to transaction handling:

****


<table>
<tr>
<th valign="top">

Integration Flow Contains the Following Elements

</th>
<th valign="top">

Recommended Settings/Limitations

</th>
</tr>
<tr>
<td valign="top">

*Aggregator* steps

</td>
<td valign="top">

*Required for JDBC* \(mandatory\)

> ### Caution:  
> Choosing JDBC transaction handling is mandatory to ensure that aggregations are executed consistently.



</td>
</tr>
<tr>
<td valign="top">

*Data Store* operations

</td>
<td valign="top" rowspan="2">

*Required for JDBC* \(recommended but not mandatory\)

If you choose *Not Required*, the related database operation is committed for each single step and no end-to-end transaction handling is implemented.

</td>
</tr>
<tr>
<td valign="top">

*Write* 

</td>
</tr>
</table>

Note that **asynchronous parallel processing of messages can't be transactional**.

For more details on parallel processing, check the documentation for the General or Iterating Splitter and Parallel Multicast.

Let us assume that you want to configure a message multicast and the integration flow also contains a *Data Store* operations step. In this case, you can choose one of the following options to overcome the mentioned limitation:

-   Deactivate transactional processing.

-   Use a *Sequential Multicast* instead of a *Parallel Multicast*.




<a name="loio2a5d4bc3b5da46df84b26ac96450587b__steps_rlj_fgr_zw"/>

## Procedure

1.  Depending on whether you want to configure transaction handling for an integration process or a local integration process, select the header of the corresponding shape in the integration flow modeling area.

2.  Specify the details for transactional processing:

    To configure a transactional process for an Integration Process, select one of the following options for the *Transaction Handling* property:

    **Transaction Handling for Integration Process**


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Required for JDBC* 
    
    </td>
    <td valign="top">
    
    You can specify that Java Database Connectivity \(JDBC\) transactional database processing is applied \(to ensure that the process is accomplished within one transaction\).

    > ### Caution:  
    > The maximum timeout setting is 12 hours.
    > 
    > It's recommended that the timeout setting doesn't exceed 1 hour \(because long running transactions can cause issues with the system database\).
    > 
    > In future, transactions that take longer than 1 hour is stopped.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Not Required* 
    
    </td>
    <td valign="top">
    
    No specific transactional processing is configured. The integration process doesn't process transactions even if \(for example\) data store operations are included.
    
    </td>
    </tr>
    </table>
    
    To configure a transactional process for a local Integration Process, select one of the following options for the *Transaction Handling* property:

    **Transaction Handling for Local Integration Process**


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *From Calling Process* 
    
    </td>
    <td valign="top">
    
    Transactional processing is inherited from the calling process. The value defined for the calling process is used as the timeout.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Required for JDBC* 
    
    </td>
    <td valign="top">
    
    You can specify that Java Database Connectivity \(JDBC\) transactional database processing is applied \(to ensure that the process is accomplished within one transaction\).

    > ### Caution:  
    > The maximum timeout setting is 12 hours.
    > 
    > It's recommended that the timeout setting doesn't exceed 1 hour \(because long running transactions can cause issues with the system database\).
    > 
    > In future, transactions that take longer than 1 hour is stopped.


    
    </td>
    </tr>
    </table>
    

**Related Information**  


[Define Data Store Operations](define-data-store-operations-79f63a4.md "You can use the data store to temporarily store messages.")

[JMS Adapter](jms-adapter-0993f2a.md "You configure the JMS adapter to enable asynchronous messaging using message queues.")

