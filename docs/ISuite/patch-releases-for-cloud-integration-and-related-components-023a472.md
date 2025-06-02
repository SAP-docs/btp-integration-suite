<!-- loio023a4725bb734f86be8a5625abe54110 -->

# Patch Releases for Cloud Integration and Related Components

This topic provides information on patch releases for hotfixes, bugfixes, and code enhancements.



This topic covers patches for the following capabilities and features of SAP Integration Suite: Cloud Integration, Trading Partner Management, Integration Advisor, Integration Assessment, Migration Assessment, and Edge Integration Cell.

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
> 6.20.12
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
> 6.20.11
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
> 6.20.10
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
> Let’s assume your previous software update was applying patch 6.20.10.
> 
> If you now update to software version 6.20.12, this patch provides you with bugfix B **and** bugfix C.

Patches for different components are associated with different major software version numbers. For example, patches for Cloud Integration in the Cloud Foundry environment have major software version 6 \(for example, `6.53.23`\). For more information, see [Understanding Software Version Numbers](understanding-software-version-numbers-caad468.md).



<a name="loio023a4725bb734f86be8a5625abe54110__section_emj_r1k_3fc"/>

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

Cloud Integration

</td>
<td valign="top">

8.29.17

</td>
<td valign="top">

This patch includes security enhancements.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.65.36

</td>
<td valign="top">

This patch fixes the following items:

-   Queue monitor failing issues to load messages due to multiple JMS broker connection requests.
-   Security Enhancements.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

8.29.16

</td>
<td valign="top">

This patch fixes the following items:

-   Gather issue with ZipAggregationStrategy.
-   In camel-3.x runtime, when multiple calls are made to MDI using the MDI receiver adapter in a single message processing, the local ID sent to the MDI service was incorrect.
-   Kafka sender adapter where the "Retry Failed Messages" functionality is not working.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.65.34

</td>
<td valign="top">

This patch fixes the following items:

-   Unable to set the MPLL log level due to a redirection issue from the config service to TRM. The redirection URL formation has been updated to resolve this issue.
-   Gather issue with ZipAggregationStrateggy.
-   In camel-3.x runtime, when multiple calls are made to MDI using the MDI receiver adapter in a single message processing, the local ID sent to the MDI service was incorrect.
-   An update for the Apache HTTP Client is required to fix CVE-2025-27820.
-   Kafka sender adapter where the "Retry Failed Messages" functionality is not working
-   Input validation for old service instances improved.



</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.99.6

</td>
<td valign="top">

This patch fixes the issue where MAG simulation fails if one of the MIGs uses a custom codelist.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.99.5

</td>
<td valign="top">

This patch fixes the following items:

-   Pretransformation fail due to the use of wrong ArtifactValue.

-   Incorrect SAP telemetry destination name in the code.




</td>
</tr>
</table>



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

Cloud Integration

</td>
<td valign="top">

6.64.31

</td>
<td valign="top">

This patch fixes the following items:

-   Hanging issues and facilitates a smooth Camel 3x migration with transaction-enabled XSLT Mapping Components.
-   Intermittent access issue affecting over 10 customers in Integration Suite, following the "@sap/approuter" update to version 19.0.0 to address a vulnerability identified by Blackduck.
-   Failure of MTMS Software Update on `it-rc-web` in larger systems.
-   Non-functional learn more banners and learning journey links.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

8.28.10

</td>
<td valign="top">

This patch fixes the hanging issues and facilitates a smooth Camel 3x migration with transaction-enabled XSLT Mapping Components.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.64.28

</td>
<td valign="top">

This patch fixes the following items:

-   Improved handling of migrated message mappings, enabling the opening of expanded recursive nodes with duplicate subtrees.
-   Splitter component by setting a default value to the SapGroup header when it is empty.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

8.28.9

</td>
<td valign="top">

This patch fixes the issue with the Kafka Sender Adapter, restoring full functionality to the "Retry Failed Messages" feature.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.64.26

</td>
<td valign="top">

This patch fixes the following items:

-   Deployment failure for `cp_it_resource_cockpit` due to revoked admin privileges from the Postgres user.
-   Kafka Sender Adapter where the "Retry Failed Messages" functionality is not working.
-   Customers to deploy Message Mappings containing JSON schemas.
-   Queue monitor not loading messages due to multiple JMS broker connection requests.



</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.98.4

</td>
<td valign="top">

This patch fixes the issue where Push to Partner Directory or Export of runtime artifacts of a MAG was taking considerably longer time.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.64.21

</td>
<td valign="top">

