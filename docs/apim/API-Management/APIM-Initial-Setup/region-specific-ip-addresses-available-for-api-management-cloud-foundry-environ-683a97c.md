<!-- loio683a97ce038a40e097524619e47d9a10 -->

# Region-Specific IP Addresses Available for API Management Cloud Foundry Environment

API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.

In case your backend service is restricting access to certain IPs as part of security measures, you need to add API Management LB and NAT IPs to the list of allowed IPs in your backend services.

> ### Note:  
> -   LB \(Load Balancer\) IPs are ingress, for incoming requests.
> 
> -   NAT \(Network Address Translation\) IPs are egress IPs for requests from API Management.
> 
> -   The ingress \(inbound\) and egress \(outbound\) LB and NAT IP addresses mentioned in the table below are applicable for API proxy execution only.
> 
> -   In the Cloud Foundry environment, IPs are controlled by the respective IaaS provider \(AWS, Azure, Google Cloud, Alibaba Cloud\). IPs may change due to network updates on the provider side. Any planned changes will be announced at least four weeks before they take effect.

To get region-specific ingress \(inbound\) and egress \(outbound\) LB and NAT IP addresses for API Management, see the following table:



**Regions for Enterprise Accounts**


<table>
<tr>
<th valign="top">

IaaS Provider

</th>
<th valign="top">

Region

</th>
<th valign="top">

Region Name

</th>
<th valign="top">

Technical Key

</th>
<th valign="top">

Technical Key of IaaS Provider

</th>
<th valign="top">

LB IPs \(ingress, for incoming requests\)

</th>
<th valign="top">

NAT IPs \(egress, for outgoing requests\)

</th>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

eu20

</td>
<td valign="top">

Europe \(Netherlands\)

</td>
<td valign="top">

cf-eu20

</td>
<td valign="top">

West Europe

</td>
<td valign="top">

51.105.226.76, 20.4.203.111

</td>
<td valign="top">

51.105.226.79, 20.4.205.181, 20.31.245.126

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

ap20

</td>
<td valign="top">

Australia \(Sydney\)

</td>
<td valign="top">

cf-ap20

</td>
<td valign="top">

Australia East

</td>
<td valign="top">

20.53.178.192

</td>
<td valign="top">

20.53.178.190

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

ap21

</td>
<td valign="top">

Singapore

</td>
<td valign="top">

cf-ap21

</td>
<td valign="top">

Southeast Asia

</td>
<td valign="top">

20.43.177.215

</td>
<td valign="top">

20.43.177.113

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

us20

</td>
<td valign="top">

US West \(WA\)

</td>
<td valign="top">

cf-us20

</td>
<td valign="top">

West US 2

</td>
<td valign="top">

51.143.127.29

</td>
<td valign="top">

51.143.126.237

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

jp20

</td>
<td valign="top">

Japan \(Tokyo\)

</td>
<td valign="top">

cf-jp20

</td>
<td valign="top">

Japan East

</td>
<td valign="top">

52.155.116.209

</td>
<td valign="top">

52.155.117.53

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

us21

</td>
<td valign="top">

US East \(VA\)

</td>
<td valign="top">

cf-us21

</td>
<td valign="top">

East US

</td>
<td valign="top">

20.42.26.85, 137.135.94.245

</td>
<td valign="top">

20.42.28.32

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

br10

</td>
<td valign="top">

Brazil \(São Paulo\)

</td>
<td valign="top">

cf-br10

</td>
<td valign="top">

sa-east-1

</td>
<td valign="top">

18.230.84.42, 54.233.108.69, 177.71.244.1

</td>
<td valign="top">

18.229.180.216, 18.230.68.32, 18.229.200.51

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

jp10

</td>
<td valign="top">

Japan \(Tokyo\)

</td>
<td valign="top">

cf-jp10

</td>
<td valign="top">

ap-northeast-1

</td>
<td valign="top">

13.112.134.183, 54.95.250.60, 54.249.225.157

</td>
<td valign="top">

52.69.140.122, 18.181.69.241, 18.182.245.202

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

ap10

</td>
<td valign="top">

