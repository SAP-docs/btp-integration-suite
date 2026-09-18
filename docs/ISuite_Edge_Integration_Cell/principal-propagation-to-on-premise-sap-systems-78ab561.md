<!-- loio78ab5614da644bbaa999bda6f7727343 -->

# Principal Propagation to On-Premise SAP Systems

Edge Integration Cell can propagate an authenticated user's identity to on-premise SAP systems.



## Overview

When a user triggers an integration that calls an on-premise SAP system \(such as SAP ERP or S/4HANA\), the backend needs to know who that specific user is. Edge Integration Cell achieves this by generating a short-lived X.509 client certificate is valid for 120 seconds. It contains the user's email address, and sends it to the backend over a secure mutual TLS \(mTLS\) connection.



## How It Works

The connection uses two separate trust layers:

-   **Layer 1: Authenticate the calling system - System Identity \(mTLS\)**

    The Edge Integration Cell runtime instance opens a mutual TLS connection to the backend using its own long-lived system certificate \(sap\_cloudintegrationcertificate\). This proves that the caller is a legitimate Edge Integration Cell runtime instance.

-   **Layer 2: Identify the end user - User Identity \(Short-lived X.509 Certificate\)**

    On top of the mTLS connection, the runtime instance sends the SSL\_CLIENT\_CERT HTTP header containing a short-lived certificate with the user's email address. The backend verifies this certificate and uses the email to identify the calling user.




### Runtime Flow

1.  The user triggers an integration. The request arrives at the Edge Integration Cell runtime instance with a signed identity JSON Web Token \(JWT\).
2.  The Edge Integration Cell runtime instance requests a short-lived user certificate from the signing service.
3.  The signing service validates the JWT, extracts the user's email, and returns a signed 120-second X.509 certificate.
4.  The runtime instance opens an mTLS connection to the backend using the system certificate \(Layer 1\).
5.  The runtime instance sends the HTTP request with the short-lived user certificate in the SSL\_CLIENT\_CERT header \(Layer 2\).
6.  The backend verifies both certificates and maps the email address to the correct user account.



## Prerequisites

> ### Caution:  
> The CA certificate should have the `KeyUsage` attribute `keyCertSign`. Many systems verify that the issuer of a certificate has this attribute and deny a client certificate, if this attribute is not present. When using the *Certificate Signing Request* procedure, the attribute will be requested for the CA certificate. Also, when generating a self-signed certificate, this attribute will be added automatically.

Complete the following one-time setup steps before running any integration flow that uses principal propagation.

**Step 1: Upload the CA Signing Certificate**

The Edge Integration Cell runtime instance signs short-lived user certificates using a Certificate Authority \(CA\) keypair. You must upload this keypair to the CPI Web UI.

1.  In the SAP Integration Suite web UI, navigate to *Settings* \> *Security* \> *Keystore*.
2.  Upload your CA keypair in PKCS\#12 format using the exact alias: `edge_sap_signing_certificate`.

> ### Note:  
> The alias `edge_sap_signing_certificate` is fixed. Any other alias name will not work.

**Step 2: Configure the Target On-Premise System**

The target system must be configured to trust both the Edge Integration Cell system certificate and the short-lived user certificates.

**Layer 1 - Trust the Edge Integration Cell System Certificate \(mTLS\)**

1.  In the SAP Integration Suite web UI, go to *Settings* \> *Security* \> *Keystore* and export the root and public certificate for the alias `sap_cloudintegrationcertificate`.
2.  Import this certificate into the target system's TLS trust store for client certificates.

