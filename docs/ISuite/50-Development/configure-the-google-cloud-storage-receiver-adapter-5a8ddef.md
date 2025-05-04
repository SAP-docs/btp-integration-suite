<!-- loio5a8ddefab612419aab4e55e527f2c906 -->

# Configure the Google Cloud Storage Receiver Adapter

Google Cloud Storage Receiver Adapter allows you to access and manage Objects, Folders and Buckets on Google Cloud Storage.



<a name="loio5a8ddefab612419aab4e55e527f2c906__section_bhw_cmj_k2c"/>

## How the Google Cloud Storage Receiver Adapter works

If you have configured the Google Cloud Storage Receiver Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Google Cloud Storage \(this is a receiver system\), Google Cloud Storage Receiver Adapter works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio5a8ddefab612419aab4e55e527f2c906__section_lx1_zmj_k2c"/>

## Configure the Google Cloud Storage Receiver Adapter

Once you have created a receiver channel and selected the Google Cloud Storage Receiver Adapter, you can configure its parameters as shown below:

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

> ### Note:  
> When *Proxy Type* is set to *On-Premise*, you must use virtual host and port from cloud connector.



</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the method for authentication to Google Cloud Storage:

-   *OAuth2 Service Account*
-   *Workload Identity Federation*



</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Token URL*

\(only when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the OAuth2 Token URL which identifies as the authorization server for producing a JWT token internally.

Example: `https://www.googleapis.com/oauth2/v4/token`

</td>
</tr>
<tr>
<td valign="top">

*Client Email*

\(only when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the Google Service Account Client email.

Example: `limited-svc-account@192843.iam.gserviceaccount.com`

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the Google Service Account Private Key for authentication.

</td>
</tr>
<tr>
<td valign="top">

*Scope*

\(only when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the scope of the connection to Google Cloud Storage service.

Default:

`https://storage.googleapis.com/auth/devstorage.full_control`

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Entra ID Credential Name*

\(only when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the Oauth2 Client Credentials security artifact created for Microsoft Entra ID

</td>
</tr>
<tr>
<td valign="top">

*STS Token URL*

\(only when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the Security Token Service URL.

Example: `https://sts.googleapis.com/v1/token`

</td>
</tr>
<tr>
<td valign="top">

*STS Audience*

\(only when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the audience i.e. the full resource name of the identity provider.

Example: `//iam.googleapis.com/projects/<project-number>/locations/global/workloadIdentityPools/<pool-id>/providers/<provider-id>`

</td>
</tr>
<tr>
<td valign="top">

*STS Scopes*

\(only when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the OAuth 2.0 scopes to include on the resulting access token, formatted as a list of space-delimited, case-sensitive strings.

Example: `https://www.googleapis.com/auth/cloud-platform`

</td>
</tr>
<tr>
<td valign="top">

*STS Options*

\(only when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the additional options to use in the STS token call.

</td>
</tr>
<tr>
<td valign="top">

*Use Service Account Impersonation*

\(only when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Enable to use Service Account Impersonation.

</td>
</tr>
<tr>
<td valign="top">

*Access Token URL*

\(only when *Use Service Account Impersonation* is enabled.\)

</td>
<td valign="top">

Specify the URL for generating access token with Service Account Impersonation.

Example: `https://iamcredentials.googleapis.com/v1/projects/-/serviceAccounts/{ACCOUNT_EMAIL_OR_UNIQUEID}:generateAccessToken`

> ### Note:  
> The - wildcard character is required; replacing it with a project ID is invalid.



</td>
</tr>
<tr>
<td valign="top">

*Service Account Impersonation Scopes*

\(only when *Use Service Account Impersonation* is enabled.\)

</td>
<td valign="top">

Specify the comma-separated scopes to be included in the resulting OAuth 2.0 access token.

Example: `https://www.googleapis.com/auth/pubsub,https://www.googleapis.com/auth/cloud-platform`

</td>
</tr>
<tr>
<td valign="top">

*Delegates*

\(only when *Use Service Account Impersonation* is enabled.\)

</td>
<td valign="top">

Specify the comma-separated sequence of service accounts in a delegation chain.

`Example: projects/-/serviceAccounts/{ACCOUNT_EMAIL_OR_UNIQUEID}`

</td>
</tr>
<tr>
<td valign="top">

*Proxy*

</td>
<td valign="top">

Specify the proxy type:

-   *Internet*
-   *On-Premise*



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

*Resource Type*

</td>
<td valign="top">

Select the resource type from the available dropdown:

-   *Buckets*
-   *Folders*
-   *Objects*



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*Project ID*

</td>
<td valign="top">

Specify the Project ID.

</td>
</tr>
<tr>
<td valign="top">

*Bucket Name*

</td>
<td valign="top">

Specify the bucket name.

</td>
</tr>
<tr>
<td valign="top">

*Destination Directory Name*

</td>
<td valign="top">

Specify the destination directory path. .

Example: `dir`

> ### Note:  
> When left empty, root folder “/” will be used..



</td>
</tr>
<tr>
<td valign="top">

*Folder Name*

</td>
<td valign="top">

Specify the folder name.

</td>
</tr>
<tr>
<td valign="top">

*Create Parent Folders*

\(Only available when *Resource Type* is set to *Folders* and *Operation* is set to *Create*.\)

</td>
<td valign="top">

Enable to create non-existing parent folders.

Example: If *Folder Name* is `parent/child`, enabling creates `parent` folder if not already present, and then creates `child`.

</td>
</tr>
<tr>
<td valign="top">

*Existing Folder Name*

\(Only available when *Resource Type* is set to *Folders* and *Operation* is set to *Rename*.\)

</td>
<td valign="top">

Specify the name of the source folder.

</td>
</tr>
<tr>
<td valign="top">

*New Folder Name*

\(Only available when *Resource Type* is set to *Folders* and *Operation* is set to *Rename*.\)

</td>
<td valign="top">

Specify the maximum time in milliseconds to archive the object.

</td>
</tr>
<tr>
<td valign="top">

*Directory*

</td>
<td valign="top">

Specify the directory path. Example: `dir`

When left empty, root folder `/` will be used.

</td>
</tr>
<tr>
<td valign="top">

*File Name*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *List*.\)

</td>
<td valign="top">

Specify the file name or pattern matching the object name.

Example: `*.pdf`

</td>
</tr>
<tr>
<td valign="top">

*Include Subdirectories*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *List*.\)

</td>
<td valign="top">

Enable to search all subdirectories.

</td>
</tr>
<tr>
<td valign="top">

*Object Name*

</td>
<td valign="top">

Specify the object name.

</td>
</tr>
<tr>
<td valign="top">

*Existing File Handling*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Create*.\)

</td>
<td valign="top">

Select action in case file to be created already exists:

-   *Fail* throws an error and skips object creation if object exists.
-   *Ignore* skips object creation without throwing any error if object exists.
-   *Override* creates a new object or replaces the existing object with a new one.



</td>
</tr>
<tr>
<td valign="top">

*Upload Type*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Create*.\)

</td>
<td valign="top">

Select the type of upload request to be used for object creation:

-   *Media*
-   *Multi-Part*
-   *Resumable*



</td>
</tr>
<tr>
<td valign="top">

*Content Type*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Create*.\)

</td>
<td valign="top">

Specify the content type of the object data.

Example:

-   `text/html`
-   `media-type`



</td>
</tr>
<tr>
<td valign="top">

*Object Metadata*

\(Only available when *Upload Type* is set to *Multi-Part*.\)

</td>
<td valign="top">

Enable to create the metadata of the object.

</td>
</tr>
<tr>
<td valign="top">

*Upload in Multiple Chunks*

\(Only available when *Upload Type* is set to *Resumable*.\)

</td>
<td valign="top">

Enable to create object in multiple chunks.

</td>
</tr>
<tr>
<td valign="top">

*Chunk Size*

\(Only available when *Upload in Multiple Chunks* is enabled\)

</td>
<td valign="top">

Specify the chunk size to be used for object creation. The chunk size should be a multiple of 256 KiB \(256 x 1024 bytes\).

</td>
</tr>
<tr>
<td valign="top">

*Get Metadata only*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Get*.\)

</td>
<td valign="top">

Enable to get the metadata of the object.

</td>
</tr>
<tr>
<td valign="top">

*Source Bucket Name*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Rewrite*.\)

</td>
<td valign="top">

Specify the source bucket name.

</td>
</tr>
<tr>
<td valign="top">

*Source Directory Name*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Rewrite*.\)

</td>
<td valign="top">

Specify the source directory path.

Example: `dir`. When left empty, root folder `/` will be used.

</td>
</tr>
<tr>
<td valign="top">

*Existing Object Name*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Rewrite*.\)

