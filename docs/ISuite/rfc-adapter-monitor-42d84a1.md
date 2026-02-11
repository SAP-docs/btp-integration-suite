<!-- loio42d84a1f578e422a949c5ef0b045cb35 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# RFC Adapter Monitor

Monitor the underlying JCo entities of the integration flows deployed with the RFC adapter.

The *RFC Adapter* card shows four different entities, and the number of items associated with them:

-   *JCo Connections*
-   *JCo Servers*
-   *JCo Destinations*
-   *Metadata Repositories*

You can select any of these entities to navigate to a more detailed view.

Some entities may include navigation links. These links lead you to the detailed view of the entity where a filter is already applied. For example, you can select *Alive* on *JCo Server*, and the servers view opens, filtering for servers in the *Alive* state.

At the bottom of the card, you find a link named :wrench: *Global RFC Adapter Properties*. Use this link to view and configure global properties for the RFC adapter. For more information, see [Global RFC Adapter Properties](rfc-adapter-monitor-42d84a1.md#loio42d84a1f578e422a949c5ef0b045cb35__section_hrn_pdk_y2w).

> ### Note:  
> The *RFC Adapter* card only displays information if there's at least one integration flow deployed on Edge Integration Cell using the RFC sender or receiver adapter. If there's no data to show, a message appears in the card, and you can’t interact with it.



<a name="loio42d84a1f578e422a949c5ef0b045cb35__section_zvf_zzj_y2c"/>

## JCo Connections

The *JCo Connections* view shows all the JCo connections \(client and server\) currently available in the system.

You can filter the list of connections to quickly locate specific information. Use *Adapt Filters* to choose which filters are displayed.

The overview table provides the following information:

****


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

*Pod*

</td>
<td valign="top">

The associated pod.

</td>
</tr>
<tr>
<td valign="top">

*Connection Handle*

</td>
<td valign="top">

The unique ID of the connection per pod.

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

The type of connection. It can be either *Server* or *Client*.

</td>
</tr>
<tr>
<td valign="top">

*Held By*

</td>
<td valign="top">

The parent object of the connection. It can be either JCo server or JCo destination. You can navigate to the parent object via the link.

</td>
</tr>
<tr>
<td valign="top">

*Group*

</td>
<td valign="top">

The identifier of a connection's group.

</td>
</tr>
<tr>
<td valign="top">

*State*

</td>
<td valign="top">

The state of the connection. It can be either *Idle* of *Active*.

</td>
</tr>
<tr>
<td valign="top">

*Last Activity*

</td>
<td valign="top">

When the connection was last active.

</td>
</tr>
<tr>
<td valign="top">

*Thread ID*

</td>
<td valign="top">

This column is hidden by default but can be made visible via the table settings. It shows the thread name where the connection was last used.

</td>
</tr>
<tr>
<td valign="top">

*Conversation ID*

</td>
<td valign="top">

This column is hidden by default but can be made visible via the table settings. It shows the current conversation ID, which may be empty for inactive server connections.

</td>
</tr>
</table>

You can select any connection from the table to view more detailed information, such as the target ABAP system.



<a name="loio42d84a1f578e422a949c5ef0b045cb35__section_kwp_jck_y2c"/>

## JCo Servers

The *JCo Servers* view displays all JCo servers currently available in the system. Each RFC sender channel in the integration flow generates a JCo server object, which acts as an object that listens for incoming RFC calls. Typically, a JCo server holds one or more connections of the server type.

The overview table provides the following information:

****


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

*Pod*

</td>
<td valign="top">

The associated pod.

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

The name of the server. Made out of a prefix plus the name of the integration flow.

</td>
</tr>
<tr>
<td valign="top">

*Group*

</td>
<td valign="top">

The identifier of a server's group.

</td>
</tr>
<tr>
<td valign="top">

*State*

</td>
<td valign="top">

The state of the server. It can be *Alive*, *HA Broken*, *Started*, *Dead*, *Stopping*, or *Stopped*.

</td>
</tr>
<tr>
<td valign="top">

*Connections*

</td>
<td valign="top">

The number of connections the JCo server has.

</td>
</tr>
</table>

Select any server to view more detailed information about it and see the list of corresponding JCo server connections. You can further drill-down into connection details by selecting a connection from the table.



<a name="loio42d84a1f578e422a949c5ef0b045cb35__section_hrn_pdk_y2c"/>

## JCo Destinations

The *JCo Destination* view shows all the JCo destinations currently available in the system. These destinations issue outgoing RFC calls to the ABAP system. The RFC receiver adapter in the integration flow uses them to send messages via the RFC protocol to an ABAP system. Both adapters also use them to retrieve metadata from the ABAP system.

The overview table provides the following information:

****


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

*Pod*

</td>
<td valign="top">

The associated pod.

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

The name of the destination. Made out of a prefix and the name of the target ABAP system.

</td>
</tr>
<tr>
<td valign="top">

*Group*

</td>
<td valign="top">

The identifier of a destination's group.

</td>
</tr>
<tr>
<td valign="top">

*Last Activity*

</td>
<td valign="top">

When this destination was last active.

</td>
</tr>
<tr>
<td valign="top">

*Connections*

</td>
<td valign="top">

The number of connections this JCo destination has.

</td>
</tr>
</table>

> ### Note:  
> Some destinations might not have any connections. Once a client connection closes, it gets removed soon. If a destination doesn't have any connections, it gets removed shortly as well.

Select any destination to view more detailed information and see the list of corresponding JCo server connections. You can further drill-down into connection details by selecting a connection from the table.



<a name="loio42d84a1f578e422a949c5ef0b045cb35__section_dpq_1fk_y2c"/>

## Metadata Repositories

The *Metadata Repository* detail view displays the number and types of currently cached objects. Both sender and receiver adapters use RFC metadata to transform messages from the native RFC format into XML format. The system stores RFC metadata internally in a cache. Each metadata repository corresponds to a connected ABAP system, and a JCo destination retrieves metadata from the system.

The overview table provides the following information:

****


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

*ID*

</td>
<td valign="top">

The identifier of the object. It usually corresponds to the SID of the connected ABAP system.

</td>
</tr>
<tr>
<td valign="top">

*Pod*

</td>
<td valign="top">

The associated pod.

</td>
</tr>
<tr>
<td valign="top">

*JCo Destinations*

</td>
<td valign="top">

The number of JCo destinations. If several JCo destinations are configured per each metadata repository, it's non-deterministic which retrieves the data.

</td>
</tr>
<tr>
<td valign="top">

*Last Activity*

</td>
<td valign="top">

The last time this repository was active.

</td>
</tr>
</table>

You can select any repository to view more detailed information about the repository, the metadata cache, and the corresponding JCo destinations.

In the*Metadata Cache* section, you have the option to reset the cache of the selected repository. This is necessary when the structure definition changes in the original repository and isn't yet reflected in the cache. When you choose *Reset Cache*, you delete all cached metadata on all pods where the selected repository exists. On the next request, the system fetches metadata directly from the ABAP system and re-caches it.

> ### Note:  
> Resetting the cache requires administrative permissions, so only administrators can use this function.

You can further drill down into JCo destination details by selecting a destination from the table. From there, you can navigate to JCo connection and view the JCo connection details.



<a name="loio42d84a1f578e422a949c5ef0b045cb35__section_hrn_pdk_y2w"/>

## Global RFC Adapter Properties

This view provides a simplified representation of the RFC adapter properties, which appear as runtime parameters for worker in *Component Monitor*. For more information, see [Runtime Parameters](runtime-parameters-63c5276.md).

Choose *Edit* to configure the global properties of the RFC adapter.

The following properties are available:

**Connection Pool**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Default Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Pool Check Interval \(s\)*

</td>
<td valign="top">

3,600

</td>
<td valign="top">

The RFC adapter creates a pool of connections for each sender channel based on the initial connection count. This property specifies how often the system checks the connection utilization in the pool. It can also resize the pool by increasing the number of connections. A check rate of zero means no check is performed.

</td>
</tr>
<tr>
<td valign="top">

*Connection Load Threshold*

</td>
<td valign="top">

0

</td>
<td valign="top">

A new connection in the pool starts only when a threshold is reached. If the current pool size \(available connections\) minus the value of this property is less than or equal to the number of currently working connections, a new connection starts. A value of zero means a new connection starts only if all available connections are working. If the value is larger, a new connection starts before all available connections are working.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Pool Size*

</td>
<td valign="top">

50

</td>
<td valign="top">

The global adapter limit for the connection pool size.

</td>
</tr>
</table>

**RFC to XML Conversion**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Default Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Include XML Preamble*

</td>
<td valign="top">

True

</td>
<td valign="top">

Determines whether an XML preamble is added to the RFC-XML.

</td>
</tr>
<tr>
<td valign="top">

*Ignore Base64 Validation*

</td>
<td valign="top">

False

</td>
<td valign="top">

If set to true, base64 incompatible characters can be decoded from RFC-XML.

</td>
</tr>
<tr>
<td valign="top">

*Invalid Characters Handling*

</td>
<td valign="top">

Ignore

</td>
<td valign="top">

This means that there's no handling of invalid XML characters. The value "substitute" means invalid characters are replaced with character "\#".

</td>
</tr>
</table>

**Related Information**  


[RFC Adapter](50-Development/rfc-adapter-98a3c19.md "Connects an SAP Cloud Integration tenant to a remote receiver system using Remote Function Call (RFC).")

