<!-- loioe01d3f0076384cf7b2d18adbccb067a1 -->

# Security Content

Manage security content on the tenant that is required to configure secure connections with remote systems.

Depending on the kind of connection, the applied authorization and authorization options, and the direction of the request \(either inbound or outbound\), different kind of security content needs to be created and deployed on the tenant.

You can access the OData API at [https://api.sap.com/api/SecurityContent/](https://api.sap.com/api/SecurityContent/) where you can find the basic operations.

This documentation provides additional information.



<a name="loioe01d3f0076384cf7b2d18adbccb067a1__section_kz2_zcx_k5b"/>

## Permissions

To authorize an API client to access the OData API, perform the steps as described in:

Perform the steps described in: [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md) 

Assign the following role template:

`MonitoringDataRead` \(see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md)\)



<a name="loioe01d3f0076384cf7b2d18adbccb067a1__section_uvw_dlf_t4b"/>

## Resources

****


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Certificate

</td>
<td valign="top">

Represents a trusted certificate \(keystore entry\) \(see [Managing Keystore Entries](managing-keystore-entries-2dc8942.md) and [X.509 Certificates](../40-RemoteSystems/x-509-certificates-8d38a83.md)\).

</td>
</tr>
<tr>
<td valign="top">

Key Pair

</td>
<td valign="top">

Represents a key pair of the tenant keystore \(see [Creating a Key Pair/SSH Key Pair](creating-a-key-pair-ssh-key-pair-b8a8601.md)\).

You can use the API to create, import, or export a private key pair. You can also create a certificate signing request, or import and export the related certificate chain.

</td>
</tr>
<tr>
<td valign="top">

Keystore Entry

</td>
<td valign="top">

Represents an entry of the tenant keystore \(see [Managing Keystore Entries](managing-keystore-entries-2dc8942.md)\).

The keystore contains private/public key pairs and certificates that are used in various scenarios.

Typically, a keystore contains keys and certificates for connections in both directions \(inbound and outbound\). Keys can be used for protecting the communication both on the transport-level and on the message-level. Keystore entries have to be maintained in accordance with the security content owned by the connected sender and receiver systems to ensure that the communication is protected based on public key technology.

For example, for scenarios where SAP Cloud Integration receives encrypted messages from a sender system, the tenant keystore needs to contain a private/public key pair \(where the private key is used by the Decryptor step of the integration flow\). The public key \(associated with the private key\) needs to be available in the corresponding key storage of the sender system.

A keystore typically contains entries that belong to the tenant administrator and entries that are owned by SAP. Each entry is uniquely identified by an alias.

Keystore entries have a dedicated lifecycle, which means that they have an expiration date and need to be renewed in a coordinated way.

Various properties are available for a keystore entry, for example, alias, key type, key size, the validation period, Subject DN and Issuer DN, and administrative information such as the time when the entry was last modified.

You can find a user interface to manage keystore entries in the *Keystore* tile of the *Monitor* section under *Manage Security*.

</td>
</tr>
<tr>
<td valign="top">

Keystore

</td>
<td valign="top">

Represents a tenant keystore \(see [Managing Keystore Entries](managing-keystore-entries-2dc8942.md)\).

You can use this resource to manage the keystore content as a whole. For managing individual keystore entries, use the Keystore Entry and Keystore resources.

You can import a keystore \(containing multiple keystore entries\) or export the public content of the keystore. You can back up keystore entries owned by the tenant administrator and, vice versa, retrieve backed-up entries. You can also trigger a mass deletion of keystore entries.

> ### Caution:  
> You need to use UTF-8 encoding for the charset of the JSON documents in the requests. The charset of the JSON documents of the responses is also UTF-8 encoded.
> 
> Hex representation is used for the `Alias` field; the server doesn't allow slashes or backslashes in a URI, even if they're percent encoded. Hex representation of the alias does mean that a UTF-8-encoded byte array is built from the alias string. A hex string is then calculated from this byte array.

> ### Note:  
> The maximum size of a keystore is 6 MB.
> 
> -   The 6 MB limit corresponds to around 6000 X.509 certificates.
> 
> -   A key pair with a chain of three X.509 certificates consumes about 3 KB, so if the keystore only contains key pairs of this type, then you can store around 1800 key pairs in the keystore.

If you upload a whole keystore \(`.jks` file\) to the tenant, the maximum keystore size is limited to 2 MB.

</td>
</tr>
<tr>
<td valign="top">

Keystore History

</td>
<td valign="top">

Represents the SAP Key History keystore \(see [Managing the Lifecycle of Keys](managing-the-lifecycle-of-keys-7d24b61.md)\).

This keystore contains old \(expired\) keys.

</td>
</tr>
<tr>
<td valign="top">

User Credentials

</td>
<td valign="top">

Represents a *User Credentials* artifact \(see [Deploying a User Credentials Artifact](deploying-a-user-credentials-artifact-6912d63.md)\).

To set up outbound connections using basic authentication, you need to deploy a *User Credentials* artifact. The artifact contains a user name and password and, if applicable, other parameters for the user associated with the outbound call.

</td>
</tr>
<tr>
<td valign="top">

OAuth2 Client Credentials

</td>
<td valign="top">

Represents an *OAuth2 Client Credentials* artifact \(see [Deploying an OAuth2 Client Credentials Artifact](deploying-an-oauth2-client-credentials-artifact-801b106.md)\).

