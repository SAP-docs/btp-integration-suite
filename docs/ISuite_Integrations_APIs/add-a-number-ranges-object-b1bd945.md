<!-- loiob1bd9453b5554211a3e619a87c8d79c6 -->

# Add a Number Ranges Object

Add a *Number Ranges* object to the tenant.



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

POST

</td>
<td valign="top">

`/NumberRanges` 

</td>
</tr>
</table>

Example: To add a *Number Ranges* object to your tenant, send the following POST request:

`https://<host address>/api/v1/NumberRanges`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

As request body, provide \(example\):

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

You find the newly created *Number Ranges* object using the *Monitor* application \(*Number Ranges* tile under *Manage Stores*\).