This patch fixes the following items:

-   Temp store accumulation by cleaning up ZIP files.
-   Critical CPU usage in Inspect's dedicated Postgres `it-db-rc`, suspected to be caused by Azure hyperscaler, observed exclusively in `eu20-001`.



</td>
</tr>
</table>



## April 2025

Software Increment: 2501

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

Cloud Integration

</td>
<td valign="top">

8.27.23

</td>
<td valign="top">

This patch fixes the following items:

-   Splitter issue in Camel by enabling rollback capability.
-   The 'Handled By Integration Flow' option in an XI sender channel causes errors due to the absence of a payload in synchronous responses when sending XI messages with Quality of Service BestEffort.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.63.47

</td>
<td valign="top">

This patch fixes the following items:

-   Splitter issue in Camel by enabling rollback capability.
-   The 'Handled By Integration Flow' option in an XI sender channel causes errors due to the absence of a payload in synchronous responses when sending XI messages with Quality of Service BestEffort.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

8.27.21

</td>
<td valign="top">

This patch fixes the following items:

-   Truncated message after GZIP flow step.
-   Groovy metadata cache clearance.
-   Integration flows failing during worker instance restart due to network issues impacting Audit Logger activation. The dependency causing errors has been removed to ensure smoother operations.
-   Feature to cache the `KeyManagerin` OData V2 Receiver is reverted.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.63.45

</td>
<td valign="top">

This patch fixes the following items:

-   Truncated message after GZIP flow step.
-   MPL Status for asynchronous messages.
-   Exclusive queue-related fixes:
    -   Reordering on reload.
    -   Duplicate entries in the move messages dialog.
    -   Issue with route generation when *Quality Of Service* type *Handled By Integration Flow* is selected.
    -   An error message was added for long loading times.

-   Deployment and staging of application `it-op-eic-admincockpit` on Ali Cloud tenants.
-   Groovy metadata cache clearance.
-   Integration flows failing during worker instance restart due to network issues impacting Audit Logger activation. The dependency causing errors has been removed to ensure smoother operations.
-   Feature to cache the `KeyManagerin` OData V2 Receiver is reverted.
-   Wrong claims in LLM-generated Script Optimization Report.
-   Redacted strings showing in script optimization proposals.



</td>
</tr>
</table>



## March 2025

Software Increment: 2501

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

Cloud Integration

</td>
<td valign="top">

8.27.16

</td>
<td valign="top">

This patch fixes the following issues:

-   Security enhancements.
-   Exchange headers are retained during exceptions, aligning functionality with Camel 2.x.
-   Attachment content is consistently of type String in Camel 3, maintaining compatibility with Camel 2.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.63.39

</td>
<td valign="top">

This patch fixes the following issues:

-   Retrieval of MPL Attachments through MPL OData APIs to 1000 items per request, ensuring more efficient data handling with the endpoint `/MessageProcessingLogs(<MPL ID>)/Attachments`.
-   Security enhancements.
-   Exchange headers are retained during exceptions, aligning functionality with Camel 2.x.
-   Attachment content is consistently of type String in Camel 3, maintaining compatibility with Camel 2.



</td>
</tr>
</table>



## March 2025

Software Increment: 2413

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

Cloud Integration

</td>
<td valign="top">

8.26.19

</td>
<td valign="top">

This patch fixes the following issues:

-   PD usage in the mail receiver adapter for encryption.
-   Message Mapping, Value Mapping, Function Library, and Imported Archive stuck in the starting state by providing exception handling and ensuring accurate artifact status updates in the UI.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.62.57

</td>
<td valign="top">

This patch fixes the following issues:

-   PD usage in the mail receiver adapter for encryption.
-   Frequent crashing issue of the IT-CO application caused by low disk space.
-   Message Mapping, Value Mapping, Function Library, and Imported Archive stuck in the starting state by providing exception handling and ensuring accurate artifact status updates in the UI.



</td>
</tr>
</table>



## February 2025

Software Increment: 2413

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

Cloud Integration

</td>
<td valign="top">

8.26.17

</td>
<td valign="top">

This patch fixes the aggregator issue on Camel 3.x.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.62.51

</td>
<td valign="top">

This patch fixes the aggregator issue on Camel 3.x.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

8.26.16

</td>
<td valign="top">

This patch fixes the following issues:

-   Metaspace consumption during script execution.
-   Runtime artifact generation by making stage timeout configurable.
-   Message processing fails when using the Mail receiver adapter with signature/encryption and a dynamic alias set via property.
-   Errors while using SOAP Sender adapter with OneWay, WS Standard, and WS Addressing configurations.
-   Errors during message processing on Camel 3.x with larger attribute size by increasing the XML max attribute to 120.000.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.62.50

