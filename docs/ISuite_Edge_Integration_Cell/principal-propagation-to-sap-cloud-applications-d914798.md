<!-- loiod914798470664609be3ee90ffa398c88 -->

# Principal Propagation to SAP Cloud Applications

Edge Integration Cell can propagate an authenticated user's identity to SAP cloud applications.



## Overview

When a user triggers an integration that calls an SAP cloud application \(such as SAP SuccessFactors or SAP Concur\), the target application needs to know who that specific user is. Edge Integration Cell uses the SAML 2.0 Bearer Assertion mechanism to obtain a user-specific OAuth 2.0 access token, which is then used to call the target application. All SAML operations are handled automatically by the Destination Service. The integration developer does not work with SAML directly. For more information, see [Deploying an OAuth2 SAML Bearer Assertion](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/deploying-oauth2-saml-bearer-assertion?version=CLOUD&ai=true)



## How It Works

1.  The user triggers an integration. The request arrives at the Edge Integration Cell runtime instance with a signed identity JSON Web Token \(JWT\).

2.  The Edge Integration Cell runtime instance passes the user JWT to the local Destination Service running inside the Edge Integration Cell cluster.

3.  The local Destination Service constructs a SAML assertion for that user, signs it, and exchanges it at the target application's token endpoint for a user-specific OAuth 2.0 access token.

4.  The Edge Integration Cell runtime instance calls the target SAP cloud application using the OAuth token.

5.  The target application identifies the calling user from the OAuth token and applies its own access rules.


The local Destination Service replicates destination configurations from BTP Cloud approximately every 2 minutes. At request time, no outbound internet call is made, everything runs within the Edge Integration Cell cluster.



## Differences from Cloud Integration Deployment

In SAP Cloud Integration, the runtime instance calls the BTP Cloud Destination Service directly. In Edge Integration Cell, a local Destination Service runs inside the Edge Integration Cell cluster and replicates from BTP Cloud, so principal propagation does not require an outbound internet call at request time.


<table>
<tr>
<th valign="top">

Aspect

</th>
<th valign="top">

Cloud Integration

</th>
<th valign="top">

Edge Integration Cell

</th>
</tr>
<tr>
<td valign="top">

Destination Service location

</td>
<td valign="top">

BTP Cloud

</td>
<td valign="top">

Local instance inside Edge Integration Cell cluster

</td>
</tr>
<tr>
<td valign="top">

Request-time network call

</td>
<td valign="top">

Outbound to BTP Cloud

</td>
<td valign="top">

In-cluster only \(no internet call\)

</td>
</tr>
<tr>
<td valign="top">

Destination creation

</td>
<td valign="top">

Auto-created on Cloud Integration deployment event

</td>
<td valign="top">

Auto-created via BTP Destination Service API

</td>
</tr>
<tr>
<td valign="top">

SAML signing key

</td>
<td valign="top">

BTP Cloud Destination Service

</td>
<td valign="top">

Same key - replicated locally from BTP Cloud

</td>
</tr>
<tr>
<td valign="top">

Replication lag

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Up to ~2 minutes after deployment

</td>
</tr>
</table>

> ### Note:  
> Because the local Destination Service in Edge Integration Cell uses the same signing key as the BTP Cloud Destination Service, the target application trust configuration is identical for both Cloud Integration and Edge Integration Cellruntime. No reconfiguration of the target application is needed when switching from Cloud Integration to Edge Integration Cell runtime. For more information, see [Runtime Profiles](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/runtime-profiles?version=CLOUD&ai=true)



## Prerequisites

Complete the following one-time setup steps before running any integration flow that uses SAML-based principal propagation.

**Step 1: Configure Trust on the Target SAP Cloud Application**

The target application must trust SAML assertions signed by the Destination Service. This is a one-time setup per BTP subaccount.

1.  In your BTP subaccount cockpit, go to *Connectivity* \> *Destinations*.

2.  Open the Destination Service settings and export the SAML signing certificate \(public key\).

3.  Import this certificate into the target application's trust configuration

    > ### Example:  
    > -   SAP SuccessFactors: Add the certificate under *Admin Center* \> *Authorized OAuth Clients*.
    > 
    > -   SAP Concur: Add the certificate under the OAuth consumer configuration.


Once the signing certificate is trusted by the target application, it will accept SAML assertions from the Destination Service and exchange them for OAuth tokens.

**Step 2: Deploy the SAML Security Artifact**

When you deploy an OAuth2SAMLBearerAssertion security artifact from the SAP Integration Suite web UI, the system automatically creates the corresponding destination entry in your BTP subaccount. No manual destination creation is required. For more information, see [OAuth2SAMLBearerAssertion](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/deploying-oauth2-saml-bearer-assertion?version=CLOUD&ai=true)

After deployment, allow up to 2 minutes for the local Destination Service inside the Edge Integration Cell cluster to replicate the new destination configuration from BTP Cloud before running the integration.



## Configuring the Integration Flow

1.  Open your integration flow in SAP Integration Suite.

2.  Select the *HTTP Receiver Adapter*. For more information, see [HTTP Receiver Adapter](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/http-receiver-adapter?version=CLOUD&ai=true)

3.  Go to the *Connection* tab.

4.  Set *Authentication* to OAuth2 SAML Bearer Assertion.




## Troubleshooting

Use the Message Processing Log \(MPL\) ID from the monitoring view in SAP Integration Suite as the primary reference when investigating failures.


<table>
<tr>
<th valign="top">

Symptom

</th>
<th valign="top">

What to Check

</th>
</tr>
<tr>
<td valign="top">

Token exchange fails at the target application

</td>
<td valign="top">

Verify the Destination Service SAML signing certificate is imported in the target application's trust configuration.

</td>
</tr>
<tr>
<td valign="top">

Destination not found

</td>
<td valign="top">

The artifact may not yet have replicated. Wait up to 2 minutes after deployment and retry.

</td>
</tr>
<tr>
<td valign="top">

Principal propagation intermittently unavailable

</td>
<td valign="top">

Check network connectivity between the Edge Integration Cell cluster and BTP Cloud. Extended connectivity loss may cause stale replication.

</td>
</tr>
</table>

To trace a failed request:

1.  Retrieve the MPL ID from the *Message Processing Log* in the monitoring view. For more information, see [Message Processing Log](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/message-processing-log?version=CLOUD&ai=true)

2.  Search the Edge Integration Cell runtime instance logs for the MPL ID to find the outbound call to the local Destination Service and any error messages. For example: destination not found or token exchange failure.




## Limitations

-   After deploying a new SAML security artifact, allow up to 2 minutes before principal propagation becomes active for that destination.

-   The local Destination Service requires periodic connectivity to BTP Cloud for replication. Principal propagation is not designed for fully offline operation.


