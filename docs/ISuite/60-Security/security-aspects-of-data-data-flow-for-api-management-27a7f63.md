<!-- loio27a7f6329f714253ac40682d1a7ec1b4 -->

# Security Aspects of Data, Data Flow for API Management 

Here you can find information on how to secure API Management applications.


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Securing APIs

</td>
<td valign="top">

Secure your APIs by referring to the following security policies supported by API Management:

-   [Basic Authentication](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/693c0d1720644d57918ed77acc6a95ef.html "Basic authentication policy takes a username and password, encode them to Base64 format and writes the resulting value to a variable. The resulting value is typically written to an HTTP header, such as the Authorization header in the form Basic Base64EncodeString.") :arrow_upper_right:
-   [OAuth v2.0](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/09b5abbd3d714ce29ee2366254261170.html "OAuth 2.0 defines an authorization protocol for protected API resources.") :arrow_upper_right:
-   [OAuth v2.0 GET](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/2e507ea5a8894836bba0877251840e4e.html "API Management generates and manages a set of OAuth resources for apps.") :arrow_upper_right:
-   [OAuth v2.0 SET](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/161c1e3ca8cc4d838c0b8c04d847fde7.html "") :arrow_upper_right:
-   [Verify API Key](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/4d15a0427494452dbb42a319e9bb420f.html "One of the mechanisms to prevent unauthorized access to APIs exposed over the internet is to use the verify API key policy.") :arrow_upper_right:
-   [SAML Assertion Policy](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/38822081dd254309a26084e92bd3614c.html "The Security Assertion Markup Language (SAML) Assertion policy enables API proxies to validate and generate SAML assertions in inbound and outbound requests, respectively.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

Security Best Practices

</td>
<td valign="top">

Security policies provide information on how to control access to your APIs with OAuth, API key and other threat protection features. For more information, refer to the following policies supported by API Management:

-   [Access Control](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/3f72aea270654527afb0a743fa52702a.html "Restrict access to your APIs based on specific Internet Protocol (IP) addresses.") :arrow_upper_right:
-   [JSON Threat Protection](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/952cbd7d32c342788ba699227e734547.html "Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.") :arrow_upper_right:
-   [XML Threat Protection](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/3de6615cc00843499d6a427e93e2c582.html "") :arrow_upper_right:
-   [Message Validation Policy](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/e68da2ff0e1241978fae3964261a41c5.html "Validates a message and rejects it if it does not conform to the specified requirements.") :arrow_upper_right:
-   [Regular Expression Protection](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/0118f91793b54ad78de0e831c10bd69f.html "API Management helps to identify common content level threats that follow certain patterns, by enabling developers configure regular expressions that can be evaluated against API traffic at runtime.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

Traffic management

</td>
<td valign="top">

API Management supports the following traffic management policies:

-   [Quota](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/1f742c1e1a5c4a21bd83994071ddaea0.html "The Quota policy defines the number of request messages an application can submit to an API over a given period of time.") :arrow_upper_right:
-   [Spike Arrest](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/bf441dc839034613b059cb508ad610f7.html "The Spike Arrest policy limits the number of requests forwarded from the point in the processing flow where the policy is attached as a processing step.") :arrow_upper_right:
-   [Concurrent Rate Limit](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/8f22baab7bce42b78e482f0599fc906d.html "The Concurrent Rate Limit policy is being decommissioned. The support for the Concurrent Rate Limit policy has come to an end. You can no longer create or update an API proxy with Concurrent Rate Limit policy. If you’re still using the policy and wondering which policy to use to best meet your rate-limiting needs, see .") :arrow_upper_right:



</td>
</tr>
</table>

