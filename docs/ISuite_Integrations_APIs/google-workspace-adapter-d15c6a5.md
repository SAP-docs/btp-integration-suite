<!-- loiod15c6a511231473fa7967b9ee68fb9e8 -->

# Google Workspace Adapter

Google Workspace adapter allows you to connect with Google Workspace APIs like Google Drive.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loiod15c6a511231473fa7967b9ee68fb9e8__section_gws_gd_receiver"/>

## How the Google Workspace Receiver Adapter Works

If you have configured the Google Workspace Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Google Drive \(this is a receiver system\), Google Drive works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loiod15c6a511231473fa7967b9ee68fb9e8__receiver_connection"/>

## Configure the Google Workspace Adapter

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

Specify the hostname to connect to Google Drive.

Example: `https://www.googleapis.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication method:

-   *OAuth2 Authorization Code* for user-level access.
-   *OAuth2 Service Account* for app-level access.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify OAuth2 Authorization Code security artifact that stores Client ID and Client Secret.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Token URL*

</td>
<td valign="top">

Specify the OAuth2 Token URL which identifies as the authorization server for producing a JWT token internally.

Default: *https://www.googleapis.com/oauth2/v4/token*

</td>
</tr>
<tr>
<td valign="top">

*Client Email*

</td>
<td valign="top">

Specify the Google Service Account Email.

Example: `yourmailservice@polar-reef.iamgserviceaccount.com`

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

</td>
<td valign="top">

Specify the Google Service Account Private Key Keystore Alias for authentication.

Example: `PKey`

</td>
</tr>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Specify the OAuth 2.0 scopes formatted as a list of space-delimited, case-sensitive strings.

Default: *https://www.googleapis.com/auth/drive*

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

Default: *60000*

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message.

Default: *60000*

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

*Configuration Type*

</td>
<td valign="top">

Select the required configuration type:

-   *Basic* provides a convenient processing capability for supported versions using UI elements like dropdowns and parameter text fields.
-   *Advanced* provides relative URL which enables proficient users to perform calls with greater control while connecting to any API endpoint.



</td>
</tr>
<tr>
<td valign="top">

*API Version* 

\(Only available when *Configuration Type* is set to *Basic*.\)

</td>
<td valign="top">

Select the API version from the dropdown.

</td>
</tr>
<tr>
<td valign="top">

*Resource* 

\(Only available when *Configuration Type* is set to *Basic*.\)

</td>
<td valign="top">

Select the required resource:

-   *About*
-   *Comments*
-   *Drives*
-   *Files*
-   *Folders*
-   *Operations*
-   *Permissions*



</td>
</tr>
<tr>
<td valign="top">

*Operation* 

\(Only available when *Configuration Type* is set to *Basic*.\)

</td>
<td valign="top">

Select the operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*Operation Parameters*

</td>
<td valign="top">

Specify the operation parameters as a key value pair.

Example: *commentID* is set to `CBCAS5kMmTUx9w`

</td>
</tr>
<tr>
<td valign="top">

*MIME Type*

</td>
<td valign="top">

Specify the MIME type of the format requested for this export.

Example: `application/pdf`

</td>
</tr>
<tr>
<td valign="top">

*Request ID*

</td>
<td valign="top">

Specify the ID \(UUID\) which uniquely identifies this user's request for idempotent creation of a shared drive.

</td>
</tr>
<tr>
<td valign="top">

*Upload Type* 

\(Only available when *Operation* is set to *Upload File \(/drive/v3/drives\)*.\)

</td>
<td valign="top">

Select the type of upload to be performed:

-   *Media*
-   *Resumable*
-   *Multipart*



</td>
</tr>
<tr>
<td valign="top">

*Upload Content Type* 

\(Only available when *Operation* is set to *Upload File \(/drive/v3/drives\)*.\)

</td>
<td valign="top">

Specify the content type of the file to upload.

Example: `text/plain`

</td>
</tr>
<tr>
<td valign="top">

*File Metadata* 

\(Only available when *Upload Type* is set to *Multipart* or *Resumable*.\)

</td>
<td valign="top">

Specify the metadata of the file.

</td>
</tr>
<tr>
<td valign="top">

*Upload in Multiple Chunks* 

\(Only available when *Upload Type* is set to *Resumable*.\)

</td>
<td valign="top">

Enable to upload file in multiple chunks.

</td>
</tr>
<tr>
<td valign="top">

*Chunk Size \(in bytes\)* 

\(Only available when *Mode* is set to *Get File in Chunks* or *Upload in Multiple Chunks* is enabled.\)

</td>
<td valign="top">

Specify the chunk size in bytes for Get File Content/Upload File. For Upload File, the chunk size should be a multiple of 262144 bytes \(256 KiB\).

Example: `262144`

</td>
</tr>
<tr>
<td valign="top">

*Mode* 

\(Only available when *Operation* is set to *Get File Content \(/drive/v3/files/:fileId\)*.\)

</td>
<td valign="top">

Select to fetch content of a file as a complete file or in multiple chunks:

-   *Get Complete File*
-   *Get File in Chunks*



</td>
</tr>
<tr>
<td valign="top">

*Max File Size \(in bytes\)* 

\(Only available when *Mode* is set to *Get Complete File*.\)

</td>
<td valign="top">

Specify the maximum size of the download in bytes.

</td>
</tr>
<tr>
<td valign="top">

*Offset \(in bytes\)* 

\(Only available when *Mode* is set to *Get File in Chunks*.\)

</td>
<td valign="top">

Specify the starting offset in bytes to begin the Get File Content operation.

Example: `524288`

</td>
</tr>
<tr>
<td valign="top">

*HTTP Update Method* 

\(Only available when *Operation* is set to *Update File Metadata \(/drive/v2/files/:fileId\)*.\)

</td>
<td valign="top">

Specify the request to be sent:

-   *PATCH*
-   *PUT*



</td>
</tr>
<tr>
<td valign="top">

*Fields*

</td>
<td valign="top">

Specify the subset of fields to return.

Example: `kind,user,storageQuota`

</td>
</tr>
<tr>
<td valign="top">

*Search Query \(q\)*

</td>
<td valign="top">

Specify the search query to filter the results of the List operation.

Example: `name%20contains%20%27google%27`

</td>
</tr>
<tr>
<td valign="top">

*Page Size*

</td>
<td valign="top">

Specify the maximum number of results to return per page.

</td>
</tr>
<tr>
<td valign="top">

*Page Token*

</td>
<td valign="top">

Specify the token for continuing a previous list request on the next page.

</td>
</tr>
<tr>
<td valign="top">

*Max Results*

</td>
<td valign="top">

Specify the maximum number of results to return per page.

> ### Note:  
> *Max Results* is the equivalent parameter used in v2 for *Page Size* \(available in v3\).



</td>
</tr>
<tr>
<td valign="top">

*HTTP Method* 

\(Only available when *Configuration Type* is set to *Advanced*.\)

</td>
<td valign="top">

Select the required method from the available dropdown:

-   *DELETE*
-   *GET*
-   *PATCH*
-   *POST*
-   *PUT*



</td>
</tr>
<tr>
<td valign="top">

*Relative URL* 

\(Only available when *Configuration Type* is set to *Advanced*.\)

</td>
<td valign="top">

Specify the relative endpoint, excluding the Host.

Example: `upload/drive/v3/files?uploadType=media`

</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the expression containing the query parameter and value.

Syntax: `param1=value1&param2=value2`

Example: `supportsAllDrives=true`

</td>
</tr>
<tr>
<td valign="top">

*Send Body* 

\(Only available when *HTTP Method* is set to *DELETE* or *GET*.\)

</td>
<td valign="top">

Enable this checkbox if you want to send the body of the message with the request.

> ### Note:  
> For methods *GET* and *DELETE*, the body is not sent by default.



</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Specify a list of custom headers, separated by `|`, to be sent to the target system. Use an asterisk \(`*`\) to send all custom headers to the target system.

> ### Note:  
> All Camel-specific headers and HTTP protocol headers except "date" are excluded by default, even if you specify them.



</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Specify a list of headers, separated by `|`, coming from the target system's response to be received in the message. Use an asterisk \(`*`\) to receive all the headers from the target system, which is also the default value.

> ### Note:  
> All Camel-specific headers and HTTP protocol headers except "date" are excluded by default, even if you specify them.



</td>
</tr>
</table>

