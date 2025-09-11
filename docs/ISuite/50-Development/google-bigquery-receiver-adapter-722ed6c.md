<!-- loio722ed6cb5bec4e8a845ba50bd3c7879a -->

# Google BigQuery Receiver Adapter

Google BigQuery Receiver adapter facilitates access to data residing on Google BigQuery.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio722ed6cb5bec4e8a845ba50bd3c7879a__section_wqx_dwk_22c"/>

## How the Google BigQuery Receiver Adapter Works

If you have configured the Google BigQuery receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Google BigQuery \(this is a receiver system\), Google BigQuery works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio722ed6cb5bec4e8a845ba50bd3c7879a__section_okv_pxk_22c"/>

## Configure the Google BigQuery Receiver Adapter

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

Specify the hostname pointing to the Google BigQuery service.

Example: `https://bigquery.googleapis.com`

> ### Note:  
> When *Proxy Type* is set to *On-Premise*, you must use virtual host and port from cloud connector.



</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the method for authentication to Google BigQuery:

-   *OAuth2 Service Account*
-   *Workload Identity Federation*



</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Token URL*

\(only available when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the OAuth2 Token URL which identifies as the authorization server for producing a JWT token internally.

Example: `https://www.googleapis.com/oauth2/v4/token`

</td>
</tr>
<tr>
<td valign="top">

*Client Email*

\(only available when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the Google Service Account Client Email.

Example: `limited-svcaccount@192843.iam.gserviceaccount`

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only available when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the alias for Google Service Account Private Key for authentication.

</td>
</tr>
<tr>
<td valign="top">

*Scope*

\(only available when *Authentication Type* is set to *OAuth2 Service Account*\)

</td>
<td valign="top">

Specify the scope of the connection to Google BigQuery service.

Default: `https://www/googleapis/auth/bigquery`

</td>
</tr>
<tr>
<td valign="top">

*Microsoft Entra ID Credential Name*

\(only available when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the Oauth2 Client Credentials security artifact created for Microsoft Entra ID.

</td>
</tr>
<tr>
<td valign="top">

*STS Token URL*

\(only available when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the Security Token Service URL.

Example: `https://sts.googleapis.com/v1/token`

</td>
</tr>
<tr>
<td valign="top">

*STS Audience*

\(only available when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the audience i.e. the full resource name of the identity provider.

Example: `//iam.googleapis.com/projects/<project-number>/locations/global/workloadIdentityPools/<pool-id>/providers/<provider-id>`

</td>
</tr>
<tr>
<td valign="top">

*STS Scopes*

\(only available when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the OAuth 2.0 scopes to include on the resulting access token, formatted as a list of space-delimited, case-sensitive strings.

Example: `https://www.googleapis.com/auth/bigquery`

</td>
</tr>
<tr>
<td valign="top">

*STS Options*

\(only available when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Specify the additional options to use in the STS token call.

</td>
</tr>
<tr>
<td valign="top">

*Use Service Account Impersonation*

\(only available when *Authentication Type* is set to *Workload Identity Federation*\)

</td>
<td valign="top">

Enable to use Service Account Impersonation.

</td>
</tr>
<tr>
<td valign="top">

*Access Token URL*

\(only available when *Use Service Account Impersonation* is enabled\).

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

\(only available when *Use Service Account Impersonation* is enabled\).

</td>
<td valign="top">

Specify the comma-separated scopes to be included in the resulting OAuth 2.0 access token.

Example: `https://www.googleapis.com/auth/pubsub,https://www.googleapis.com/auth/cloud-platform`

</td>
</tr>
<tr>
<td valign="top">

*Delegates*

\(only available when *Use Service Account Impersonation* is enabled\).

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

*Location ID*

\(only when *Proxy* is set to *On-Premise*\)

</td>
<td valign="top">

Specify the Location ID from Cloud Connector.

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

Specify the maximum waiting time \(in milliseconds\) for the connection to be established with Google BigQuery service.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received with Google BigQuery service.

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

-   *Basic* for convenient processing capability using dropdowns and parameter text fields.
-   *Processing* for advanced users enables proficient users to perform calls with greater control while connecting to any API endpoint.



</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Select the entity for operation:

-   *Datasets*
-   *Jobs*
-   *Models*
-   *Projects*
-   *Routines*
-   *Row Access Policies*
-   *Table Data*
-   *Tables*



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

*Dataset ID*

</td>
<td valign="top">

Specify the Dataset ID to be used.

</td>
</tr>
<tr>
<td valign="top">

*Job ID*

</td>
<td valign="top">

Specify the Job ID.

</td>
</tr>
<tr>
<td valign="top">

*Model ID*

</td>
<td valign="top">

Specify the Model ID.

</td>
</tr>
<tr>
<td valign="top">

*Policy ID*

</td>
<td valign="top">

Specify the Policy ID.

</td>
</tr>
<tr>
<td valign="top">

*Table ID*

</td>
<td valign="top">

Specify the Table ID.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify the key value pairs \(& separated\) to be used as query parameters.

Example: `maxResults=50`

> ### Note:  
> Ensure that the query parameter value is properly encoded before being passed.
> 
> `filter=labels.department:finance%20labels.owner:data-team`



</td>
</tr>
<tr>
<td valign="top">

*Max Results*

</td>
<td valign="top">

Specify the maximum results to be returned.

Example: `100`

</td>
</tr>
<tr>
<td valign="top">

*Page Token*

</td>
<td valign="top">

Specify the nextPageToken returned in the response, to retrieve the next page of results.

> ### Note:  
> A value of null or an empty string retrieves the first page.



</td>
</tr>
<tr>
<td valign="top">

*State Filter*

</td>
<td valign="top">

Select the state filter fo the jobs:

-   *Done*
-   *Pending*
-   *Running*



</td>
</tr>
<tr>
<td valign="top">

*Object Metadata*

</td>
<td valign="top">

Specify the object metadata.

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

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

*Filter*

</td>
<td valign="top">

Select the filter for routines:

-   *Procedure*
-   *Routine Type Unspecified*
-   *Scalar Function*
-   *Table Valued Function*



</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

</td>
<td valign="top">

Select the required HTTP method from the available dropdown:

-   *DELETE*
-   *GET*
-   *HEAD*
-   *PATCH*
-   *POST*
-   *PUT*



</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

</td>
<td valign="top">

Specify the endpoint path, excluding the Host.

Example: `/bigquery/v2/projects/my_project/datasets`

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

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property

</td>
</tr>
</table>

