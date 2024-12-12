<!-- loio0fe80dc9d3be4dfbbb89ee4c791d326e -->

# Partner Directory

The Partner Directory contains information on partners that are connected to a tenant in the context of a larger business partner network.

You can access the OData API at:

[https://api.sap.com/api/PartnerDirectory/](https://api.sap.com/api/PartnerDirectory/)

There, you find the basic operations.

This documentation provides additional information.

> ### Note:  
> There's also a Java API to access the Partner Directory using a programming language like Java Script or Groovy. For more information, check out the JavaDoc linked to at [SDK API](sdk-api-c5c7933.md) \(for example, check out the package `com.sap.it.api.pd`\).

> ### Caution:  
> The data is stored unencrypted in the Partner Directory. Therefore, make sure that the data does not contain any sensitive information \(for example, passwords or personal information\).

There's no dedicated user interface to access the Partner Directory. You can access its content only based on APIs.



<a name="loio0fe80dc9d3be4dfbbb89ee4c791d326e__section_qf3_gcx_k5b"/>

## Permissions

To authorize an API client to access the OData API, perform the steps as described at:

Perform the steps described at: [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md) 

Assign the following role collection:

`AuthGroup_TenantPartnerDirectoryConfigurator` \(see [Permissions](permissions-eaa8779.md)



<a name="loio0fe80dc9d3be4dfbbb89ee4c791d326e__section_uvw_dlf_t4b"/>

## Resources

More information on the concepts: [Partner Directory Concepts](partner-directory-concepts-f917d6e.md)

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

Alternative Partners

</td>
<td valign="top">

Represents an alternative partner.

You can access \(read, write, delete\) an alternative partner.

A partner can be identified by different identifiers. For example, a bank can be identified by the German bank code number \(Bankleitzahl or: BLZ\) or the international Bank Identifier Code \(BIC\).

Each alternative partner has three string fields: Agency, Scheme, and ID.

</td>
</tr>
<tr>
<td valign="top">

Authorized Users

</td>
<td valign="top">

Represents the user with which a partner sender system can log in into SAP Cloud Integration.

You can access \(read, write, delete\) an authorized user.

This entity is required for the authorization of the partner sender system when calling Cloud Integration. If the partner uses HTTPS with client certificate authentication to connect to Cloud Integration, a certificate-to-user-mapping is required \(in the Neo environment\).

An authorized user has a `user` property \(name of the authorized user\) and a `Pid` property \(internal identifier of the associated partner\).

The Pid may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

</td>
</tr>
<tr>
<td valign="top">

Binary Parameters

</td>
<td valign="top">

You can access \(read, write, delete\) a binary parameter of the Partner Directory \(for example, for an XSD document\).

A Partner Directory parameter has a value and a type. The currently supported predefined types are `Binary` and `String`.

The ID of this entity may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

A binary parameter has a maximum size of 1,5 MB.

The following content types are supported \(defined by the `ContentType` parameter\): xml, xsl, xsd, json, text, zip, gz \(for GZIP files\), zlib, crt \(for DER encoded X.509 certificates\)

Here, you can also specify the encoding for xml, xsl, xsd, json, and text \(separated by semicolon\), for example: `xml;encoding=UTF-8`

The parameter `Value` of this entity can have a maximum length of 262144 bytes.

</td>
</tr>
<tr>
<td valign="top">

Partners

</td>
<td valign="top">

You can read all partners or delete a partner from the Partner Directory.

A partner is identified by an internal identifier \(referred to as `Pid`\) \(which is unique within the tenant partner directory and has a maximum length of 60 characters\).

The Pid may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

A partner can have parameters \(StringParameter, BinaryParameter, or UserCredentialParameter\). The parameter is uniquely identified by the Pid of the partner to which the parameter belongs and its Id.

The ID of this entity may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

</td>
</tr>
<tr>
<td valign="top">

String Parameters

</td>
<td valign="top">

You can access \(read, write, delete\) a string parameter of the Partner Directory.

A Partner Directory parameter has a value and a type. The currently supported predefined types are Binary and String.

The ID of this entity may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

A string parameter has a maximum length of 4000 characters.

</td>
</tr>
<tr>
<td valign="top">

User Credential Parameters

</td>
<td valign="top">

Represents a *User Credentials* artifact \(that is to be used for outbound calls to a partner system\).

You can access \(read, write, delete\) a *User Credentials* artifact.

You use this parameter to configure and deploy *User Credentials* artifacts.

The *User Credentials* parameter contains a user and a password \(both maximum length of 200 characters\).

The ID of this entity may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

Note that the user credentials \(user and password\) relate to the receiver \(partner\) system that is targeted by an outbound call \(where these credentials are used for basic authentication\).

> ### Note:  
> For user credentials artifacts created by the OData API, an alias with the following naming convention is generated:
> 
> `pd:<Pid>:<Id>:UserCredential` 
> 
> `Pid` is the internal identifier of the Partner and `Id` is the Id of the User Credential Parameter.

> ### Note:  
> User credentials artifacts created with the API are displayed in the Web UI under *Manage Security* \(*Security Material* tile\).



</td>
</tr>
</table>

For general information about query options, see [Query Options](query-options-99f4b70.md).



<a name="loio0fe80dc9d3be4dfbbb89ee4c791d326e__AlternativePartner"/>

## Alternative Partner

Each alternative partner has the following properties:

-   *Agency*

    Abbreviation for the organization that defines the identification scheme and that issues names for the partner to be identified \(maximum length of 120 characters\)

-   *\(Identification\) Scheme*

    Reference framework within which partners are uniquely identified by names \(maximum length of 120 characters\)

-   *Id*

    Identifier for the partner \(issued by the agency\) \(maximum length of 225 characters\)

    Example: A person can be identified in many different ways, for example, by their customer number at a mail order company, or their name or employee number at their place of work. To able to identify a person uniquely, it isn't sufficient to just know the customer number, for example, you must know that **this** number is a customer number. Only once the frame of reference \(the identification scheme `Customer Number` \) is also known can a person be identified uniquely \(by using the number\). In the example, the agency `Mail Order Company` manages the identification scheme `Customer Number` . Different customers are issued unique names \(customer numbers\) within this scheme.

-   Pid

    Internal identifier of the associated partner


Restriction:

-   The triple `Agency`, `Scheme`, `Id` must be unique.

-   The triple `Agency`, `Scheme`, `Pid` must be unique \(only then you can look up the alternative partner Id from such a triple\).




<a name="loio0fe80dc9d3be4dfbbb89ee4c791d326e__section_wsk_33x_54b"/>

## Example Requests

You find various example requests on SAP Business Accelerator Hub at [https://api.sap.com/api/PartnerDirectory/](https://api.sap.com/api/PartnerDirectory/).

For more example requests, see [Partner Directory Example Requests](partner-directory-example-requests-30e9cd6.md).



To trigger the modifying actions \(POST, PUT, and DELETE\), you need to fetch a CSRF token first. You can do that in the following way: First, send a GET call to the API with a header `X-CSRF-Token` with the value `Fetch`. As a response, you get the value of the token in the header `X-CSRF-Token`. When sending the modifying request, add the header `X-CSRF-Token` with the token retrieved from the first call.



On SAP Business Accelerator Hub, you can test API calls against a sandbox tenant or against a custom tenant \(to be configured under *API Environment*\). If you want to perform an API call against your custom tenant using an HTTP client such like Postman, make sure that the request URL is composed in the following way:

`https://<host address>/api/v1/<relative resource path>`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

You can find the relative resource path for each operation on SAP Business Accelerator Hub.



> ### Caution:  
> **Limitations**
> 
> Be aware of the following limitations when working with the Partner Directory:
> 
> Size restrictions for the different entity types:
> 
> -   Maximum number of StringParameters overall: 3,000,000 \(corresponds to 10,000 partners each using 300 StringParameters\)
> 
> -   Maximum number of BinaryParameters overall: 400,000 \(corresponds to 10,000 partners each using 40 BinaryParameters\)
> 
> -   Maximum number of AlternativePartners overall: 1,000,000 \(corresponds to 10,000 partners each using 100 AlternativePartners\)
> 
> -   Maximum number of AuthorizedUsers overall: 500,000 \(corresponds to 10,000 partners each using 50 AuthorizedUsers\)



The maximum size of a keystore is 6 MB \(when using the Cloud Foundry environment\).

-   The 6 MB limit corresponds to around 6000 X.509 certificates.

-   A key pair with a chain of three X.509 certificates consumes about 3 KB, so if the keystore only contains key pairs of this type, then you can store around 1800 key pairs in the keystore.


If you upload a whole keystore \(`.jks` file\) to the tenant, the maximum keystore size is limited to 2 MB.



For detailed step-by-step descriptions how to use the Partner Directory, see the following blogs:

-   [Cloud Integration – Partner Directory – Step-by-Step Example](https://blogs.sap.com/2017/07/25/cloud-integration-partner-directory-step-by-step-example/)

-   [Cloud Integration – Partner Directory – Partner Dependent XML Structures and IDs](https://blogs.sap.com/2017/08/22/cloud-integration-partner-directory-partner-dependent-xml-structures-and-ids/)

-   [Cloud Integration – Partner Directory – Sender Partner Connecting with Client Certificate Authentication](https://blogs.sap.com/2017/08/24/cloud-integration-partner-directory-sender-partner-connecting-with-client-certificate-authentication/)

-   [Cloud Integration – Partner Directory – Partner Dependent User Credential Selection](https://blogs.sap.com/2017/08/25/cloud-integration-partner-directory-partner-dependent-user-credential-selection/)

-   [Cloud Integration – Partner Directory – Mass Configuration](https://blogs.sap.com/2017/08/25/cloud-integration-partner-directory-mass-configuration/)


**Related Information**  


[Parameterizing Integration Flows Using the Partner Directory](parameterizing-integration-flows-using-the-partner-directory-b7812a5.md "The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network.")

[Partner Directory Concepts](partner-directory-concepts-f917d6e.md "")

[Partner Directory Example Requests](partner-directory-example-requests-30e9cd6.md "")

