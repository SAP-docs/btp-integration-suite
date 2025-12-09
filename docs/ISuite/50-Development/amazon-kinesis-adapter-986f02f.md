<!-- loio986f02fd78934085ad45952e082ecbe8 -->

# Amazon Kinesis Adapter

Amazon Kinesis Adapter for SAP Integration Suite facilitates and accelerates connectivity to Amazon Kinesis Data Streams, streamlining data communication and enhancing real-time data processing.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio986f02fd78934085ad45952e082ecbe8__section_bhw_cmj_aiadapter"/>

## How the Amazon Kinesis Adapter works

Amazon Kinesis Adapter functions as a receiver adapter, after configuring the Amazon Kinesis Adapter, data exchange is performed as follows at runtime:SAP Integration Suite tenant sends the operation request to Amazon Kinesis Data Streams \(this is a receiver system\), Amazon Kinesis Data Streams works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio986f02fd78934085ad45952e082ecbe8__section_lx1_zmj_k2c"/>

## Configuring the Amazon Kinesis Adapter

**Connection**


<table>
<tr>
<th valign="top">

*Parameter*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Host*

</td>
<td valign="top">

Specify the host for the Amazon Kinesis Data Streams service.

Example: `amazonaws.com`

</td>
</tr>
<tr>
<td valign="top">

*Region Name*

</td>
<td valign="top">

Select the AWS region where the Data Stream resides.

Example: `eu-central-1 Europe (Frankfurt)`

If the required region is not listed in the dropdown, you can manually specify the value.

Example: `cn-north-1`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type:

-   *Access and Secret Key* for access with long-term credentials.
-   *Security Token Service \(AssumeRole\)* for temporary IAM role-based access.
-   *Security Token Service \(AssumeRoleWithWebIdentity\)* to use a Web Identity Provider.



</td>
</tr>
<tr>
<td valign="top">

*Access Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that stores the AWS Access Key.

</td>
</tr>
<tr>
<td valign="top">

*Secret Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that stores the AWS Secret Key.

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Entra ID Credential*

\(Only available when *Security Token Service \(AssumeRoleWithWebldentity\)* is selected.\)

</td>
<td valign="top">

Specify the OAuth2 Client Credentials security artifact created for Microsoft Entra ID as a Web Identity Provider.

> ### Note:  
> A trust should be established between Microsoft Entra ID and AWS account, which enables AWS to validate tokens issued by Entra ID and grant access to AWS services.



</td>
</tr>
<tr>
<td valign="top">

*External ID Alias*

