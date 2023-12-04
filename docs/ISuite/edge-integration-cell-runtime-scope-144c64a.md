<!-- loio144c64af999f4cda8c9b1912ac1edb92 -->

# Edge Integration Cell Runtime Scope



<a name="loio144c64af999f4cda8c9b1912ac1edb92__section_ww2_4wl_lvb"/>

## Supported Features


<table>
<tr>
<th valign="top">

Supported Features

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Artifact types

</td>
<td valign="top">

-   Integration flow

-   APIs




</td>
</tr>
<tr>
<td valign="top">

Reusable artifacts

</td>
<td valign="top">

-   Script Collection

-   Integration Adapter

-   Value Mapping

-   Message Mapping




</td>
</tr>
<tr>
<td valign="top">

Policy Steps

</td>
<td valign="top">

The behavior of an API can be defined using policy steps, which allows for the incorporation of API-led integration capabilities into the API endpoint. The API artifact on Edge Integration Cell supports the following security and traffic management capabilities:

-   Traffic Management

    -   Quota Policy

    -   Surge Protection

    -   IP Filter


-   Security

    -   Authorization

    -   Authentication

    -   JSON Threat Protection

    -   CORS



For more information see, [Policy Definition and Types of Policies Supported by Edge Integration Cell](50-Development/policy-definition-and-types-of-policies-supported-by-edge-integration-cell-c744df5.md)

</td>
</tr>
<tr>
<td valign="top">

Integration flow steps

</td>
<td valign="top">

-   Process steps:

    *Integration Process*, *Local Integration Process*, *Exception Subprocess*

-   Transformation steps:

    *Content Modifier*, *Script*, *Filter*, *XML Modifier*, *XML to JSON Converter*, *XML to CSV Converter*, *EDI to XML Converter*, *XML to EDI Converter*, Encoders/Decoders \(*MIME*, *ZIP*, *GZIP*, *Base64*\), *Message Digest*

-   Mapping steps:

    *XSLT Mapping*, *ID Mapping*, *Message Mapping*

-   Persistence steps:

    *Write Variables*, *Data Store Operations*, *Persist*

-   Call steps:

    *Request Reply*, *Poll-Enrich*, *Send*, *Process Call*, *Looping Process Call*, *Idempotent Process Call*

-   Routing steps:

    *Router*, *Aggregator*, *EDI Splitter*, *General Splitter*, *Iterating Splitter*,*Zip Splitter*, *Tar Splitter*, *Multicast*, *Join*, *Gather*

-   Security steps:

    *PGP Encryptor*, *PGP Decryptor*, *PKCS7 Encryptor*, *PKCS7 Decryptor*, *PKCS7 Signer*, *PKCS7 Signature Verifier*, *XML Digital Signer*, *XML Signature Verifier*, *Simple Signer*

-   Validator steps:

    *XML Validator*, *EDI Validator*

-   Event steps:

    *Timer*, *Start Message*, *End Message*, *Start*, *Error Start*, *Error End*, *Terminate Message*, *Escalation End*


For more information see, [Configure Integration Flow Components](50-Development/configure-integration-flow-components-3171795.md).

</td>
</tr>
<tr>
<td valign="top">

Adapters

</td>
<td valign="top">

-   Sender adapters:

    AMQP, Ariba, AS4, Data Store, FTP, HTTPS, IDoc, JMS, Kafka, Mail, OData, ProcessDirect, SFTP, SOAP \(SAP RM\), SOAP \(1.x\), SuccessFactors REST, SuccessFactors SOAP, and XI.

-   Receiver adapters:

    AMQP, Ariba, AS4, ELSTER, Facebook, FTP, HTTP, IDoc, JDBC, JMS, Kafka, LDAP, Mail, OData V2, OData V4, ODC, OpenConnectors, ProcessDirect, SFTP, SOAP \(SAP RM\), SOAP \(1.x\), SuccessFactors OData V2, SuccessFactors OData V4, SuccessFactors REST, SuccessFactors SOAP, Twitter, and XI.


More information: [Configure Adapter in Communication Channels](50-Development/configure-adapter-in-communication-channels-1f06633.md).

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

-   Message monitoring, including tracing

-   Job scheduler


For more information about restrictions with regard to monitoring, see: [Application Monitoring](application-monitoring-c9863ba.md).

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

Secure content lifecycle using location-specific encryption keys

</td>
</tr>
</table>



<a name="loio144c64af999f4cda8c9b1912ac1edb92__section_rlx_rmq_lvb"/>

## Runtime Scope

This section describes the scope when working with Edge Integration Cell. Also, refer to the SAP Note [3391207](https://me.sap.com/notes/3391207), to know more about the out of scope actions for Edge Integration Cell.


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Scope

</th>
</tr>
<tr>
<td valign="top">

Integration content

</td>
<td valign="top">

500 MB

Refer to the SAP Community blog:

</td>
</tr>
<tr>
<td valign="top">

X.509 keystores

</td>
<td valign="top">

max. 20

</td>
</tr>
<tr>
<td valign="top">

Number of runtimes associated with a credential or X.509 keystore

</td>
<td valign="top">

max. 20

</td>
</tr>
<tr>
<td valign="top">

Message processing log \(MPL\) persistence

</td>
<td valign="top">

Depends on database storage size.

See: [Cloud Integration – Setting the Log Level for Message Processing](https://blogs.sap.com/2017/06/22/cloud-integration-setting-the-log-level-for-message-processing/)

</td>
</tr>
<tr>
<td valign="top">

Data store message persistence

</td>
<td valign="top">

Depends on database storage size.

See: [Optimize Performance](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/491c80d16c3547c3b124cf38857f1332.html)

</td>
</tr>
<tr>
<td valign="top">

Disk space

</td>
<td valign="top">

Depends on cluster node storage size.

See: SAP Note [2648415](https://me.sap.com/notes/2648415) to learn how to optimize the integration flow development in such a way that the integration flow doesn't run into the `No More Space left on Disk` error.

</td>
</tr>
<tr>
<td valign="top">

X.509 keystore

</td>
<td valign="top">

1 MB

</td>
</tr>
<tr>
<td valign="top">

PGP keyrings \(secring & pubring\)

</td>
<td valign="top">

1 MB

</td>
</tr>
<tr>
<td valign="top">

Known Host file

</td>
<td valign="top">

1 MB

</td>
</tr>
<tr>
<td valign="top">

JDBC data sources

</td>
<td valign="top">

500 per edge runtime

</td>
</tr>
<tr>
<td valign="top">

Max. number of credentials for the following four credential types combined:

-   User Credential

-   Secure Parameter

-   OAuth2 Client Credentials

-   OAuth2 SAML Bearer Assertion


> ### Note:  
> OAuth2 Authorization Code credential isn't supported in Edge runtime.



</td>
<td valign="top">

500 per runtime

</td>
</tr>
<tr>
<td valign="top">

JMS resources

</td>
<td valign="top">

Depends on cluster node storage size.

See: [JMS Resource Limits for Edge Integration Cell](50-Development/jms-resource-limits-for-edge-integration-cell-17366b3.md)

</td>
</tr>
</table>

> ### Note:  
> *Delay Software Update*
> 
> The Delay Software Update feature isn't available for Edge Integration Cell, because customers manage the edge nodes themselves.

