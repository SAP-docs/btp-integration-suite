<!-- loio139a6b2109904d0090a160b023ffb763 -->

# Update a Number Ranges Object



Perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

PUT

</td>
<td valign="top">

`/NumberRanges('{objectName}')` 

</td>
</tr>
</table>



For example, to update a Number Ranges object with name `My NRO Object`\), send the following PUT request:

`https://<host address>/api/v1/NumberRanges('My NRO Object')`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

In the request body, provide the new properties of the Number Ranges object \(example\):

> ### Sample Code:  
> ```
> {"CurrentValue":"0",
> "Name":"My NRO Object",
> "MinValue":"0",
> "MaxValue":"9999",
> "Description":" Number Range Object ",
> "Rotate":"true",
> "FieldLength":"4"}
> ```

You find the updated *Number Ranges* object using the *Monitor* application \(*Number Ranges* tile under *Manage Stores*\).

