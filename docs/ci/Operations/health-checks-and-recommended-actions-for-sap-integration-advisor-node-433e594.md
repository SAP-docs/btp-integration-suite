<!-- loio433e594dce894b2a962e26457a08d18e -->

# Health checks and recommended actions for SAP Integration Advisor Node

Currently, the following health checks are covered for Integration Advisor node:


<table>
<tr>
<td valign="top">

Integration Advisor State

</td>
<td valign="top">

The MBean checks the health of Integration Advisor. The threshold check is String ‘Available’. In case Integration Advisor’s health is good the check returns ‘ Available’ and ‘Unavailable’ in case Integration Advisor’s health is poor.

</td>
</tr>
<tr>
<td valign="top">

Availability Check

</td>
<td valign="top">

It checks the availability of the application via HTTP ping. The check is executed every second. Default values of 50 seconds for warning and 60 seconds for critical are currently assigned to this check. This means that if the ping response time is more than 50 or 60 seconds a warning or critical alert will be generated respectively.

</td>
</tr>
</table>

