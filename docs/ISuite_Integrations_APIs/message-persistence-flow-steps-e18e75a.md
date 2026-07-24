<!-- loioe18e75adb3e041daa48a45a732b60213 -->

# Message Persistence Flow Steps

Persistence steps enable you to store, retrieve, and manage message data during the processing of an API artifact. You can add these steps to the policy model of your API artifact to persist message payloads, manage data store entries, and write variables that can be reused across the API flow.



## Use

You use persistence steps in an API artifact to:

-   Store message payloads temporarily or permanently for later retrieval.
-   Perform operations on data store entries such as select, write, get, or delete.
-   Write variables that can be accessed at different stages of the API flow.



## Persistence Steps


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Sub Category

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

Data Store Operations

</td>
<td valign="top">

Delete

</td>
<td valign="top">

Deletes an entry from a transient data store.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Data Store Delete Operations](define-data-store-delete-operations-5efa3ac.md).

</td>
</tr>
<tr>
<td valign="top">

Get

</td>
<td valign="top">

Gets a specific entry from the transient data store.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Data Store Get Operations](define-data-store-get-operations-232ac46.md).

</td>
</tr>
<tr>
<td valign="top">

Select

</td>
<td valign="top">

Selects entries from a transient data store and creates a bulk message containing the data store entries.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Data Store Select Operations](define-data-store-select-operations-8cfe004.md).

</td>
</tr>
<tr>
<td valign="top">

Write

</td>
<td valign="top">

Performs a Write operation on the transient data store.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Data Store Write Operations](define-data-store-write-operations-46260ee.md).

</td>
</tr>
<tr>
<td valign="top">

Persist

</td>
<td valign="top">

 

</td>
<td valign="top">

Stores a message, so that you can access the stored message and analyze it at a later point in time.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Persist Messages](persist-messages-8c35f3f.md).

</td>
</tr>
<tr>
<td valign="top">

Write Variables

</td>
<td valign="top">

 

</td>
<td valign="top">

Creates a variable at a certain point within the message exchange.

You can define variables to share data across different integration flows \(deployed on the same tenant\).

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Write Variables](define-write-variables-de04b75.md).

</td>
</tr>
</table>

