<!-- loioec213ce5e195424fb68a2bb42b0a4a8b -->

# Configure the Google Cloud Storage Sender Adapter

Google Cloud Storage Sender Adapter provides the ability to read and process storage objects from Cloud Storage.



<a name="loioec213ce5e195424fb68a2bb42b0a4a8b__section_swf_khh_h2c"/>

## How the Google Cloud Storage Sender Adapter works

If you have configured the Google Cloud Storage Sender Adapter, data exchange is performed as follows at runtime: Google Cloud Storage sends the operation request to SAP Integration Suite tenant, Google Cloud Storage Sender Adapter works on the request and sends the data to SAP Integration Suite tenant.



<a name="loioec213ce5e195424fb68a2bb42b0a4a8b__section_k23_rnh_h2c"/>

## Configure the Google Pub/Sub Sender Adapter

**Connection**


<table>
<tr>
<th valign="top">

Description

</th>
<th valign="top">

Processing

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Specify the hostname pointing to the Google Cloud Storage service.

Default: `https://storage.googleapis.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the method for authentication to Google Cloud Storage. Currently *OAuth2 Service Account* is supported.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Token URL*

</td>
<td valign="top">

Specify the OAuth2 Token URL which identifies as the authorization server for producing a JWT token internally.

Example: `https://www.googleapis.com/oauth2/v4/token`

</td>
</tr>
<tr>
<td valign="top">

*Client Email*

</td>
<td valign="top">

Specify the Google Service Account Client email.

Example: `limited-svc-account@192843.iam.gserviceaccount.com`

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

</td>
<td valign="top">

Specify the Google Service Account Private Key for authentication.

</td>
</tr>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Specify the scope of the connection to Google Cloud Storage service.

Default: `devstorage.full_control`

</td>
</tr>
<tr>
<td valign="top">

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specify the Polling Interval \(in ms\).

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable the reuse of connection objects from the internal connection pool which in turn improves the network turnaround time for multiple communications to a same end point.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established with Google Cloud Storage service.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received from Google Cloud Storage service.

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

*Bucket Name*

</td>
<td valign="top">

Specify the name of the bucket.

</td>
</tr>
<tr>
<td valign="top">

*Directory*

</td>
<td valign="top">

Specify the directory path.

</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the file name or pattern matching the object name.

Example: `*.pdf`

</td>
</tr>
<tr>
<td valign="top">

*Include Subdirectories*

</td>
<td valign="top">

Enable to search all subdirectories under the directory.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify the key value pairs \(comma separated\) to be used as query parameters.

Example: `prefix=test&delimiter=/`

> ### Note:  
> -   For *Create* operation for *Folders*, avoid using query parameter as it conflicts with *Create Parent Folders* option.
> 
> -   Don’t use alt query parameter as it conflicts with the adapter’s response.



</td>
</tr>
<tr>
<td valign="top">

*Max Results*

</td>
<td valign="top">

Specify the maximum number of objects to be returned.

> ### Note:  
> The maximum value is `1000`. If you want more results, use pagination using the Receiver Adapter.



</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check Expiration \(in ms\)*

</td>
<td valign="top">

Specify the expiry time in milliseconds \(minimum 300000 ms\) while handling the Duplicate check. The default value is 300000.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Select the action to be performed after processing the object:

-   *Archive Object after Processing*
-   *Delete Object after Processing*
-   *Keep Object after Processing*



</td>
</tr>
<tr>
<td valign="top">

*Archive Wait Time \(in ms\)*

\(Only available when *Post-Processing* is set to *Archive Object after Processing*.\)

</td>
<td valign="top">

Specify the maximum time in milliseconds to archive the object.

</td>
</tr>
<tr>
<td valign="top">

*Move to same Bucket*

\(Only available when *Post-Processing* is set to *Archive Object after Processing*.\)

</td>
<td valign="top">

Enable to move the object to the same bucket.

</td>
</tr>
<tr>
<td valign="top">

*Destination Bucket Name*

\(Only avaiable when *Move to same Bucket* is disabled.

</td>
<td valign="top">

Specify the destination bucket name.

</td>
</tr>
<tr>
<td valign="top">

*Destination Folder*

\(Only available when *Post-Processing* is set to *Archive Object after Processing*.\)

</td>
<td valign="top">

Specify the destination folder.

Example: `dir`

</td>
</tr>
<tr>
<td valign="top">

*Archive Object Name*

\(Only available when *Post-Processing* is set to *Archive Object after Processing*.\)

</td>
<td valign="top">

Specify the name for the archived object. When left empty existing object name is used. Camel expressions can be used to name the object dynamically.



Example: `${file:name.noext.single}.${date:now:yyyy-MM-dd HH:mm:ss}.${file:name.ext.single}`

</td>
</tr>
<tr>
<td valign="top">

*Object Encrypted with Custom Key*

</td>
<td valign="top">

Enable if object is encrypted with custom key.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Key Alias*

\(Only available if *Object Encrypted with Custom Key* is enabled\)

</td>
<td valign="top">

Specify the Alias for Encryption Key.

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Destination Object with Custom Key*

</td>
<td valign="top">

Enable to encrypt destination object with custom key.

</td>
</tr>
<tr>
<td valign="top">

*Destination Encryption Key Type*

</td>
<td valign="top">

Select the type of encryption key to be used for the object that will be archived:

-   *Cloud KMS Key*
-   *Customer-Supplied Encryption Key*



</td>
</tr>
<tr>
<td valign="top">

*Destination Encryption Key Alias*

\(Only available when *Destination Encryption Key Type* is set to *Customer-Supplied Encryption Key*\)

</td>
<td valign="top">

Specify the alias for destination Encryption Key.

</td>
</tr>
<tr>
<td valign="top">

*Destination Cloud KMS Key Name*

\(Only available when *Destination Encryption Key Type* is set to *Cloud KMS Key*\)

</td>
<td valign="top">

Specify the resource name of the destination Cloud KMS key.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an \* to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

