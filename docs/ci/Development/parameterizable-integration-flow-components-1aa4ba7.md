<!-- loio1aa4ba7a38fa4f0e8324553e3b15d05d -->

# Parameterizable Integration Flow Components



The following integration flow components are parameterizable so that partner-specific information \(such as partner endpoint address, specific mapping, client certificates for inbound calls\) can be used at runtime.

-   XSLT: XSLT files are specified by each partner

-   XML Schema Validator: XSD files are specified by each partner

-   HTTP receiver adapter: receiver address \( however, one common user or client certificate is used to call the partner system\)

-   HTTP receiver adapter: user credential

-   HTTP sender adapter: sender partner-specific user or client certificate

-   AS2 receiver adapter: receiver address, partner X509 certificate to encrypt message \(however, one common user or client certificate is used to call the partner system\)

-   AS2 sender adapter: sender partner X.509 certificate to verify partner signature, sender partner-specific user or client certificate

-   SOAP receiver adapter: user credential

-   Script: for accessing partner-specific information and performing partner-specific operations




<a name="loio1aa4ba7a38fa4f0e8324553e3b15d05d__section_yn4_p4k_pdb"/>

## Partner Directory Parameters for AS2 Adapter

The AS2 sender reads the following parameters from the Partner Directory:

****


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Decrypt Message

</td>
<td valign="top">

SAP\_AS2\_Inbound\_Decrypt\_Message

</td>
<td valign="top">

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

Private Key Alias

</td>
<td valign="top">

pd:<pd parameter name\>

</td>
<td valign="top">

Parameter name of private key alias in Partner Directory.

</td>
</tr>
<tr>
<td valign="top">

Verify Signature

</td>
<td valign="top">

SAP\_AS2\_Inbound\_Verify\_Signature

</td>
<td valign="top">

-   notRequired

-   trustedCertificate

-   trustedRootCertificate




</td>
</tr>
<tr>
<td valign="top">

Public Key Alias

</td>
<td valign="top">

pd:<pd parameter name\>

</td>
<td valign="top">

Parameter name of public key in Partner Directory.

</td>
</tr>
</table>



AS2 MDN sender reads the following parameters from Partner Directory:

****


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Verify Signature

</td>
<td valign="top">

SAP\_AS2\_Inbound\_Mdn\_Verify\_Signature

</td>
<td valign="top">

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

Verify MIC

</td>
<td valign="top">

SAP\_AS2\_Inbound\_Mdn\_Verify\_Mic

</td>
<td valign="top">

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

Public Key Alias

</td>
<td valign="top">

pd:<pd parameter name\>

</td>
<td valign="top">

Parameter name of public key in Partner Directory.

</td>
</tr>
</table>

> ### Note:  
> PD parameters are shown in the MPL log as MPL properties.



<a name="loio1aa4ba7a38fa4f0e8324553e3b15d05d__section_lrt_h4k_pdb"/>

## Partner Directory Parameters for EDI Splitter


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Header Name

</td>
<td valign="top">

Defines the location of the XSD schema.

> ### Note:  
> The EDI splitter fetches the header name from the Partner Directory. For example, a header name for an EDIFACT message is defined as `pd:PID:<<pattern>>:binary`, where **<<pattern\>\>** can be `${edi.EDI_Document_Standard}_${edi.EDI_Message_Type}_${edi.EDI_Message_Version}` . At runtime, the splitter automatically picks up the EDI document standard \(UN-EDIFACT\), message type, and message version from the payload. Hence, an EDIFACT header name can look like this: `pd:userName:UN-EDIFACT_ORDERS_D96A:binary`.



</td>
</tr>
</table>

For a step-by-step example of how to use the Partner Directory, see [Cloud Integration – Partner Directory – Step-by-Step Example](https://blogs.sap.com/2017/07/25/cloud-integration-partner-directory-step-by-step-example/).

