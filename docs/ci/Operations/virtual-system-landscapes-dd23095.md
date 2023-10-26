<!-- loiodd2309565a0c4be2892ecbf223bc9277 -->

# Virtual System Landscapes

There are different virtual system landscapes.



## Landscapes, Virtual Servers and IP Addresses

For the list of available landscapes and respective IP addresses, see: [Regions and Hosts Available for the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/d722f7cea9ec408b85db4c3dcba07b52.html).



## Ports for Outbound Communication

When configuring an **outbound** channel \(receiver adapter\), make sure to use the following standard ports:

-   Outbound **HTTP/HTTPS** connections: By default, **port 443 and all ports \> 1024** are opened in the SAP BTP firewall.

    In case of any issues, open a ticket.

-   For **SFTP** connections, make sure that the SSH data channel between SAP Cloud Integration and the SFTP server is opened. Use **port 22** at SAP BTP side.

-   For **SMTP** connections, use **port 25**.




<a name="loiodd2309565a0c4be2892ecbf223bc9277__section_e43_sck_srb"/>

## IP Addresses for Trial \(Cloud Foundry Environment\)

When using SAP Cloud Integration with an SAP BTP trial account, the following landscapes are available with the following IP addresses:


<table>
<tr>
<th valign="top">

Region / SAP Cloud Integration Domain

</th>
<th valign="top">

IPs for outbound requests from SAP Cloud Integration

</th>
<th valign="top">

Load balancer IPs for inbound requests to SAP Cloud Integration

</th>
</tr>
<tr>
<td valign="top">

\*.eu10-001.hana.ondemand.com

</td>
<td valign="top">

3.123.188.210

3.124.136.11

3.124.47.101

3.67.214.188

3.122.185.150

3.66.178.54

3.66.41.248

3.67.212.190

3.65.22.214

3.67.244.246

52.57.199.163

3.121.5.26

3.67.214.217

35.157.77.220

18.157.166.207

3.67.217.171

3.67.50.130

3.66.207.74

3.66.114.211

35.158.167.12

3.65.56.47

3.67.164.208

3.66.111.58

3.124.140.47

3.67.203.162

35.157.51.108

18.195.153.225

</td>
<td valign="top">

3.124.250.14

18.185.50.121

3.124.200.210

</td>
</tr>
<tr>
<td valign="top">

\*.eu10-002.hana.ondemand.com

</td>
<td valign="top">

18.198.196.89

18.193.21.232

3.65.9.91

18.197.134.65

52.29.190.137

3.67.255.232

3.67.182.154

3.68.44.236

3.66.249.150

</td>
<td valign="top">

3.64.227.236

3.126.229.22

18.193.180.19

</td>
</tr>
<tr>
<td valign="top">

\*.us10.hana.ondemand.com

</td>
<td valign="top">

52.200.16.71

52.23.123.125

52.202.170.155

18.211.235.11

54.156.172.106

34.234.191.59

34.192.134.47

18.204.173.15

3.213.197.54

184.73.43.82

18.210.47.160

3.216.16.207

34.225.190.250

52.2.110.230

54.234.93.200

35.153.88.132

52.204.111.138

3.88.250.160

52.20.242.182

52.71.83.110

52.200.165.163

54.208.119.130

34.202.136.35

34.192.100.96

54.85.65.82

54.205.71.200

54.221.30.9

</td>
<td valign="top">

52.23.189.23

52.4.101.240

52.23.1.211

</td>
</tr>
<tr>
<td valign="top">

\*.us10-001.hana.ondemand.com

</td>
<td valign="top">

18.213.153.162

52.0.214.195

54.227.144.195

34.233.151.91

3.225.73.158

3.222.22.16

23.23.172.117

34.194.239.31

34.238.1.234

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

\*.ap21.hana.ondemand.com

</td>
<td valign="top">

40.90.179.153

20.198.169.214

20.198.168.45

20.198.169.5

40.90.170.226

20.198.225.78

20.198.225.102

20.198.225.27

40.90.162.117

20.191.154.174

20.191.154.191

20.191.154.193

</td>
<td valign="top">

20.184.61.122

</td>
</tr>
</table>

> ### Note:  
> The **IPs for outbound requests from SAP Cloud Integration** addresses are related to **outbound communication**, that means: for calls from SAP Cloud Integration to a receiver system. They are required by the customers to configure the firewall settings \(*IP allowlisting*\) to enable their system to connect to the cloud-based integration platform.

**Related Information**  


[Tool Access](../WhatIsCloudIntegration/tool-access-30e39fa.md "You can access and manage integration content and operate and monitor integration artifacts and messages at runtime.")

