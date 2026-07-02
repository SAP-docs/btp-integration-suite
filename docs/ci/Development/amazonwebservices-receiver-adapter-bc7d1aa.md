<!-- loiobc7d1aac1c494af591f8edd5c52bea0f -->

# AmazonWebServices Receiver Adapter

Use the receiver adapter to accelerate the implementation time and reduce the complexity of connecting to AWS. You configure the receiver channel with the AWS adapter, based on a desired protocol, to streamline Outbound data transfer to AWS platform. The adapter supports the following protocols:

-   S3: Simple Cloud Storage

-   SQS: Simple Queue Service 

-   SNS: Simple Notification Service

-   SWF: Simple Workflow Service


> ### Note:  
> You need to download the adapter from SAP Software Download Center. You can find more information on the download navigation path [here](https://api.sap.com/package/AmazonWebServicesAdapter?section=Overview).
> 
> After you complete the download, uncompress and extract the files to your local system. Then deploy the adapter on your tenant.
> 
> -   For more information on deploying the adapter in multicloud environment, see [Importing Custom Integration Adapter](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/482286e544014098874fde0da4bcca2c.html).
> 
> -   For tenants hosted on Neo environment, you must import the adapter to your Eclipse tool and deploy the adapter project. For more information see, [Develop Adapter](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/f798db6491424460bb4b43d4a86ed1cf.html).



The following tables describe the parameters that you need to configuration for a selected protocol.



### S3 Protocol

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

*Host* 

</td>
<td valign="top">

Specify the domain of the AWS region.

Defualt value: amazonaws.com

</td>
</tr>
<tr>
<td valign="top">

*Region Name* 

</td>
<td valign="top">

Select the AWS Region. If the region doesn’t exist in the preconfigured list, then the user can manually enter the region name in the text box.

</td>
</tr>
<tr>
<td valign="top">

*Bucket Name* 

</td>
<td valign="top">

Specify the name of the bucket to be used.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type.

-   *Access and Secret Key* for access with long term credentials.
-   *Security Token Service \(AssumeRole\)*for temporary IAM role-based access.
-   *Security Token Service \(AssumeRoleWithWebldentity\)* to use an Identity Provider.
-   *Security Token Service \(IAMRolesAnywhere\)* to use IAM Roles on systems outside of AWS.



</td>
</tr>
<tr>
<td valign="top">

*Access Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS access key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*Secret Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS secret key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*OIDC Credential Name*

\(Only available when Security Token Service \(AssumeRoleWithWebldentity\) is selected.\)

</td>
<td valign="top">

Specify the OAuth2 Client Credentials security artifact created for a Web Identity Provider.

Example: Microsoft Entra ID or SAP IAS.

</td>
</tr>
<tr>
<td valign="top">

*Role ARN Alias*

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Role ARN.

</td>
</tr>
<tr>
<td valign="top">

*Role Session Name*

</td>
<td valign="top">

Specify the Role Session Name for a session of the same role assumed with different principals.

</td>
</tr>
<tr>
<td valign="top">

*External ID Alias*

\(Only available when Security Token Service \(AssumeRole\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the External ID, as defined in the condition of the IAM role’s trust relationship.

</td>
</tr>
<tr>
<td valign="top">

*Profile ARN Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the profile ARN. A profile defines which IAM roles can be assumed and applies session policies to control the permissions granted to authenticated workloads.

</td>
</tr>
<tr>
<td valign="top">

*Trust Anchor Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Trust Anchor ARN. A trust anchor is the configured Certificate Authority \(CA\) that IAM Roles Anywhere trusts to verify certificates and grant access to IAM roles.

</td>
</tr>
<tr>
<td valign="top">

*Key Pair Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the alias of the key pair \(private key and certificate\) stored in the Keystore.

</td>
</tr>
<tr>
<td valign="top">

*Requester Pays*

</td>
<td valign="top">

Select the checkbox to make the requester pay for the data transfer and the request.

</td>
</tr>
<tr>
<td valign="top">

*Enable Legacy Connectivity*

</td>
<td valign="top">

Select this option to enable the AWS legacy connectivity.

> ### Note:  
> This option is disabled by default.



</td>
</tr>
</table>

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

*Operation*

</td>
<td valign="top">

Select to specify if the files are written or read from the S3 bucket. The default value is Write Operation. Select from the following options:

-   *Write Operation* 
-   *Read Operation* 
-   *List Operation*



</td>
</tr>
<tr>
<td valign="top">

*Directory*

</td>
<td valign="top">

Specify the location on the S3 bucket where the file is written.

> ### Example:  
> Directory/SubDirectory

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the name of the file to be written. If the field is left blank, the filename is created using the message ID.

> ### Example:  
> `Test.json`

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
<tr>
<td valign="top">

*Append Timestamp*

</td>
<td valign="top">

Select to append the date and timestamp to the filename.

</td>
</tr>
<tr>
<td valign="top">

*Append MessageId*

</td>
<td valign="top">

Use this option to append messageId to the filename.

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

</td>
<td valign="top">

Specify the MIME type of the file to be written.

> ### Example:  
> "application/xml" or "text/plain"

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
<tr>
<td valign="top">

*Content Encoding*

</td>
<td valign="top">

Specify the content encoding of the file.

> ### Example:  
> gzip

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
<tr>
<td valign="top">

*Storage Class*

</td>
<td valign="top">

Select the AWS Storage Class from the following options:

-   *Glacier*

-   *Glacier Deep Archive* 

-   *Intelligent-Tiering*

-   *One Zone-Infrequent Access*

-   *Reduced Redundancy*

-   *Standard*

-   *Standard-Infrequent Access*




</td>
</tr>
<tr>
<td valign="top">

*Existing File Handling*

</td>
<td valign="top">

Select the file handling behavior, if a file with the same name exists in the directory, from the following options:

-   *Fail*: Select this option to raise an exception 

-   *Ignore*: Select this option to ignore the file 

-   *Overwrite*: Select this option to overwrite the existing file




</td>
</tr>
<tr>
<td valign="top">

*Upload Message Attachments*

</td>
<td valign="top">

Select this option to upload each message attachment in the exchange as an S3 object.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

\(only if  Operation is Read Operation\)

</td>
<td valign="top">

Specify the action taken after the file is processed. Select from the following options:

-   Delete File

-   Keep File

-   Move File to an Archive directory

-   Copy file to an Archive Bucket

-   Move file to an Archive Bucket




</td>
</tr>
<tr>
<td valign="top">

*Customer Decryption Key Alias*

\(only if  Operation is Read Operation\)

</td>
<td valign="top">

Specify the name of the secured parameter that contains the decryption key for the Amazon S3 to decrypt data.

</td>
</tr>
<tr>
<td valign="top">

*Max Keys*

</td>
<td valign="top">

Specify the maximum number of keys to be returned in the response. This value cannot exceed 1000.

Example: "750".

</td>
</tr>
<tr>
<td valign="top">

*Include Sub-Directories*

</td>
<td valign="top">

Select the checkbox to list all the files in the directory and subdirectory.

</td>
</tr>
<tr>
<td valign="top">

*Continuation Token*

</td>
<td valign="top">

Specify the token to continue listing on the current bucket.

Example: "place\_holder".

</td>
</tr>
<tr>
<td valign="top">

*Sorting*

</td>
<td valign="top">

The property on which sorting should be done while listing the files. The sorting will be done in ascending order of the option selected. Available options:

-   File Name: The sorting is performed based on the filename.

-   File Size: Sorting is performed based on file size.

-   Time Stamp: Sorting is performed based on the timestamp.

-   None \(default\): No sorting is performed. This is the default option for sorting.




</td>
</tr>
</table>

**Advanced**


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

*Encryption Option*

</td>
<td valign="top">

Select the server-side encryption, used for storing the file in AWS, from the following options:

-   SSE-C \(with Customer-Provided Key\)

-   SSE-KMS \(with Customer Master Keys Stored in AWS Key Management Service\)

-   SSE-S3 \(with Amazon S3-Managed Keys\)

-   The default value is NONE




</td>
</tr>
<tr>
<td valign="top">

*Custom Metadata*

</td>
<td valign="top">

Specify any additional header name-value pairs that you want to send to AWS.

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
</table>



### SQS Protocol

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

*Host* 

</td>
<td valign="top">

Specify the domain of the AWS region.

Defualt value: amazonaws.com

</td>
</tr>
<tr>
<td valign="top">

*Region Name* 

</td>
<td valign="top">

Select the AWS Region. If the region doesn’t exist in the preconfigured list, then the user can manually enter the region name in the text box.

</td>
</tr>
<tr>
<td valign="top">

*Account Number* 

</td>
<td valign="top">

Specify the 12-digit AWS account number for the queue.

</td>
</tr>
<tr>
<td valign="top">

*Queue Name*

</td>
<td valign="top">

Specify the AWS Queue name where the data needs to be written.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type.

-   *Access and Secret Key* for access with long term credentials.
-   *Security Token Service \(AssumeRole\)* for temporary IAM role-based access.
-   *Security Token Service \(AssumeRoleWithWebldentity\)* to use an Identity Provider.
-   *Security Token Service \(IAMRolesAnywhere\)* to use IAM Roles on systems outside of AWS.



</td>
</tr>
<tr>
<td valign="top">

*Access Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS access key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*Secret Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS secret key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*OIDC Credential Name*

\(Only available when Security Token Service \(AssumeRoleWithWebldentity\) is selected.\)

</td>
<td valign="top">

Specify the OAuth2 Client Credentials security artifact created for a Web Identity Provider.

Example: Microsoft Entra ID or SAP IAS.

</td>
</tr>
<tr>
<td valign="top">

*Role ARN Alias*

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Role ARN.

</td>
</tr>
<tr>
<td valign="top">

*Role Session Name*

</td>
<td valign="top">

Specify the Role Session Name for a session of the same role assumed with different principals.

</td>
</tr>
<tr>
<td valign="top">

*External ID Alias*

\(Only available when Security Token Service \(AssumeRole\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the External ID, as defined in the condition of the IAM role’s trust relationship.

</td>
</tr>
<tr>
<td valign="top">

*Profile ARN Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the profile ARN. A profile defines which IAM roles can be assumed and applies session policies to control the permissions granted to authenticated workloads.

</td>
</tr>
<tr>
<td valign="top">

*Trust Anchor Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Trust Anchor ARN. A trust anchor is the configured Certificate Authority \(CA\) that IAM Roles Anywhere trusts to verify certificates and grant access to IAM roles.

</td>
</tr>
<tr>
<td valign="top">

*Key Pair Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the alias of the key pair \(private key and certificate\) stored in the Keystore.

</td>
</tr>
</table>

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

*Delays*

</td>
<td valign="top">

Specify the duration \(in seconds\) after which messages become available for processing. Valid values: 0–900 .

</td>
</tr>
<tr>
<td valign="top">

*Message Deduplication ID*

</td>
<td valign="top">

Specify the message deduplication ID.

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
<tr>
<td valign="top">

*Message Group ID*

</td>
<td valign="top">

Specify the message group ID.

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
</table>

**Advanced**


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

*Enable Large Payload*

</td>
<td valign="top">

Enable the checkbox to process large-size messages. If this option is enabled, then all the payload having a size above the specified threshold will be sent via an S3 bucket and a notification with the S3 object Id will be received in the SQS Queue.

</td>
</tr>
<tr>
<td valign="top">

*Message Size Threshold*

\(Only available when Enable Large Payload is enabled.\)

</td>
<td valign="top">

The threshold value of the payload size above which the payload will be sent to the S3 bucket. Possible values: 0 to 262144 \(256Kb\).

The Default Value is 262144 \(256Kb\).

</td>
</tr>
<tr>
<td valign="top">

*Bucket Name*

\(Only available when Enable Large Payload is enabled.\)

</td>
<td valign="top">

Enable the checkbox to process large-size messages. If this option is enabled, then all the payload having a size above the specified threshold will be sent via an S3 bucket and a notification with the S3 object Id will be received in the SQS Queue.

</td>
</tr>
<tr>
<td valign="top">

*Message Attribute*

</td>
<td valign="top">

Specify any additional message attribute name-value pairs that you can send to AWS.

</td>
</tr>
</table>



### SNS Protocol

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

*Host* 

</td>
<td valign="top">

Specify the domain of the AWS region.

Defualt value: amazonaws.com

</td>
</tr>
<tr>
<td valign="top">

*Region Name* 

</td>
<td valign="top">

Select the AWS Region. If the region doesn’t exist in the preconfigured list, then the user can manually enter the region name in the text box.

</td>
</tr>
<tr>
<td valign="top">

*Account Number* 

</td>
<td valign="top">

Specify the 12-digit AWS account number for the queue.

</td>
</tr>
<tr>
<td valign="top">

*Topic Name*

</td>
<td valign="top">

Specify the AWS Topic name.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type.

-   *Access and Secret Key*for access with long term credentials.
-   *Security Token Service \(AssumeRole\)* for temporary IAM role-based access.
-   *Security Token Service \(AssumeRoleWithWebldentity\)*to use an Identity Provider.
-   *Security Token Service \(IAMRolesAnywhere\)* to use IAM Roles on systems outside of AWS.



</td>
</tr>
<tr>
<td valign="top">

*Access Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS access key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*Secret Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS secret key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*OIDC Credential Name*

\(Only available when Security Token Service \(AssumeRoleWithWebldentity\) is selected.\)

</td>
<td valign="top">

Specify the OAuth2 Client Credentials security artifact created for a Web Identity Provider.

Example: Microsoft Entra ID or SAP IAS.

</td>
</tr>
<tr>
<td valign="top">

*Role ARN Alias*

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Role ARN.

</td>
</tr>
<tr>
<td valign="top">

*Role Session Name*

</td>
<td valign="top">

Specify the Role Session Name for a session of the same role assumed with different principals.

</td>
</tr>
<tr>
<td valign="top">

*External ID Alias*

\(Only available when Security Token Service \(AssumeRole\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the External ID, as defined in the condition of the IAM role’s trust relationship.

</td>
</tr>
<tr>
<td valign="top">

*Profile ARN Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the profile ARN. A profile defines which IAM roles can be assumed and applies session policies to control the permissions granted to authenticated workloads.

</td>
</tr>
<tr>
<td valign="top">

*Trust Anchor Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Trust Anchor ARN. A trust anchor is the configured Certificate Authority \(CA\) that IAM Roles Anywhere trusts to verify certificates and grant access to IAM roles.

</td>
</tr>
<tr>
<td valign="top">

*Key Pair Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the alias of the key pair \(private key and certificate\) stored in the Keystore.

</td>
</tr>
</table>

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

*Topic Type*

</td>
<td valign="top">

Select the type of topic to be used. Possible options include:

> ### Note:  
> -   Standard
> -   FIFO



</td>
</tr>
<tr>
<td valign="top">

*Subject*

</td>
<td valign="top">

Specify the subject of the message.

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
<tr>
<td valign="top">

*Message Structure*

</td>
<td valign="top">

Select the structure of the message from the following options:

-   Identical Payload for all Delivery Protocols

-   Custom Payload for each Delivery Protocol




</td>
</tr>
<tr>
<td valign="top">

*Enable Large Payload*

</td>
<td valign="top">

Enable the checkbox to process large-size messages. If this option is enabled, then all the payloads having a size above the specified threshold will be sent to the S3 bucket and a notification with the S3 object Id will be received in the SQS Queue.

</td>
</tr>
<tr>
<td valign="top">

*Message Size Threshold*

\(Only available when Enable Large Payload is

enabled.\)

</td>
<td valign="top">

The threshold value of the payload size above which the payload will be sent to the S3 bucket.

Possible values: 0 to 262144 \(256Kb\).

Default Value: 262144 \(256Kb\).

</td>
</tr>
<tr>
<td valign="top">

*Bucket Name*

\(Only available when Enable Large Payload is

enabled.\)

</td>
<td valign="top">

The name of the S3 bucket where the large files should be written.

> ### Note:  
> The bucket name should not contain “.” characters.



</td>
</tr>
<tr>
<td valign="top">

*Message Attribute*

</td>
<td valign="top">

Specify any additional message attribute name-datatype-value pairs that you can send to AWS.

-   Name: Specify the custom header name to be passed in the request to AWS. Value can also be read dynamically.
-   Datatype: Specify the required datatype. The available options include String, String.Array, Number, and Binary actions. Value can also be read dynamically.
-   Value: Specify the custom header value to be passed in the request to AWS. Value can also be read dynamically.



</td>
</tr>
<tr>
<td valign="top">

*Response*

</td>
<td valign="top">

Specify the format of the response message sent by AWS. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
</table>



### SWF Protocol

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

*Host* 

</td>
<td valign="top">

Specify the domain of the AWS region.

Defualt value: amazonaws.com

</td>
</tr>
<tr>
<td valign="top">

*Region Name* 

</td>
<td valign="top">

Select the AWS Region. If the region doesn’t exist in the preconfigured list, then the user can manually enter the region name in the text box.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type.

-   *Access and Secret Key* for access with long term credentials.
-   *Security Token Service \(AssumeRole\)* for temporary IAM role-based access.
-   *Security Token Service \(AssumeRoleWithWebldentity\)* to use an Identity Provider.
-   *Security Token Service \(IAMRolesAnywhere\)*to use IAM Roles on systems outside of AWS.



</td>
</tr>
<tr>
<td valign="top">

*Access Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS access key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*Secret Key Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the AWS secret key needed to connect to AWS.

</td>
</tr>
<tr>
<td valign="top">

*OIDC Credential Name*

\(Only available when Security Token Service \(AssumeRoleWithWebldentity\) is selected.\)

</td>
<td valign="top">

Specify the OAuth2 Client Credentials security artifact created for a Web Identity Provider.

Example: Microsoft Entra ID or SAP IAS.

</td>
</tr>
<tr>
<td valign="top">

*Role ARN Alias*

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Role ARN.

</td>
</tr>
<tr>
<td valign="top">

*Role Session Name*

</td>
<td valign="top">

Specify the Role Session Name for a session of the same role assumed with different principals.

</td>
</tr>
<tr>
<td valign="top">

*External ID Alias*

\(Only available when Security Token Service \(AssumeRole\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the External ID, as defined in the condition of the IAM role’s trust relationship.

</td>
</tr>
<tr>
<td valign="top">

*Profile ARN Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the profile ARN. A profile defines which IAM roles can be assumed and applies session policies to control the permissions granted to authenticated workloads.

</td>
</tr>
<tr>
<td valign="top">

*Trust Anchor Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Trust Anchor ARN. A trust anchor is the configured Certificate Authority \(CA\) that IAM Roles Anywhere trusts to verify certificates and grant access to IAM roles.

</td>
</tr>
<tr>
<td valign="top">

*Key Pair Alias*

\(Only available when Security Token Service \(IAMRolesAnywhere\) is selected.\)

</td>
<td valign="top">

Specify the alias of the key pair \(private key and certificate\) stored in the Keystore.

</td>
</tr>
</table>

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

*Action*

</td>
<td valign="top">

Select the API action to be performed in AWS Simple Workflow.

> ### Example:  
> List Domains, List Activity Types.



</td>
</tr>
<tr>
<td valign="top">

*Request*

</td>
<td valign="top">

Specify the format of the request message to send to AWS. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top">

*Response*

</td>
<td valign="top">

Specify the format of the response message sent by AWS. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
</table>

