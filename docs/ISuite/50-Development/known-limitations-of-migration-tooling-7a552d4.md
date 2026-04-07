<!-- loio7a552d40e1144af78d6ee0981ff2a54c -->

# Known Limitations of Migration Tooling

The following table describes the limitations when using the migration tool:


<table>
<tr>
<th valign="top">

Components

</th>
<th valign="top">

Limitations

</th>
</tr>
<tr>
<td valign="top">

CSV to XML Converter

XML to CSV Converter

</td>
<td valign="top">

For the patterns that support CSV to XML or XML to CSV converter, the following limitations apply:

-   XSD schema files from the source integration object aren't migrated. As an integration developer, you must manually download the schema files from the Enterprise Services Repository of SAP Process Integration/SAP Process Orchestration and upload the same as resources in the integration flow. Then, configure the converter flow step before you deploy the integration flow.

-   Field Fixed-Length separator isn't supported. You can't directly migrate field fixed length file-based integration objects.




</td>
</tr>
<tr>
<td valign="top">

Standard Adapter Module

</td>
<td valign="top">

Migration tool does not import the standard adapter modules automatically. For more information how to migrate them manually, see [Adapter Modules](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/adapter-modules).

As alternative, you can also use the released community package [Message Transformation Utilities](https://api.sap.com/package/com.sap.integration.cloud.utilities.MessageTransformations/overview) to make some of these adapter modules available in groovy script.

</td>
</tr>
<tr>
<td valign="top">

Custom Adapter Module

</td>
<td valign="top">

Migration tool does not import custom adapter modules automatically. You can consider use the standard Cloud Integration functionalities to re-implement it using JavaScript or Groovy script.

</td>
</tr>
<tr>
<td valign="top">

JDBC transaction handling

</td>
<td valign="top">

The use of JDBC Sender scenarios, where data is selected and later updated within the same transaction, is not supported in SAP Cloud Integration. This behaviour is also not handled by the migration tool when moving from SAP Process Integration/SAP Process Orchestration.

Even if you try to replicate the logic using a Timer and Request-Reply pattern, there is the possibility that the records selected at the beginning may not match those updated at the end, potentially leading to data inconsistencies. To prevent inconsistent data or failed updates, a redesign is needed — typically involving stored procedures and intermediate status flags at the database layer.

</td>
</tr>
<tr>
<td valign="top">

Message Mapping

</td>
<td valign="top">

-   Parameterized message mappings from ES Repository can be imported with certain limitations. Only message mapping objects with *Simple Type* parameter category of the type *Import* are supported during migration. For more information, see [Designing and Configuring Parameterized Mapping Programs](https://help.sap.com/docs/SAP_NETWEAVER_750/bbd7c67c5eb14835843976b790024ec6/c47b8d9349e143a2b62e9b747eae4bce.html?version=latest).

-   Multi-message: scenarios involving multiple source or target messages \(1:N, N:1, or M:N\) are not supported by the migration tool.

    1:N mappings can be imported. However, message splitting is not supported by the migration tool.

    N:1 and N:M scenarios, typically implemented using business process management in SAP Process Integration/SAP Process Orchestration, are not supported.

    These cases require additional enhancements in the Integration Flow to replicate the behaviour in Cloud Integration.

    > ### Example:  
    > -   To model a scenario with 1:N mapping with one target message type, see [Pipeline v2 Template Step07 - Outbound Processing One-to-Many with One Message Type](https://hub.sap.com/integrationflow/com.sap.integration.cloud.pipeline.v2.template.step07.outbound.processing.o2mo)
    > 
    > -   To model a scenario with 1:N mapping with multiple target message types, see [Pipeline v2 Template Step07 - Outbound Processing One-to-Many with Multiple Message Types](https://hub.sap.com/integrationflow/com.sap.integration.cloud.pipeline.v2.template.step07.outbound.processing.o2mm)

-   JDBC lookup: Migration of message mappings using the standard JDBC lookup function is not supported. In Cloud Integration, JDBC lookups must be implemented using either XSLT mapping or Process Direct. For more information, see [JDBC Lookup Tutorial](https://developers.sap.com/tutorials/ci-jdbc-lookup.html)
-   RFC lookup: Message mappings using the standard RFC lookup function are not supported by the migration tool. In Cloud Integration, this functionality must be recreated using Groovy scripts or user-defined functions. For more information, see [RFC Lookup Tutorial](https://developers.sap.com/tutorials/ci-rfclookup.html).
-   Sender and Receiver standard node functions: Sender and Receiver node functions in message mappings are not supported in Cloud Integration. After migration, message mappings must be reviewed and redesigned using Integration Flow logic or additional mapping steps.
-   Migration tool does not migrate scenarios with RFC and ‘.xml’ files as source message as these inbound structures are not supported in Cloud Integration.




</td>
</tr>
<tr>
<td valign="top">

Value Mapping

</td>
<td valign="top">

Migration tool does not migrate value mapping automatically. It needs to be imported as a standalone artifact and assigned in appropriate message mapping.

</td>
</tr>
<tr>
<td valign="top">

Java Mapping

</td>
<td valign="top">

Java mapping with supported functions and methods on Cloud Integration are migrated directly using groovy script wrapper. More complex Java mappings might not be supported using groovy script wrapper approach. For more information, see [Migrating Java Mappings](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/migrating-java-mappings?locale=en-US) 

</td>
</tr>
<tr>
<td valign="top">

XSLT Mapping with Java class

</td>
<td valign="top">

The below functionalities in XSLT mapping are not supported by migration tool and requires additional enhancement after migration:

-   Simple Java classes

    > ### Example:  
    > -   Date/number transformations
    > 
    > -   String formatting
    > 
    > -   Counters
    > 
    > -   Variables

-   RFC and JDBC calls
-   Value Mapping


XSLT mappings referenced within another one are mapped incorrectly after migration. In Cloud Integration, other referenced stylesheets should be uploaded in the References and path to the folder structure should be removed, then all templates from referenced XSLT are called in original XSLT.

For more information, see [Migrating XSLT mappings from SAP Process Orchestration to SAP Integration Suite](https://community.sap.com/t5/integration-blog-posts/migrating-xslt-mappings-from-sap-process-orchestration-to-sap-integration/ba-p/14284726)

</td>
</tr>
<tr>
<td valign="top">

Asynchronous and Synchronous Bridge scenarios

</td>
<td valign="top">

Migration tool does not support the Sync-Async Bridge scenarios or combined scenarios involving the Async-Sync Bridge and Recipient List. The Integration flow must be redesigned manually to handle the message correlation in SAP Integration Suite.

</td>
</tr>
<tr>
<td valign="top">

REST Receiver adapter

</td>
<td valign="top">

REST adapter from SAP Process Integration/SAP Process Orchestration migrates to Cloud Integration as HTTPS adapter and all attributes from REST adapter are mapped to HTTPS. When path variables are used in REST adapter, it is not supported in HTTPS in Cloud Integration and hence it throws error.

To resolve the error, you must construct the full URL manually in the Integration Flow using one of the following approaches:

-   Store variable in a property \(from payload, header, or constant\) and construct the full URL with that property, in the adapter.

    > ### Example:  
    > http://…/$\{property.variable\}

-   Write it to the special header `CamelHttpUri`, which Cloud Integration uses at runtime to override the HTTP adapter’s static URL.



</td>
</tr>
<tr>
<td valign="top">

Fault Message

</td>
<td valign="top">

Fault message generation as supported in SAP Process Integration/SAP Process Orchestration is not available. Instead, exception handling must be implemented using Exception Subprocesses to manage and process errors. After migration, scenarios that rely on fault messages need to be adapted by designing appropriate exception handling flows in Cloud Integration to replicate the required behavior.

</td>
</tr>
<tr>
<td valign="top">

Schema Validation

</td>
<td valign="top">

The Migration Tool does not support the schema validation property and hence post migration manual adjustments are necessary. This functionality can be achieved within the Integration flow by using the XML validator in Cloud Integration.

</td>
</tr>
<tr>
<td valign="top">

Synchronous Use Case Support

</td>
<td valign="top">

Synchronous use cases are supported only through the standard approach. If you intend to use the pipeline approach, see to the [Inbound Processing Synchronous Template](https://api.sap.com/integrationflow/com.sap.integration.cloud.pipeline.v2.template.step01.inbound.processing.sync) provided in the Pipeline Standard package.

</td>
</tr>
<tr>
<td valign="top">

Extended Receiver Determination

</td>
<td valign="top">

Extended Receiver Determination scenarios with multiple operations are migrated partially and the integration flow requires additional enhancement post migration.

Extended Receiver determination with receiver wildcard and agreement are not supported by the migration tool.

</td>
</tr>
<tr>
<td valign="top">

Content Based Routing – Synchronous

</td>
<td valign="top">

Content Based Routing with synchronous pattern is not supported by the Migration Tool. The interface can still be migrated as CBR-Async pattern and necessary adaptions could be done post migration.

</td>
</tr>
<tr>
<td valign="top">

Quality of Service as Exactly Once In Order \(EOIO\)

</td>
<td valign="top">

Although Migration tool migrates adapters configured with the Quality of Service as EOIO, it does not preserve the specific EOIO functionality. After migration, the intended behaviour can be achieved by using JMS Queue with the access type set to Exclusive. See [Quality of Service Exactly Once In Order](https://help.sap.com/docs/integration-suite/sap-integration-suite/quality-of-service-exactly-once-in-order?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Function Library

</td>
<td valign="top">

Migration tool does not support importing function libraries in the following cases:

-   User‑Defined Functions \(UDFs\) use arguments of type Channel
-   The init method uses arguments of type Parameter
-   The function library name and class name are not identical
-   Attribute category and title combinations are not unique within the function library class



</td>
</tr>
<tr>
<td valign="top">

Maintain Order at Runtime

</td>
<td valign="top">

Migration of scenarios with Maintain Order at Runtime is partially supported in Migration Tool. Scenarios with a single receiver will be migrated, but any XPath-based interface conditions will be skipped and must be manually added.

Scenarios with multiple receivers are not supported and require additional enhancements.

You can manually model a scenario with order at runtime requirement. See [Pipeline v2 Template Step07 - Outbound Processing Maintain Order At Runtime](https://hub.sap.com/integrationflow/com.sap.integration.cloud.pipeline.v2.template.step07.outbound.processing.moar)

</td>
</tr>
<tr>
<td valign="top">

Sender agreement with wildcard

</td>
<td valign="top">

Sender agreements using wildcards are supported only through the standard approach and are not supported through the pipeline approach. If you plan to use the pipeline approach, see [Special Cases – Sender Wildcard Scenarios](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/special-cases#sender-wildcard-scenarios) section under the SAP help pipeline documentation.

</td>
</tr>
<tr>
<td valign="top">

Receiver agreement with wildcard

</td>
<td valign="top">

Migration Tool does not migrate Receiver agreement with wildcard, if the receiver is determined dynamically by XPath expression. The integration flow needs to be manually redesigned to support message correlation in SAP Integration Suite.

</td>
</tr>
</table>



<a name="loio7a552d40e1144af78d6ee0981ff2a54c__section_ej4_4hp_k2c"/>

## Limitations of Receiver Determination Object

-   You cannot extract the scenarios that don’t involve Receiver Determination object.
-   A sender agreement is mandatory. If it is absent in a particular scenario, an error stating "Couldn't find Sender Agreement \(Inbound processing details\)" may occur. Without a configured sender sgreement, the details of the Sender Communication Channel cannot be retrieved.
-   A receiver agreement is mandatory. If it is absent in a particular scenario, an error stating "Couldn't find Receiver Agreement \(Outbound processing details\)" may occur. Without a configured receiver agreement, the details of the Receiver Communication Channel cannot be retrieved.



<a name="loio7a552d40e1144af78d6ee0981ff2a54c__section_fb2_qng_tzb"/>

## Limitations of CSV to XML Converter

**Necessary Manual Interventions**


<table>
<tr>
<th valign="top">

SAP PO – File Content Conversion \(FCC\) Parameter

</th>
<th valign="top">

Cloud Integration – Manual Intervention after Migration

</th>
</tr>
<tr>
<td valign="top">

Document Name + Recordset Name \(optional\) + Recordset Structure

</td>
<td valign="top">

Define *Path to Target Element in XSD* as per SAP PO FCC Parameter sequence.

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.fieldSeparator = ‘ ’ or ‘0x20’

RecordsetStructureValue.fieldSeparator = ‘ ’ or ‘0x90’

</td>
<td valign="top">

In the *Field Separator in CSV* menu, define *Space* and *Tab*.

</td>
</tr>
<tr>
<td valign="top">

Recordset Structure= Value,1

</td>
<td valign="top">

Add an additional message mapping to map the RecordsetStructureValue to RecordsetNameValue

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.keyFieldValue

</td>
<td valign="top">

Define a value in the *Record Marker in CSV* field.

</td>
</tr>
</table>

**Parameters Available with Certain Limitation**


<table>
<tr>
<th valign="top">

SAP PO – File Content Conversion \(FCC\) Parameter

</th>
<th valign="top">

Cloud Integration Property

</th>
<th valign="top">

Restriction

</th>
</tr>
<tr>
<td valign="top">

Document Offset

</td>
<td valign="top">

Exclude First Line Header

</td>
<td valign="top">

Document Offset value can’t be defined more than 1.

</td>
</tr>
<tr>
<td valign="top">

Document Name + Recordset Name \(optional\) + Recordset Structure

</td>
<td valign="top">

Path to Target Element in XSD

</td>
<td valign="top">

It isn't currently possible to define more than one Recordset Structure in the respective parameter of the integration flow.

Each row in the CSV file creates a new node as per the defined Recordset structure.

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.keyFieldValue

</td>
<td valign="top">

Record Marker in CSV

</td>
<td valign="top">

It isn't currently possible to define more than one Record Marker value.

</td>
</tr>
</table>

**Missing Parameters**


<table>
<tr>
<th valign="top">

SAP PO – File Content Conversion \(FCC\) Parameter

</th>
<th valign="top">

Cloud Integration Property

</th>
</tr>
<tr>
<td valign="top">

Document Namespace

</td>
<td valign="top">

It isn’t necessary to define it separately as the value is taken from the XML Schema.

</td>
</tr>
<tr>
<td valign="top">

Recordset Namespace

</td>
<td valign="top">

It isn’t necessary to define it separately as the value is taken from the XML Schema.

</td>
</tr>
<tr>
<td valign="top">

Recordset Sequence

</td>
<td valign="top" align="center" rowspan="12">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Recordset per Message

</td>
</tr>
<tr>
<td valign="top">

RecordsetName = Value && ignoreRecordsetName = True

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.endSeparator

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.beginSeparator

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.missingLastFields = add

RecordsetStructureValue.missingLastFields = ignore

RecordsetStructureValue.missingLastFields = error

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.additionalLastFields = error

RecordsetStructureValue.additionalLastFields = ignore

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.enclosureSign

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.enclosureSignEnd

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.enclosureSignEscape

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.enclosureSignEndEscape

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.enclosureSignConversion

</td>
</tr>
</table>



<a name="loio7a552d40e1144af78d6ee0981ff2a54c__section_cdk_fqg_tzb"/>

## Limitations of XML to CSV Converter

**Necessary Manual Interventions**


<table>
<tr>
<th valign="top">

SAP PO – File Content Conversion \(FCC\) Parameter

</th>
<th valign="top">

Cloud Integration – Manual Intervention after Migration

</th>
</tr>
<tr>
<td valign="top">

Recordset Structure

</td>
<td valign="top">

Define *Path to Target Element in XSD* of the Record Identifier.

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.fieldSeparator = ‘ ’ or ‘0x20’

RecordsetStructureValue.fieldSeparator = ‘ ’ or ‘0x90’

</td>
<td valign="top">

In the *Field Separator in CSV* menu, define *Space* and *Tab*.

</td>
</tr>
<tr>
<td valign="top">

Recordset Structure= Parent Element \(for example, Header\)

</td>
<td valign="top">

Enable *Include Parent Element* and enter a value for *Path to Parent Element*.

</td>
</tr>
</table>

**Parameters Available with Certain Limitation**


<table>
<tr>
<th valign="top">

SAP PO – File Content Conversion \(FCC\) Parameter

</th>
<th valign="top">

Cloud Integration Property

</th>
<th valign="top">

Restriction

</th>
</tr>
<tr>
<td valign="top">

Recordset Structure

</td>
<td valign="top">

Path to Source Element in XSD

</td>
<td valign="top">

It isn't currently possible to define more than one Recordset Structure in the respective parameter of the integration flow.

</td>
</tr>
</table>

**Missing Parameters**


<table>
<tr>
<th valign="top">

SAP PO – File Content Conversion \(FCC\) Parameter

</th>
<th valign="top">

Cloud Integration Property

</th>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.headerLine

</td>
<td valign="top" rowspan="5">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.addHeaderLine = 2

RecordsetStructureValue.addHeaderLine = 3

RecordsetStructureValue.addHeaderLine = 4

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.endSeparator

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.beginSeparator

</td>
</tr>
<tr>
<td valign="top">

RecordsetStructureValue.absoluteRowWidth

</td>
</tr>
</table>

