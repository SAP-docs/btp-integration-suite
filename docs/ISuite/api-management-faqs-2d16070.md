<!-- loio2d1607095c7346e6bb3d5d4a1a2d2181 -->

# API Management FAQs

Frequently asked questions for SAP API Management.



<a name="loio2d1607095c7346e6bb3d5d4a1a2d2181__section_t2q_2mq_wbc"/>

## Connections


<table>
<tr>
<th valign="top">

Questions

</th>
<th valign="top">

Answers

</th>
</tr>
<tr>
<td valign="top">

How does API Management connect to on-premise back-end system \(SAP CRM, ERP, S/4 Hana\)?

</td>
<td valign="top">

SAP API Management supports cloud connector and through cloud connector, it connects to backend on premise system.

</td>
</tr>
<tr>
<td valign="top">

If APIM connects to on-premise system via cloud connector, is there any degrade in the performance?

</td>
<td valign="top">

We do not see any degradation in performance when connecting APIM to on-premise system via cloud connector.

</td>
</tr>
</table>



<a name="loio2d1607095c7346e6bb3d5d4a1a2d2181__section_i5j_hmq_wbc"/>

## Supported Technologies


<table>
<tr>
<th valign="top">

Questions

</th>
<th valign="top">

Answers

</th>
</tr>
<tr>
<td valign="top">

Are HANA xsOData APIs supported by API Management?

</td>
<td valign="top">

