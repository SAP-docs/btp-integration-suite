<!-- loio16772e3bd410433b9bb47d9361b03e3c -->

# AmazonWebServices Sender Adapter

Use the sender adapter to accelerate the implementation time and reduce the complexity of connecting to AWS. The adapter supports the following protocols:

-   S3: Simple Cloud Storage

-   SQS: Simple Queue Service 


> ### Note:  
> You need to download the adapter from SAP Software Download Center. You can find more information on the download navigation path under the following link: [Amazon Web Services Adapter for SAP Integration Suite](https://api.sap.com/package/AmazonWebServicesAdapter/overview).
> 
> After you complete the download, uncompress and extract the files to your local system. Then deploy the adapter on your tenant.
> 
> -   For more information on deploying the adapter in multicloud environment, see [Importing Custom Integration Adapter](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/482286e544014098874fde0da4bcca2c.html).



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

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specifies the value of the Polling Interval in milliseconds.

The default value is 60000.

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

\(Only available when *Security Token Service \(AssumeRoleWithWebldentity\)* is selected.\)

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

\(Only available when *Security Token Service \(AssumeRole\)* is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the External ID, as defined in the condition of the IAM role’s trust relationship.

</td>
</tr>
<tr>
<td valign="top">

*Profile ARN Alias*

\(Only available when *Security Token Service \(IAMRolesAnywhere\)* is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the profile ARN. A profile defines which IAM roles can be assumed and applies session policies to control the permissions granted to authenticated workloads.

</td>
</tr>
<tr>
<td valign="top">

*Trust Anchor Alias*

\(Only available when *Security Token Service \(IAMRolesAnywhere\)* is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Trust Anchor ARN. A trust anchor is the configured Certificate Authority \(CA\) that IAM Roles Anywhere trusts to verify certificates and grant access to IAM roles.

</td>
</tr>
<tr>
<td valign="top">

*Key Pair Alias*

\(Only available when *Security Token Service \(IAMRolesAnywhere\)* is selected.\)

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

*Directory*

</td>
<td valign="top">

Specify the location on the S3 bucket where the file is written.

> ### Example:  
> Directory/SubDirectory



</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the name of the file to be written. If the field on the left is not filled out, the filename is created using the Cloud Integration message ID.

> ### Example:  
> `Test.json`



</td>
</tr>
<tr>
<td valign="top">

*Sorting*

</td>
<td valign="top">

Specify which property should be used for sorting while polling files. The sorting will be done in ascending order of the selected property. It is possible to choose from the following options:

-   *None*

-   *File Name*

-   *File Size*

-   *Time Stamp*




</td>
</tr>
<tr>
<td valign="top">

*Include Sub-Directories*

</td>
<td valign="top">

Select to read all the files in the directory and subdirectory.

</td>
</tr>
<tr>
<td valign="top">

*Execute Post-Processing When Message Successfully Processed*

</td>
<td valign="top">

Select this checkbox to execute post-processing step only when the file is successfully processed by the exchange.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Select the action that should be taken after the file has been processed. It is possible to choose from the following options:

-   *Delete File*

-   *Keep File and Process Again*

-   *Move File to an Archive directory*

-   *Copy file to an Archive Bucket*

-   *Move file to an Archive Bucket*




</td>
</tr>
<tr>
<td valign="top">

*Archive Directory*

</td>
<td valign="top">

Specify the directory where to move the processed files. Only files are moved, not the associated metadata.

</td>
</tr>
<tr>
<td valign="top">

*Append Timestamp*

</td>
<td valign="top">

Select to append the date timestamp to the archived filename.

</td>
</tr>
<tr>
<td valign="top">

*Apply Encryption When Archiving*

</td>
<td valign="top">

Select to enable the server-side encryption when archiving the file in AWS.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Option*

\(Only available when *Apply Encryption When Archiving* is enabled.\)

</td>
<td valign="top">

Select the server-side encryption used for storing the file in AWS.

Example: SSE-S3.

-   *SSE-C \(with Customer-Provided Key\)*
-   *SSE-KMS \(with Customer Master Keys Stored in AWS Key Management Service\)*
-   *SSE-S3 \(with Amazon S3-Managed Keys\)*



</td>
</tr>
<tr>
<td valign="top">

*Encryption Key Alias*

\(Only available when Encryption Option is set to*SSE-C*.\)

</td>
<td valign="top">

Specify the name of the secure parameter which stores the customer-provided encryption key \(256-bit, base64-encoded\).

</td>
</tr>
<tr>
<td valign="top">

*Customer Managed Key ID*

\(Only available when Encryption Option is set to*SSE-KMS*.\)

</td>
<td valign="top">

Specify the name of the secure parameter which stores the ID of the symmetric customer-managed AWS KMS CMK.

</td>
</tr>
<tr>
<td valign="top">

*Custom Metadata*

\(Only available when *Apply Encryption When Archiving* is enabled.\)

</td>
<td valign="top">

Header: Specify the custom header name to be passed in the request to AWS.

Value: Specify the custom header value to be passed in the request to AWS.

</td>
</tr>
<tr>
<td valign="top">

*Archive Bucket*

</td>
<td valign="top">

Specify the bucket where to copy or move the processed files. Only files are moved, not associated metadata.

</td>
</tr>
<tr>
<td valign="top">

*Optional S3 Metadata*

</td>
<td valign="top">

Specify the property parameter to be populated from S3 object metadata. If specified, then a property with the name will be created in Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

*S3 Pre-Signed URL*

</td>
<td valign="top">

Select this option to generate a pre-signed URL. Select the HTTP method and the expiration duration of the pre-signed URL.

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method of Pre-Signed URL*

\(Only available when *S3 Pre-Signed URL* is enabled.\)

</td>
<td valign="top">

Select the HTTP method that should be used for the pre-signed URL. Select from the following options:

-   *GET*

-   *DELETE*

-   *HEAD*

-   *PATCH*

-   *POST*

-   *PUT*




</td>
</tr>
<tr>
<td valign="top">

*Expired Duration of Pre-Signed URL \(secs\)*

\(Only available when *S3 Pre-Signed URL* is enabled.\)

</td>
<td valign="top">

Specify the duration in seconds for the Pre-Signed URL to expire. The default value is 86400.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check*

</td>
<td valign="top">

Enable this option to avoid duplicate message processing for the period which will be specified by the Message Expiration Period field.

</td>
</tr>
<tr>
<td valign="top">

*Duplication Key*

\(Only available when *Duplicate Check* is enabled.\)

</td>
<td valign="top">

Select the Key on which the duplication check should be performed.

It is possible to choose from the following options:

-   *S3 Object Key*
-   *S3 File Name*



</td>
</tr>
<tr>
<td valign="top">

*Message Expiration Period \(in secs\)*

\(Only available when *Duplicate Check* is enabled.\)

</td>
<td valign="top">

Specify the time \(in seconds\) for which the message key will be stored for the duplicate check.

</td>
</tr>
<tr>
<td valign="top">

*Customer Decryption Key Alias*

</td>
<td valign="top">

Specify the name of the secured parameter that contains the decryption key for the Amazon S3 to decrypt data.

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

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specifies the value of the Polling Interval in milliseconds.

The default value is 60000.

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

\(Only available when *Security Token Service \(AssumeRoleWithWebldentity\)* is selected.\)

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

\(Only available when *Security Token Service \(AssumeRole\)* is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the External ID, as defined in the condition of the IAM role’s trust relationship.

</td>
</tr>
<tr>
<td valign="top">

*Profile ARN Alias*

\(Only available when *Security Token Service \(IAMRolesAnywhere\)* is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the profile ARN. A profile defines which IAM roles can be assumed and applies session policies to control the permissions granted to authenticated workloads.

</td>
</tr>
<tr>
<td valign="top">

*Trust Anchor Alias*

\(Only available when *Security Token Service \(IAMRolesAnywhere\)* is selected.\)

</td>
<td valign="top">

Specify the name of the secure parameter that stores the Trust Anchor ARN. A trust anchor is the configured Certificate Authority \(CA\) that IAM Roles Anywhere trusts to verify certificates and grant access to IAM roles.

</td>
</tr>
<tr>
<td valign="top">

*Key Pair Alias*

\(Only available when *Security Token Service \(IAMRolesAnywhere\)* is selected.\)

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

*Max Number of Messages*

</td>
<td valign="top">

Specifies the maximum number of messages to be read from the queue. Possible values can be between 1 and 10. The default value is set to 10.

</td>
</tr>
<tr>
<td valign="top">

*Wait Time \(in sec\)*

</td>
<td valign="top">

Specifies the duration in seconds to wait for a message to arrive in the queue. The default value is set to 20.

</td>
</tr>
<tr>
<td valign="top">

*Visibility Timeout \(in sec\)*

</td>
<td valign="top">

Specifies the duration in seconds that the message is hidden from subsequent retrieval requests. The default value is set to 30.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Specifies the action to be performed after the message processing in the queue. It is possible to choose from the following options:

-   *Keep Message in the queue*

-   *Delete Message from the queue*




</td>
</tr>
<tr>
<td valign="top">

*Execute Post-Processing When Message Successfully Processed*

</td>
<td valign="top">

Select this checkbox to execute post-processing step only when the file is successfully processed by the exchange.

</td>
</tr>
<tr>
<td valign="top">

*Optional SQS Metadata*

</td>
<td valign="top">

Specify the header parameters to be populated from SQS object metadata. Separate the metadata with comma “,”.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check On Message ID*

</td>
<td valign="top">

Select this option to avoid duplicate message processing based on SQS message ID.

</td>
</tr>
<tr>
<td valign="top">

*Message Expiration Period \(in secs\)*

\(Only available when *Duplicate Check On Message ID* is enabled.\)

</td>
<td valign="top">

Specify the time \(in seconds\) for which the message ID will be stored for a duplicate check.

</td>
</tr>
</table>

