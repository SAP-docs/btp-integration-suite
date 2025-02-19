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

*Requester Pays*

</td>
<td valign="top">

Select the checkbox to make the requester pay for the data transfer and the request.

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

Specify the name of the file to be written. If the field is left blank, the filename is created using the Cloud Integration message ID.

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

*Post-Processing*

\(only if Operation is Write Operation\)

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

\(only if Operation is Write Operation\)

</td>
<td valign="top">

Specify the name of the secured parameter that contains the decryption key for the Amazon S3 to decrypt data.

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

Specify the AWS Topic name where the data needs to be written.

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

*Message Attribute*

</td>
<td valign="top">

Specify any additional message attribute name-value pairs that you can send to AWS.

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

*Region Name* 

</td>
<td valign="top">

Select the AWS Region. If the region doesn’t exist in the preconfigured list, then the user can manually enter the region name in the text box.

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

