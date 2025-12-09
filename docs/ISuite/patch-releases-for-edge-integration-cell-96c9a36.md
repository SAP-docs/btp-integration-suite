<!-- loio96c9a3664b054d34813ef07e9a82f25d -->

# Patch Releases for Edge Integration Cell



This topic covers patches for Edge Integration Cell.

The following patch release information covers the most recent changes made to the latest version of the software.



> ### Tip:  
> Each software patch always contains the current bug fix as well as the bug fixes provided to the previous patches.
> 
> The following example illustrates this rule:
> 
> Let’s assume that SAP has recently provided the following patches:
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Software Version
> 
> </th>
> <th valign="top">
> 
> Description
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> 8.33.12
> 
> </td>
> <td valign="top">
> 
> Bugfix C
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> 8.33.11
> 
> </td>
> <td valign="top">
> 
> Bugfix B
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> 8.33.10
> 
> </td>
> <td valign="top">
> 
> Bugfix A
> 
> </td>
> </tr>
> </table>
> 
> Let’s assume your previous software update was applying patch 8.33.10.
> 
> If you now update to software version 8.33.12, this patch provides you with bugfix B **and** bugfix C.

Patches for different components are associated with different major software version numbers. For example, patches for Cloud Integration in the Cloud Foundry environment have major software version 6 \(for example, `6.53.23`\). For more information, see [Understanding Software Version Numbers](understanding-software-version-numbers-caad468.md).



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_m21_tqk_fhc"/>

## November 2025

Software Increment: 2509

****


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

Edge Integration Cell

</td>
<td valign="top">

8.35.18

</td>
<td valign="top">

This patch fixes the issue with solution upgrades.

</td>
</tr>
</table>



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_yfs_tn4_xgc"/>

## October 2025

Software Increment: 2507

****


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

Edge Integration Cell

</td>
<td valign="top">

8.33.16

</td>
<td valign="top">

This patch fixes deployment issues for integration flows using XI adapters, ensuring successful execution for version 1.15 and above. It supports Quality of Service settings: At Least Once \(ALO\), Exactly Once \(EO\), and High Business Impact \(HBI\).

</td>
</tr>
</table>



## September 2025

Software Increment: 2507

****


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

Edge Integration Cell

</td>
<td valign="top">

8.33.15

</td>
<td valign="top">

This patch addresses intermittent authentication and authorization issues observed during concurrent user scenarios under high load in Edge Integration Cell.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.33.14

</td>
<td valign="top">

This patch includes the following items:

-   JDBC adapter moved to a stable version.
-   Updates related to Message Processing Log Attachment view on Monitor Message Processing screen.



</td>
</tr>
</table>



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_lpr_wgz_ygc"/>

## August 2025

Software Increment: 2506

****


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

Edge Integration Cell

</td>
<td valign="top">

8.32.11

</td>
<td valign="top">

This patch fixes the following issues:

-   The patch provides MPL enhancements for sporadic token fetch errors.
-   It fixes intermittent authentication and authorization issues that occur during concurrent user scenarios under high load in the Edge Integration Cell.



</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.32.9

</td>
<td valign="top">

This patch fixes the following issues:

-   Issues with proxy handling.
-   Authentication panic failures in concurrent scenarios while fetching public keys for token validation.
-   Inefficient queue mgmt api.



</td>
</tr>
</table>



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_szt_bhz_ygc"/>

## August 2025

Software Increment: 2505

****


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

Edge Integration Cell

</td>
<td valign="top">

8.31.18

</td>
<td valign="top">

The patch introduces retry and backoff mechanism to prevent occurrence of sporadic errors from XSUAA while fetching tokens.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.31.17

</td>
<td valign="top">

This patch fixes issues with proxy handling.

</td>
</tr>
</table>



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_kz5_ghz_ygc"/>

## July 2025

Software Increment: 2505

****


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

Edge Integration Cell

</td>
<td valign="top">

8.31.16

</td>
<td valign="top">

This patch fixes inefficient queue mgmt api.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.31.15

</td>
<td valign="top">

This patch addresses authentication panic failures in concurrent scenarios. It resolves issues that occur while fetching public keys for token validation.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.31.14

</td>
<td valign="top">

This patch enhances the Edge Deploy Controller log.

</td>
</tr>
</table>



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_rsf_khz_ygc"/>

## June 2025

Software Increment: 2504

****


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

Edge Integration Cell

</td>
<td valign="top">

8.30.16

</td>
<td valign="top">

This patch defers the Redis readiness check. It unblocks customers with incorrect Redis configurations, allowing them to deploy artifacts and iFlows.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.30.15

</td>
<td valign="top">

This patch fixes the permission issues with sapgenpse that prevented SNC enablement.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.30.13

</td>
<td valign="top">

This patch fixes theissue with ID field size in the endpoint poll info table within the EDC database.

</td>
</tr>
</table>



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_uwk_thz_ygc"/>

## May 2025

Software Increment: 2503

****


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

Edge Integration Cell

</td>
<td valign="top">

8.29.12

</td>
<td valign="top">

This patch fixes the permission issues with sapgenpse that prevented SNC enablement.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.29.11

</td>
<td valign="top">

This patch fixes the issue with the Kafka Sender Adapter, restoring full functionality to the "Retry Failed Messages" feature.

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell

</td>
<td valign="top">

8.29.8

</td>
<td valign="top">

This patch fixes the issue of diagnostics - file handle.

</td>
</tr>
</table>



<a name="loio96c9a3664b054d34813ef07e9a82f25d__section_i1q_yhz_ygc"/>

## April 2025

Software Increment: 2502

****


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

Edge Integration Cell

</td>
<td valign="top">

8.28.6

</td>
<td valign="top">

This patch fixes the issue with the Kafka Sender Adapter, restoring full functionality to the "Retry Failed Messages" feature.

</td>
</tr>
</table>

