<!-- loioe8e6ba6a38a14041bdd630d3386a5d3e -->

# Configure the Splunk Receiver Adapter

Enables SAP Integration Suite to get data from the Splunk storage or to create, modify, or delete data on the Splunk storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the Splunk receiver adapter, you can configure the following attributes.

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

    Connects to Splunk using basic authentication.

-   *Splunk Token*

    Connects to Splunk using a Splunk token.

-   *None*

    Connects to Splunk without any authentication. This option is only available for `Add Data to Index` operation.

-   *Dynamic*

    Connects to Splunk using a dynamic value. The value is to be passed on as property \(`SAP_Splunk_Outbound_AuthenticationType`\).




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if *Basic Authentication* or *Dynamic* is selected for *Authentication*\)

</td>
<td valign="top">

Name of the *User Credentials* artifact that contains the user name and password.

See: [Deploying a User Credentials Artifact](deploying-a-user-credentials-artifact-6912d63.md)

</td>
</tr>
<tr>
<td valign="top">

*Splunk Token Alias*

\(only if *Splunk Token* or *Dynamic* is selected for *Authentication*\)

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

The type of proxy that you’re using to connect to the target system.

-   Select *Internet* if you’re connecting to a cloud system.

-   Select *On-Premise* if you’re connecting to an SAP Cloud Connector instance.

-   Select *Dynamic* if you’re using a dynamic value. The value is to be passed on as property \(`SAP_Splunk_Outbound_Proxy`\).


For more information, see [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(only if *On-Premise* or *Dynamic* is selected for *Proxy Type*\)

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

Specifies the time range, in milliseconds, that the client waits for a response before it times out; default value: `30000`.

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

*Product Type* 

</td>
<td valign="top">

You can select one of the following product types:

-   *Splunk Cloud Platform*

-   *Splunk Enterprise*


Depending on the chosen product type, you can select different operations.

</td>
</tr>
<tr>
<td valign="top">

*Operation Details* 

</td>
<td valign="top">

You can select from the following operations:

-   *Delete*

-   *Patch*

    This operation is not available when for *Product Type* you have selected *Splunk Enterprise*.

-   *Post*

-   *Query*


Which operations and methods are available for each product type, are listed under [Operations and Methods](operations-and-methods-a5ffb3f.md).

</td>
</tr>
<tr>
<td valign="top">

*Method* 

</td>
<td valign="top">

Which methods are available for each operation depends on the chosen product type. For more information, see [Operations and Methods](operations-and-methods-a5ffb3f.md).

</td>
</tr>
<tr>
<td valign="top">

*Model Name*

\(only if for *Method* one of the following options is selected: *Delete Data Model*, *Create Data Model*, *Modify Data Model*, or *Get Data Model*\)

</td>
<td valign="top">

Name of the model that is subject to the selected operation and method.

</td>
</tr>
<tr>
<td valign="top">

*Description*

\(only if for *Method* the option *Create Data Model* is selected\)

</td>
<td valign="top">

Description of the data model.

Use JSON format, for example:

`{"description":"demo"}`

</td>
</tr>
<tr>
<td valign="top">

*Username*

Only if for *Method* one of the following options is selected:

-   For Splunk Cloud Platform: *Delete Saved Search*, *Remove Input*, *Modify Input*, *Create Input*, *Run One Shot Search*, *Run Saved Search*, *View Named Saved Search*, *Edit Saved Search Permission* 

-   For Splunk Enterprise: *Delete Saved Search*, *Remove Input*, *Modify Input*, *Modify Index*, *Create Input*, *Create Index*, *Run One Shot Search*, *Run Saved Search*, *Get Input*, *View Named Saved Search*, *Add Data to TCP Input*, *Add Data to UDP Input*, *Enable Global Settings*\)




</td>
<td valign="top">

Splunk username. It is appended in the endpoint URL.

Example:

`https://host:port/serviceNS/username`

</td>
</tr>
<tr>
<td valign="top">

*Index Name*

Only if for *Method* one of the following options is selected:

-   For Splunk Cloud Platform: *Remove Index*, *Modify Index*, *Create Index*, *Get Index* 

-   For Splunk Enterprise: *Remove Index*, *Modify Index*, *Create Index*, *Get Index*




</td>
<td valign="top">

Name of the index that is subject to the selected operation and method.

