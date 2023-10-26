<!-- loio38822081dd254309a26084e92bd3614c -->

# SAML Assertion Policy

The Security Assertion Markup Language \(SAML\) Assertion policy enables API proxies to validate and generate SAML assertions in inbound and outbound requests, respectively.

SAML specification defines formats and protocols that enable applications to exchange XML-formatted information for authentication and authorization. A "security assertion" is a trusted token that describes an attribute of an app, an app user, or some other participant in a transaction. Security assertions are managed and consumed by two types of entities:

• Identity providers: Generate security assertions on behalf of participants.

• Service providers: Validate security assertions through trusted relationships with identity providers.

The API platform can act as an identity provider and as a service provider. It acts as an identity provider by generating assertions and attaching them to request messages, making those assertions available for processing by backend services. It acts as a service provider by validating assertions on inbound request messages.

**Generate SAML Assertion**

Policy Processing:

-   If the message type is not XML, and IgnoreContentType is not set to true, raise a fault.
-   If the Template is set, process the template as described for the AssignMessage policy. If any variables are missing and IgnoreUnresolvedVariables is not set, raise a fault.

    If the Template is not set, construct an assertion that includes the values of the Subject and Issuer parameters or their references.

-   Sign the assertion using the specified key.
-   Add the assertion to the message at the specified XPath.

Sample Schema for SAML Assertion Generation

> ### Sample Code:  
> ```
> <!--  The policy will gererate saml assertion and assign assertion to the varibale defined in xpath-->
> 
> <GenerateSAMLAssertion async="false" continueOnError="false" enabled="true" ignoreContentType="false" xmlns="http://www.sap.com/apimgmt"> 
>    <Issuer ref="saml.issuer">Issuer name</Issuer>
>     <KeyStore>
>    <Name >saml_key_store</Name>
>     <Alias >key_store</Alias>
>    </KeyStore>
>     <OutputVariable>
>         <FlowVariable>sapapim.assertion</FlowVariable>
>         <Message name="request">
>       <Namespaces>
>         <Namespace prefix="env">http://schemas.xmlsoap.org/soap/envelope/</Namespace>
>       </Namespaces>
>       <XPath>/env:Envelope/env:Header</XPath>
>     </Message>
>     </OutputVariable>
>     <Subject ref="saml.subject">Subject name</Subject>
> <Template ignoreUnresolvedVariables="false"><![CDATA[
> <saml2:Assertion ID="{saml.id}" IssueInstant="{saml.issueInstant}" Version="2.0" xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
>     <saml2:Issuer xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">{saml.issuer}</saml2:Issuer>
>     <saml2:Subject xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">
>         <saml2:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified">{saml.subject}</saml2:NameID>
>         <saml2:SubjectConfirmation Method="urn:oasis:names:tc:SAML:2.0:cm:bearer">
>             <saml2:SubjectConfirmationData NotOnOrAfter="{sapapim.notOnorAfter}" Recipient="{saml.recipient}"/>
>         </saml2:SubjectConfirmation>
>     </saml2:Subject>
>     <saml2:Conditions NotBefore="{sapapim.notBefore}" NotOnOrAfter="{sapapim.notOnorAfter}" xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">
>         <saml2:AudienceRestriction>
>             <saml2:Audience>{saml.audience}</saml2:Audience>
>         </saml2:AudienceRestriction>
>     </saml2:Conditions>
>     <saml2:AuthnStatement AuthnInstant="{sapapim.timestamp}" SessionNotOnOrAfter="{sapapim.notOnorAfter}" xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">
>         <saml2:AuthnContext>
>             <saml2:AuthnContextClassRef>urn:none</saml2:AuthnContextClassRef>
>         </saml2:AuthnContext>
>     </saml2:AuthnStatement>
> </saml2:Assertion>
>                 ]]></Template>
> </GenerateSAMLAssertion>
> ```

**Element Reference**


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

The name of the policy instance. The name must be unique in the organization. Characters you can use in the name are restricted to: A-Z0-9.\_\\-$ %. However, the Management UI enforces additional restrictions, such as automatically removing characters that are not alphanumeric.

