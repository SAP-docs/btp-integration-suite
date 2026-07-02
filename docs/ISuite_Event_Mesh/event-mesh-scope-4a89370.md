<!-- loio4a89370af1184bb4b712103eb09435b8 -->

# Event Mesh Scope

Understand the scope and limitations of the Event Mesh capability.



<a name="loio4a89370af1184bb4b712103eb09435b8__section_s5x_b5x_gbc"/>

## Region Availability

For more information about region availability, see SAP Note [3461547](https://me.sap.com/notes/3461547).



<a name="loio4a89370af1184bb4b712103eb09435b8__section_jgf_rwx_gbc"/>

## Messaging Protocols

Event Mesh supports the following protocols:

-   AMQP




<a name="loio4a89370af1184bb4b712103eb09435b8__section_rf3_c5x_gbc"/>

## Allowed Limits



### Message Size

-   The maximum allowed message size is 1 MB.

-   The maximum storage space \(spool size\) for all messages in all the queues is 2 GB.




### Messaging Resources


<table>
<tr>
<th valign="top">

Messaging Resource

</th>
<th valign="top">

Default

</th>
<th valign="top">

Maximum

</th>
</tr>
<tr>
<td valign="top">

Connections

</td>
<td valign="top">

200

</td>
<td valign="top">

200

</td>
</tr>
<tr>
<td valign="top">

Producers

</td>
<td valign="top">

600

</td>
<td valign="top">

600

The maximum number of producers allowed per connection is 3.

</td>
</tr>
<tr>
<td valign="top">

Consumers

</td>
<td valign="top">

600

</td>
<td valign="top">

600

The maximum number of consumers allowed per connection is 3.

</td>
</tr>
<tr>
<td valign="top">

Queues

</td>
<td valign="top">

250

</td>
<td valign="top">

250

</td>
</tr>
<tr>
<td valign="top">

Topic Subscriptions

</td>
<td valign="top">

3000

</td>
<td valign="top">

3000

</td>
</tr>
</table>



<a name="loio4a89370af1184bb4b712103eb09435b8__section_vxv_mt3_4bc"/>

## Parity With SAP Event Mesh

SAP Event Mesh users can refer to the SAP Note [3461547](https://me.sap.com/notes/3461547) to understand the parity of functional and non-functional qualities.

> ### Remember:  
> An one-to-one parity between the Event Mesh capability and the standalone offering SAP Event Mesh is not in scope.

