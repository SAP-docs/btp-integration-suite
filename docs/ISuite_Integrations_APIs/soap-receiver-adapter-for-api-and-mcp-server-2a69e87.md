<!-- loio2a69e87868d441f3a286812f7414fd7f -->

# SOAP Receiver Adapter for API and MCP Server

The SOAP receiver adapter forwards requests from an API artifact to a SOAP web service. It acts as the outbound communication endpoint of the policy model and enables the API artifact to invoke SOAP-based services hosted on cloud or on-premise systems.



The SOAP receiver adapter is automatically added when you create an API artifact with the **SOAP** service type. After requests are processed by the configured policies, the adapter forwards them to the target SOAP service using either a direct service URL or an SAP BTP destination.

The adapter supports two connection types:

-   **URL-based** – Connects directly to a SOAP service by specifying its WSDL and endpoint information.
-   **Destination-based** – Connects to a SOAP service through a configured SAP BTP destination.

The adapter configuration defines how the API artifact connects to the target SOAP service, including the connection type, authentication method, transport settings, and WS-Security configuration.

When a client invokes a SOAP API artifact, the request is processed as follows:

-   The sender adapter receives the client request.
-   The policy model applies the configured policies.
-   The SOAP receiver adapter forwards the processed request to the configured SOAP service.
-   The backend response is returned through the policy model to the client.



**SOAP Receiver Adapter \(URL-based\)**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Property

</th>
<th valign="top">

Value/Options

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

General

</td>
<td valign="top">

Name

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies a unique name for the SOAP receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies an optional description for the adapter configuration.

</td>
</tr>
<tr>
<td valign="top">

Adapter Type

</td>
<td valign="top">

SOAP \(Read-only\)

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **SOAP** and cannot be changed.

</td>
</tr>
<tr>
<td valign="top" rowspan="10">

Connection

</td>
<td valign="top">

Type

</td>
<td valign="top">

URL \(Read-only\)

</td>
<td valign="top">

Specifies that the adapter connects directly to a SOAP service.

</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

Internet

</td>
<td valign="top">

Specifies the network used to connect to the SOAP service. Currently, only **Internet** is supported for URL-based connections.

</td>
</tr>
<tr>
<td valign="top">

URL to WSDL

</td>
<td valign="top">

Select a WSDL from your file system.

</td>
<td valign="top">

Specifies the URL or uploaded WSDL file that describes the SOAP web service.

</td>
</tr>
<tr>
<td valign="top">

Service

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies the service defined in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

Endpoint

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Name of the selected port of a selected service \(that you provide in the *Service Name* field\) contained in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

You can select one of the following authentication methods:

-   *None*

    No authentication.

-   *Basic*

    The tenant authenticates itself against the receiver using user credentials \(user name and password\).

-   *Client Certificate* \(only if *Proxy Type* is set to *Internet*\)

    The tenant authenticates itself against the receiver using a client certificate.




</td>
<td valign="top">

Specifies the authentication method used to connect to the SOAP service.

</td>
</tr>
<tr>
<td valign="top">

Private Key Alias

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Allows you to enter the private key alias name that gets the private key from the keystore and authenticates you to the receiver in an HTTPS communication.

> ### Note:  
> Available only when **Authentication** is set to **Client Certificate**.



</td>
</tr>
<tr>
<td valign="top">

Timeout \(in ms\)

</td>
<td valign="top">

60000

</td>
<td valign="top">

Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

The default value is 60000 milliseconds \(1 minute\).

</td>
</tr>
<tr>
<td valign="top">

Compress Message

</td>
<td valign="top">

Enabled

</td>
<td valign="top">

Enables the WS endpoint to send compressed request messages to the WS provider and to indicate to the WS provider that it can handle compressed response messages.

</td>
</tr>
<tr>
<td valign="top">

Allow Chunking

</td>
<td valign="top">

Enabled

</td>
<td valign="top">

Used for enabling HTTP chunking of data while sending messages.

> ### Note:  
> This option is enabled by default to avoid large HTTP messages. Make sure that the receiver of the message allows chunking if the *Allow Chunking* option is enabled.



</td>
</tr>
<tr>
<td valign="top" rowspan="6">

WS-Security

</td>
<td valign="top">

WS-Security Configuration

</td>
<td valign="top">

Based on Policies in WSDL

</td>
<td valign="top">

Specifies how WS-Security settings are to be configured.

-   *Via Manual Configuration in Channel*

    The security settings are to be configured manually

-   *Based on Policies in WSDL*

    The security settings are specified as part of the receiver endpoint \(within the endpoint WSDL\) in elements as defined by the WS-Policy standard.

-   *None*

    No WS-Security is applied for the message exchange.




</td>
</tr>
<tr>
<td valign="top">

Credential Name

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies how the user name token is to be configured. Select this option to authenticate at message level based on a user ID and a password \(transported within a SOAP message\).

</td>
</tr>
<tr>
<td valign="top">

Private Key Alias for Signing

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies an alias for the tenant private key that is to be used to sign the message.

</td>
</tr>
<tr>
<td valign="top">

Public Key Alias for Encryption

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies an alias for the public key that is to be used to encrypt the message.

</td>
</tr>
<tr>
<td valign="top">

