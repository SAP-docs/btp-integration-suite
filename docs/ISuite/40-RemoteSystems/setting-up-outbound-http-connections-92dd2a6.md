<!-- loio92dd2a6fdb6045f98d23c828d1567fef -->

# Setting Up Outbound HTTP Connections

You can use various receiver adapters \(for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter\) to connect the tenant to a receiver system through the HTTP protocol.

The following figure illustrates the basic setup for HTTP outbound communication:

![The figure shows a simplified setup for HTTP outbound communication. Thanks to the Outbound Communication the Cloud Integration can be set up successfully for the Remote System.](images/Outbound_Communication_306026f.png)



<a name="loio92dd2a6fdb6045f98d23c828d1567fef__section_syp_4bc_kdb"/>

## Outbound Connections to On-Premise Systems in the Customer Landscape

For connections like this \(when SAP Integration Suite sends a message to the on-premise system\) you have to make sure that the on-premise business systems connected to the cloud are not directly exposed to the Internet.

Therefore, a further component is interconnected between the on-premise system and the integration platform in the SAP Cloud that protects the on-premise system agains external calls \(from the Internet\).

There are two different options for this component:

-   SAP Cloud Connector

-   Reverse proxy \(for example, SAP Web Dispatcher\)




The following table lists the options for setting up secure connections for the different protocols. Consider the following table as a connection setup checklist. For a detailed description of the available properties for integration flow design, see the documentation of the individual adapters and integration flow steps.

****


<table>
<tr>
<th valign="top">

Authentication

</th>
<th valign="top">

Description

</th>
<th valign="top">

How to configure \(checklist\) ...

</th>
</tr>
<tr>
<td valign="top">

Basic

</td>
<td valign="top">

Cloud Integration authenticates itself against receiver system is based on user credentials \(username and password\).

Supported by the following receiver adapters: AS2 \(only for Enterprise license\), OData, HTTP, IDoc, ODC, SOAP \(SOAP 1.x\), SOAP \(SAP RM\), SuccessFactors

More information: [Basic Authentication](basic-authentication-a5d77b1.md)

</td>
<td valign="top">

Receiver administrator: Configure keystore so that it contains certificate that is signed by a certification authority \(CA\) which is also part of the tenant keystore.

Tenant administrator:

-   Make sure that the tenant *Keystore* contains receiver server root certificate.

-   In integration flow / sender adapter, as *Authentication* option choose *Basic* and specify name of *User Credentials* artifact.

-   Create and deploy a *User Credentials* artifact that contains username and password.


More information:

[Setting Up Outbound HTTP Connections \(with Basic Authentication\)](setting-up-outbound-http-connections-with-basic-authentication-2d808e7.md)

</td>
</tr>
<tr>
<td valign="top">

Client certificate

</td>
<td valign="top">

Cloud Integration authenticates itself against receiver system is based on a client certificate.

Supported by the following receiver adapters: Ariba, AS2 \(only for Enterprise license\), OData, HTTP, IDoc, SOAP \(SOAP 1.x\), SOAP \(SAP RM\)

More information: [Client Certificate Authentication \(Outbound\)](client-certificate-authentication-outbound-c4e4a15.md)

</td>
<td valign="top">

Receiver administrator: Configure keystore. This keystore must contain a certificate that is signed by a certification authority \(CA\) which is also part of the tenant keystore. Furthermore, it must contain the tenant client root certificate \(that identifies CA that has signed the tenant client certificate\), and a receiver server certificate \(signed by CA with which the tenant has a trust relationship\).

Tenant administrator:

-   Make sure that the tenant *Keystore* contains receiver server root certificate \(which is accepted by the receiver\).

-   Make sure that the tenant *Keystore* contains a client certificate \(including public and private key\) and receiver server root certificate which is accepted by the receiver.

-   In integration flow / sender adapter, as *Authentication* option choose *Client Certificate*. You have the option to specify the *User Private Key Alias* \(to refer to a specific key pair in the tenant keystore\). If you don't specify this attribute, any valid key pair from the tenant *Keystore* will be used for authentication.


