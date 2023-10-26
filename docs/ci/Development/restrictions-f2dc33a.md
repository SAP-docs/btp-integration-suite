<!-- loiof2dc33aec94f4996b2d2c07d9831596b -->

# Restrictions

The Integration Designer allows you to model specific patterns which are handled at runtime in an unexpected way.



**Restrictions and Alternative Configuration Settings**


<table>
<tr>
<th valign="top">

Modelled Pattern

</th>
<th valign="top">

Expected Behavior at Runtime

</th>
<th valign="top">

Actual Behavior at Runtime

</th>
<th valign="top">

Alternative Modeling Option

</th>
</tr>
<tr>
<td valign="top">

Integration flow step with more than one outgoing sequence flows

For example, after a Message Persistence step the message is supposed to be sent to multiple receivers in parallel.

</td>
<td valign="top">

The same message is processed in parallel after the integration flow step.

</td>
<td valign="top">

The messages are delivered to the different receivers in a sequence.

Hereby, the order in that the messages are delivered is randomly generated.

In addition to that, the following behavior may occur: the message which results from the processing in the previous sequence flow is taken as input for the next sequence flow.

> ### Note:  
> As an example, consider two parallel sequence flows where the first one contains an encryption step and the second one not. In that case, the receiver of the second sequence flow also gets an encrypted message \(although in the second sequence flow no encryption step has been configured\).



</td>
<td valign="top">

Configure only one outgoing sequence flow and parallel processing using a multicast of messages.

</td>
</tr>
</table>



### Comment on Database Transactions

The following step types include *transactional database processing*.

If one of the below listed steps is contained in an integration flow, the processing of the message is executed in one transaction.

-   Data Store Operations step

    -   Select \(in case delete=true\)

    -   Write

    -   Get \(in case delete=true\)

    -   Delete


-   Usage of Write variables

-   Aggregator step

-   Content Enricher


> ### Caution:  
> Such steps might lead to resource shortages because long running transactions can cause node instability and impede other processes that are running in transactions.
> 
> Some of the above mentioned steps or adapters persist data in the database. In case of an error, the whole process is rolled back and the original state is being re-established. That means, data from failed processes remain and, in case message processing fails, customers normally cannot access data about the failed processing \(due to the roll-back\).
> 
> In case an error is propagated back to the calling component, all data that have been written in the course of the \(failed\) transaction are being removed \(in other words: not persisted in the database\). For the calling component, an error implies, therefore, to restart the integration flow.
> 
> Transactional processing is also to be considered in scenarios that contain asynchronous decoupling. Let’s assume integration flow A contains a Data Store Operation step. Integration flow B contains a Select operation on the Data Store and runs into an error. In that case, that data is preserved that has been written to the database by integration flow A. This behavior makes sense in particular when you consider the case that integration flow B changes or deletes the data that has been stored by integration flow A. In case integration flow B fails, the original data from integration flow A can be retrieved.

