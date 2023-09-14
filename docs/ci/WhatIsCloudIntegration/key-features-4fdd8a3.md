<!-- loio4fdd8a3fde434e4a9c237342700feff8 -->

# Key Features

SAP Cloud Integration supports end-to-end process integration across cloud-based and on-premise applications \(cloud-cloud and cloud-on-premise integration\).

> ### Remember:  
> There are currently certain limitations when working in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).



<a name="loio4fdd8a3fde434e4a9c237342700feff8__section_pxd_p25_3nb"/>

## Feature Overview

SAP Cloud Integration comprises the following key features:

-   Core runtime for processing, transformation, and routing of messages to be exchanged between the involved customer systems

    It is ensured that data related to different customers connected to Cloud Integration is isolated. This is important, for example, when using Cloud Integration for business-to-business scenarios.

-   Out-of-the-box connectivity support \(for example, IDoc, SFTP, SOAP/HTTPS, SuccessFactors, OData, HTTPS\)
-   Security features such as content encryption and certificate-based communication

Upon purchase, predefined, ready-to-use prepackaged integration content can be made available by SAP without the immediate need for additional hardware or integration skills on the customer’s side. This drastically reduces integration project lead times and lowers resource consumption significantly.

Cloud Integration offers full flexibility in how messages can be exchanged between customer systems by the following:

-   Leveraging preconfigured integration patterns. These integration patterns provide different options for configuring the data flow between participants, for example, by using routing rules.
-   Using various connectivity options. This covers a set of adapters \(or endpoint types\) that allow participants to connect with different communication protocols to SAP Cloud Integration.

You – as an Cloud Integration customer – can use the integration capabilities without the need to install an integration middleware on your own – as it would be the case with an on premise integration solution.



<a name="loio4fdd8a3fde434e4a9c237342700feff8__section_xjz_fg5_3nb"/>

## Compatibility with SAP Process Orchestration

You can also run integration content on the on-premise runtime of SAP Process Integration. For the Cloud Integration Web UI you can select the version of the SAP Process Integration so that the feature set of the integration content designer is adapted to the capabilities of the target runtime.

More information: [Runtime Profiles](../IntegrationSettings/runtime-profiles-8007daa.md)



<a name="loio4fdd8a3fde434e4a9c237342700feff8__section_bhf_nh5_3nb"/>

## Cloud Integration Runtime Features

There is a wide range of supported ways how Cloud Integration can process messages and exchanged them with sender and receiver systems \(see: [Integration Capabilities](integration-capabilities-e32cede.md) and [Connectivity \(Adapters\)](connectivity-adapters-55325f2.md)\).

For the delivery of messages received from a sender system Cloud Integration supports quality of service *at least once*. This means that the platform guarantees to process an inbound message at least once on the tenant. When you use the one of the following adapters, you can configure additional quality of service settings:


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

At least once



</td>
<td valign="top">

Inbound message is processed at least once by Cloud Integration.

If the same message is received multiple times from a sender, all of them are processed.

> ### Note:  
> This quality of service is supported by all sender adapter types.



</td>
</tr>
<tr>
<td valign="top">

Best effort



</td>
<td valign="top">

Inbound message is sent synchronously and an immediate response is given back to the sender system.



</td>
</tr>
<tr>
<td valign="top">

Exactly once



</td>
<td valign="top">

Inbound message is processed exactly once by Cloud Integration.

If a message with identical message ID \(for example, XI message ID\) is received multiple times from a sender, only the first one is processed by the sender adapter. The subsequent messages can be identified as duplicates and are not processed.

> ### Note:  
> In the AS2 sender adapter, duplicate message handling needs to be configured explicitly.



</td>
</tr>
</table>

> ### Note:  
> Quality of service *at least once* is supported by all sender adapter types.
> 
> Quality of service *best effort* and *exactly once* are supported by certain adapter types such like, for example, the following ones:
> 
> -   AS2 sender adapter \(see: [Configure the AS2 Sender Adapter](../Development/configure-the-as2-sender-adapter-5d7ee17.md)\)
> 
> -   AS4 sender adapter with ebMS3 receipt \(see: [Configuring Sender Channel with ebMS3 Receipt](../Development/configuring-sender-channel-with-ebms3-receipt-428ae65.md)\)
> 
> -   XI sender adapter \(see: [Configure the XI Sender Adapter](../Development/configure-the-xi-sender-adapter-41a1a57.md)\)
> 
> -   XI receiver adapter \(see: [Configure the XI Receiver Adapter](../Development/configure-the-xi-receiver-adapter-5d2670f.md)\)

> ### Note:  
> The XI receiver adapter also supports the quality of service options *best effort* and *exactly once*.
> 
> -   Best effort:
> 
>     The message is sent synchronously; this means that Cloud Integration waits for a response before it continues processing.
> 
> -   Exactly once:
> 
>     The message is sent asynchronously. This means that Cloud Integration does not wait for a response before continuing processing. It is expected that the receiver guarantees that the message is processed exactly once.
> 
>     The XI receiver adapter ensures that the same message is sent with the same XI message ID. That way, the receiver of this message is able to identify this is a duplicate and can handle the message accordingly.
> 
> 
> More information: [Configure the XI Receiver Adapter](../Development/configure-the-xi-receiver-adapter-5d2670f.md)



<a name="loio4fdd8a3fde434e4a9c237342700feff8__section_mnb_yh5_3nb"/>

## Security

Various features guarantee that data processed by Cloud Integration during the execution of an integration scenario is protected at a maximum level.

More information:

[Security, Neo Environment](../SecurityNeo/security-neo-environment-cfade20.md)

[Security, Cloud Foundry Environment](../SecurityCF/security-cloud-foundry-environment-eb9923e.md)



<a name="loio4fdd8a3fde434e4a9c237342700feff8__section_qxv_2g5_3nb"/>

## Cloud Integration OData API

An application programming interface \(API\) allows you to access Cloud Integration entities such like integration content artifacts, monitoring data, or security content, for example.

More information: [OData API](../Development/odata-api-a617d6f.md)



<a name="loio4fdd8a3fde434e4a9c237342700feff8__section_z5c_z25_3nb"/>

## Partner Directory

The Partner Directory allows you to store information about communication partners and to parameterize integration flows using this information. You can manage the content of the Partner Drectory using the OData API.

A use case for the Partner Directory is the design and operation of business-to-business scenarios.

More information: [Partner Directory](partner-directory-e7fa1e2.md)

**Related Information**  


[Tool Access](tool-access-30e39fa.md "You can access and manage integration content and operate and monitor integration artifacts and messages at runtime.")

