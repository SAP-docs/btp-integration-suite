<!-- loio845ec2122180497ebe4f0dfaa955d641 -->

# Configure the Google Pub/Sub Sender Adapter

Google Pub/Sub Sender adapter provides the ability to consume messages seamlessly from Google Pub/Sub.



<a name="loio845ec2122180497ebe4f0dfaa955d641__gps_sender_section_cl2_kgx_ydc"/>

## How the Google Pub/Sub Sender Adapter Works

If you have configured the Google Pub/Sub Sender Adapter, data exchange is performed as follows at runtime: Google Pub/Sub sends the operation request to SAP Integration Suite tenant, Google Pub/Sub Sender Adapter works on the request and sends the data to SAP Integration Suite tenant.

The Sender adapter supports the following variants:

-   gRPC
-   REST



<a name="loio845ec2122180497ebe4f0dfaa955d641__gps_sender_section_yst_12z_ydc"/>

## Configure the Google Pub/Sub Sender Adapter



### gRPC

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

Specify the hostname pointing to the Google Pub/Sub service.

Example: `https://pubsub.googleapis.com`

> ### Note:  
> When *Proxy Type* is set to *On-Premise*, you must use virtual host and port from cloud connector.



</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the method for authentication to Google Pub/Sub:

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

Specify the scope of the connection to Google Pub/Sub service.

Default: `https://www/googleapis/auth/pubsub`

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

Example: `https://www.googleapis.com/auth/pubsub`

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

*Connection Check Interval \(in ms\)*

</td>
<td valign="top">

Specify the interval in milliseconds to verify the connection validity of the gRPC.

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

*Project ID*

</td>
<td valign="top">

Specify the Google Pub/Sub project ID.

</td>
</tr>
<tr>
<td valign="top">

*Subscription ID*

</td>
<td valign="top">

Specify the Google Pub/Sub Subscription ID from which the messages will be read.

</td>
</tr>
<tr>
<td valign="top">

*Post Processing*

</td>
<td valign="top">

Select the action to be performed after polling a message:

-   *Acknowledge after Successful Processing*
-   *Acknowledge Immediately*
-   *Do not Acknowledge*

> ### Note:  
> For gRPC, *Do not Acknowledge* is only meant for testing and is not recommended for a production scenario.



</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check Expiration \(in ms\)*

</td>
<td valign="top">

Specify the expiry time in milliseconds while handling the Duplicate check.

The default value is 300000.

> ### Note:  
> Duplicate Check uses the Google PubSub message id to suppress the duplicates. This is only valid for success scenarios.



</td>
</tr>
</table>



### REST

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

Specify the hostname pointing to the Google Pub/Sub service.

Example: `https://pubsub.googleapis.com`

> ### Note:  
> When *Proxy Type* is set to *On-Premise*, you must use virtual host and port from cloud connector.



</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the method for authentication to Google Pub/Sub:

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

Specify the scope of the connection to Google Pub/Sub service.

Default: `https://www/googleapis/auth/pubsub`

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable to reuse this connection.

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

\(only available when *Proxy* is set to *On-Premise*\)

</td>
<td valign="top">

Specify the Location ID from Cloud Connector.

</td>
</tr>
<tr>
<td valign="top">

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specify the Polling Interval in milliseconds.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established with Google Pub/Sub service.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received from Google Pub/Sub service.

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

Description

</th>
<th valign="top">

Parameters

</th>
</tr>
<tr>
<td valign="top">

*Project ID*

</td>
<td valign="top">

Specify the Google Pub/Sub project ID.

</td>
</tr>
<tr>
<td valign="top">

*Subscription ID*

</td>
<td valign="top">

Specify the Google Pub/Sub Subscription ID from which the messages will be read.

> ### Note:  
> Default behaviour is to auto acknowledge a message once it is read.



</td>
</tr>
<tr>
<td valign="top">

*Max Messages to Read*

</td>
<td valign="top">

Specify the maximum number of messages to be returned for this request. This must be a positive integer. The Google Pub/Sub system may return fewer than the number specified.

> ### Note:  
> Maximum number of messages allowed in a Pull response is 1000.



</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Select the action to be performed after polling a message:

-   *Acknowledge after Successful Processing*
-   *Acknowledge Immediately*
-   *Do not Acknowledge*



</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check Expiration \(in ms\)*

</td>
<td valign="top">

Specify the expiry time in milliseconds while handling the Duplicate check.

The default value is 300000.

> ### Note:  
> Duplicate Check uses the Google PubSub message id to suppress the duplicates. This is only valid for success scenarios.



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

