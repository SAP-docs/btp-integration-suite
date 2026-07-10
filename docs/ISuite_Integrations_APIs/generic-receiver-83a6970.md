<!-- loio83a6970e633b4a8f9e4407038c8512f1 -->

# Generic Receiver

The generic receiver is implemented with a separate integration flow \(with name GenericReceiver\) that creates a data store entry for each receiver call.

When setting up integration scenarios, a significant effort is typically required to configure the connected sender and receiver systems. One simple receiver component available to everyone for free is an email account that can be connected with SAP Cloud Integration using the Mail adapter.

However, even setting up a connection with an email server requires additional steps such as:

-   Performing specific security settings for the email account

-   Uploading the email provider's server certificate to the keystore


To save these efforts for you and to enable you to focus on the guideline, a generic receiver has been added to certain integration flows. The generic receiver component is implemented using a dedicated integration flow: *Generic Receiver*.

> ### Note:  
> As a prerequisite to read data store content, your user needs to have the *AuthGroup.BusinessExpert* authorization group assigned.

Each integration flow for which a receiver component is modeled, calls the integration flow *Generic Receiver* through the ProcessDirect adapter \(always using the same address\). When called, the *Generic Receiver* integration flow creates a data store entry on your tenant with the following components:

![](images/Generic_Receiver_Flow_202cfa1.png)

The *Generic Receiver* integration flow is called from a sender integration flow through the ProcessDirect adapter. The sender integration flow provides a header with the name *context*. This value represents the pattern or guideline that is covered by the calling integration flow. In some cases, the sender integration flow provides an additional header with the name *receiver*.

The *Check context* Script step checks the value of *context* header that is provided by the calling integration flow. If no value is provided, the default value *Result* is set.

The Data Store Write step *Write payload in data store* creates a data store entry with the following attributes:


<table>
<tr>
<td valign="top">

Data Store Name

</td>
<td valign="top">

Generated from the value of the *context* header \(through the dynamic expression *$\{header.context\}*\).

</td>
</tr>
<tr>
<td valign="top">

Entry ID

</td>
<td valign="top">

Generated from the value of the *receiver* header \(through the dynamic expression *$\{header.receiver\}*\).

If the calling integration flow doesn’t provide any such value, a unique identifier is generated.

> ### Note:  
> If the calling integration flow sends the message potentially to more than 1 receiver \(for example, in one of the variants that showcase the Content-Based Routing pattern\), the data store could have different entries. The *Entry ID* value for the actual message processing run is generated based on the actual value of the *receiver* header.



</td>
</tr>
</table>

> ### Note:  
> Each integration package \(as listed under [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md)\) has its own *Generic Receiver* integration flow with an integration package-specific address.



## Example

The *Pattern Content Based Routing - Ignore If No Receiver* integration flow \(for pattern variant [Variant: Ignore](variant-ignore-4998bd8.md)\) sets the following header values:


<table>
<tr>
<th valign="top">

Header

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*context*

</td>
<td valign="top">

*ContentBasedRouting-IgnoreIfNoReceiver*

This value identifies the pattern variant.

</td>
</tr>
<tr>
<td valign="top">

*receiver*

</td>
<td valign="top">

The value depends on the value of the *shippingCountry* element in the actual message processing run.

</td>
</tr>
</table>