> ### Example:  
> For ABAP systems \(SAP ERP, S/4HANA\)
> 
> -   Import the `sap_cloudintegrationcertificate` and `edge_sap_signing_certificate` certificate, and download the Root certificate of `sap_cloudintegrationcertificate` in transaction `STRUST` under the SSL Server Standard identity.
> -   To configure the Internet Communication Manager \(ICM\) to trust the system certificate for identity propagation, follow the below steps:
> 
>     -   Open the *Profile Editor* with transaction RZ10.
>     -   Choose the profile you want to edit. For example, the *DEFAULT* profile.
>     -   Select the *Extended* maintenance radio button and choose the *Change* button.
>     -   Create the parameter: `icm/trusted_reverse_proxy_<x> = SUBJECT="<subject>", ISSUER="<issuer>"`.
>     -   Select a free index for <x\>.
> 
>         <subject\> is the subject of the system certificate `sap_cloudintegrationcertificate` \(For example: `CN=SCC, OU=BTP Scenarios, O=Trust Community, C=DE`\).
> 
>         <issuer\> is the issuer of the system certificate `sap_cloudintegrationcertificate` \(For example: `CN=MyCompany CA, O=Trust Community, C=DE` \).
> 
>         > ### Example:  
>         > icm/trusted\_reverse\_proxy\_2 = SUBJECT="CN=SCC, OU=BTP Scenarios, O=Trust Community, C=DE", ISSUER="CN=MyCompany CA, O=Trust Community, C=DE".
> 
> 
>     For more information, see [Configure an ABAP System to Trust the Cloud Connector's System Certificate](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-principal-propagation-for-https?version=Cloud&ai=true#1.-configure-an-abap-system-to-trust-the-cloud-connector's-system-certificate)
> 
> -   Restart ICM via *SMICM* \> *Administration* \> *ICM* \> *Exit Hard* \> *Global*.

**Layer 2 - Configure User Certificate Mapping**

> ### Example:  
> For ABAP systems \(SAP ERP, S/4HANA\):
> 
> -   Enable rule-based certificate mapping by setting the ICM profile parameter:
> 
>     ```
>     login/certificate_mapping_rulebased = 1
>     ```
> 
> -   Configure mapping rules in transaction `CERTRULE` to extract the user from the CN field \(which contains the email address\).
> -   For older ABAP releases, use transaction `EXTID_DN` to create explicit subject-to-user mappings.

**Proxy or Gateway in Front of the Backend**

If a reverse proxy, Web Dispatcher, or API gateway sits in front of the target system, configure it to forward the SSL\_CLIENT\_CERT header to the backend without modifying or removing it.



## Configuring the Integration Flow

1.  Open your integration flow in SAP Integration Suite.
2.  Select the *HTTP Receiver Adapter*. For more information, see [HTTP Receiver Adapter](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/http-receiver-adapter?version=CLOUD&ai=true)
3.  Go to the *Connection* tab.
4.  Set *Authentication* to Principal Propagation.



## Troubleshooting

Use the Message Processing Log \(MPL\) ID from the monitoring view in SAP Integration Suite as the primary reference when investigating failures.

**Troubleshooting Information**


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

Authentication fails at the backend

</td>
<td valign="top">

Verify the sap\_cloudintegrationcertificate is imported in STRUST \(Layer 1\).

</td>
</tr>
<tr>
<td valign="top">

User not recognized by the backend

</td>
<td valign="top">

Verify certificate-to-user mapping is configured in CERTRULE or EXTID\_DN \(Layer 2\).

</td>
</tr>
<tr>
<td valign="top">

SSL\_CLIENT\_CERT header missing

</td>
<td valign="top">

If a proxy is in front of the backend, confirm it forwards this header.

</td>
</tr>
<tr>
<td valign="top">

Signing key unavailable error

</td>
<td valign="top">

Confirm the CA keypair is uploaded with alias edge\_sap\_signing\_certificate in keystore.

</td>
</tr>
</table>

**To trace a failed request:**

1.  Retrieve the MPL ID from the *Message Processing Log* in the monitoring view. For more information, see [Message Processing Log](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/message-processing-log?version=CLOUD&ai=true)
2.  Search the Edge Integration Cell runtime instance logs for the MPL ID to find the outbound signing call and any errors.
3.  If the error indicates a missing signing key, verify the edge\_sap\_signing\_certificate alias in the keystore.



## Limitations

-   The CA signing certificate alias must be exactly `edge_sap_signing_certificate`. Other alias names are not supported.
-   Short-lived user certificates are valid for 120 seconds only. They are generated fresh for each request.



## Related Information

[Configure a CA Certificate](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-ca-certificate-for-principal-propagation?version=Cloud)