Australia \(Sydney\)

</td>
<td valign="top">

cf-ap10

</td>
<td valign="top">

ap-southeast-2

</td>
<td valign="top">

3.105.46.220, 13.237.97.179, 3.104.188.200

</td>
<td valign="top">

3.105.155.212, 13.211.74.25, 13.55.87.26

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

ap11

</td>
<td valign="top">

Asia Pacific \(Singapore\)

</td>
<td valign="top">

cf-ap11

</td>
<td valign="top">

ap-southeast-1

</td>
<td valign="top">

175.41.164.167, 18.139.72.206, 54.251.80.143

</td>
<td valign="top">

54.254.127.94, 54.179.36.212, 54.151.195.2

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

ap12

</td>
<td valign="top">

Asia Pacific \(Seoul\)

</td>
<td valign="top">

cf-ap12

</td>
<td valign="top">

ap-northeast-2

</td>
<td valign="top">

52.79.158.48, 3.36.84.59, 15.165.191.243

</td>
<td valign="top">

3.35.108.250, 54.180.45.228, 3.36.176.209

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

ca10

</td>
<td valign="top">

Canada \(Montreal\)

</td>
<td valign="top">

cf-ca10

</td>
<td valign="top">

ca-central-1

</td>
<td valign="top">

35.182.82.207, 99.79.96.34, 99.79.183.119

</td>
<td valign="top">

3.96.232.61, 3.96.230.37, 15.222.204.174

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

eu10

</td>
<td valign="top">

Europe \(Frankfurt\)

</td>
<td valign="top">

cf-eu10

</td>
<td valign="top">

eu-central-1

</td>
<td valign="top">

52.57.227.184, 35.156.111.245, 3.72.121.203, 18.195.254.216, 52.59.65.179, 18.157.127.228, 3.71.212.236, 3.78.133.131, 3.125.67.253, 3.120.18.81, 52.57.122.96, 35.157.72.246, 52.59.9.207, 3.122.187.52, 35.158.244.146

</td>
<td valign="top">

52.29.48.148, 3.120.95.10, 18.194.144.165, 18.196.191.48, 52.59.78.206, 18.195.138.5, 3.73.160.117, 52.57.130.124, 3.72.189.179

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

eu11

</td>
<td valign="top">

Europe \(Frankfurt\)

</td>
<td valign="top">

cf-eu11

</td>
<td valign="top">

eu-central-1

</td>
<td valign="top">

3.65.99.47, 3.127.192.196, 3.64.16.82

</td>
<td valign="top">

18.156.85.8, 3.65.144.116, 3.121.107.212

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

us10

</td>
<td valign="top">

US East \(VA\)

</td>
<td valign="top">

cf-us10

</td>
<td valign="top">

us-east-1

</td>
<td valign="top">

54.86.152.69, 3.227.214.88, 3.222.180.54, 54.165.0.197, 18.211.185.170, 54.152.176.132, 3.227.146.112, 54.204.200.84, 3.213.190.155, 3.94.236.44, 52.2.5.170, 34.239.31.28

</td>
<td valign="top">

3.213.79.219, 3.209.244.202, 3.213.81.148, 54.87.110.53, 54.208.172.140, 54.86.163.159

</td>
</tr>
<tr>
<td valign="top">

Google Cloud

</td>
<td valign="top">

us30

</td>
<td valign="top">

US Central \(IA\)

</td>
<td valign="top">

cf-us30

</td>
<td valign="top">

us-central-1

</td>
<td valign="top">

35.209.91.33

</td>
<td valign="top">

35.223.165.172, 34.133.13.45, 34.72.36.170

</td>
</tr>
<tr>
<td valign="top">

Alibaba Cloud

</td>
<td valign="top">

cn40

</td>
<td valign="top">

China \(Shanghai\)

</td>
<td valign="top">

cf-cn40

</td>
<td valign="top">

cn-shanghai

</td>
<td valign="top">

139.224.173.96

</td>
<td valign="top">

101.132.190.155, 106.14.165.33, 106.14.184.113

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

ch20

</td>
<td valign="top">

Switzerland \(Zurich\)