If you keep indexing your data, all indexed data is stored in index, increasing the used disk space. At some point, you need to think of data retention to save disk space. The default value of data retention is 188697600 seconds \(approximately 6 years\). If you like to keep the historical data, depends on the use case. If you need 6 years of historical data, you can keep the settings same and estimate the disk space requirements appropriately.

> ### Note:  
> Example:
> 
> To set indexes to keep your data for 180 days, configure the `frozenTimePeriodInSecs` setting in `indexes.conf` accordingly:
> 
> `frozenTimePeriodInSecs = 15552000` \(180 Days\)



</td>
</tr>
<tr>
<td valign="top">

*Input Name*

\(only if for *Method* one of the following options is selected: *Remove Input*, *Create Input*, *Get Input*, *Modify Input*\)

</td>
<td valign="top">

Name of the input that is subject to the selected operation and method.

</td>
</tr>
<tr>
<td valign="top">

*Response Format* 

</td>
<td valign="top">

Response format. The following options are available:

-   *JSON*

-   *XML*

-   *Dynamic*

    Select this option if you’re using a dynamic value. The value is to be passed on as property \(`SAP_Splunk_Outbound_ResponseFormat`\).




</td>
</tr>
<tr>
<td valign="top">

*Additional Request Parameters* 

</td>
<td valign="top">

Choose *Add* and maintain the values of the *Key* and *Value* fields.

</td>
</tr>
<tr>
<td valign="top">

*Key* 

</td>
<td valign="top">

Name of request parameter.

The following keys are supported:

actions

alert\_type

auto\_cancel

auto\_finalize\_ec

auto\_pause

cron\_schedule

datatype

description

earliest\_time

force\_bundle\_replication

frozenTimePeriodInSecs

host

actions

alert\_type

auto\_cancel

auto\_finalize\_ec

auto\_pause

cron\_schedule

datatype

description

earliest\_time

force\_bundle\_replication

frozenTimePeriodInSecs

host

</td>
</tr>
<tr>
<td valign="top">

*Value* 

</td>
<td valign="top">

Value of the property.

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}`.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Search Name* 

</td>
<td valign="top">

Rrelevant search name:

-   normal

-   realtime


If set to `realtime`, search runs over live data. By default, the option `normal` is used.

</td>
</tr>
<tr>
<td valign="top">

*Search* 

</td>
<td valign="top">

Search ID number to get results of a particular search.

</td>
</tr>
<tr>
<td valign="top">

*Search Query* 

</td>
<td valign="top">

Search query for Splunk system.

</td>
</tr>
<tr>
<td valign="top">

*Search ID* 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Execution Mode* 

</td>
<td valign="top">

-   The *Run One Shot Search* method only supports execution mode `oneshot`.

-   The *Run Blocking Search* method only supports execution mode `blocking`.




</td>
</tr>
<tr>
<td valign="top">

*Owner* 

</td>
<td valign="top">

Username of resource owner \(default: resource creator\). This parameter is required for updating any knowledge object ACL properties.

</td>
</tr>
<tr>
<td valign="top">

*Sharing* 

</td>
<td valign="top">

Indicates how the resource is shared. This parameter is required for updating any knowledge object ACL properties.

-   *app*: Shared within a specific app.

-   *global* \(default\): Shared globally to all apps.

-   *user*: Private to a user.




</td>
</tr>
<tr>
<td valign="top">

*Token* 

</td>
<td valign="top">

Token that is to be retrieved from the getinput/createinput operation.

</td>
</tr>
<tr>
<td valign="top">

*Event*

\(only if for *Method* one of the following options is selected: *Add Data to Index*\)

</td>
<td valign="top">

Specify "event" in JSON format to add data to index.

Example:

`{"event": "Hello, world!"}`

</td>
</tr>
<tr>
<td valign="top">

*Port No*

\(only if for *Method* one of the following options is selected: *Add Data to TCP Input*, *Add Data to UDP Input*\)

</td>
<td valign="top">

Name of port to perform create operation.

Example:

`443`

</td>
</tr>
<tr>
<td valign="top">

*Disabled*

\(only if for *Method* one of the following options is selected: *Enable Global Settings*\)

</td>
<td valign="top">

Specify value `0` to disable permission and `1` to enable permission.

</td>
</tr>
</table>

