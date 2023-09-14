<!-- loiob7812a546ab14de6aa0a7c919d8272bb -->

# Parameterizing Integration Flows Using the Partner Directory

The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network.

You can use the information stored in the Partner Directory to parameterize integration flows. Parameterizing works in such a way that partner-specific information can be read from the Partner Directory by certain integration flow steps and processed during runtime. Partner-specific information is read from the Partner Directory at runtime based on partner-specific values contained in the incoming request or the payload of the inbound message. We also refer to this behavior as *dynamic* usage of integration flow parameters.

> ### Note:  
> Partner-specific information comprises information such as endpoints, XSLT mappings, XSD definitions, or certificates \(to mention some examples\).

The Partner Directory doesn’t come with a dedicated user interface. You can access \(read/write\) its content through the OData API as well as during message processing through certain \(parameterized\) integration flow steps.

Storing partner-specific information in the Partner Directory has the advantage that you can add new partners to the network without the need to edit and redeploy any integration flow. Therefore, it provides a convenient option to extend your business partner network without any downtime of your scenario.



<a name="loiob7812a546ab14de6aa0a7c919d8272bb__section_i5k_fkn_2gb"/>

## Want to Learn More

For an introduction into the concepts, see: [Partner Directory Concepts](partner-directory-concepts-f917d6e.md).

For information on the OData API access to the Partner Directory, see: [Partner Directory](partner-directory-0fe80dc.md).

For information on the integration flow components that can be parameterized with Partner Directory content, see [Parameterizable Integration Flow Components](parameterizable-integration-flow-components-1aa4ba7.md).

Dedicated integration flow design guidelines show you how to use the Partner Directory. For more information, see [Use the Partner Directory Appropriately](use-the-partner-directory-appropriately-6e00412.md).

The following SAP Community blogs introduce you step-by-step to the topic:

-   [Cloud Integration – Partner Directory – Step-by-Step Example](https://blogs.sap.com/2017/07/25/cloud-integration-partner-directory-step-by-step-example/)

-   [Cloud Integration – Partner Directory – Partner Dependent XML Structures and IDs](https://blogs.sap.com/2017/08/22/cloud-integration-partner-directory-partner-dependent-xml-structures-and-ids/)

-   [Cloud Integration – Partner Directory – Sender Partner Connecting with Client Certificate Authentication](https://blogs.sap.com/2017/08/24/cloud-integration-partner-directory-sender-partner-connecting-with-client-certificate-authentication/)

-   [Cloud Integration – Partner Directory – Partner Dependent User Credential Selection](https://blogs.sap.com/2017/08/25/cloud-integration-partner-directory-partner-dependent-user-credential-selection/)

-   [Cloud Integration – Partner Directory – Mass Configuration](https://blogs.sap.com/2017/08/25/cloud-integration-partner-directory-mass-configuration/)




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
> 
> 
> Limit for certificate-to-user mapping \(when using the Neo environment\): 2 MB \(corresponds to about 2000 X.509 certificates\)
> 
> This component stores data on your tenant. Note that the tenant space is limited and shared with other tenant data like message processing logs.



> ### Note:  
> The maximum size of a keystore is 2 MB \(when using the Neo environment\).
> 
> -   The 2 MB limit corresponds to around 2000 X.509 certificates.
> 
> -   A key pair with a chain of three X.509 certificates consumes about 3 KB, so if the keystore only contains key pairs of this type, then you can store around 600 key pairs in the keystore.
> 
> 
> The maximum size of a keystore is 6 MB \(when using the Cloud Foundry environment\).
> 
> -   The 6 MB limit corresponds to around 6000 X.509 certificates.
> 
> -   A key pair with a chain of three X.509 certificates consumes about 3 KB, so if the keystore only contains key pairs of this type, then you can store around 1800 key pairs in the keystore.

If you upload a whole keystore \(`.jks` file\) to the tenant, the maximum keystore size is limited to 2 MB.

