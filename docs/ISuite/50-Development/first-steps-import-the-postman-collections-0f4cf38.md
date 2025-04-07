<!-- loio0f4cf38a058042e3a194b07948752b1c -->

# First Steps - Import the Postman Collections

The integration package contains the following Postman collections:

**Postman Collections**


<table>
<tr>
<th valign="top">

Postman Collection

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*SAP Cloud Integration Tenant Parameters Postman Environment \(CF\)* 

</td>
<td valign="top">

You can use this Postman collection as template to set up a Postman environment to test the example integration flows \(in the Cloud Foundry environment\).

</td>
</tr>
<tr>
<td valign="top">

*Partner Directory Example Integration Flows Postman Collection* 

</td>
<td valign="top">

You can use this Postman collection to call the Partner Directory OData API and the related example integration flows.

</td>
</tr>
</table>



<a name="loio0f4cf38a058042e3a194b07948752b1c__section_kx2_kqt_3mb"/>

## Setting Up the Postman Environment

After import of the collection, the related environments are added. The following figure shows the situation when you've imported both collections.

![](images/Guidelines_PD_Postman_Environments_2f5d810.png)

The environments created with these collections have the following parameters \(column *Environment* indicates if a parameter is relevant for Neo, Cloud Foundry, or both cloud environments\):

> ### Note:  
> The parameters for which **only** the *Neo* environment is indicated, are only relevant when using SAP Cloud Integration as standalone service in the Neo environment. These parameters are **not** relevant for SAP Integration Suite customers.

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Environment

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

partner\_id

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

Parameter to define the partner ID

You can flexibly specify different partner IDs with this parameter.

</td>
</tr>
<tr>
<td valign="top">

cpi\_username

\(Not relevant when using SAP Integration Suite; only relevant when using SAP Cloud Integration in the Neo environment\)

</td>
<td valign="top">

Neo

</td>
<td valign="top">

Enter the user of the user that is authenticated to call Cloud Integration \(for example, your S user\).

</td>
</tr>
<tr>
<td valign="top">

cpi\_password

\(Not relevant when using SAP Integration Suite; only relevant when using SAP Cloud Integration in the Neo environment\)

</td>
<td valign="top">

Neo

</td>
<td valign="top">

Enter the password for the user that is authenticated to call Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

cpi\_clientId

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Enter the clientid \(from the service key\) from the OAuth client that is authenticated to call Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

cpi\_clientSecret

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Enter the clientid \(from the service key\) from the OAuth client that is authenticated to call Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

cpi\_api\_clientId

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

`clientid` used to get the OAuth access token

