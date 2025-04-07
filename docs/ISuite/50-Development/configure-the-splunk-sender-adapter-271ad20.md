<!-- loio271ad20bef0b4bb5a4e0977b1f6a3a11 -->

# Configure the Splunk Sender Adapter

Enables SAP Integration Suite to receive search-related information from the Splunk storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a sender channel and selected the Splunk sender adapter, you can configure the following attributes.

Select the *General* tab to access the following parameters.

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

*Name* 

</td>
<td valign="top">

Enter the name of the Splunk channel.

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

Shows *Splunk* as adapter type.

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

Shows *HTTPS* as transport protocol.

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

Shows *REST* as message protocol.

</td>
</tr>
</table>

You can provide more information in the *Description* field.

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


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

*Address* 

</td>
<td valign="top">

Base URL of the Splunk server.

Example:

`https://host:port`

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Authorization option for the sender.

You can select one of the following options:

-   *Basic Authentication*

    Connects to Splunk account using basic authentication.

-   *Splunk Token*

    Connects to Splunk account using a splunk token.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if *Basic Authentication* is selected for *Authentication*\)

</td>
<td valign="top">

Name of the *User Credentials* artifact that contains the user name and password.

See: [Deploying a User Credentials Artifact](deploying-a-user-credentials-artifact-6912d63.md)

</td>
</tr>
<tr>
<td valign="top">

*Splunk Token Alias*

\(only if *Splunk Token* is selected for *Authentication*\)

</td>
<td valign="top">

Name of the *Secure Parameter* artifact that contains the Splunk token credentials.

See: [Deploying a Secure Parameter Artifact](deploying-a-secure-parameter-artifact-4641d6c.md)

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

Ttype of proxy that you’re using to connect to the target system.

Select *Internet* if you’re connecting to a cloud system.

Select *On-Premise* if you’re connecting to an SAP Cloud Connector instance.

For more information, see [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(only if *On-Premise* is selected for *Proxy Type*\)

</td>
<td valign="top">

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration on the cloud side.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Specifies the amount of time, in milliseconds, that the client waits for a response before it times out; default value: `30000`.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


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

*Method* 

</td>
<td valign="top">

Method to perform further operations.

-   *On Run Export Search*

    This method returns a large set of results.

-   *On Run Normal Search*

    This method returns a search job immediately. Set `search_mode` to `normal` for this search. If `search_mode` isn't specified, by default it's set to normal.

-   *On Run Real Time Search*

    This method returns live events as they are indexed. Set `search_mode` to `realtime` for this search.




</td>
</tr>
<tr>
<td valign="top">

*Search Query* 

</td>
<td valign="top">

Search query for Splunk system.

Example:

`search index = "indexname*"`

> ### Note:  
> Spaces are not allowed. As a suffix, only `_` is allowed



</td>
</tr>
<tr>
<td valign="top">

*Search Time Range* 

</td>
<td valign="top">

Time range to retrieve the data for the particular time period from Splunk.

When you select *Custom Range*, you can specify the parameters *Earliest Time* and *Latest Time*. Otherwise, multiple options are available to specify the time range.

*Earliest Time* and *Latest Time* are mandatory parameters, and *Condition* is an optional one.

</td>
</tr>
<tr>
<td valign="top">

*Earliest Time*

\(only if *Custom Range* is selected for *Search Time Range*\)

</td>
<td valign="top">

Beginning point of time range or exact timestamp where you want to start the search. You can either use a standard unit of measure or enter an absolute timestamp in the format `MM/DD/YY: HH:MM:SS`. For example, enter `4` and select `Hour` as unit, to specify: 4 hours from now. Alternatively, enter the exact timestamp, for example `10/18/2022: 14:50:00`. You can also use the specific formats supported by Splunk.

</td>
</tr>
<tr>
<td valign="top">

*Latest Time*

\(only if *Custom Range* is selected for *Search Time Range*\)

</td>
<td valign="top">

Ending point of time range or exact timestamp where you want to end the search. You can either use a standard unit of measure or enter an absolute timestamp in the format `MM/DD/YY: HH:MM:SS`. For example, enter `2` and select `Hour` as unit to specify: for 2 hours from now. Alternatively, enter the exact timestamp, for example `10/18/2022: 16:50:00`. You can also use the specific formats supported by Splunk.

</td>
</tr>
<tr>
<td valign="top">

*Condition* 

</td>
<td valign="top">

Condition to filter out the results in the required format, for example: `| stats count | where count > 1000`.

You can implement scheduled alerts from SAP Cloud Integration using this parameter.

</td>
</tr>
<tr>
<td valign="top">

*Query Response Format*

\(only if *On Run Export Search* is selected for *Method*\)

</td>
<td valign="top">

Query response format \(*JSON* or *XML*\).

</td>
</tr>
<tr>
<td valign="top">

*Additional Request Parameters*

\(only if *On Run Export Search* is selected for *Method*\)

</td>
<td valign="top">

Choose *Add* and maintain the values of the *Key* and *Value* fields.

</td>
</tr>
<tr>
<td valign="top">

*Key*

\(only if *On Run Export Search* is selected for *Method*\)

</td>
<td valign="top">

Name of request parameter.

The following keys are supported:

auto\_cancel

auto\_finalize\_ec

auto\_pause

enable\_lookups

force\_bundle\_replication

id

index\_earliest

index\_latest

max\_time

namespace

now

reload\_macros

remote\_server\_list

required\_field\_list

rf

rt\_blocking

rt\_indexfilter

rt\_maxblocsecs

rt\_queue\_size

search\_listener

sync\_bundle\_replication

time\_format

timeout

</td>
</tr>
<tr>
<td valign="top">

*Value*

\(only if *On Run Export Search* is selected for *Method*\)

</td>
<td valign="top">

Value of the property.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Username*

\(only if *On Run Normal Search* or *On Run Real Time Search* is selected for *Method*\)

</td>
<td valign="top">

Splunk username. It is appended in the endpoint URL.

Example:

`https://host:port/serviceNS/username`

</td>
</tr>
<tr>
<td valign="top">

*Search Mode*

\(only if *On Run Normal Search* or*On Run Real Time Search* is selected for *Method*\)

</td>
<td valign="top">

Valid values:

-   normal

-   realtime


If set to `realtime`, search runs over live data. By default, `normal` is used.

</td>
</tr>
</table>

