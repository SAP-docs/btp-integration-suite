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

Message Mapping

</td>
<td valign="top">

Parameterized message mappings from ES Repository can be imported with certain limitations. Only message mapping objects with *Simple Type* parameter category of the type *Import* are supported during migration. For more information, see [Designing and Configuring Parameterized Mapping Programs](https://help.sap.com/docs/SAP_NETWEAVER_750/bbd7c67c5eb14835843976b790024ec6/c47b8d9349e143a2b62e9b747eae4bce.html?version=latest).

</td>
</tr>
<tr>
<td valign="top">

CSV to XML Converter

XML to CSV Converter

</td>
<td valign="top">

For the patterns that support CSV to XML or XML to CSV converter, the following limitations apply:

-   XSD schema files from the source integration object aren't migrated. As an integration developer, you must manually download the schema files from the Enterprise Services Repository of SAP Process Orchestration and upload the same as resources in the integration flow. Then, configure the converter flow step before you deploy the integration flow.

-   Field Fixed-Length separator isn't supported. You can't directly migrate field fixed length file-based integration objects.




</td>
</tr>
<tr>
<td valign="top">

File-based adapters with encryption/decryption

</td>
<td valign="top">

For File-based adapter scenarios in Process Integration/Process Orchestration that require decryption, the migration tool does not automatically map the adapter module properties to the corresponding encryptor/decryptor step in the integration flow. You must manually add the PGP Encryptor/PGP Decryptor flow step in the migrated integration flow to maintain the same configuration as in the respective adapter's communication channel.

</td>
</tr>
</table>



<a name="loio7a552d40e1144af78d6ee0981ff2a54c__section_ej4_4hp_k2c"/>

## Limitations of Receiver Determination Object

-   You cannot extract the scenarios that don’t involve Receiver Determination object.
-   A sender agreement is mandatory. If it is absent in a particular scenario, an error stating "Couldn't find Sender Agreement \(Inbound processing details\)" may occur. Without a configured sender sgreement, the details of the Sender Communication Channel cannot be retrieved.
-   A receiver agreement is mandatory. If it is absent in a particular scenario, an error stating "Couldn't find Receiver Agreement \(Outbound processing details\)" may occur. Without a configured receiver agreement, the details of the Receiver Communication Channel cannot be retrieved.
-   Extended Receiver Determination type \(Dynamic Receiver\) is not supported.



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

