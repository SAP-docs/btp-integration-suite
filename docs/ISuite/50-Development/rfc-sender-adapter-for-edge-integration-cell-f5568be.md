<!-- loiof5568be44b474e44b267fc284a509094 -->

# RFC Sender Adapter for Edge Integration Cell

The RFC sender adapter for Edge Integration Cell \(EIC\) enables direct, on-premise communication with SAP and third-party systems without relying on the SAP Cloud Connector, allowing these systems to initiate RFC calls.

> ### Note:  
> RFC sender adapter is only available for the Edge Integration Cell runtime.

Edge Integration Cell allows direct connection to backend systems without using the SAP Cloud Connector. Thus, the RFC sender adapter running on Edge Integration Cell can benefit from native RFC \(CPI-C\) communication through an SAP Gateway.

The adapter uses the Java Connector \(JCo\) Standalone 3.1 library to receive and transform remote-enabled Function Module \(RFM\) calls from SAP or external \(JCo-based\) systems and applications. RFC Metadata is used for the transformation from native RFC to RFC-XML and vice versa.

The adapter supports two RFC call types: Synchronous RFC Calls \(sRFC\), and Transactional RFC Calls \(tRFC\). For more information, see the table below.

To ensure secure communication, Secure Network Communications \(SNC\) should be enabled in Edge Integration Cell and configured for the RFC sender adapter.

The EIC RFC sender adapter supports generic configuration. A single RFC sender channel can be used for multiple RFM types \(interfaces\) and provides configuration options to read RFM metadata from multiple systems.

**Supported Features**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Gateway Connection Registration

</td>
<td valign="top">

-   For each EIC RFC sender channel, the adapter creates a JCo server which registers a pool of connections on a gateway that listens for incoming calls from the ABAP system.
-   The adapter supports a High-Availability \(HA\) configuration. There is an option to register with multiple local gateways of an ABAP system simultaneously. This ensures that the system remains operational even if one gateway becomes unavailable.
-   It's possible to receive calls from a non-ABAP system through an SAP Gateway. For more information, see SAP Note [1877907](https://me.sap.com/notes/1877907).




</td>
</tr>
<tr>
<td valign="top">

Synchronous RFC \(sRFC\) Support

</td>
<td valign="top">

The EIC RFC sender adapter can process synchronous calls based on the sRFC standard.

For synchronous RFC calls, the response is received as RFC-XML and converts back to the native RFC data format. The conversion is based on the RFM metadata, ensuring that the response is properly structured and understood by the receiving system.

</td>
</tr>
<tr>
<td valign="top">

Transactional RFC \(tRFC\) Support

</td>
<td valign="top">

