<!-- loio26a78946be2f48c4a65323459deab159 -->

# Solace Monitor

Monitor Solace Broker metrics, keep track of resource utilization, and access information about message VPNs, queues, and clients.

The Solace Monitor card provides status updates on the *Kubernetes Custom Resource*`SolaceSoftwareBroker`, the *Guaranteed Messaging* capability and the *Config-Sync* feature. The status of the Kubernetes Custom Resource indicates the operational state of the Solace Broker, which is used as a messaging service by the Edge Integration Cell, installed on your Kubernetes cluster. The Guaranteed Messaging capability signifies the reliability of message delivery, even in the face of network failures or downtime with the receiving application. Config-Sync is an internal Solace feature which ensures configurations remain in sync, allowing the system to continue functioning in the event of a failover. Config-Sync status is available only in a high-availability setup.

Choose the card to monitor the current state, track resource utilization, and view detailed information about message VPNs, queues, and messaging clients in real-time. On the screen, you see the following information:


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Message VPNs

</td>
<td valign="top">

Displays the available VPNs \(Virtual Private Networks\). The Edge Integration Cell uses three VPNs:

-   The Events Message VPN manages the internal events within the Edge Integration Cell.

-   The JMS Message VPN provides JMS processing within integration flows.

-   The Config-Sync Message VPN is responsible for synchronizing configurations between Message VPNs within a high-availability group.


To view the general information and resource utilization details for a specific Message VPN, choose it from the table.

</td>
</tr>
<tr>
<td valign="top">

Resource Utilization

</td>
<td valign="top">

The Resource Utilization section displays the usage of Solace key metrics spread across all message VPNs.

If Resource Utilization displays critical values, you can either select the linked value or choose *View Queues* and *View Clients* to show details about key metrics.

</td>
</tr>
</table>

**Related Information**  


[Access the Message Service](access-the-message-service-abbb36a.md "Learn how to access the Message Service.")