\(Only available when *Security Token Service \(AssumeRole\)* is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the External ID, as defined in the condition of the IAM role’s trust relationship.

Example: `KinesisExternalID`

</td>
</tr>
<tr>
<td valign="top">

*Security Token Service URL*

</td>
<td valign="top">

Specify the URL used to fetch temporary credentials from the Security Token Service \(STS\) via the AssumeRole.

Default value: *https://sts.us-east-1.amazonaws.com/*

Example: `https://sts.<region>.amazonaws.com/` for a region-specific token, or `https://sts.amazonaws.com/` for global.

> ### Note:  
> AWS recommends using Regional STS endpoints within your applications and avoid using the global \(legacy\) STS endpoint.



</td>
</tr>
<tr>
<td valign="top">

*Role ARN Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact which stores the Amazon Resource Name \(ARN\) of the IAM role to be used for fetching temporary credentials via the Security Token Service \(STS\).

*To find your Role ARN:* AWS Console → IAM → Roles → \[Select Role\] → Summary → Copy Role ARN

Example: `arn:aws:iam::123456789:role/AWSRole_Test`

</td>
</tr>
<tr>
<td valign="top">

*Role Session Name*

</td>
<td valign="top">

Specify the Role Session Name for a session of the same role assumed with different principals.

Example: `kinesis-adapter-prod`

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable this property to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

*Parameter*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Configuration Type*

</td>
<td valign="top">

Select the required configuration type: *Basic* to use dropdowns and parameter text fields, or *Advanced* to specify request parameters that require a custom setup.

</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Select the required entity.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation to be performed for the selected entity.

</td>
</tr>
<tr>
<td valign="top">

*Request Payload Source*

</td>
<td valign="top">

Select an option to specify the source for request payload:

-   *UI Configurable* provides user-friendly fields to create the payload automatically.
-   *Exchange Body* allows you to specify the required structure and values.



</td>
</tr>
<tr>
<td valign="top">

*Stream ARN*

</td>
<td valign="top">

Specify the Amazon Resource Name \(ARN\) of the Kinesis Data Stream to be used for this operation.

*To find your Stream ARN:* AWS Console → Kinesis → Data Streams → \[Select Stream\] → Details → Copy Stream ARN

Example: `arn:aws:kinesis:us-east-1:123456789:stream/Test`

</td>
</tr>
<tr>
<td valign="top">

*Stream Name*

</td>
<td valign="top">

Specify the name of the Amazon Kinesis Data Stream to be used.

</td>
</tr>
<tr>
<td valign="top">

*Partition Key*

</td>
<td valign="top">

Specify the Partition Key for the record. A data stream can have multiple shards.

> ### Note:  
> This field determines which shard in the stream the data record is assigned to. Partition keys are Unicode strings with a maximum length of 256 characters.



</td>
</tr>
<tr>
<td valign="top">

*Encode Data*

</td>
<td valign="top">

Enable to encode the data being sent to Amazon Kinesis Data Streams. The stream expects data to be encoded in Base64 format.

> ### Note:  
> If the data is already encoded, this field should be disabled.



</td>
</tr>
<tr>
<td valign="top">

*Explicit Hash Key*

</td>
<td valign="top">

Specify the Explicit Hash Key for the record. It is a hash value that overrides the partition key hash to explicitly determine which shard the data record is assigned to.

</td>
</tr>
<tr>
<td valign="top">

*Retention Period \(in hrs\)*

</td>
<td valign="top">

Specify the Retention Period \(in hours\). If you have not changed the value after creation of the Stream then it should be `24` hours. Minimum can be `24` hours.

</td>
</tr>
<tr>
<td valign="top">

*Shard ID*

</td>
<td valign="top">

Specify the shard ID of the Amazon Kinesis Data Streams to perform the operation.

</td>
</tr>
<tr>
<td valign="top">

*Adjacent Shard ID*

</td>
<td valign="top">

Specify the ID of the adjacent shard that will be merged with the current shard.

</td>
</tr>
<tr>
<td valign="top">

*Shard Iterator*

</td>
<td valign="top">

Specify the position in the shard from which you want to start reading data records sequentially.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Results*

</td>
<td valign="top">

Specify the maximum results to be listed. The maximum permissible value is `10000`.

</td>
</tr>
<tr>
<td valign="top">

*New Starting Hash Key*

</td>
<td valign="top">

Specify the hash key value that will serve as the starting hash key for one of the child shards created by the split.

This value must fall within the current shard’s hash key range. All hash keys equal to or greater than this value are assigned to the new child shard, while lower hash keys remain with the other child shard.

</td>
</tr>
<tr>
<td valign="top">

*Shard Iterator Type*

</td>
<td valign="top">

Select the shard position from which to start reading data records.

-   *After Sequence Number*
-   *At Sequence Number*
-   *At Timestamp*
-   *Latest*
-   *Trim Horizon*



</td>
</tr>
<tr>
<td valign="top">

*Timestamp*

</td>
<td valign="top">

Specify the timestamp to use for the request.

> ### Note:  
> A timestamp is the Unix epoch date with precision in milliseconds.

Example:`1459799926.48`

</td>
</tr>
<tr>
<td valign="top">

*Starting Sequence Number*

</td>
<td valign="top">

Specify the sequence number of the data record in the shard from which to start reading.

</td>
</tr>
<tr>
<td valign="top">

*Stream Mode*

</td>
<td valign="top">

Select the capacity mode for the new Amazon Kinesis Data Stream mode:

-   *Provisioned*
-   *On-demand*



</td>
</tr>
<tr>
<td valign="top">

*Shard Count*

</td>
<td valign="top">

Specify the number of shards that the stream will use for this operation.

</td>
</tr>
<tr>
<td valign="top">

*Tag Key*

</td>
<td valign="top">

Specify the name of the tag.

Example: `Environment`

</td>
</tr>
<tr>
<td valign="top">

*Tag Value*

</td>
<td valign="top">

Specify the value of the tag.

Example: `Prod`

</td>
</tr>
<tr>
<td valign="top">

*Enforce Consumer Deletion*

</td>
<td valign="top">

Enable to force deletion of the stream even if it has registered consumers. If disabled, Delete Stream fails with a Resource In Use Exception when consumers are registered.

</td>
</tr>
<tr>
<td valign="top">

*Exclusive Start Stream Name*

</td>
<td valign="top">

Specify the name of the stream to start the list with.

</td>
</tr>
<tr>
<td valign="top">

*Exclusive Start Shard ID*

</td>
<td valign="top">

Specify the Shard ID from which to start the stream description. The response includes shards starting immediately after this Shard ID.

</td>
</tr>
<tr>
<td valign="top">

*Limit*

</td>
<td valign="top">

Specify the maximum number of records to be returned. Value ranges from 1 to 10000.

</td>
</tr>
<tr>
<td valign="top">

*Next Token*

</td>
<td valign="top">

Specify the next token received in a list response to fetch the next set of response.

</td>
</tr>
<tr>
<td valign="top">

*Shard Filter*

</td>
<td valign="top">

Enable to filter shards.

</td>
</tr>
<tr>
<td valign="top">

*Stream Creation Timestamp*

</td>
<td valign="top">

Specify the Stream creation timestamp to distinguish between data streams that have the same name.

For example, if you create a data stream and then delete it, and you later create another data stream with the same name, you can use this input parameter to specify which of the two streams you want to list the shards for.

> ### Note:  
> A timestamp is the Unix epoch date with precision in milliseconds.

Example:`1459799926.48`

</td>
</tr>
<tr>
<td valign="top">

*Shard Filter Type*

</td>
<td valign="top">

Select the shard filter type to retrieve the desired shards.

-   *After Shard ID*
-   *At Latest*
-   *At Timestamp*
-   *At Trim Horizon*
-   *From Timestamp*
-   *From Trim Horizon*



</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

</td>
<td valign="top">

Select the required HTTP method from the available dropdown.

</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

</td>
<td valign="top">

Specify the relative URL if required.

> ### Note:  
> This field is not mandatory to be populated unless explicitly required as per your configuration.



</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the query that should be transferred with the HTTP request.

Example: `param1=value1;param2=value2`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
</table>