</td>
</tr>
<tr>
<td valign="top">

ignoreContentTypeattribute

</td>
<td valign="top">

A boolean that needs to be set to false. By default, the assertion will not be generated if the content type of the message is not an XML Content-Type. If this is set to true, then the message will be treated as XML regardless of the Content-type.

</td>
</tr>
<tr>
<td valign="top">

Issuer

</td>
<td valign="top">

The unique identifier of the identity provider. If the optional refattribute is present, then the value of Issuer will be assigned at runtime based on the specified variable. If the optional refattribute is not present, then the value of Issuer will be used.

</td>
</tr>
<tr>
<td valign="top">

KeyStore

</td>
<td valign="top">

The name of the KeyStore that contains the private key and the alias of the private key used to digitally sign SAML assertions.

</td>
</tr>
<tr>
<td valign="top">

OutputVariable

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

FlowVariable

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Message

</td>
<td valign="top">

The target of the policy. Valid values are message, request, and response. When set to message, the policy conditionally retrieves the message object based on the attachment point of the policy. When attached to the request Flow, the policy resolvesmessage to request, and when attached to the response Flow, the policy resolves message to response. Note that GenerateSAMLAssertion can only be attached to the TargetEndpoint request Flow. So, when using the Generate SAML Assertion policy, you should set this value to request.

</td>
</tr>
<tr>
<td valign="top">

XPath

</td>
<td valign="top">

An XPath expression that indicates the element on the outbound XML document to which the policy will attach the SAML assertion.

</td>
</tr>
<tr>
<td valign="top">

SignatureAlgorithm

</td>
<td valign="top">

SHA1 or SHA256

</td>
</tr>
<tr>
<td valign="top">

Subject

</td>
<td valign="top">

The unique identifier of the subject of the SAML assertion. If the optional ref attribute is present, then the value of Subject will be assigned at runtime based on the specified variable. If the optionalref attribute is not present, then the value of Subject will be used.

</td>
</tr>
<tr>
<td valign="top">

Template

</td>
<td valign="top">

If present, then the assertion will be generated by running this template, replacing everything denoted \{\} with the corresponding variable, and then digitally signing the result. The template is processed following the AssignMessage policy rules.

</td>
</tr>
</table>

**SAML Assertion Validation**

Policy Processing:

-   The policy verifies that the inbound message request's media type is XML, by checking if the content type matches the formats text/\(.\*+\)?xml or application/\(.\*+\)?xml. If the media type is not XML, or if IgnoreContentType is not set, the policy raises a fault.
-   The policy parses the XML. If parsing fails, it raises a fault.
-   The policy validates the XML digital signature, using the values of TrustStore and ValidateSigner as described above. If validation fails, it raises a fault.
-   The policy checks the current timestamp \(if present\) against the NotBefore and NotOnOrAfter elements in the assertion.

Successful completion of the policy ensures the following:

-   The digital signature on the assertion is valid and was signed by a trusted CA.
-   The assertion is valid for the current time period.
-   The subject and issuer of the assertion would be extracted and set in flow variables. Other policies would use these values for additional authentication, such as checking if the subject name is valid, or passing it to a target system for validation.

Sample Schema for SAML Assertion Validation

> ### Sample Code:  
> ```
> <!-- The policy will validate saml request, the saml assertion is extracted from variable defined in xpath -->
> 
> <ValidateSAMLAssertion async="false" continueOnError="false" enabled="true" ignoreContentType = "false" xmlns="http://www.sap.com/apimgmt">
>     <RemoveAssertion>false</RemoveAssertion>
>     <Source name="request">
>     <Namespaces>
>     <Namespace prefix="samlp">urn:oasis:names:tc:SAML:2.0:protocol</Namespace>
>     <Namespace prefix="saml2">urn:oasis:names:tc:SAML:2.0:assertion</Namespace>
>     </Namespaces>
>     <XPath>/samlp:Response/saml2:Assertion</XPath>
>     </Source>
>     <TrustStore>saml_trust_store</TrustStore>
> </ValidateSAMLAssertion>
> ```