More information:

[Setting Up Outbound HTTP Connections \(with Client Certificate Authentication\)](setting-up-outbound-http-connections-with-client-certificate-authentication-f7597d2.md)

</td>
</tr>
<tr>
<td valign="top">

Principal propagation

</td>
<td valign="top">

Cloud Integration authenticates itself against the receiver system by forwarding the identity \(principal\) of the user \(associated with the inbound request\) to SAP Cloud Connector and from there to the receiver system \(for example, an on premise SAP system\).

Supported by the following receiver adapters: OData, HTTP, IDoc, ODC, SOAP \(SOAP 1.x\), SOAP \(SAP RM\)

</td>
<td valign="top">

More information:

[Setting Up Principal Propagation \(Example Scenario\)](setting-up-principal-propagation-example-scenario-34eff84.md)

</td>
</tr>
<tr>
<td valign="top">

OAuth

</td>
<td valign="top">

Cloud Integration authenticates itself against the receiver system by using OAuth.

</td>
<td valign="top">

More information:

[Setting Up Outbound HTTP Connections \(with OAuth\)](setting-up-outbound-http-connections-with-oauth-cb7abee.md)

</td>
</tr>
<tr>
<td valign="top">

OAuth with Twitter and Facebook adapter

</td>
<td valign="top">

Using the Twitter or Facebook receiver adapter, you can connect Cloud Integration to Twitter or Facebook using OAuth.

Supported by the following receiver adapters: Twitter, Facebook

More information: [OAuth 2.0](oauth-2-0-3823134.md#loio382313443b8d4453b0fd536b82b9e15d)

</td>
<td valign="top">

-   Configure the Twitter or Facebook API to accept calls from Cloud Integration \(during this step, you generate the OAuth credentials\).

-   Configure the Twitter or Facebook adapter and specify the name of the *Secure Parameter* artifacts \(for the required OAth credentials\).

-   Create and deploy a *Secure Parameter* for each required OAuth credential.




</td>
</tr>
</table>



> ### Note:  
> When you connect an on-premise \(receiver\) system to the integration platform, you need to interconnect either a reverse proxy or an SAP Cloud Connector between the on-premise system and the integration platform.
> 
> More information: [Outbound/On-Premise: Reverse Proxy or SAP Cloud Connector](outbound-on-premise-reverse-proxy-or-sap-cloud-connector-14567e1.md)

You can access the following link to see the list of available landscapes and respective IP addresses used by SAP Integration Suite: [Landscape Hosts](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/d722f7cea9ec408b85db4c3dcba07b52.html).

**Related Information**  


[Outbound/On-Premise: Reverse Proxy or SAP Cloud Connector](outbound-on-premise-reverse-proxy-or-sap-cloud-connector-14567e1.md "When you connect an on-premise (receiver) system to the integration platform, you need to interconnect either a reverse proxy or an SAP Cloud Connector between the on-premise system and the integration platform in the SAP Cloud.")

[Setting Up Outbound HTTP Connections \(with Basic Authentication\)](setting-up-outbound-http-connections-with-basic-authentication-2d808e7.md "")

[Setting Up Outbound HTTP Connections \(with Client Certificate Authentication\)](setting-up-outbound-http-connections-with-client-certificate-authentication-f7597d2.md "Using this option, authentication of Cloud Integration calling a receiver is performed based on a client certificate.")

[Twitter Receiver Adapter](../50-Development/twitter-receiver-adapter-453c174.md "You use the Twitter receiver adapter to extract information from the Twitter platform based on certain criteria such as keywords, user data, for example. As one example, you can use this feature to send, search for and receive Twitter feeds.")

[Facebook Receiver Adapter](../50-Development/facebook-receiver-adapter-3dcc408.md "You use the Facetbook receiver adapter to extract information from Facebook (which is the receiver platform) based on certain criteria such as keywords, user data, for example. As one example, you can use this feature in social marketing activities to do social media data analysis based on Facebook content.")

