<!-- loio023a4725bb734f86be8a5625abe54110 -->

# Patch Releases for Cloud Integration and Related Components

This topic provides information on patch releases for hotfixes, bugfixes, and code enhancements.



This topic covers patches for the following capabilities and features of SAP Integration Suite: Cloud Integration, Trading Partner Management, Integration Advisor, Integration Assessment, Migration Assessment, and Edge Integration Cell.

The following patch release information covers the most recent changes made to the latest version of the software.



<a name="loio023a4725bb734f86be8a5625abe54110__section_i5x_kr5_4dc"/>

## December 2024

Software Increment: 2409


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

Cloud Integration

</td>
<td valign="top">

8.22.17

</td>
<td valign="top">

Internal properties in Exchange were not being propogated when using ProcessDirect adapter in Camel 3x migration. This patch resolves the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.58.40

8.22.15

</td>
<td valign="top">

On Cloud Foundry, the Cloud Integration worker application failed to connect to the Credential Store Service due to network issues, causing the keystore to be unavailable. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_h4k_drs_ldc"/>

## November 2024

Software Increment: 2409


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

Trading Partner Management

</td>
<td valign="top">

6.58.34

</td>
<td valign="top">

Users are unable to select the newly created number range in the B2B scenario receiver interchange number range dropdown when the number of number ranges defined under profiles exceeds 255. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.58.31

</td>
<td valign="top">

Users are unable to add a certificate when the length of some fields exceeds 255 characters. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.58.31

</td>
<td valign="top">

The JDBC Adapter version 1.5 is currently not available in Camel 3.x tenants due to a version difference in the command \(cmd\) between the Camel 2.x and 3.x branches. This patch resolves the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_gp4_42n_vcc"/>

## October 2024

**Software Increment: 2409**


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

Cloud Integration

</td>
<td valign="top">

8.22.9

</td>
<td valign="top">

The Process Direct Adapter with Camel 3.x software was stuck in the processing state when called for Dynamic Address Resolution for the process direct consumer. This patch resolves the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.58.24

</td>
<td valign="top">

The JDBC Adapter version 1.5 was unavailable in Camel 3x tenants due to the command version difference between the Camel 2x and 3x branches. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_gv4_42n_vcc"/>

## September 2024

**Software Increment: 2408**


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

Cloud Integration

</td>
<td valign="top">

6.57.28

</td>
<td valign="top">

Fix for content deployment failures caused by authentication issue between the underlying microservices.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.91.6

</td>
<td valign="top">

The following issues have been fixed with this patch:

-   Display problems with mapping lines in MAG when an invalid mapping element is present.

-   MIG Simulation not working correctly with EDI Flat files.

-   EDI Flat files not being accepted for the customization of MIG during its creation.




</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_oy3_prr_ncc"/>

## August 2024

**Software Increment: 2407**


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

Integration Advisor

</td>
<td valign="top">

1.90.2

</td>
<td valign="top">

Issues were reported when activating a MAG with target MIG based on a custom message. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.56.33

</td>
<td valign="top">

