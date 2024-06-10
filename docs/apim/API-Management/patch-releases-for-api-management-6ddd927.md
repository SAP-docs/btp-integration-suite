<!-- loio6ddd927cbeaa42e384dc903e6002e269 -->

# Patch Releases for API Management

This topic provides information on patch releases for API Management that are provided for bug fixes.



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

-   When navigating to product details from the product list in the Application details page, particularly when the product has a different name and title in API business hub enterprise the following issues were observed:

    -   Users are unable to navigate to the product details from the product list if the product has a different name and title.

    -   The APIProduct uses the name as the primary key in API business hub enterprise, but the Application details page uses the title to navigate, which resulted in an error.


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