</td>
<td valign="top">

Specify the source object name.

</td>
</tr>
<tr>
<td valign="top">

*Destination Bucket Name*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Rewrite*.\)

</td>
<td valign="top">

Specify the destination bucket name.

</td>
</tr>
<tr>
<td valign="top">

*New Object Name*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Rewrite*.\)

</td>
<td valign="top">

Specify the destination object name.

</td>
</tr>
<tr>
<td valign="top">

*Rewrite Token*

\(Only available when *Resource Type* is set to *Objects* and *Operation* is set to *Rewrite*.\)

</td>
<td valign="top">

Specify the rewrite token if present.

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

*Encryption Key Type*

\(Only available when *Object Encrypted with Custom Key* is enabled.\)

</td>
<td valign="top">

Select the type of encryption to be used:

-   *Cloud KMS Key*
-   *Customer-Supplied Encryption Key*



</td>
</tr>
<tr>
<td valign="top">

*Encryption Key Alias*

Only available when *Encryption Key Type* is set to *Customer-Supplied Encryption Key* \)

</td>
<td valign="top">

Specify the encryption key alias.

</td>
</tr>
<tr>
<td valign="top">

*Cloud KMS Key Name*

\(Only available when *Encryption Key Type* is set to *Cloud KMS Key Name*\)

</td>
<td valign="top">

Specify the resource name of the Cloud KMS key.

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

\(Only available when *Resource Typee* is set to *Objects* and *Operation* is set to *Rewrite*\)

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

Specify the alias for destination encryption key.

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

*Max Results*

</td>
<td valign="top">

Specify the maximum number of items to be returned.

</td>
</tr>
<tr>
<td valign="top">

*Page Token*

</td>
<td valign="top">

Specify the next page token.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify the key value pairs \(& separated\) to be used as query parameters.

Example: `prefix=test&delimiter=/`

> ### Note:  
> For *Create* operation for *Folders*, avoid using query parameter as it conflicts with *Create Parent Folders* option.



</td>
</tr>
<tr>
<td valign="top">

*Response Fields*

</td>
<td valign="top">

Specify the fields \(comma separated\) to be returned in the response.

Example:

-   `name,generation,size`
-   `items/id`



</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to send to the target system. By default, no custom headers are sent. Use an asterisk \(\*\) to send all custom headers to the target system. Alternatively, you can dynamically pass the values by defining a property that includes a list of headers.

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