In the tenants using Apache Camel 3.14 runtime the integration flows utilizing AS2 and AS4 adapters experience frequent retries during message processing failures. For more details and solution, see [3516264](https://me.sap.com/notes/3516264)

This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_td5_gcw_hcc"/>

## August 2024

**Software Increment: 2406**


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

Integration Advisor

</td>
<td valign="top">

1.89.3

</td>
<td valign="top">

Issues were reported when activating a MAG with target MIG based on a custom message. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.55.21

8.19.14

</td>
<td valign="top">

A recent security fix for GHAS/CodeQL message mapping runtime, which blocked XML payloads containing Document Type Declarations \(DTDs\), has been reverted due to customer impact. This patch withdraws the security fix.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.55.15

</td>
<td valign="top">

There was an issue with agreement activation.

Sending requests to an AS2 sender caused the issue of a partner Id not found. This patch fixes this issue. For more information, see SAP note [3506468](https://me.sap.com/notes/3506468).

There was a gateway timeout issue which resulted in the situation that loading the agreements failed. This patch mitigates this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.55.13

</td>
<td valign="top">

The following issues have been fixed with this patch:

-   The conversion from property to exchangeProperty was not properly implemented for the generation step, thus preventing the initiation of integration flows.

-   The default to use breadcrumb has been changed with Camel 3.x from `true` to `false`. As some customers rely on that header, the value has been reverted back to `true`




</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.55.12

</td>
<td valign="top">

OEM adapters will be upgraded to Apache Camel version 3.x during the migration to Camel 3.x. This patch provides a change that makes this step transparent on the user interface.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_vyv_klk_2cc"/>

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

Trading Partner Management

</td>
<td valign="top">

6.54.31

</td>
<td valign="top">

Message imports were failing due to the addition of an excess parameter in the **zip** file. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_r1l_g42_sbc"/>

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

Cloud Integration

</td>
<td valign="top">

6.53.31

</td>
<td valign="top">

A null pointer exception was thrown when sending an XI message. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.53.29

</td>
<td valign="top">

During software update, a *Timer* step configured with a start date triggered the writing of a message processing log at an unscheduled time.

This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.53.27

</td>
<td valign="top">

The JDBC Kafka consumer took too much time in case of an error.

The patch fixes the issue so that processing happens in asynchronous mode now.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.53.25

</td>
<td valign="top">

Content transport was impacted by an outdated service key stored in the credential store. The patch fixes this issue and ensures a consistent update of the affected entry in the credential store.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.53.23

</td>
<td valign="top">

When updating an authorized user ID that contains special characters in the Partner Directory, the user ID was not encoded. This patch fixes the issue

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.53.23

</td>
<td valign="top">

There was an issue with the EDI Splitter when processing requests containing attachments in ISO-8859-1 encoded stream. Special characters got converted to invalid characters. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_pr1_hzx_3bc"/>

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

Trading Partner Management

</td>
<td valign="top">

6.52.21

</td>
<td valign="top">

When activating an AS2 security which is configured with a certificate, the certificate configured for the security wasn’t found. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.52.20

</td>
<td valign="top">

There have been DNS cache issues with JCo library resulting in the RFC receiver adapter to throw the error `Opening socket to partner failed: error 111 - Connection refused`. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.52.19

</td>
<td valign="top">

The *Inspect* feature was not available. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.52.18

8.16.7

</td>
<td valign="top">

The missing DOCNUM field in the request payload was causing an error “Mandatory IDoc SOAP header missing”. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.52.17

</td>
<td valign="top">

There was an issue with number range redeployment that lead to artifacts getting stuck. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_blr_mdf_cbc"/>

## April 2024

**Software Increment: 2402**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">



</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.51.28

</td>
<td valign="top">

There have been problems to load *Monitor* page. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.51.27

</td>
<td valign="top">

There were some issues with the generation of key-pairs with X.509 certificates using elliptic curve algorithms \(for example, secp192k1, secp256k1, secp192r1, and others\). This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.51.26

</td>
<td valign="top">

There has been a performance issue with the Inspect feature. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.51.25

</td>
<td valign="top">

There was an issue with a potential negative impact on the deployment and undeployment of integration artifacts. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.51.23

</td>
<td valign="top">

System performance has been improved and truncation of value mapping has been fixed by changing the way XML files are read.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_g3d_cvj_51c"/>

## March 2024

**Software Increment: 2401**


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

Cloud Integration

</td>
<td valign="top">

6.50.23

</td>
<td valign="top">

There have been outages where scenarios stopped working. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.50.22

8.14.12

</td>
<td valign="top">

For some customers, scenarios using the SFTP adapter stopped working. Even after already having patched this issue, few customers observed continuation in following error message being raised: `SSH_MSG_DISCONNECT: 2 Failed to read binary`. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.50.22

</td>
<td valign="top">

There have been issues with the validation of agreements when many B2B transactions were operated. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.50.x

</td>
<td valign="top">

There were issues when TPM fetches tenant metadata from Cloud Integration-related tables, when Cloud Integration is not activated. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

5.58.9

7.23.13

</td>
<td valign="top">

There were multiple timer executions during camel 3x migration. This patch fixes the issue.There were multiple timer executions, during camel 3x migration. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

5.58.9

7.23.12

</td>
<td valign="top">

Some customers experienced issues with SFTP scenarios which stopped working and receiving connection errors from servers with message SSH\_MSG\_DISCONNECT: 2 Failed to read binary packet data! this patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

7.23.11

8.14.8

</td>
<td valign="top">

As the behaviour of Camel 3x has changed, some customers face an execution error in an edge case, when setting and reading the body within the same Groovy script. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_esy_5zq_51c"/>

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
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_p24_3d4_m1c"/>

## February 2024

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

Cloud Integration

</td>
<td valign="top">

6.49.27

</td>
<td valign="top">

This patch ensures that the API returns the details of the artifact version which is available on worker even if the multiple versions are available in CO db after executing regeneration.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.49.25

</td>
<td valign="top">

There have been partly broken integration flow processes, due to Database Timeouts happening upon degraded encryption/decryption performance. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.49.20.

</td>
<td valign="top">

The trading partner dynamic parameters used by the new migrated agreement could not be exported, and the user with the Read\_Only role is able to operate the cross actions. This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.49.4

</td>
<td valign="top">

EDI splitter threw an exception in integration flow for the Partners sending the EDIFACT payload without line feed and ?’ \(escape character + segment terminator\) in one segment. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.49.21

</td>
<td valign="top">

There was a performance degradation for message processing caused by repetitively calling NM functionality to retrieve the tenant name. This patch fixes the issue by caching this single value to avoid redundant calls.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_nyz_rrv_11c"/>

## January 2024

**Software Increment: 2312**


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

Cloud Integration

</td>
<td valign="top">

6.48.22

8.12.2

</td>
<td valign="top">

The patch addresses performance degradation issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.48.20

8.12.1

</td>
<td valign="top">

There has been an issue with upsert operations when using the JDBC adapter. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.48.19

</td>
<td valign="top">

In some cases, the list of trading partner agreements wasn’t shown when the ID of the associated B2B scenarios wasn’t defined. Furthermore, operating the trading partner agreements wasn’t possible. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_lb1_qwh_rzb"/>

## December 2023

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

Cloud Integration

</td>
<td valign="top">

6.46.40

</td>
<td valign="top">

Tenant provisioning was failing in some cases. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.46.39

</td>
<td valign="top">

There were the following issues:

-   Certificates for signature at AS2 sender side were not pushed to the Partner Directory.

-   It was not possible to create custom search attributes at receiver side in the one-way business transaction activity of the agreement.


This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

Integration Assessment

</td>
<td valign="top">

6.46.38

</td>
<td valign="top">

The following issues have been fixed with this patch:

-   Some security material artifacts were deactivated after being associated with one or more runtimes \(and the system returned an error message\).

-   
Furthermore, the consumption logic for Kafka acknowledgment messages has been improved.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.46.36

</td>
<td valign="top">

Issues have been observed when two EDI to XML converter steps were executed with different values for the *Exclude Interchange and Group envelopes*null parameter. This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.46.27

</td>
<td valign="top">

There is an issue occurring intermittently, affecting customers using the HTTP sender adapter under heavy load, resulting in MPLs in state COMPLETED and an HTTP 500 status response/ HTTP 200 with empty response. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_kwn_3l1_tzb"/>

## December 2023

**Software Increment: 2309**


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
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_yly_swh_rzb"/>

## November 2023

**Software Increment: 2309**


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

Cloud Integration

</td>
<td valign="top">

6.45.22

</td>
<td valign="top">

The following issues have been observed when designing message implementation guidelines \(MIGs\):

-   The MIG message type of the imported agreement has been wrong.

-   Import stopped when an agreement failed before agreement was executed.

-   Customers were unable to define custom separators.


This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.45.18

</td>
<td valign="top">

There was an issue with integration flows containing SFTP sender adapters that stopped processing and could not be redeployed. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_x11_bxw_fzb"/>

## November 2023

**Software Increment: 2309**


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

Cloud Integration

</td>
<td valign="top">

6.45.22

</td>
<td valign="top">

The following issues have been observed when designing message implementation guidelines \(MIGs\):

-   The MIG message type of the imported agreement has been wrong.

-   Import stopped when an agreement failed before agreement was executed.

-   Customers were unable to define custom separators.


This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.45.18

</td>
<td valign="top">

There was an issue with integration flows containing SFTP sender adapters that stopped processing and could not be redeployed. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_d44_zpb_bzb"/>

## October 2023

**Software Increment: 2308**


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

Cloud Integration

</td>
<td valign="top">

6.44.12

</td>
<td valign="top">

Back-up keystore entries were not shown due to an issue in the UI. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.78.5

</td>
<td valign="top">

Customers are unable to activate their MAGs due to a code issue as the UI generates duplicate mappings for the target nodes. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.44.13

</td>
<td valign="top">

As the external logging activation is not synchronized with Kafka activation, depending on the timing, the external logging activation can terminate during start-up and activation changes are no longer processed. External logging activation must be manually restarted. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_wd4_c52_qyb"/>

## September 2023

**Software Increment: 2305**


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

Cloud Integration

</td>
<td valign="top">

2.64.1

</td>
<td valign="top">

On some tenants, it was impossible to create or update integration flows using the JMS enterprise capability, due to a missing configuration on the on the enterprise licensing information. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_slp_hbl_jyb"/>

## August 2023

**Software Increment: 2305**


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

Cloud Integration

</td>
<td valign="top">

6.41.32

</td>
<td valign="top">

mTLS based XSUAA keys might get expired. This patch fixes the issue by extending the validity of mTLS based keys to 150 days.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.41.30

</td>
<td valign="top">

The integration flow execution was getting impacted during Neo to Cloud Foundry migration. This patch fixes the issue by improving the integration flow execution time.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_l42_2wn_fyb"/>

## July 2023

**Software Increment: 2305**


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

Cloud Integration

</td>
<td valign="top">

6.41.26

</td>
<td valign="top">

Transporting integration content from Transport Management Service or CTS+ to Cloud Integration was failing for some customers in the Cloud Foundry environment. This patch fixes the issue by allowing to fetch the required parameter before constructing the URL attribute.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.41.26

</td>
<td valign="top">

When `itspace` was included in the URL path of the *Monitor* \> *Integrations* \(message processing log monitoring\) application of SAP Integration Suite, the navigation between *Monitor* \> *Integrations* \(message processing log monitoring\) and *Monitor* \> *B2B Scenarios* was not possible. To fix the issue, with this patch `itspace` was removed from the SAP Integration Suite address.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.41.25

</td>
<td valign="top">

Customers were facing sporadic issues during script collection deployment. This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.41.24

</td>
<td valign="top">

1.  Due to object store issues, customers were not able to perform deployments or undeployments. This patch has enhanced logs to help identify root cause of the issue.

2.  There were CO crashes observed due to high CPU usage. This patch has a fix which improves the efficiency.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.41.23

</td>
<td valign="top">

When trying to deploy a message mapping artifact, the deployment was failing. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ghz_gbm_1yb"/>

## July 2023

**Software Increment: 2304**


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

Integration Advisor

</td>
<td valign="top">

1.74.3

</td>
<td valign="top">

There was an issue with activating agreements. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.40.20

</td>
<td valign="top">

There was the issue that when designing APIs \(using the *API Management* capability\) deployed integration flows could not be fetched. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.40.18

</td>
<td valign="top">

There was an issue with long-running transactions that resulted in exhaustion of database resources. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ycv_t1x_5xb"/>

## June 2023

**Software Increment: 2303**


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
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ir2_xh3_mxb"/>

## May 2023

**Software Increment: 2303**


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

Cloud Integration

</td>
<td valign="top">

6.39.18

</td>
<td valign="top">

There was an issue wis the de-commissioning of tenants. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.73.2

</td>
<td valign="top">

For pre-transformation of message implementation guidelines, only a limited amount of source nodes was selectable. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.39.17

</td>
<td valign="top">

There have been issues with the usage of JMS adapters. This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Integration Assessment

</td>
<td valign="top">

6.39.16

</td>
<td valign="top">

There have been issues with maintaining the sequence of questions in Integration Assessment questionnaires. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_bqs_d4l_cxb"/>

## April 2023

**Software Increment: 2302**


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

Integration Advisor

</td>
<td valign="top">

1.72.3

</td>
<td valign="top">

You were not able to finish the expected pre-transformation step, as some nodes from the source message implementation weren't shown in the drop down box and couldn't be selected.

Therefore it was not possible to save the mapping guidelines. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.38.23

</td>
<td valign="top">

The SAP UI5 dropdown box entries are limited to 100. If you have more than 100 tradings partners for example, the ones exceeding the limit will not be shown and cannot be selected for further operations. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.38.22

</td>
<td valign="top">

The deployment of artifacts from packages with names containing non ASCII characters was impossible in the Cloud Foundry environment with latest software version. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.38.21

</td>
<td valign="top">

The upcoming Netty version upgrade requests additional loggers to collect **request and response headers** for the AS2 adapter, to avoid incompatibility. This patch is for runtime data collection.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.38.20

</td>
<td valign="top">

There have been issues in productive tenants with too much logging, when the database connection is used in an uncategorized context. This makes the log analysis difficult. The default log level should be “Info” and only changed on demand. This patch fixes the issues

</td>
</tr>
<tr>
<td valign="top">

Migration Assessment

</td>
<td valign="top">

6.38.19

</td>
<td valign="top">

There have been issues with mapping projects that can’t be completed because of erroneous mapping lines contained in the corresponding MAG. These line are due to ambiguous node Ids, created during pre-transformation. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.38.16

</td>
<td valign="top">

There has been an issue with the script collection not being available after undeployment and redeployment. This causes the message processing to fail for the integration flows referring to the script collection. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_dqr_f35_vwb"/>

## March 2023

**Software Increment: 2301**


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

Cloud Integration

</td>
<td valign="top">

6.37.26

</td>
<td valign="top">

There has been an issue with the *Trace* log level that resulted in message processing failure when multiple integration flows have been traced. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.37.25

</td>
<td valign="top">

There has been an issue with the activation of endpoints with self-signed certificates \(for example, involved when using external logging with Splunk trial instances\). This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.71.3

</td>
<td valign="top">

There has been an issue with the export of MIGs based on old custom messages. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ufp_c35_vwb"/>

## February 2023

**Software Increment: 2213**


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

Cloud Integration

</td>
<td valign="top">

6.36.20

</td>
<td valign="top">

There was an issue with integration flows that processed many calls to adapters writing attributes \(for example, RFC adapter\). The time required to persist message processing logs increased quadratically with the number of adapter attributes. This resulted in failures and infinite retries. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_abx_1jl_jwb"/>

## February 2023

**Software Increment: 2212**


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

Cloud Integration

</td>
<td valign="top">

6.35.20

</td>
<td valign="top">

There was an issue with the data archiving feature as customers were unable to activate data archiving with client credentials. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.35.19

</td>
<td valign="top">

There was an issue in the DB when a large amount of data is being fetched, setting a transaction into "read only"mode and blocking the message transfer. The patch now allows the explicit closing of the transaction, setting the "read only" mode to "false" and restores the dirty connection.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.35.18

</td>
<td valign="top">

There were issues in some micro-services: if the Operations applications are restarted under load, a data race condition can cause the startup to fail and require a manual restart. No database connections can be made and all requests are rejected until the application is manually restarted. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.35.14

</td>
<td valign="top">

There has been an issue with the OData API resource `IntegrationRuntimeArtifacts` \(of the `Integration Content` API\) . This patch fixes the issue, and you can now use the following paths to fetch artifact information in the CLoud Foundry environment:

`/IntegrationRuntimeArtifacts(Id='{id}')/{property}/$value` 

`/IntegrationRuntimeArtifacts(Id='{id}')`

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_af3_nnm_fwb"/>

## January 2023

**Software Increment: 2212**


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

Cloud Integration

</td>
<td valign="top">

6.35.15

</td>
<td valign="top">

There was an issue with the XI sender adapter: Attachments with content types `text/*` and without `Content-Transfer-Encoding` header have been lost when parameter *Quality Of Service* was set to *Exactly Once*. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.35.13

</td>
<td valign="top">

There was a coding error that had an impact on the data consistency on the customer tenant. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_v1n_jf4_dwb"/>

## January 2023

**Software Increment: 2210**


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

Cloud Integration

</td>
<td valign="top">

6.33.32

</td>
<td valign="top">

In high volume situations, few customers observed intermittent SQL exception errors such as `Cannot execute INSERT/DELETE/UPDATE/SELECT FOR UPDATE in read-only mode` during runtime processing of messages. The patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.33.31

</td>
<td valign="top">

With this patch, user accounts that contain vertical bars can be parsed successfully.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_gqp_cdm_vvb"/>

## December 2022

**Software Increment: 2210**


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

Cloud Integration

</td>
<td valign="top">

6.33.26

</td>
<td valign="top">

With this patch, the following change has been implemented:

A check has been introduced for the process of copying an integration adapter package from the *Discover* to the *Design* section. This new check validates if the integration adapter contained in the package is supposed to be available for your service plan.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.67.5

</td>
<td valign="top">

There have been issues with the mapping documentation and the import and export feature. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.33.25

</td>
<td valign="top">

With this patch, the following change has been implemented:

The pretransformation feature was available for Integration Advisor as part of standalone SAP Cloud Integration \(but not in SAP Integration Suite\). With this patch, the feature is also available for SAP Integration Suite.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ikw_kks_jvb"/>

## November 2022

**Software Increment: 2209**


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

Integration Advisor

</td>
<td valign="top">

1.66.9

</td>
<td valign="top">

A coding error has resulted in customizing data being wrongly displayed. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Migration Tooling \(Beta\)

</td>
<td valign="top">

6.32.24

</td>
<td valign="top">

There have been issues with certain Migration Tooling \(Beta\) templates. This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.32.23

</td>
<td valign="top">

There was an issue with the integration flow simulation feature \(mapping simulations run into a timeout\). This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.32.19

</td>
<td valign="top">

There had been the following issue with the XI receiver adapter. Under certain conditions, the adapter doesn't send messages as expected: The message contains an attachment that already contains a content ID. The content ID is used to create the request without checking if the content ID is in accordance with the specification. The patch provides a bugfix that enables the XI receiver adapter to generate a new content ID in the described case and, that way, to make sure that message processing doesn't fail.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.32.18

</td>
<td valign="top">

There had been the following issue: An integration flow disappears from the Web UI after the first deployment, when the runtime location status transitions from NEW to ACTIVE. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_yth_4mw_bvb"/>

## October 2022

**Software Increment: 2208**


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

Cloud Integration

</td>
<td valign="top">

6.31.31

</td>
<td valign="top">

Customers are unable to access/navigate to the Integration Suite capabilities via home page, as the XUSAA token is giving an incorrect URL and impacting the token exchange flow. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.31.30

</td>
<td valign="top">

Integration flow simulations time out if kafka consumer rebalancing occurs during the simulation process, impairing the use of the simulation feature. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.31.26

</td>
<td valign="top">

If a stuck artifact is identified, deployment of new artifacts is disabled. This fix allows deployments/undeployment of artifacts and improves exception handling during the same.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.31.25

</td>
<td valign="top">

Due to a missing path in the Integration Studio router, customers could not use the CPI Discovery feature for APIM in the Integration Studio context. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.31.24

</td>
<td valign="top">

Due an existing bug, message processing can occasionally continue even if an artifact was undeployed. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.31.23

</td>
<td valign="top">

There were issues when using the environment variable `IT_TENANT_UX_DOMAIN` for URL calculation on Integration Studio tenants, as the environment variable value was changed.The value of `IT_TENANT_UX_DOMAIN` has been reset, and we introduced a new environment variable `IT_TENANT_ISTUDIO_UX_DOMAIN` to be used on Integration Studio tenants for URL calculation pointing to the Web UI.

For non-Integration-Studio tenants you still have to use `IT_TENANT_UX_DOMAIN` for all URL calculations.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.31.20

</td>
<td valign="top">

There is an issue in the JMS queue, as large messages are blocking the queue and stopping all messages deliveries. This patch fixes the issue in the API.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ekg_b1j_s5b"/>

## September 2022

**Software Increment: 2207**


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

Cloud Integration

</td>
<td valign="top">

6.30.16

</td>
<td valign="top">

There was an issue with the XMLFactory due to missing libraries in OData V2 receiver. This patch fixes the issue and contains log enhancements for trouble shooting.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.30.13

</td>
<td valign="top">

Due to an inconsistency in the unlocking/unlocking processes, timer based integration flow executions are overlapping. This patch fixes the issue

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.30.11

</td>
<td valign="top">

There is an issue in the simulation request execution for integration flows, message mappings and other artifacts. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.30.10

</td>
<td valign="top">

In some cases, DB connections are not closed in case of errors. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.30.9

</td>
<td valign="top">

The Integration flow deployment was failing due to worker configurations. The default worker was updated configuration to resolve the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_qpt_wns_j5b"/>

## August 2022

**Software Increment: 2206**


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

Cloud Integration

</td>
<td valign="top">

6.29.17

</td>
<td valign="top">

Improved the application parameters for optimized database communication during “Determination of Artifact status" and "On-demand deployment of Artifacts"

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.63.6

</td>
<td valign="top">

Due to missing name documentation for some nodes, the MIGs’ migration based on a custom message and containing qualified nodes is not possible. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.63.6

</td>
<td valign="top">

Since the validation check for messages requiring prefixes is failing, the use of MIG simulation for MIGs based on Edifact, Eancom and X12 TypeSystems is impossible. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.29.16

</td>
<td valign="top">

The TRM deployment experienced issues due to circular dependencies. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.29.15

</td>
<td valign="top">

In some cases, prepackaged content from “Order Management Foundation” \(OMF\) is adding debug information via scripts to MPLs, even if the log level is set to “info” due to a change in CPI behavior. This patch makes sure that the restriction on log level “debug” is considered again by the prepackaged content.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.29.14

</td>
<td valign="top">

The IDoc adapter generates and sets a new DOCNUM field in the payload when starting, but usually, the receiver system rejects this field. This patch deactivates this functionality for the customer.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.29.14

</td>
<td valign="top">

Optimize Database access to improve performance.

</td>
</tr>
<tr>
<td valign="top">

Integration Assessment

</td>
<td valign="top">

6.29.13

</td>
<td valign="top">

Activation of SAP Integration Suite Integration Assessment capability was failing. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.29.12

</td>
<td valign="top">

Concurrent connections to the same FTP server could run into communication errors. This patch fixes this issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_jd4_fhd_c5b"/>

## July 2022

**Software Increment: 2204**


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

Cloud Integration

</td>
<td valign="top">

6.27.24

</td>
<td valign="top">

Since object store calls are taking more time than expected, artifacts are stuck in intermediate state, impacting subsequent deployment and undeployment. To considerably improve the situation and allow further analysis, we removed redundant object store calls and added a log statement for the time taken for each call .

</td>
</tr>
<tr>
<td valign="top">

Integration Assessment

</td>
<td valign="top">

6.27.23

</td>
<td valign="top">

Memory optimization.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.27.22

</td>
<td valign="top">

Exceptions are not caught up properly on the worker instance when number ranges artifacts are not able to create DB sequences. This leads to artifacts not being deployed, and blocks further deployments as well.

This patch fixes the issues.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_l5x_d4v_5tb"/>

## June 2022

**Software Increment: 2204**


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

Integration Advisor

</td>
<td valign="top">

1.61.3

</td>
<td valign="top">

Customers were not able to use the export/import feature if source and target tenant were in the same region. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.27.16

</td>
<td valign="top">

In some high load situations and using JMS, the following issues have been observed:

-   Cloud Integration raises the following error message: `400: Too Many Producers`.

-   A JMS thread blocking Issue


This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.27.16

</td>
<td valign="top">

If using the AS2 adapter requesting a signed MDN with SHA1 algorithm and configured to verify MIC, verification of the MDN fails because value of *Received-content-MIC* has been changed from `sha1` to `sha-1`. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.27.14

</td>
<td valign="top">

There was an issue when converting the ASC\_X12 payload with a fixed value of *UN*. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.27.13

</td>
<td valign="top">

The SAP Master Data Integration adapter didn't process the parameters *Address*, *ODM Entity Type*, and *ODM Entity Version* when configured dynamically using a header or an exchange property. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.27.11

</td>
<td valign="top">

If there's a runtime error during the start of an integration flow, an error message is shown. This error can also be accessed using the Cloud Integration OData API \(*Error Information of Runtime Artifact* resource of [Integration Content API](https://api.sap.com/api/IntegrationContent/resource)\). However, when displaying the error message using the OData API, an HTTP 204 empty body was retrieved. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.27.10

</td>
<td valign="top">

Integration flows containing script collections often started before the dependent script collection. This inconsistency of order resulted in messages not being processed. The patch addresses the issue by correcting the deployment order.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_y1v_fpp_stb"/>

## June 2022

**Software Increment: 2203**


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

Cloud Integration

</td>
<td valign="top">

6.26.21

</td>
<td valign="top">

SOAP-based sender adapters didn’t work on Alibaba Cloud. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.26.20

</td>
<td valign="top">

Integration flows with LDAP connections failed. This patch fixes this issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_yyl_wyr_4tb"/>

## May 2022

**Software Increment: 2203**


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

Cloud Integration

</td>
<td valign="top">

6.26.19

</td>
<td valign="top">

Customers have been billed for their test tenant. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.26.18

</td>
<td valign="top">

On undeployment of erroneous artifact, the artifact state is stuck in stopping state. The patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.60.2

</td>
<td valign="top">

For preprocessing of message implementation guidelines, the qualification of simple content was missing. As a result, wrong runtime artifacts have been created for Cloud Integration. This caused errors in processing of the affected integration flows. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_kdc_fqx_2tb"/>

## May 2022

**Software Increment: 2202**


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

Cloud Integration

</td>
<td valign="top">

6.25.22

</td>
<td valign="top">

There was the issue that customers have been billed for their test tenant. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.25.20

</td>
<td valign="top">

There have been issues with processing UPDATE requests to the `ValueMapping` resource from the Integration Content API of the [Cloud Integration OData API](https://api.sap.com/api/IntegrationContent/resource). This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.25.19

</td>
<td valign="top">

There have been issues with processing GET requests to the `ValueMapping` resource from the Integration Content API of the [Cloud Integration OData API](https://api.sap.com/api/IntegrationContent/resource). This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.25.18

</td>
<td valign="top">

There was an issue with processing timestamps that led to cases where system log entries showed dates in the future. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_afg_gw3_ltb"/>

## April 2022

**Software Increment: 2202**


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

Cloud Integration

</td>
<td valign="top">

6.25.17

</td>
<td valign="top">

Cloud integration deployments fail after software update, and artifacts can't be viewed in the package view, because of the rate limiting applied to the service manager connection. With this patch, the service manager binding, which is defined as optional, is removed.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

6.25.17

</td>
<td valign="top">

There is an issue with the Integration Advisor showing a busy status when qualifying a node using a MIG Local Codelist. This patch fixes the issue.

Customers are unable to migrate their MIGs if multiple values are selected in a business context. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Integration Assessment

</td>
<td valign="top">

6.25.16

</td>
<td valign="top">

Activation of SAP Integration Suite Integration Assessment capability was failing. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.25.15

</td>
<td valign="top">

In some cases, there have been issues with multiple concurrent SuccessFactors OData requests resulting in network errors. This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.25.14

</td>
<td valign="top">

If the creation of a service instance fails, the service instance will be in state *Creation Failed* and the instance can't be used or deleted. This patch allows the deletion of the service instance.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_jzx_zhw_wsb"/>

## March 2022

**Software Increment: 2201**


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

Cloud Integration

</td>
<td valign="top">

6.24.29

</td>
<td valign="top">

In some cases, there have been issues with multiple concurrent SF ODATA requests, as our current connection reuse implementation has shortcomings, and multiple connections are left idle. This is leading to network errors. This patch fixes the issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

1.58.4

</td>
<td valign="top">

There was an issue in activating multiple versions of a Custom message. This patch fixes the issue.

Creation of a draft version of a MIG or a MAG was prohibited, if an active version doesn’t exist. This limitation has been removed.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.24.26

</td>
<td valign="top">

A security vulnerability was found that can lead to denial-of-service \(DoS\) attacks. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.24.25

</td>
<td valign="top">

There have been issues with execution of timer-based integration flows because of an incorrect datasource reference. This was only seen with subset of tenants who uses JDBC driver for their JDBC adapter scenarios. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.24.20

6.24.22

</td>
<td valign="top">

There has been an issue that the Cloud Integration database reached its limit that resulted in deployment failures. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.24.21

</td>
<td valign="top">

There was an issue in the connection management logic of the OData Adapter during retry causing an exception and leading to message failures. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_hh5_njg_psb"/>

## February 2022

**Software Increment: 2113**


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

Cloud Integration

</td>
<td valign="top">

6.23.13

</td>
<td valign="top">

A security vulnerability was found that can lead to denial-of-service \(DoS\) attacks. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.23.12

</td>
<td valign="top">

Activation of SAP Integration Suite capabilities was failing. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.23.11

</td>
<td valign="top">

There have been the following issues:

-   Only on trial tenants: Issues using Cloud Integration and deploying artifacts.

-   Issues with the deployment of Cloud Integration artifacts in the correct sequence.

    This resulted in situations such like the following one: An integration flow using a value mapping is started before the value mapping. As consequence, the integration flow can't find and process the value mapping at runtime.


This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.23.10

</td>
<td valign="top">

There have been issues with the Cloud Integration user interface: It was either not opened, or a *session expired* error message being shown. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.23.9

</td>
<td valign="top">

In some cases, under high load, customers get JMS transaction-related errors like: `javax.jms.JMSException: Error rollback - internal error (Operation ROLLBACK disallowed in state COMMITTING.)` or `com.solacesystems.jcsmp.InvalidOperationException: Operation CREATEFLOW disallowed in state COMMITTING`. The error messages can vary but they all refer to transactional operations. This patch prevents the occurrence of these errors.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_av3_1qd_hsb"/>

## January/February 2022

**Software Increment: 2112**


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

Cloud Integration

</td>
<td valign="top">

6.22.14

</td>
<td valign="top">

This bugfix prevents Cloud Integration from consuming too many platform resources.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.22.13

</td>
<td valign="top">

The initialization of the repository destination XXX failed because of a library update, causing an RFC principal propagation issue. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.22.12

</td>
<td valign="top">

In some cases, during integration flow deployment, “the request reply generation” is skipped. This behaviour stops the execution of the integration flow. As the current log size is insufficient to identify the root cause, we increase the log size with this patch.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.22.11

</td>
<td valign="top">

Sometimes, the aggregator component does not release the lock set on the aggregate. This leads to a continuous aggregation until the lock is released manually. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.22.8

</td>
<td valign="top">

There has been an issue when storing the headers of a message processing log in a customer hosted CMS system. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.22.8

</td>
<td valign="top">

There have been concurrency issues with the process that updates the artifact instances in the database. Because of these issues, it took time for the system to get integration flows from status *Starting* to status *Started*. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.22.6

</td>
<td valign="top">

There was the following issue with scenarios using the HTTP receiver adapter: If the set-cookie header \(from the response message\) isn’t stored in a cookie, in some cases the *HTTP Session Reuse* feature doesn’t work. The reason is that the Cloud Integration runtime code doesn’t check if the set-cookie header is case insensitive. This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_m5l_nml_vrb"/>

## December/January 2021

**Software Increment: 2110**


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

Cloud Integration

</td>
<td valign="top">

6.20.22

</td>
<td valign="top">

There have been issues with the deployment of integration content. This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.20.20

</td>
<td valign="top">

A concurrency conflict caused an error in JMS processing and resulted in a retry in message processing. This patch resolves this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.20.19

</td>
<td valign="top">

There have been issues with the deployment of *Number Range Object* artifacts. This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.20.17

</td>
<td valign="top">

Improvement in Content Security Policy \(CSP\).

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_shd_g4k_hrb"/>

## October/November 2021

**Software Increment: 2109**


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

Cloud Integration

</td>
<td valign="top">

6.19.25

</td>
<td valign="top">

There have been issues with successfully saving changes for existing integration flows, as well as with integration flows not getting unlocked. This was corrected.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.24

6.19.23

</td>
<td valign="top">

There have been issues with scenarios using the HTTP receiver adapter with *Authentication* parameter set to `OAuth2 Client Credentials` or `OAuth2 SAML Bearer Assertion`. The default *Timeout* setting wasn't used as expected. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.22

</td>
<td valign="top">

When using an FTP sender adapter with the *Post Processing* parameter set to *Move File*, Cloud Integration waits for a timeout during command completion. The patch fixes the issue so that, first, the command is completed and, secondly, the file is moved. That way, the file processing order is kept.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.21

</td>
<td valign="top">

With this patch, we have optimized CPU usage for the Kafka broker.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.20

</td>
<td valign="top">

With this patch, you get the option to relax the name check in the JSON-to-XML converter. The relaxed check does allow that JSON member names can contain letters, digits, hyphens \(‘-‘\), underscores \(‘\_’\), periods \(‘.’\), hash characters \(‘\#’\), spaces, and at-signs \(‘@’\), but the original name check does only allow JSON names that are compliant with the name specification of XML names \(see: [https://www.w3.org/TR/2008/REC-xml-20081126/\#NT-NameChar’](https://www.w3.org/TR/2008/REC-xml-20081126/#NT-NameChar’)\). By default, the relaxed check isn't active. In order to activate the relaxed check, open a ticket on component LOD-HCI-PI-CON-SOAP and request that the Java System Property `com.sap.it.xmljson.name.checker.simplified.active=true` is to be configured for the worker nodes.

See also: [3112970 - JSON-to-XML Converter Exception Caused by Invalid JSON Member Name](https://launchpad.support.sap.com/#/notes/3112970) \(Knowledge Base Article\)

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.19

</td>
<td valign="top">

Improvement in telemetry \(payload size\).

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.18

</td>
<td valign="top">

Improvement in telemetry \(message size\).

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.17

</td>
<td valign="top">

This patch fixes the following issues:

-   Several JMS problems such as blocking undeployment of integration flows have been fixed.

-   Logging support for scenarios that involve the OpenConnectors adapter has been improved.




</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.15

</td>
<td valign="top">

There have been issues on tenants using the XI adapter with a JMS license but without provisioned broker. This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.14

</td>
<td valign="top">

Messages have no grace period to finish processing, when integration flows are getting undeployed. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.12

</td>
<td valign="top">

The Ariba adapter failed to read the content from the attachment after fetching it from pending queue. This was because of a bug in the adapter, and the content was lost. This patch fixes this issue with the Ariba adapter.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.19.11

</td>
<td valign="top">

The Ariba adapter failed to fetch messages with attachment from pending queue. This patch fixes this issue with the adapter.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_kqv_rdk_crb"/>

## September 2021

**Software Increment: 2108**


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

Cloud Integration

</td>
<td valign="top">

6.18.17

</td>
<td valign="top">

This patch fixes the mapping simulation failures because the high number of Kafka producer threads on CO.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.18.16

</td>
<td valign="top">

There have been the following issues:

-   Users weren't able to open message monitoring and to deploy integration flows.

-   Integration adapter redeployment failed after deployment failure.


This patch fixes these issues.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.18.14

</td>
<td valign="top">

There has been an issue with archiving of message processing logs if a message contained multiple attachments with the same name.

This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.18.13

</td>
<td valign="top">

This patch fixes the following issues:

-   An issue with PGP keyring caching: In some cases, the system didn't cache PGP keyrings correctly on the worker nodes.

-   An issue with failed messages when using the SuccessFactors OData receiver adapter with the *OAuth2 SAML Bearer Assertion* authentication option.

-   An issue with errors during database maintenance




</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.18.12

</td>
<td valign="top">

There was an issue with the tenant database when Number Ranges artifacts were involved in the scenario.

This patch fixes the issue.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_q5y_xqv_gqb"/>

## August 2021

**Software Increment: 2107**


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

Cloud Integration

</td>
<td valign="top">

6.17.21

</td>
<td valign="top">

The errors in the interceptors caused by undeployment can lead to a successful HTTP response code for inflight messages although the messages failed. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.17.18

</td>
<td valign="top">

In scenarios with an outbound connection to an on-premise system \(with *Proxy Type* set to *On-Premise* and the *Location ID* parameter specified in the HTTP receiver channel\), the following issue was observed: Custom headers with a wildcard character \(`*`\) specified by the *Request Headers* parameter have not been sent to the receiver system. As a result, Cloud Integration didn't send any X-CSRF token to the receiver system, causing in an HTTP 403 error.

This patch fixes the issue.

</td>
</tr>
</table>

