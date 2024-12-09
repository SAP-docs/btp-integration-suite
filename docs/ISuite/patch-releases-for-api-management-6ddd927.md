<!-- loio6ddd927cbeaa42e384dc903e6002e269 -->

# Patch Releases for API Management

This topic provides information on patch releases for API Management that are provided for bug fixes.



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_g1l_fv4_4dc"/>

## December 2024


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.174.4

</td>
<td valign="top">

The credential type "instance-secret" is deprecated in the oauth2-configuration of the security descriptor. This patch fixes the changes in the XSUAA security descriptor for the deprecated configurations.

</td>
</tr>
</table>



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_x33_ssd_zcc"/>

## October 2024


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.173.4

</td>
<td valign="top">

The following issues have been identified:

-   Opproxy deployments were failing in stage 2 DCs.

-   There were data inconsistencies when publishing products manually and during product transport.

-   The activation/deactivation of the API Management capability in Integration Suite was failing intermitently. The same issue was also observed in the standalone API Management service.


This patch fixes the above issues.

</td>
</tr>
</table>



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_os3_hxb_pcc"/>

## September 2024


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.172.4

</td>
<td valign="top">

Key names in Key Value Maps don't allow trailing spaces. When you create key names, always check that you haven't included unintended spaces at the end.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.173.3

</td>
<td valign="top">

Validation of service instance key creation was causing an issue as the condition for provision instance use-case was not handled correctly. This issue has now been fixed.

</td>
</tr>
</table>



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_afk_kzm_1cc"/>

## July 2024

**Software Increment: 2405**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.170.4

</td>
<td valign="top">

Users were unable to discover resources for a few EDMX files. However, this issue has now been resolved.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.171

</td>
<td valign="top">

The current status of the existing credentials in the credstore didn't match the expected status outlined in the v3 docs. This issue has now been resolved.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.172

</td>
<td valign="top">

The on-premise API was returning an error when making a POST request with a body. However, we've resolved this issue.

</td>
</tr>
</table>



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_rkm_1sd_sbc"/>

## June 2024

**Software Increment: 2404**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.169.5

</td>
<td valign="top">

The import of the apiproxy with multiple target endpoints having the same on-premise provider as the target was previously failing. However, this issue has been resolved.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.169.5

</td>
<td valign="top">

The issue of API Discovery including resources that were marked as false in the service metadata has been resolved.

</td>
</tr>
</table>



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_hll_dw1_3bc"/>

## May 2024

**Software Increment: 2403**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.168.4

</td>
<td valign="top">

The transport of the apiprovider was failing due to a missing KVM. However, this issue has been resolved by creating the necessary KVMs during the provider creation process.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.168.4

</td>
<td valign="top">

The issue with the key credentials of the Devportal node service broker has been resolved. The correct key credentials are now available to access the application APIs.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.168.3

</td>
<td valign="top">

UI issues in the policy editor have been resolved. You can now move the splitters around effortlessly, enter the necessary policy details, and edit their flows without any interruptions to the user interface.

</td>
</tr>
</table>



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_dgt_12r_g1c"/>

## March 2024

**Software Increment: 2313**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.165.3

</td>
<td valign="top">

The prefix "custom\_" has been added to all custom metrics during creation. Additionally, the Policy Validator for the StatsCollector will check if a custom metric already exists and update it accordingly with the "custom\_" prefix in the StatsCollector.

</td>
</tr>
</table>



<a name="loio6ddd927cbeaa42e384dc903e6002e269__section_u3g_xqj_hrb"/>

## January 2024

**Software Increment: 2310**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Software Version

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Management 

</td>
<td valign="top">

1.162.7

</td>
<td valign="top">

The following issues have been identified:

-   In the event of an onboarding failure after successfully creating a keystore for opproxy, the same step was being executed again.

-   When navigating to product details from the product list in the Application details page, particularly when the product has a different name and title in Developer Hub the following issues were observed:

    -   Users are unable to navigate to the product details from the product list if the product has a different name and title.

    -   The APIProduct uses the name as the primary key in Developer Hub, but the Application details page uses the title to navigate, which resulted in an error.


-   The rate limiting for the SAP PKI Certificate Service on all Public & Private Cloud landscapes went live on November 16, 2023, according to the certificate service team. So adjustments need to be made to accommodate the rate limiting.


This patch fixes the above issues.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.162.6

</td>
<td valign="top">

In the Neo platform, the onboarding process for new developers in runtime was not functioning properly. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

1.162.5

</td>
<td valign="top">

Request initiated for all services to adopt the latest xsuaa security patch.

</td>
</tr>
</table>