</td>
<td valign="top">

cf-ch20

</td>
<td valign="top">

Switzerland North

</td>
<td valign="top">

20.250.176.223, 20.250.113.139

</td>
<td valign="top">

20.250.216.117, 20.250.176.24

</td>
</tr>
<tr>
<td valign="top">

Google Cloud

</td>
<td valign="top">

in30

</td>
<td valign="top">

India \(Mumbai\) GCP

</td>
<td valign="top">

cf-in30

</td>
<td valign="top">

asia-south1

</td>
<td valign="top">

35.207.228.176, 35.207.205.83

</td>
<td valign="top">

34.100.176.82, 34.93.181.26, 35.200.251.32, 34.100.182.244, 34.93.184.71, 34.100.176.113

</td>
</tr>
<tr>
<td valign="top">

Google Cloud

</td>
<td valign="top">

eu30

</td>
<td valign="top">

Europe \(Frankfurt\) GCP

</td>
<td valign="top">

cf-eu30

</td>
<td valign="top">

europe-west3

</td>
<td valign="top">

35.207.154.151, 35.207.169.22

</td>
<td valign="top">

34.159.208.178, 34.159.31.39, 34.141.20.163, 34.107.78.67, 34.159.45.83, 35.246.220.63

</td>
</tr>
<tr>
<td valign="top">

Google Cloud

</td>
<td valign="top">

il30

</td>
<td valign="top">

Israel GCP

</td>
<td valign="top">

cf-il30

</td>
<td valign="top">

me-west1

</td>
<td valign="top">

34.165.125.123, 34.165.194.207

</td>
<td valign="top">

34.165.118.98, 34.165.112.191, 34.165.248.77, 34.165.101.134, 34.165.34.61, 34.165.18.227

</td>
</tr>
<tr>
<td valign="top">

Google Cloud

</td>
<td valign="top">

sa30

</td>
<td valign="top">

Saudi Arabia GCP

</td>
<td valign="top">

cf-sa30

</td>
<td valign="top">

me-central2

</td>
<td valign="top">

34.166.73.136, 34.166.63.230

</td>
<td valign="top">

34.166.47.150, 34.166.52.146, 34.166.73.249, 34.166.68.32, 34.166.56.42, 34.166.55.182

</td>
</tr>
</table>

> ### Note:  
> In case any discrepancies are observed in the IPs, please create a support ticket on the **OPU-API-OD-OPS** component.



<a name="loio683a97ce038a40e097524619e47d9a10__section_ujb_1cg_rwb"/>

## Regions for Trial Accounts


<table>
<tr>
<th valign="top">

IaaS Provider

</th>
<th valign="top">

Region

</th>
<th valign="top">

Region Name

</th>
<th valign="top">

Technical Key

</th>
<th valign="top">

Technical Key of IaaS Provider

</th>
<th valign="top">

LB IPs \(ingress, for incoming requests\)

</th>
<th valign="top">

NAT IPs \(egress, for outgoing requests\)

</th>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

ap21

</td>
<td valign="top">

Singapore

</td>
<td valign="top">

cf-ap21

</td>
<td valign="top">

Southeast Asia

</td>
<td valign="top">

20.195.53.58

</td>
<td valign="top">

20.195.52.254

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

us10

</td>
<td valign="top">

US East \(VA\)

</td>
<td valign="top">

cf-us10

</td>
<td valign="top">

us-east-1

</td>
<td valign="top">

54.160.203.34, 3.219.96.75, 3.222.55.46

</td>
<td valign="top">

54.172.191.202, 52.1.75.180, 52.207.193.169

</td>
</tr>
</table>

> ### Note:  
> If customers are implementing allow or deny listing based on IPs from their clients to API Management design time applications - API Portal, API Business Hub Enterprise, or other platform services in Cloud Foundry, such as SAP Authorization and Trust Management Service \(XSUAA\) for fetching tokens, they will need to refer to the documentation for SAP Business Technology Platform Cloud Foundry IP addresses, which can be found at the following link: [Regions and API Endpoints Available for the Cloud Foundry Environment | SAP Help Portal](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).

