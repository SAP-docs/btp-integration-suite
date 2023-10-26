<!-- loio19e0e73a57f142299f20ed16fc3e8ed1 -->

# Decision Help for Choosing the Right Content Transport Option

There are different criteria that help you to decide on a transport option.

The following table lists the characteristics and advantages and disadvantages of the different transport options.


<table>
<tr>
<th valign="top">

Transport Option

</th>
<th valign="top">

Recommendations

</th>
</tr>
<tr>
<td valign="top">

Manual export/import

</td>
<td valign="top">

Use this option only in exceptional cases, for example for urgent fixes in case the transport system is down.

This option is easy-to-use out-of-the-box \(no configuration required\).

However, there is no control and logging of the transport events and the involved users.

You have the risk of losing control of who is transporting what and when. Using this option, you don't have any advantage of the tool support provided by a transport system, like, for example, logging. For this reason, manual exports and imports should be avoided in an integration project or while operating SAP Cloud Integration. It could be used.

</td>
</tr>
<tr>
<td valign="top">

CTS+

</td>
<td valign="top">

This is a recommended option.

This option provides a fully-automated transport mechanism \(allows the assignment of roles, definition of transport routes, approvals, and comes with additional useful features like logging\).

If an on-premise CTS+ is already installed and used for other systems or objects, it is an option of choice to use CTS+ also for integration content transport.

> ### Note:  
> CTS+ is available for many years to transport on-premise non-ABAP content. This concept has been extended some time ago to support SAP BTP. However, only cloud content that can be packaged in MTAR files can be transported. For integration content transport, this constraint is fulfilled. Therefore, if you use MTAR-based content only in SAP BTP, CTS+ is a valid choice.



</td>
</tr>
<tr>
<td valign="top">

Transport Management Service \(TMS\)

</td>
<td valign="top">

This is a recommended option.

This option provides a fully automated transport mechanism \(allows the assignment of roles, definition of transport routes, approvals, and comes with additional useful features like logging\).

If there is no on-premise CTS+ available in your landscape, a good option is to go for TMS. TMS is the solution for transporting content in SAP BTP. Compared to using CTS+, this option initially implies a smaller investment in implementation and operation. Note that TMS is a cloud service \(subscription-based and maintenance and updates by SAP\). TMS is therefore the way to go for customers planning to implement projects using SAP BTP services.

</td>
</tr>
<tr>
<td valign="top">

MTAR Download

</td>
<td valign="top">

This is a semi-automated option \(in between manual export/import on the one and using CTS+ or TMS on the other hand\).

This option allows you to download an integration package manually from a source tenant as an`.mtar` file. In a subsequent step, you can upload this file to the transport system and, finally, transport it to the target tenant.

Using this option, you benefit of having certain advantages of a transport system. However, there is still a manual step. As manual steps should be avoided as far as possible, it is recommended to use this option only in exceptional cases, for example for urgent fixes in case the connection between source tenant and transport system is down.

</td>
</tr>
</table>

Both options, CTS+ and TMS are recommended as summarized in the table. In the long run, a good practice is to perform all cloud-related transports via TMS and the on-premise transport with CTS+. For more information and a comparison between TMS and CTS+, see [Interplay of Transport Management, CTS+ and ChaRM in hybrid landscapes](https://blogs.sap.com/2020/01/31/interplay-of-sap-cloud-platform-transport-management-cts-and-charm-in-hybrid-landscapes/).

The following table provides a further decision help along certain typical requirements that you encounter in an integration project.


<table>
<tr>
<th valign="top">

Criteria

</th>
<th valign="top">

Requirement

</th>
<th valign="top">

Recommended Transport Option

</th>
</tr>
<tr>
<td valign="top">

Lifecycle phase

</td>
<td valign="top">

Exploring Cloud Integration 

</td>
<td valign="top">

Manual Export/Import

</td>
</tr>
<tr>
<td valign="top">

Lifecycle phase

</td>
<td valign="top">

Operating Cloud Integration 

</td>
<td valign="top">

Automated transport \(TMS/CTS+\)

</td>
</tr>
<tr>
<td valign="top">

Exceptional Case: Urgent Intervention

</td>
<td valign="top">

Transport system down

</td>
<td valign="top">

Manual Export/Import

</td>
</tr>
<tr>
<td valign="top">

Exceptional Case: Urgent Intervention

</td>
<td valign="top">

Connection to transport system down

</td>
<td valign="top">

MTAR Download

</td>
</tr>
<tr>
<td valign="top">

Facts given by your current landscape

</td>
<td valign="top">

CTS+ already implemented and used \(benefit from available infrastructure\)

</td>
<td valign="top">

CTS+

</td>
</tr>
<tr>
<td valign="top">

Facts given by your current landscape

</td>
<td valign="top">

CTS+ already implemented and used

</td>
<td valign="top">

TMS

</td>
</tr>
<tr>
<td valign="top">

Facts given by your current landscape

</td>
<td valign="top">

CTS+ not implemented

</td>
<td valign="top">

TMS

</td>
</tr>
<tr>
<td valign="top">

Strategy

</td>
<td valign="top">

On-premise

</td>
<td valign="top">

CTS+

</td>
</tr>
<tr>
<td valign="top">

Strategy

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

TMS

</td>
</tr>
</table>

