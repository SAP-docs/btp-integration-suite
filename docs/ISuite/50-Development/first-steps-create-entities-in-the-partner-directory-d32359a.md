<!-- loiod32359a67e444c6e899084577e041a0a -->

# First Steps - Create Entities in the Partner Directory

> ### Note:  
> As prerequisite to create entities in the Partner Directory, you need to configure secure inbound authentication for the API client to call the OData API.
> 
> The detailed procedure depends on the cloud environment \(Cloud Foundry \) and on the desired authentication option.
> 
> For more information, check out the links under *Related Information*.



To work with the example integration flows, you need to create the following entities in Partner Directory for sample partner `PartnerA`:

****


<table>
<tr>
<th valign="top">

Entity Type

</th>
<th valign="top">

Entity

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

String Parameters

</td>
<td valign="top">

ReceiverUrl

</td>
<td valign="top">

Endpoint of receiver that is called by the integration flow *Partner Directory – Dynamic Receiver*

</td>
</tr>
<tr>
<td valign="top">

String Parameters

</td>
<td valign="top">

AS2\_inbound\_decrypt\_message

</td>
<td valign="top">

Indicates if the message has to be decrypted in the integration flow *Partner Directory – AS2 Dynamic Keys* 

</td>
</tr>
<tr>
<td valign="top">

String Parameters

</td>
<td valign="top">

ReceiverPrivateKey

</td>
<td valign="top">

Private key alias to identify key in Cloud Integration keystore used to decrypt message in the integration flow *Partner Directory – AS2 Dynamic Keys* 

</td>
</tr>
<tr>
<td valign="top">

String Parameters

</td>
<td valign="top">

AS2\_inbound\_verify\_signature

</td>
<td valign="top">

Indicates if the signature of a message must be validated in the integration flow *Partner Directory – AS2 Dynamic Keys* 

</td>
</tr>
<tr>
<td valign="top">

User Credentials

</td>
<td valign="top">

ReceiverCredentials

</td>
<td valign="top">

Security artifact \(deployed on the Cloud Integration tenant\) that is used to call the receiver endpoint in integration flow *Partner Directory – Dynamic Receiver* 

</td>
</tr>
<tr>
<td valign="top">

Authorized User

</td>
<td valign="top">

\(Create an authorized user with arbitrary name\)

</td>
<td valign="top">

User assigned to Partner ID for integration flow *Partner Directory – Authorized User* and *Partner Directory – AS2 Dynamic Keys* 

</td>
</tr>
<tr>
<td valign="top">

Alternative Partner Id

</td>
<td valign="top">

\(Define an alternative partner Id with arbitrary value\)

</td>
<td valign="top">

Alternative partner id assigned to partner id for the integration flow *Partner Directory – Alternative Partner Id* 

</td>
</tr>
<tr>
<td valign="top">

Binary Parameter

</td>
<td valign="top">

SenderPublicKey

</td>
<td valign="top">

Public key of Mendelson tool for signing messages for the integration flow *Partner Directory – AS2 Dynamic Keys* 

</td>
</tr>
<tr>
<td valign="top">

Binary Parameter

</td>
<td valign="top">

MyMapping

</td>
<td valign="top">

XSLT mapping used in the integration flow *Partner Directory – XSLT Mapping* 

</td>
</tr>
<tr>
<td valign="top">

Binary Parameter

</td>
<td valign="top">

MyMappingSchema

</td>
<td valign="top">

XSD schema used in the integration flow *Partner Directory – XSLT Mapping* 

</td>
</tr>
</table>

Perform the following initial steps with Postman.

1.  Initially create the Partner Directory entries.

2.  Start the Postman Runner and select collection *CPI Partner Directory Example Flows*.

3.  Select folder *Update PD \(CF\)*. This folder contains a request that automatically creates the sample partner `PartnerA` with the entities listed in table above.

4.  Start the Postman runner for folder *Update PD \(CF\)*.


**Related Information**  


[Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md "An application programming interface (API) allows you to access Cloud Integration data, for example, monitoring data.")

[Setting Up Inbound HTTP Connections (for API Clients), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/fbae09c89d9246f88149c5293c96ab5f.html "") :arrow_upper_right:

