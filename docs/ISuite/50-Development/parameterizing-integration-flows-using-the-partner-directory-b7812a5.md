<!-- loiob7812a546ab14de6aa0a7c919d8272bb -->

# Parameterizing Integration Flows Using the Partner Directory

The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network.

The Partner Directory facilitates the management of integration scenarios encompassing communication networks with numerous partners. In these scenarios, integration flows are parameterized with partner-specific parameters that are centrally stored in the Partner Directory. At runtime, integration flows can read information from the Partner Directory, based on the partner-specific values contained in the incoming request or the payload of the inbound message. This *dynamic* usage of integration flow parameters provides the advantage of adding new partners to the network without the need to edit and redeploy any integration flow, allowing for the extension of the business partner network without any downtime of the scenario.

> ### Note:  
> Partner-specific information comprises information such as endpoints, XSLT mappings, XSD definitions, or certificates \(to mention some examples\).

You can access \(read/write\) the content of the partner directory through the OData API as well as during message processing through certain \(parameterized\) integration flow steps.



To display and maintain Partner Directory entries, there are the following options:

****


<table>
<tr>
<th valign="top">

Option

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

User interface access

</td>
<td valign="top">

In the *Monitor* section, you can access the Partner Directory, display existing entries and create new ones.

See: [Managing Partner Directory Entries](managing-partner-directory-entries-3d6eee7.md)

</td>
</tr>
<tr>
<td valign="top">

API access

</td>
<td valign="top">

You can access \(read/write\) its content through the OData API as well as during message processing through certain \(parameterized\) integration flow steps.

See: [Partner Directory](partner-directory-0fe80dc.md)

</td>
</tr>
</table>



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
> This component stores data on your tenant. Note that the tenant space is limited and shared with other tenant data like message processing logs.



> ### Note:  
> The maximum size of a keystore is 6 MB.
> 
> -   The 6 MB limit corresponds to around 6000 X.509 certificates.
> 
> -   A key pair with a chain of three X.509 certificates consumes about 3 KB, so if the keystore only contains key pairs of this type, then you can store around 1800 key pairs in the keystore.

If you upload a whole keystore \(`.jks` file\) to the tenant, the maximum keystore size is limited to 2 MB.

