<!-- loio16772e3bd410433b9bb47d9361b03e3c -->

# AmazonWebServices Sender Adapter

Use the sender adapter to accelerate the implementation time and reduce the complexity of connecting to AWS. The adapter supports the following protocols:

-   S3: Simple Cloud Storage

-   SQS: Simple Queue Service 


> ### Note:  
> You need to download the adapter from SAP Software Download Center. You can find more information on the download navigation path under the folloeing link: [Amazon Web Services Adapter for SAP Integration Suite](https://api.sap.com/package/AmazonWebServicesAdapter/overview).
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

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specifies the value of the Polling Interval in milliseconds.

The default value is 300000.

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

Specify the name of the file to be written. If the field on the left is not filled out, the filename is created using the Cloud Integration message ID.

> ### Example:  
> `Test.json`

> ### Note:  
> You can use an exchange header or a property to dynamically read the value.



</td>
</tr>
<tr>
<td valign="top">

*Sorting*

</td>
<td valign="top">

Specify which property should be used for sorting while polling files. The sorting will be done in ascending order of the selected property. It is possible to choose from the following options:

-   None

-   File Name

-   File Size

-   Time Stamp




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

*Post-Processing*

</td>
<td valign="top">

Select the action that should be taken after the file has been processed. It is possible to choose from the following options:

-   Delete File

-   Keep File and Process Again

-   Move File to an Archive directory

-   Copy file to an Archive Bucket

-   Move file to an Archive Bucket




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

</td>
<td valign="top">

Select the HTTP method that should be used for the pre-signed URL. Select from the following options:

-   GET

-   DELETE

-   HEAD

-   PATCH

-   POST

-   PUT




</td>
</tr>
<tr>
<td valign="top">

*Expired Duration of Pre-Signed URL \(secs\)*

</td>
<td valign="top">

Specify the duration in seconds for the Pre-Signed URL to expire. The default value is 86400.

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

-   Keep Message in the queue

-   Delete Message from the queue




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
</table>