</td>
<td valign="top">

This patch fixes the following issues:

-   Metaspace consumption during script execution
-   Design time loading issue by disabling Telemetry Kafka topics.
-   Runtime artifact generation by making stage timeout configurable.
-   Function Library cannot access certain packages included in the Java core library due to missing import-package entries in those java core libraries.
-   Message Mapping, Value Mapping, Function Library, and Imported Archive remain in the starting state for an extended period.
-   Message processing fails when using the Mail receiver adapter with signature/encryption and a dynamic alias set via property.
-   Switchable legacy behavior for:
    -   String functions with line separator in XSLT mapping.
    -   Message History, which is by default switched off in Camel 3.x.

-   Errors while using SOAP Sender adapter with OneWay, WS Standard, and WS Addressing configurations.
-   Thread blocking in the design service that causes crashes.
-   Errors during message processing on Camel 3.x with larger attribute size by increasing the XML max attribute to 120.000.



</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ctb_2cq_yyc"/>

## January 2025

Software Increment: 2412


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

6.61.41

</td>
<td valign="top">

This patch fixes the following issues:

-   Skip regeneration for artifacts that are deployed in Cloud Integration runtime location will.
-   Credential rotation is optimized for unused keys.
-   Data conversion affecting the interpretation of search results in the PI/PO system.



</td>
</tr>
<tr>
<td valign="top">

Trading Partner Management

</td>
<td valign="top">

6.61.38

</td>
<td valign="top">

Trading Partner Management deployment fails due to an issue in the Kafka binding. This patch fixes the issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.37

</td>
<td valign="top">

This patch fixes:

-   The issue that occurs while editing a datasource in the JDBC adapter.
-   The issue with process direct adapter that occurs while identifying addresses with spaces along with their respective integration flow names.



</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.36

</td>
<td valign="top">

This patch fixes the issue of excessive file descriptors usage detected in camel stream cache.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.35

</td>
<td valign="top">

This patch fixes the issue of message mapping script functions.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.34

</td>
<td valign="top">

This patch fixes the blocking issue caused by the codenarc scans for groovy scripts during deployment.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.32

</td>
<td valign="top">

This patch fixes login related issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.30

</td>
<td valign="top">

This patch fixes the loading issue of the Capabilities section on the Home Page.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.29

</td>
<td valign="top">

This patch fixes the billing related issue.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.95.4

</td>
<td valign="top">

MAG Simulation and export of runtime artifacts suddenly started failing while looking-up for some codelist after the release of 1.95.3. This patch fixes this issue.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.28

</td>
<td valign="top">

This patch fixes the issue with creating and rendering design time artifacts.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.27

</td>
<td valign="top">

With this patch, for FTP Sender adapter, *Streaming* is enabled only if *Change Directory Stepwise* is disabled.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.27

</td>
<td valign="top">

With this patch, for FTP Sender adapter, *Streaming* is enabled only if *Change Directory Stepwise* is disabled.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.25

</td>
<td valign="top">

This patch fixes the issue with integration flows when using Process Direct Adapter.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

6.61.24

</td>
<td valign="top">

This patch restores the download option for PGP Keys.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_ctb_2cq_ydc"/>

## January 2025

Software Increment: 2410


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

6.59.53

</td>
<td valign="top">

JDBC exceptions and file descriptor overflow were reported due to too many open files.

This patch resolves the issue by advising the user to keep the Datasource limit at 49, as recommended.

</td>
</tr>
</table>



<a name="loio023a4725bb734f86be8a5625abe54110__section_nwm_jf5_qdc"/>

## December 2024

Software Increment: 2410


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

6.59.39

</td>
<td valign="top">

In the Camel 3.x migration, internal properties in Exchange weren't being propagated when using the Process Direct Adapter.

This patch enables the selective migration of certain properties based on an environment variable. If the environment variable is turned ON, only specific properties migrate. If the environment variable is absent or turned OFF, the default behavior allows the migration of all properties, both internal and external.

</td>
</tr>
<tr>
<td valign="top">

Integration Advisor

</td>
<td valign="top">

1.93.4

</td>
<td valign="top">

This patch resolves issues with the Pre, Post, and Mag XSLTs generated during the MAG runtime export, when the MIG contains a default namespace with unqualified nodes. Before, the default namespace was incorrectly assigned to certain nodes.

</td>
</tr>
</table>



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