-   The EIC RFC sender adapter can process transactional calls based on the tRFC standard.
-   A single RFC call per LUW \(logical unit of work\) or transaction is supported.
-   tRFC ensures that a function module \(RFM\) is executed only once, even if there are retries due to network issues or system downtime.
-   The transaction is stored with a unique Transaction ID \(TID\) and can be retried from the sender \(the adapter supports retries but doesn't initiate them\).The uniqueness of the TID is guaranteed with built-in duplicate message handling support.
-   No response message is expected to be sent to the ABAP System.



</td>
</tr>
<tr>
<td valign="top">

Remote Function Module Handling

</td>
<td valign="top">

-   The EIC RFC sender adapter provides a Remote Function Module implementation that can be called by client programs via sRFC or tRFC
-   The adapter uses the JCo server function handling model, allowing different integration flows \(iFlows\) to be configured for different RFM interfaces, supporting generic interface handling.



</td>
</tr>
<tr>
<td valign="top">

RFC-XML Conversion Support

</td>
<td valign="top">

-   Incoming RFC data will be converted into RFC-XML format based on the metadata of the RFMs.
-   The metadata, essential for the conversion process, will be dynamically loaded from an ABAP system using the RFC destination and kept in memory for processing.
-   The payload format is compliant with the RFC specification and the PI/PO RFC adapter implementation.



</td>
</tr>
<tr>
<td valign="top">

Automatic Gateway Reconnects Support

</td>
<td valign="top">

The EIC RFC sender adapter supports automatic reconnection to the gateway in case of connectivity issues.

</td>
</tr>
<tr>
<td valign="top">

Dynamic Connection Pool Increase Support

</td>
<td valign="top">

The EIC RFC sender adapter supports dynamic connection pool expansion based on configuration settings and system load.

</td>
</tr>
<tr>
<td valign="top">

Stateless Communication Support

</td>
<td valign="top">

The adapter supports only stateless communication, meaning each RFC call is independent and doesn't retain any session information between calls.

</td>
</tr>
<tr>
<td valign="top">

Secure Network Communications \(SNC\) Support

</td>
<td valign="top">

-   Communication between the RFC sender adapter and backend systems is secured using Secure Network Communications \(SNC\).
-   SNC ensures the confidentiality, integrity, and authenticity of data transmitted across the network.



</td>
</tr>
<tr>
<td valign="top">

Sender System Verification Support

</td>
<td valign="top">

For ABAP sender systems, the adapter can verify the sender SID and client against the configured Access Control List \(ACL\) to ensure that only authorized sender systems can interact with the RFC sender channel.

</td>
</tr>
<tr>
<td valign="top">

Multiple Sender Systems Support

</td>
<td valign="top">

Multiple repositories can be defined for a single JCo Server based on sender system SID and client. This allows one RFC channel to receive calls from multiple sender systems simultaneously.

</td>
</tr>
<tr>
<td valign="top">

SAP Passports Support

</td>
<td valign="top">

SAP Passports are defined data structures that carry correlation information along with details about processing components. This passport information is transported as a header: SAP-PASSPORT.

</td>
</tr>
</table>

> ### Restriction:  
> -   Avoid registering multiple JCo Servers on the same gateway with the same program ID, as this leads to indeterministic processing.
> -   Multiple repository systems with the same SID for metadata reading aren't allowed.
> -   Unicode and non-Unicode systems are supported; however, MDMP systems aren't supported.
> -   The RFC sender adapter supports function modules only if they have at least one parameter \(import, export, changing, or tables\).
> -   SAP R/3 systems before Release 3.1H aren't supported.



<a name="loiof5568be44b474e44b267fc284a509094__section_qbq_4y1_1fc"/>

## Prerequisites

To configure the RFC sender adapter, you must:

-   Create a new destination of TCP/IP type in the ABAP system to establish a connection in the sender system. Note that this prerequisite step is only applicable to ABAP systems and doesn't apply to non-ABAP systems. For more information, see [Setting Up an RFC Destination for the RFC Adapter](https://help.sap.com/docs/SAP_NETWEAVER_750/5cf7d2de571a45cc81f91261668b7361/448f8cc0c5a43672e10000000a114a6b.html?q=Setting+Up+an+RFC+Destination+for+the+RFC+Adapter).
-   Create a new RFC destination with Proxy Type *Local* in BTP Destinations environment. For more information, see [Creating an RFC Destination](creating-an-rfc-destination-3b55fa7.md).
-   Set up SNC on Edge Integration Cell for productive use of the RFC sender adapter. For more information, see [Set Up SNC on Edge Integration Cell](../60-Security/set-up-snc-on-edge-integration-cell-c2315d3.md).
-   When you enable SNC, you should also activate it in the TCP/IP destinations. For more information, see [RFC: TCP/IP Connection](https://help.sap.com/doc/saphelp_nw73ehp1/7.31.19/en-us/4d/a8410336831f8de10000000a15822b/frameset.htm).



<a name="loiof5568be44b474e44b267fc284a509094__section_r3q_ykh_1fc"/>

## Configure the RFC Sender Adapter

The RFC Sender adapter acts as the server for RFC requests, transforming incoming RFC data into an RFC-XML format for further processing. Configure the RFC Sender adapter within your integration flow to handle the incoming RFC requests from SAP or third-party RFC systems. Once you have created a sender channel and selected the RFC Sender adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows:

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Enter the name of the RFC channel.

</td>
</tr>
</table>

Select the *Server Connection* tab and provide values in the fields as follows:

**Connection**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="9">

CONNECTION PROPERTIES

</td>
<td valign="top">

Connection Setup

</td>
<td valign="top">

Defines whether the JCo Server registers on one or multiple gateways. Depending on the selected option different sets of gateway properties should be configured.

> ### Note:  
> The JCo server is instantiated for each RFC sender channel. It registers itself with the SAP Gateway using a unique Program ID \(PID\) and listens for incoming RFC calls. The server is generic and not tied to any specific RFM interface, making it flexible and reusable.

Select one of the two options:

-   *Single Gateway \(default option\):*Configures the gateway connection information for the single gateway.
-   *Multiple Gateways:* Allows registration to all or some parts of an ABAP system, depending on the configured set of properties. As a prerequisite, in the TCP/IP destination configuration \(transaction SM59\) within the ABAP system, the gateway host, and service fields must be left empty. This ensures that the local gateway is used for each application server when establishing the connection to the server.



</td>
</tr>
<tr>
<td valign="top">

Program ID

</td>
<td valign="top">

Unique program ID for the connection on the configured gateway\(s\). It is a valid option for a single or multiple gateway setups.

</td>
</tr>
<tr>
<td valign="top">

Gateway Host

\(only if you select *Single Gateway* for Server Setup\)

</td>
<td valign="top">

Gateway host where the particular SAP gateway is running.

</td>
</tr>
<tr>
<td valign="top">

Gateway Service

\(only if you select *Single Gateway* for Server Setup\)

</td>
<td valign="top">

Gateway service where the particular SAP gateway is running.

</td>
</tr>
<tr>
<td valign="top">

Message Server Host

\(only if you select *Multiple Gateways* for Server Setup\)

</td>
<td valign="top">

The message server host from which information about the application servers is retrieved for use in the high availability setup.

</td>
</tr>
<tr>
<td valign="top">

Message Server Service

\(only if you select *Multiple Gateways* for Server Setup\)

</td>
<td valign="top">

The details of the message server service where the specific SAP Message Server is running.

</td>
</tr>
<tr>
<td valign="top">

Message Server System ID

\(only if you select *Multiple Gateways* for Server Setup\)

</td>
<td valign="top">

The system ID of the message server to which the system belongs.

</td>
</tr>
<tr>
<td valign="top">

Logon Group

\(only if you select *Multiple Gateways* for Server Setup\)

</td>
<td valign="top">

The logon group defined in ABAP that identifies a set of application servers to whose gateways the JCo server registers. If no logon group is specified in the configuration, registration occurs at the gateways of all application servers within that ABAP system.

</td>
</tr>
<tr>
<td valign="top">

Update Time \(in sec\)

\(only if you select *Multiple Gateways* for Server Setup\)

</td>
<td valign="top">

The frequency at which the list of application servers is retrieved from the message server.

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

CONNECTION POOL PROPERTIES

</td>
<td valign="top">

Initial Connections

</td>
<td valign="top">

The starting number of connections established with the gateway. The default value is 1.

</td>
</tr>
<tr>
<td valign="top">

Maximum Connections

</td>
<td valign="top">

The maximum number of connections that can be established with the gateway. The default value is 50.

</td>
</tr>
<tr>
<td valign="top">

Maximum Reconnect Delay \(in sec\)

</td>
<td valign="top">

The maximum delay time, in seconds, for server startup. In the event of connectivity issues with the gateway\(s\), the JCo server attempts to reconnect at intervals of 1, 2, 4, 8, 16, ..., up to the maximum delay, and then continue at the maximum interval. The default value is 3600 seconds.

</td>
</tr>
<tr>
<td valign="top">

ADVANCED PROPERTIES

</td>
<td valign="top">

Add Advanced JCo Properties

</td>
<td valign="top">

A set of custom JCo server properties that aren't included in the standard channel configuration. When you enable this option, you can define a key-value pair of JCo Server properties not specified in the standard channel configuration.

</td>
</tr>
</table>

Select the *Security* tab and provide values in the fields as follows:

**Security**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

SECURE NETWORK COMMUNICATION \(SNC\)

</td>
<td valign="top">

Enable SNC

</td>
<td valign="top">

Allows you to enable or disable SNC for the JCo Server. Available selections. The default setting is enabled.

</td>
</tr>
<tr>
<td valign="top">

SNC QoP \(only if *SNC Enabled* has been selected\)

</td>
<td valign="top">

The SNC Quality of Protection \(QoP\) configuration allows you to choose the appropriate level of security based on your requirements. The available levels are:

-   1- Open. No protection.
-   2- Integrity. Ensures data integrity.
-   3- Privacy. Ensures data privacy.
-   8- Default. Standard protection level.
-   9- Maximum. Highest protection level.



</td>
</tr>
<tr>
<td valign="top">

SNC Name \(only if the *Enable SNC* has been selected\)

</td>
<td valign="top">

The SNC name of the JCo server, which may be optional. This name corresponds to the unique identifier of the key pair used during the SNC setup. It follows the format: `p:<Distinguished Name>`. For example: `p:CN=miller, OU=ADMIN, O=myCompany, C=US`.

For more information, see [Set Up SNC on Edge Integration Cell](../60-Security/set-up-snc-on-edge-integration-cell-c2315d3.md)

</td>
</tr>
<tr>
<td valign="top">

SNC Access Control List \(only if *Enable SNC* has been selected\)

</td>
<td valign="top">

List of permitted SNC partner names. By default, it's set to \(no limitation\), allowing all partners. The format for SNC partner names is `p:<Distinguished Name>`, where the distinguished name is derived from the public certificates of the trusted partners. This configuration helps manage and restrict access to specific SNC partners based on their certificates.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

SENDER SYSTEM VERIFICATION

</td>
<td valign="top">

Verify Sender System

</td>
<td valign="top">

This option enables verification of sender systems. For ABAP sender systems, the sender SID and client are checked and verified. The default setting is true, but it should be deactivated for non-ABAP sender systems.

</td>
</tr>
<tr>
<td valign="top">

Allowed Sender Systems \(only if *Verify Sender System* has been selected\)

</td>
<td valign="top">

You can configure a comma-separated list of allowed sender systems using the following formats:

-   <SID\>: Represents the SAP System ID. If only the SID is configured, all clients within that system are allowed. Example: UF0, QW5.
-   <SID\>\#<Client\>: Specifies both the SAP System ID and a particular client. This format allows different sender systems with specific clients. Example: ABC\#200, DEF\#100. It can also be used to specify multiple clients within the same sender system. Example: QWO\#001, QWO\#002, QWO\#003.
-   <SID\>\#<Client\>,<SID\>: A combination of the above formats can be configured to allow specific clients and entire systems. Example: ABC\#200, QW5, DEF\#100, UF0.



</td>
</tr>
</table>

Select the *Repository System* tab and provide values in the fields as follows:

**Repository System**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

RFC METADATA REPOSITORY

</td>
<td valign="top">

Default Destination

</td>
<td valign="top">

Name of the RFC destination used as the client connection to an ABAP system for reading the Remote Function Module \(RFM\) metadata.

</td>
</tr>
<tr>
<td valign="top">

Multiple Repository Configuration

</td>
<td valign="top">

Allows you to configure multiple repositories for metadata reading based on the SAP System ID \(SID\) and Client. You can set up a semicolon-separated list of repositories using the following formats:

-   <SID\>\(<CLIENT\>\) = <DESTINATION NAME\>: Specifies the SAP System ID and Client, mapping them to a particular destination name. Example: ABC\(200\) = DEST1.
-   <SID\> = <DESTINATION NAME\>: Specifies the SAP System ID, mapping it to a destination name without specifying a client. Example: DEF = DEST2.

> ### Example:  
> -   *PRD\(100\)=PRD\_DDIC\_100;PRD\(200\) = PRD\_DDIC\_200;PRP=PRP\_DDIC*: This configuration specifies that for the SAP System ID *PRD*, client **100** uses the destination name *PRD\_DDIC\_100*. This directs calls from this specific client to the defined destination. Similarly, client *200* within the PRD system uses the destination name *PRD\_DDIC\_200*. This ensures that calls from this client are directed to its specified destination. Additionally, for the separate SAP System ID *PRP*, all calls are directed to the destination name *PRP\_DDIC*.
> 
> -   *PRD\(100\),PRD\(200\) = PRD\_DDIC\_100*: This configuration specifies that for the SAP System ID *PRD* with clients **100** and **200**, the destination name *PRD\_DDIC\_100* should be used. This means that calls from these specific clients is directed to the specified destination.
> 
> -   *PRD = PRD\_DDIC\_000*: This configuration specifies that for the SAP System ID *PRD* without specifying a client, the destination name *PRD\_DDIC\_000* should be used. This acts as a default for any client under the "PRD" SID that isn't specifically listed
> 
> 
> This setup allows a single RFC Sender channel to handle calls from multiple sender systems, each with its own set of Remote Function Modules \(RFMs\). By defining additional repositories using the sender system's SID and optional Client, you can manage different connections and metadata reads efficiently. If no specific match is found for a sender system and client combination, the default repository is used. This ensures that there is always a fallback destination for handling calls.



</td>
</tr>
</table>

