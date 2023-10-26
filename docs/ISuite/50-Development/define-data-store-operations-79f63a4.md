<!-- loio79f63a4bf5a44b5996aa34c51e2f187f -->

# Define Data Store Operations

You can use the data store to temporarily store messages.



## Context

You can use the data store to implement the following use cases:

-   Push pull pattern

    The message received from a sender is stored in the data store. A receiver actively polls \(reads\) the message from there in another message processing run.

-   Temporarily store the message for later use

    The data store can be used to temporarily store the message so that it can be used across different integration flows.


The data store supports four types of operations:

**Data Store Operations**


<table>
<tr>
<th valign="top">

Operation

</th>
<th valign="top">

Used to ...

</th>
</tr>
<tr>
<td valign="top">

*Write* 

</td>
<td valign="top">

Store the messages temporarily in the data store.

If you use a *Write* operation, you can store the messages in the data store by configuring the data store name and a unique *Entry ID*.

More information: [Define Data Store Write Operations](define-data-store-write-operations-46260ee.md)

</td>
</tr>
<tr>
<td valign="top">

*Delete* 

</td>
<td valign="top">

Trigger the deletion of messages in the data store.

More information: [Define Data Store Delete Operations](define-data-store-delete-operations-5efa3ac.md)

</td>
</tr>
<tr>
<td valign="top">

*Select* 

</td>
<td valign="top">

Fetch messages in bulk from the data store.

You can also specify the maximum number of messages you fetch in each poll.

More information: [Define Data Store Select Operations](define-data-store-select-operations-8cfe004.md)

</td>
</tr>
<tr>
<td valign="top">

*Get* 

</td>
<td valign="top">

Fetch a specific message from the data store.

From component version 1.5 onwards, the *Created At* \(header: `SAP_DataStoreCreatedAt`\) and *Retain Until* \(header: `SAP_DataStoreExpiresAt`\) timestamps of the data store entry are included in the message.

More information: [Define Data Store Get Operations](define-data-store-get-operations-232ac46.md)

</td>
</tr>
</table>

This component stores data on your tenant \(using SAP ASE Platform Edition\). Note that there is an overall DB space limit of 32 GB.

**Related Information**  


[Examples](examples-c8ba267.md "")