When an OAuth 2.0 client credentials grant is implemented, the client gets access to the protected resources in two steps: After presenting a set of client credentials, the client fetches an access token from the token service. In a subsequent step, the client uses the access token to get access to the protected resources.

</td>
</tr>
<tr>
<td valign="top">

Certificate-to-User-Mapping \(Neo environment\)

</td>
<td valign="top">

Represents a *Certificate-to-User-Mapping* artifact required for inbound calls based on client certificate authentication and *User Role* authorization \(see [Managing Certificate-to-User Mappings, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/88ea2e5336d445f783c194c8d2780d35.html "The Manage Security area provides an overview of security-related artifacts. It also provides access to all certificate-to-user mappings defined for the tenant.") :arrow_upper_right:\).

> ### Note:  
> Certificate-to-user mappings are only available when using SAP Cloud Integration in the Neo environment.
> 
> The sender authenticates itself against Cloud Integration based on a digital client certificate. This certificate is also mapped to a user \(based on the information contained in a *Certificate-to-User Mapping* artifact deployed on the tenant\).

> ### Restriction:  
> Be aware of the following restrictions:
> 
> -   Only 1:n relationships between user and certificate are supported. The same user can be used for different certificates.
> 
> -   When using an entity in the context of the Partner Directory, only 290 entries for certificate-to-user mappings are allowed in the Partner Directory.
> 
> -   The user name \(`user` attribute\) can have a maximum length of 150 characters.
> 
> -   The key field `Id` contains the MD5 of the certificate in hex format. Note that certificates with the same MD5 value overwrite each other. The MD5 is calculated from the DER-encoded bytes \(not on the PEM format\) and the hex format uses lower case characters \(maximum length of 32 characters\).
> 
> -   The `Certificate` attribute contains an X.509 certificate in PEM-DER format \(maximum length of 8192 characters\).
> 
> -   When using an entity in the context of the Partner Directory, note that the Partner Directory creates the necessary user-to-role assignments for these users so that the users can execute integration flows on the runtime node.
> 
> 
> When deleting a certificate-to-user mapping, there are restrictions for change sets in a batch:
> 
> -   A change set can only contain one request with the `CertificateUserMapping` entity type.
> 
> -   If a change set contains a `CertificateUserMapping` request, it can't contain other requests with other entity types.



</td>
</tr>
<tr>
<td valign="top">

Acces Policies

</td>
<td valign="top">

Access policies allow you to restrict the access to integration artifacts and their associated data.

See: [Managing Access Policies](managing-access-policies-318d107.md)

</td>
</tr>
<tr>
<td valign="top">

Artifact References

</td>
<td valign="top">

Artifact references define for which artifacts \(for example, integration flows\) an access policy applies.

See: [Managing Access Policies](managing-access-policies-318d107.md)

</td>
</tr>
</table>

For general information about query options, see [Query Options](query-options-99f4b70.md).

> ### Note:  
> TheCloud Integration *Monitor* application provides a user interface to access these resources:
> 
> -   For User Credentials and OAuth2 Client Credentials, see the *Security Material* tile under *Manage Security*.
> 
> -   For Certificate, Key Pair, Keystore Entry, Keystore History, and Keystore, see the *Keystore* tile under *Manage Security*.
> 
> -   For Certificate-to-User-Mapping \(only available in the Neo environment\), see the *Certificate-to-User Mappings* tile under *Manage Security*.



<a name="loioe01d3f0076384cf7b2d18adbccb067a1__section_wsk_33x_54b"/>

## Example Requests

You find various example requests on SAP Business Accelerator Hub at [Security Content](https://api.sap.com/api/SecurityContent).

For additional example requests, see [Security Content Example Requests](security-content-example-requests-acb89ef.md).



Certain values \(for example, for the alias when indicated in the example request as `<hexalias>`\) need to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my alias` is expressed by the following decimal numbers: `109 121 32 97 108 105 97 115` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 6C 69 61 73`. Note that `6D` is the hexadecimal representation of `109`, and so forth. If you like to specify `my alias` in an example request, enter `6D7920616C696173`.

To trigger the modifying actions \(POST, PUT, and DELETE\), you need to fetch a CSRF token first. You can do that in the following way: First, send a GET call to the API with a header `X-CSRF-Token` with the value `Fetch`. As a response, you get the value of the token in the header `X-CSRF-Token`. When sending the modifying request, add the header `X-CSRF-Token` with the token retrieved from the first call.



On SAP Business Accelerator Hub, you can test API calls against a sandbox tenant or against a custom tenant \(to be configured under *API Environment*\). If you want to perform an API call against your custom tenant using an HTTP client such like Postman, make sure that the request URL is composed in the following way:

`https://<host address>/api/v1/<relative resource path>`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

You can find the relative resource path for each operation on SAP Business Accelerator Hub.

**Related Information**  


[Manage Security](manage-security-6e7c44c.md "The Manage Security section allows you to manage various kinds of security material (for example, user credentials, keystore entries), and to perform outbound connectivity tests.")

[Concepts of Secure Communication](../40-RemoteSystems/concepts-of-secure-communication-3545808.md "There are several options to protect the message exchange. You can secure the communication on transport level by selecting the HTTPS or SFTP protocol and installing specific authentication methods. In addition to that, you can set up methods to encrypt and decrypt the content of the message and to digitally sign and verify the message.")

[Keystore](../40-RemoteSystems/keystore-b163513.md "Certificates and key pairs are stored in one keystore per tenant, referred to also as tenant keystore.")

