<!-- loio683a97ce038a40e097524619e47d9a10 -->

# Region-Specific IP Addresses Available for API Management Cloud Foundry Environment

API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.

In case you are restricting access to certain IPs for security reasons, you need to add API Management LB and NAT IPs to the list of allowed IPs on your client \(Ingress\) or backend \(Egress\) as appropriate.

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

51.105.226.76, 20.4.203.111, 20.31.245.142

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

20.53.178.192, 20.191.255.210

</td>
<td valign="top">

20.53.178.190, 52.187.215.7

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

20.43.177.215, 20.188.97.45

</td>
<td valign="top">

20.43.177.113, 20.188.109.228

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

51.143.127.29, 52.148.182.6

</td>
<td valign="top">

51.143.126.237, 20.191.81.230

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

52.155.116.209, 74.226.171.139

</td>
<td valign="top">

52.155.117.53, 74.226.171.98

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

20.42.26.85, 172.174.66.71

</td>
<td valign="top">

20.42.28.32, 172.172.138.223

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

br20

</td>
<td valign="top">

Brazil \(São Paulo\)

</td>
<td valign="top">

cf-br20

</td>
<td valign="top">

Brazil South

</td>
<td valign="top">

4.201.169.164, 191.235.235.12

</td>
<td valign="top">

4.201.170.128, 191.232.172.61

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure

</td>
<td valign="top">

cn20

</td>
<td valign="top">

China North

</td>
<td valign="top">

cf-cn20

</td>
<td valign="top">

China North 3

</td>
<td valign="top">

40.162.84.8, 40.162.22.238

</td>
<td valign="top">

40.162.18.201, 40.162.87.191

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

18.230.84.42, 54.233.108.69, 177.71.244.1, 18.228.110.35, 177.71.184.143

</td>
<td valign="top">

18.229.180.216, 18.230.68.32, 18.229.200.51, 54.233.170.188, 54.94.213.131

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

13.112.134.183, 54.95.250.60, 54.249.225.157, 3.115.241.36, 13.231.63.102, 57.180.232.216

</td>
<td valign="top">

52.69.140.122, 18.181.69.241, 18.182.245.202, 57.182.97.71, 54.95.121.1, 52.192.248.246

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

3.105.46.220, 13.237.97.179, 3.104.188.200, 54.79.76.85, 52.65.179.71, 52.65.224.8

</td>
<td valign="top">

3.105.155.212, 13.211.74.25, 13.55.87.26, 13.55.92.44, 13.55.155.224, 52.62.117.94

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

175.41.164.167, 18.139.72.206, 54.251.80.143, 18.140.161.118, 52.220.206.104, 13.251.183.32

</td>
<td valign="top">

54.254.127.94, 54.179.36.212, 54.151.195.2, 18.140.175.153, 52.221.54.253, 52.77.22.159

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

52.79.158.48, 3.36.84.59, 15.165.191.243, 3.34.216.93, 43.202.175.47

</td>
<td valign="top">

3.35.108.250, 54.180.45.228, 3.36.176.209, 3.34.8.2, 3.38.235.189, 52.79.43.132

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

35.182.82.207, 99.79.96.34, 99.79.183.119, 3.98.11.222, 3.98.34.130, 3.96.232.194

</td>
<td valign="top">

3.96.232.61, 3.96.230.37, 15.222.204.174, 3.97.51.169, 15.157.233.2, 3.96.251.174

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

52.57.227.184, 35.156.111.245, 3.72.121.203, 3.120.18.81, 52.57.122.96, 35.157.72.246, 52.59.9.207, 3.122.187.52, 35.158.244.146, 3.123.77.184, 18.159.171.255, 18.185.226.25

</td>
<td valign="top">

52.29.48.148, 3.120.95.10, 18.194.144.165, 18.196.191.48, 52.59.78.206, 18.195.138.5, 3.73.160.117, 52.57.130.124, 3.72.189.179, 35.158.6.36, 18.193.41.16, 18.153.185.186

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

54.86.152.69, 3.227.214.88, 3.222.180.54, 3.227.146.112, 54.204.200.84, 3.213.190.155

</td>
<td valign="top">

3.213.79.219, 3.209.244.202, 3.213.81.148, 54.87.110.53, 54.208.172.140, 54.86.163.159

</td>
</tr>
<tr>
<td valign="top">

Amazon Web Services

</td>
<td valign="top">

us11

</td>
<td valign="top">

United States \(Oregon\)

</td>
<td valign="top">

cf-us11

</td>
<td valign="top">

us-west-2

</td>
<td valign="top">

54.148.73.252, 35.81.237.247, 52.35.10.163, 35.81.194.19, 52.38.122.4, 54.202.160.125

</td>
<td valign="top">

44.229.238.5, 52.26.207.125, 34.214.93.228, 52.11.99.88, 54.149.2.74, 44.226.123.133

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

34.172.191.154, 35.193.220.207

</td>
<td valign="top">

35.223.165.172, 34.133.13.45, 34.72.36.170, 34.71.185.2, 34.71.158.14, 34.70.15.83

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

34.93.242.91, 34.47.144.45

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

34.159.53.41, 35.198.177.136

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

Israel \(Tel Aviv\) GCP

</td>
<td valign="top">

cf-il30

</td>
<td valign="top">

me-west1

</td>
<td valign="top">

34.165.86.22, 34.165.8.207

</td>
<td valign="top">

34.165.228.53, 34.165.36.68, 34.165.22.213, 34.165.65.70, 34.165.40.115, 34.165.55.44

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

KSA \(Dammam\) GCP public sector

</td>
<td valign="top">

cf-sa30

</td>
<td valign="top">

me-central2

</td>
<td valign="top">

34.166.106.77, 34.166.125.42

</td>
<td valign="top">

34.166.118.185, 34.166.84.100, 34.166.141.246, 34.166.98.103, 34.166.97.210, 34.166.124.16

</td>
</tr>
<tr>
<td valign="top">

Google Cloud

</td>
<td valign="top">

sa31

</td>
<td valign="top">

KSA \(Dammam\) GCP

</td>
<td valign="top">

cf-sa31

</td>
<td valign="top">

me-central2

</td>
<td valign="top">

34.166.143.67, 34.166.104.175

</td>
<td valign="top">

34.166.154.51, 34.166.88.99, 34.166.28.71, 34.166.124.42, 34.166.21.81, 34.166.53.136

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
> If customers are implementing allow or deny listing based on IPs from their clients to API Management design time applications - API Portal, Developer Hub, or other platform services in Cloud Foundry, such as SAP Authorization and Trust Management Service \(XSUAA\) for fetching tokens, they will need to refer to the documentation for SAP Business Technology Platform Cloud Foundry IP addresses, which can be found at the following link: [Regions and API Endpoints Available for the Cloud Foundry Environment | SAP Help Portal](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).

**Related Information**  


[Configuring Additional Virtual Host in Cloud Foundry Environment](configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "A virtual host allows you to host multiple domain names on the API Management capability within SAP Integration Suite.")

[Shadow Users](shadow-users-a0f5fe5.md "Whenever a user authenticates at an application in your subaccount using any identity provider, it’s essential that user-related data provided by the identity provider is stored in the form of shadow users.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from SAP Integration Suite to disable your account from the API Management service.")

[Setting Up API Management with SAP Cloud Identity Services](setting-up-api-management-with-sap-cloud-identity-services-1e88d9c.md "SAP Cloud Platform allows customers to connect their SAP Cloud Identity Services with the BTP offerings.")