Signature Algorithm

</td>
<td valign="top">

SHA1/RSA

</td>
<td valign="top">

Specify a signature algorithm to be applied when signing the request message.

Possible values:

-   SHA1 \(default value\)

-   SHA256

-   SHA512




</td>
</tr>
<tr>
<td valign="top">

Receiver is Basic Security Profile Compliant

</td>
<td valign="top">

Enabled

</td>
<td valign="top">

Leave this option selected if the receiver system complies with the basic security profile \(as assumed to be the case for most systems\). Deselect this option if the receiver system does not support this security profile.

</td>
</tr>
</table>



**SOAP Receiver Adapter \(Destination-based\)**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Property

</th>
<th valign="top">

Value/Options

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

General

</td>
<td valign="top">

Name

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies a unique name for the SOAP receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies an optional description for the adapter configuration.

</td>
</tr>
<tr>
<td valign="top">

Adapter Type

</td>
<td valign="top">

SOAP \(Read-only\)

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **SOAP** and cannot be changed.

</td>
</tr>
<tr>
<td valign="top" rowspan="11">

Connection

</td>
<td valign="top">

Type

</td>
<td valign="top">

URL \(Read-only\)

</td>
<td valign="top">

Specifies that the adapter connects directly to a SOAP service.

</td>
</tr>
<tr>
<td valign="top">

Destination

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies the SAP BTP destination used to access the SOAP service.

</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

Internet

</td>
<td valign="top">

Specifies the network used to connect to the SOAP service. Currently, only **Internet** is supported for URL-based connections.

</td>
</tr>
<tr>
<td valign="top">

URL to WSDL

</td>
<td valign="top">

Select a WSDL from your file system.

</td>
<td valign="top">

Specifies the URL or uploaded WSDL file that describes the SOAP web service.

</td>
</tr>
<tr>
<td valign="top">

Service

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies the service defined in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

Endpoint

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Name of the selected port of a selected service \(that you provide in the *Service Name* field\) contained in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

You can select one of the following authentication methods:

-   *None*

    No authentication.

-   *Basic*

    The tenant authenticates itself against the receiver using user credentials \(user name and password\).

-   *Client Certificate* \(only if *Proxy Type* is set to *Internet*\)

    The tenant authenticates itself against the receiver using a client certificate.




</td>
<td valign="top">

Specifies the authentication method used to connect to the SOAP service.

</td>
</tr>
<tr>
<td valign="top">

Private Key Alias

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Allows you to enter the private key alias name that gets the private key from the keystore and authenticates you to the receiver in an HTTPS communication.

> ### Note:  
> Available only when **Authentication** is set to **Client Certificate**.



</td>
</tr>
<tr>
<td valign="top">

Timeout \(in ms\)

</td>
<td valign="top">

60000

</td>
<td valign="top">

Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

The default value is 60000 milliseconds \(1 minute\).

</td>
</tr>
<tr>
<td valign="top">

Compress Message

</td>
<td valign="top">

Enabled

</td>
<td valign="top">

Enables the WS endpoint to send compressed request messages to the WS provider and to indicate to the WS provider that it can handle compressed response messages.

</td>
</tr>
<tr>
<td valign="top">

Allow Chunking

</td>
<td valign="top">

Enabled

</td>
<td valign="top">

Used for enabling HTTP chunking of data while sending messages.

> ### Note:  
> This option is enabled by default to avoid large HTTP messages. Make sure that the receiver of the message allows chunking if the *Allow Chunking* option is enabled.



</td>
</tr>
<tr>
<td valign="top" rowspan="6">

WS-Security

</td>
<td valign="top">

WS-Security Configuration

</td>
<td valign="top">

Based on Policies in WSDL

</td>
<td valign="top">

Specifies how WS-Security settings are to be configured.

-   *Via Manual Configuration in Channel*

    The security settings are to be configured manually

-   *Based on Policies in WSDL*

    The security settings are specified as part of the receiver endpoint \(within the endpoint WSDL\) in elements as defined by the WS-Policy standard.

-   *None*

    No WS-Security is applied for the message exchange.




</td>
</tr>
<tr>
<td valign="top">

Credential Name

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies how the user name token is to be configured. Select this option to authenticate at message level based on a user ID and a password \(transported within a SOAP message\).

</td>
</tr>
<tr>
<td valign="top">

Private Key Alias for Signing

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies an alias for the tenant private key that is to be used to sign the message.

</td>
</tr>
<tr>
<td valign="top">

Public Key Alias for Encryption

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies an alias for the public key that is to be used to encrypt the message.

</td>
</tr>
<tr>
<td valign="top">

Signature Algorithm

</td>
<td valign="top">

SHA1/RSA

</td>
<td valign="top">

Specify a signature algorithm to be applied when signing the request message.

Possible values:

-   SHA1 \(default value\)

-   SHA256

-   SHA512




</td>
</tr>
<tr>
<td valign="top">

Receiver is Basic Security Profile Compliant

</td>
<td valign="top">

Enabled

</td>
<td valign="top">

Leave this option selected if the receiver system complies with the basic security profile \(as assumed to be the case for most systems\). Deselect this option if the receiver system does not support this security profile.

</td>
</tr>
</table>