Yes, HANA xsOData APIs are supported by API Management. Further, API Management takes advantage of ODATA REST APIs through the metadata. This allows to quickly create API proxies, which will automatically import resources and documentation from the metadata. For more information, see [Connecting and exposing APIs from SAP HANA](https://community.sap.com/t5/technology-blogs-by-sap/blog-series-api-provider-part-4-connecting-and-exposing-apis-from-sap-hana/ba-p/13311799).

</td>
</tr>
<tr>
<td valign="top">

Are JMS, AS2, RFC supported by API Management?

</td>
<td valign="top">

No. These communication protocols are quite specific, and not within the scope of a dedicated API Management solution. For advanced integration scenarios in which protocol conversion or protocol support is needed, we recommend to use SAP Cloud Integration.

</td>
</tr>
</table>



<a name="loio2d1607095c7346e6bb3d5d4a1a2d2181__section_elj_mmq_wbc"/>

## Differences Between Services


<table>
<tr>
<th valign="top">

Questions

</th>
<th valign="top">

Answers

</th>
</tr>
<tr>
<td valign="top">

What is the difference between SAP Developer Hub and SAP API Management?

</td>
<td valign="top">

SAP API Management is a solution that helps customers to secure, manage, transform and publish APIs from both SAP and non-SAP systems. The published APIs can be consumed within mobile or web applications on any platform. Application developers who want to use a published API need to subscribe to the respective API. Usage of the published APIs can be monitored and analyzed from SAP API Management.

SAP Developer Hub provides a central catalog of SAP and selected partner APIs allowing developers to search, discover, experience and consume the services they need to build new applications, app extensions or process integrations.

</td>
</tr>
<tr>
<td valign="top">

What is the difference between an Enterprise Service Bus \(ESB\) with API Management Capabilities and SAP API Management?

</td>
<td valign="top">

Enterprise Service Buses \(ESB\) are solutions designed to perform integration between siloed applications and systems, and direct partners. ESB evolved from the backend upwards, providing adapters to systems of records. ESB usually runs in the core of the IT, serves predictable traffic and provides protection against typical internal threats. Also, developers using the ESB’s interfaces are usually part of the core IT team, hence they have simplified access to the interfaces and their documentation.

API Management is a solution designed at managing connectivity of modern, API-based, clients and applications: each interaction with the client or application involves a query to the backend. API Management is designed for the access from the outside world, with specific and unpredictable traffic as well as specific security threats. Lastly, because developers using the APIs may not be part of the core IT team of the providing organization, they need to rely on a well-documented and self-service oriented API Catalog to work efficiently.

All the aspects described below significantly differentiate an ESB and an API Management:

-   An ESB is built for predictable traffic and internal usage, whereas API Management can handle unpredictable and very high traffic.

-   An ESB usually does not provide business monitoring capabilities, which is provided by API Management to steer digitalization projects.
-   An ESB is built for securing interfaces using standard internal integration mechanisms, whereas API Management provides resilience to specific, new internet threats.
-   An ESB can integrate with an Enterprise Service Repository, whereas API Management is built from the ground to provide simple API access to the developers through an API catalog.



</td>
</tr>
<tr>
<td valign="top">

How is the API trial offering different from product offering?

</td>
<td valign="top">

There is no difference in the feature set. All features available in production are also available in the trial. However, in the trial, you cannot onboard other developers.

</td>
</tr>
<tr>
<td valign="top">

Is Raise Fault policy different from Fault Rules?

</td>
<td valign="top">

In API Management, the Raise Fault policy is used to generate a custom HTTP status code. For more information, see [Creating your own status codes](https://community.sap.com/t5/technology-blogs-by-sap/sap-api-management-creating-your-own-status-codes/ba-p/13332769).

</td>
</tr>
</table>



<a name="loio2d1607095c7346e6bb3d5d4a1a2d2181__section_dcs_nmq_wbc"/>

## Capabilities


<table>
<tr>
<th valign="top">

Questions

</th>
<th valign="top">

Answers

</th>
</tr>
<tr>
<td valign="top">

Can non-SAP APIs be managed by API Management?

</td>
<td valign="top">

Yes, API Management is agnostic when it comes to the APIs it manages. It can handle SAP APIs, non-SAP APIs, ODATA REST APIs, and many others.

</td>
</tr>
<tr>
<td valign="top">

Can you implement business logic in API Management?

</td>
<td valign="top">

Yes, it is possible to some extent. However, complex business logic should either be externalized into a microservice or implemented in the integration layer, such as SAP Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

Is data validation possible within API Management?

</td>
<td valign="top">

Yes, to some extent. XML formats can be validated against XML schemas, for instance. However, API Management does not validate the content of the message itself but rather checks the metadata and structure of the payload. For instance, API Management will fend off threats like XML bombs, amount of nested JSON structures, or code injections.

</td>
</tr>
</table>



<a name="loio2d1607095c7346e6bb3d5d4a1a2d2181__section_i5r_4mq_wbc"/>

## Other


<table>
<tr>
<th valign="top">

Questions

</th>
<th valign="top">

Answers

</th>
</tr>
<tr>
<td valign="top">

How to use SAP PO's SOAP interfaces in API Management?

</td>
<td valign="top">

SAP Process Orchestration is the middleware of choice for SAP customers to build A2A and B2B interfaces. In this digital age, more customers are opening up interfaces for digital interactions as open APIs. Open APIs are used to integrate with partners and with other supply chain business networks and marketplaces. APIs are becoming the digital building blocks for integrations, especially in the B2B world. For more information, see [Blog Series](https://community.sap.com/t5/technology-blogs-by-sap/blog-series-use-sap-cloud-platform-api-management-to-expose-sap-process/ba-p/13343283).

</td>
</tr>
<tr>
<td valign="top">

Where can I find more information on policies?

</td>
<td valign="top">

For detailed information regarding policy types, see [Policy Types](https://help.sap.com/docs/sap-api-management/sap-api-management/policy-types?version=Cloud).

</td>
</tr>
<tr>
<td valign="top">

How to onboard an application developer on the Developer Hub?

</td>
<td valign="top">

For detailed instructions on how to onboard an application developer, see [Onboard an Application Developer](https://help.sap.com/docs/sap-api-management/sap-api-management/onboard-application-developer?version=Cloud).

</td>
</tr>
<tr>
<td valign="top">

What are the predefined variables available in API Management policies?

</td>
<td valign="top">

For detailed information of all the available variables in API Management policies, see [Variable References](https://help.sap.com/docs/sap-api-management/sap-api-management/variable-references?version=Cloud).

</td>
</tr>
<tr>
<td valign="top">

What are the security policies offered by API Management?

</td>
<td valign="top">

API Management offers many out-of-the-box API security best practices which can be customized based on your enterprise requirements. For more detailed information, see [API Security Best Practices](https://community.sap.com/t5/technology-blogs-by-sap/part-1-api-security-best-practices-restrict-access-to-api-based-on-ip/ba-p/13335433).

</td>
</tr>
</table>

**Related Information**  


[Limits in API Management](limits-in-api-management-f70f425.md "This topic describes the product configuration and the naming conventions for API Management.")

[Monitor the Health of Custom Domain Virtual Host Certificates Using SAP Cloud ALM](monitor-the-health-of-custom-domain-virtual-host-certificates-using-sap-cloud-alm-7bd9d9f.md "You can use SAP Cloud Application Lifecycle Management (ALM) application to proactively detect issues and monitor the health of custom domain virtual host certificates in API Management.")