See: [OAuth with Client Credentials Grant for API Clients](../40-RemoteSystems/oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

</td>
</tr>
<tr>
<td valign="top">

cpi\_api\_clientSecret

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

`clientsecret` used to get the OAuth access token

See: [OAuth with Client Credentials Grant for API Clients](../40-RemoteSystems/oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

</td>
</tr>
<tr>
<td valign="top">

cpi\_runtime\_url

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

Enter the base URL of the Cloud Integration runtime. This is the base address of a deployed integration flow endpoint with an HTTP-based sender adapter.

When you've deployed an integration flow with HTTPS sender adapter, the integration flow endpoint address is: `https://<cpi_runtime_url>/http/<relative adapter address>`

</td>
</tr>
<tr>
<td valign="top">

cpi\_designtime\_url

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

Enter the base URL of the Cloud Integration host. Note that here you need to enter the address at which you reach the Web UI and the OData API resources.

Note that the Web UI address is: `https://<cpi_designtime_url>/itspaces`

</td>
</tr>
<tr>
<td valign="top">

cpi\_token\_url

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Address of the OAuth authorization server

Note that when accessing the Partner Directory in the Cloud Foundry environment, you use OAuth with client credentials grant as authentication option.

Enter the value for `tokenurl` as provided in the service key.

See: [OAuth with Client Credentials Grant for API Clients](../40-RemoteSystems/oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

</td>
</tr>
<tr>
<td valign="top">

cpi\_api\_token

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

OAuth access token to access the Partner Directory OData API

See: [OAuth with Client Credentials Grant for API Clients](../40-RemoteSystems/oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

</td>
</tr>
<tr>
<td valign="top">

cpi\_x\_csrf\_token

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

CSRF token used for inbound HTTP calls.

</td>
</tr>
<tr>
<td valign="top">

cpi\_pd\_x\_csrf\_token

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

CSRF token used for inbound HTTP calls.

</td>
</tr>
<tr>
<td valign="top">

AS2\_inbound\_decrypt\_message

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

Specifies parameter *Decrypt Message* of the AS2 sender adapter in scenario [Use the AS2 Adapter with Dynamic Encryption and Signature Verification](use-the-as2-adapter-with-dynamic-encryption-and-signature-verification-2cd252c.md).

This boolean parameter can have the values `true` or `false`.

</td>
</tr>
<tr>
<td valign="top">

AS2\_inbound\_verify\_signature

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

Specifies parameter *Verify Signature* of the AS2 sender adapter in scenario [Use the AS2 Adapter with Dynamic Encryption and Signature Verification](use-the-as2-adapter-with-dynamic-encryption-and-signature-verification-2cd252c.md).

</td>
</tr>
<tr>
<td valign="top">

AS2\_SenderPublicKey

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

Public key used to encrypt message

Enter the Base64-encoded *CPIGuidelinesSenderKey* from the Mendelson tool as described under [Install and Configure Mendelson](install-and-configure-mendelson-cfa038e.md).

</td>
</tr>
<tr>
<td valign="top">

AS2\_ReceiverPrivateKey

</td>
<td valign="top">

Cloud Foundry

Neo

</td>
<td valign="top">

Alias of private key used by Cloud Integration to decrypt the message in the integration scenario [Use the AS2 Adapter with Dynamic Encryption and Signature Verification](use-the-as2-adapter-with-dynamic-encryption-and-signature-verification-2cd252c.md)

Enter the alias of the private key from the Cloud Integration keystore.

</td>
</tr>
</table>



<a name="loio0f4cf38a058042e3a194b07948752b1c__section_tzt_gwt_3mb"/>

## Importing the Collection to Set Up the Postman Requests

After you've imported the collection *Partner Directory Example Integration Flows Postman Collection*, it's displayed in the collections area in Postman.

The collection contains 2 folder structures for the different environments \(Cloud Foundry and Neo\).

Each environment-specific folder contains the following sub folders.

-   Folders to initially create Partner Directory entities

    The folders *Update Partner Directory \(Neo\)* and *Update Partner Directory \(CF\)* contain requests to create and update the necessary entities in the Partner Directory \(see: [First Steps - Create Entities in the Partner Directory](first-steps-create-entities-in-the-partner-directory-d32359a.md)\).

-   The folders contained in folder *Integration Flows \(Neo\)* or *Integration Flows \(CF\)* contain the requests to call the various example integration flows.

    -   Folder *Dynamic Receiver* contains requests to execute scenario [Dynamically Address Receivers](dynamically-address-receivers-dde6b3a.md).

    -   Folder *Authorized User* contains requests to execute scenario [Fetch the Partner Info from the Partner Directory](fetch-the-partner-info-from-the-partner-directory-a44a1f9.md).

    -   Folder *XSLT* contains requests to execute scenario [Perform an XSLT Mapping](perform-an-xslt-mapping-c6bf239.md).

    -   Folder *Alternative Partner ID* contains requests to execute scenario [Use an Alternative Partner Id to Retrieve Partner Information](use-an-alternative-partner-id-to-retrieve-partner-information-01a784c.md).


    > ### Note:  
    > Scenario [Use the AS2 Adapter with Dynamic Encryption and Signature Verification](use-the-as2-adapter-with-dynamic-encryption-and-signature-verification-2cd252c.md) is not called by Postman. Instead of this, you use the Mendelson tool to call this scenario.

-   Folders to illustrate Partner Directory OData API

    The folders *Partner Directory APIs \(Neo\)* and *Partner Directory APIs \(CF\)* contain requests to illustrate how to call the Partner Directory OData API. You don't necessarily execute the requests to run the example scenarios.