**Element Reference**


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

name attribute

</td>
<td valign="top">

The name of the policy instance. The name must be unique in the organization. Characters you can use in the name are restricted to: A-Z0-9.\_\\-$ %. However, the Management UI enforces additional restrictions, such as automatically removing characters that are not alphanumeric.

</td>
</tr>
<tr>
<td valign="top">

ignoreContentTypeattribute

</td>
<td valign="top">

A boolean that needs to be set to false. By default, the assertion will not be generated if the content type of the message is not an XML Content-Type. If this is set to true then the message will be treated as XML regardless of the Content-type.

</td>
</tr>
<tr>
<td valign="top">

Source

</td>
<td valign="top">

The target of the policy. Valid values are message, request, and response. When set to message, the policy conditionally retrieves the message object based on the attachment point of the policy. When attached to the request Flow, the policy resolves message to request, and when attached to the response Flow, the policy resolves message to response. Note that ValidateSAMLAssertion can only be attached to the ProxyEndpoint request Flow.

</td>
</tr>
<tr>
<td valign="top">

XPath

</td>
<td valign="top">

Child of Source. An XPath expression that indicates the element on the inbound XML document from which the policy can extract the SAML assertion.

</td>
</tr>
<tr>
<td valign="top">

Truststore

</td>
<td valign="top">

The name of the TrustStore that contains trusted X.509 certificates used to validate digital signatures on SAML assertions.

</td>
</tr>
<tr>
<td valign="top">

RemoveAssertion

</td>
<td valign="top">

A boolean that can be set to true or false. When true, the SAML assertion will be stripped from the request message before the message is forwarded to the backend service.

</td>
</tr>
</table>

The following flow variables are available after the policy is executed:

**Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

saml.id

</td>
<td valign="top">

The SAML assertion ID

</td>
</tr>
<tr>
<td valign="top">

saml.issuer

</td>
<td valign="top">

The "Issuer" of the assertion, converted from its native XML type to a string

</td>
</tr>
<tr>
<td valign="top">

saml.subject

</td>
<td valign="top">

The "Subject" of the assertion, converted from its native XML type to a string

</td>
</tr>
<tr>
<td valign="top">

saml.valid

</td>
<td valign="top">

Returns true or false based on the result of the validity check

</td>
</tr>
<tr>
<td valign="top">

saml.attribute.\{attribute\_name\}

</td>
<td valign="top">

The value of the named "Attribute" present in the assertion, converted from its native XML to a string

</td>
</tr>
<tr>
<td valign="top">

saml.attributeNames

</td>
<td valign="top">

The names of all the "Attributes" present in the assertion, in a comma-separated list

</td>
</tr>
<tr>
<td valign="top">

saml.issueInstant

</td>
<td valign="top">

IssueInstant

</td>
</tr>
<tr>
<td valign="top">

saml.subjectFormat

</td>
<td valign="top">

Subject format

</td>
</tr>
<tr>
<td valign="top">

saml.scmethod

</td>
<td valign="top">

Subject confirmation method

</td>
</tr>
<tr>
<td valign="top">

saml.scdaddress

</td>
<td valign="top">

Subject confirmation data address

</td>
</tr>
<tr>
<td valign="top">

saml.scdinresponse

</td>
<td valign="top">

Subject confirmation data in response

</td>
</tr>
<tr>
<td valign="top">

saml.scdrcpt

</td>
<td valign="top">

Subject confirmation data recipient

</td>
</tr>
<tr>
<td valign="top">

saml.authnSnooa

</td>
<td valign="top">

AuthnStatement SessionNotOnOrAfter

</td>
</tr>
<tr>
<td valign="top">

saml.authnContextClassRef

</td>
<td valign="top">

AuthnStatement AuthnContextClassRef

</td>
</tr>
<tr>
<td valign="top">

saml.authnInstant

</td>
<td valign="top">

AuthnStatement AuthInstant

</td>
</tr>
<tr>
<td valign="top">

saml.authnSessionIndex

</td>
<td valign="top">

AuthnStatement Session Index

</td>
</tr>
</table>

