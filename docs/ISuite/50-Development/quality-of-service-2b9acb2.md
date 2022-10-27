<!-- loio2b9acb2790f64310adcb7db741af4c1f -->

# Quality of Service

The quality of service defines how a system guarantees the message delivery from a sender to a receiver.

There are the following types:


<table>
<tr>
<th valign="top">

Quality of Service



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Best Effort \(BE\)



</td>
<td valign="top">

Doesn't provide any guarantee if or how often the message is delivered.



</td>
</tr>
<tr>
<td valign="top">

At Least Once \(ALO\)



</td>
<td valign="top">

Guarantees that a message is delivered at least one time; duplicate delivery of the same message is possible.



</td>
</tr>
<tr>
<td valign="top">

At Most Once \(AMO\)



</td>
<td valign="top">

Guarantees that the same message isn't sent multiple times; however, in certain cases the message isn't delivered at all.



</td>
</tr>
<tr>
<td valign="top">

Exactly Once \(EO\)



</td>
<td valign="top">

Guarantees that a message is delivered only once. Therefore, this quality of service is a combination of ALO and AMO.

See: [Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md)



</td>
</tr>
<tr>
<td valign="top">

In Order \(IO\) \(including Exactly Once In Order \(EOIO\)\)



</td>
<td valign="top">

The order of message delivery is kept.

There's the variant *Exactly Once In Order \(EOIO\)* that implements all features given by quality of service EO in addition to a guaranteed order of message delivery.

See: [Quality of Service In Order](quality-of-service-in-order-b91a840.md)



</td>
</tr>
</table>

