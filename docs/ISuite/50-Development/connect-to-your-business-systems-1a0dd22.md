<!-- loio1a0dd22121214edd90e644755260e51a -->

# Connect to Your Business Systems

As an administrator, you need to set up the data sources you want to use in your business data graphs, setup the connectivity between Graph and your business systems, and create destinations.

Graph supports data sources based on SAP S/4HANA \(all editions, cloud and on-premise\), SAP SuccessFactors, and SAP Sales Cloud.

> ### Note:  
> Graph supports SAP ERP Central Component \(ECC\) content which has been prepared and exposed as an OData service. To create the service interface, you can use Gateway Builder starting from SAP Gateway version GW\_FND 7.52 and the latest SP \(refer to [2217489 - Maintenance and Update Strategy for SAP Fiori Front-End Server](https://me.sap.com/notes/2217489 - Maintenance and Update Strategy for SAP Fiori Front-End Server)\) or OData Provisioning.



<a name="loio1a0dd22121214edd90e644755260e51a__section_fnl_ds3_3yb"/>

## Set Up Data Sources

To create a business data graph, you must have data sources \(business systems\). Adding data sources to your subaccount consists of two steps for each data source:

1.  Establish trust between the business systems and the SAP BTP subaccount. You can include various SAP systems into a formation and thus combine diverse SAP solutions into an extended business scenario.

    For more information, see [Including SAP Systems in a Formation](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/68b04fa73aa740cb96ed380a85a4761a.html).

2.  Create a destination for each service of these data sources that is exposed to client applications.



<a name="loio1a0dd22121214edd90e644755260e51a__section_xqs_z32_5xb"/>

## Custom SAP BTP Destination Annotations

Graph supports custom annotations for SAP BTP destinations.

In the SAP BTP cockpit, you can add *Additional Properties* to destinations. The properties provide additional configuration options. You can add predefined properties forSAP BTP or add freestyle properties using any name and value.

The following table provides an overview of the custom annotations that Graph supports for SAP BTP destinations:


<table>
<tr>
<th valign="top">

**Name**

</th>
<th valign="top">

**Value**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

`Graph.Ignore` 

</td>
<td valign="top">

true

</td>
<td valign="top">

A destination is ignored during Graph configuration, generation, and activation.

</td>
</tr>
</table>

**Related Information**  


[Create a Business Data Graph in Integration Suite](create-a-business-data-graph-in-integration-suite-42daf3b.md "As a Graph Key User, you can create a new business data graph. You can also use an existing configuration file to create a business data graph.")

[Actions and Functions](actions-and-functions-3572dfb.md "Actions and functions provide a way to introduce server-side behaviors into the otherwise data-centric model. Graph mirrors actions and functions as provided by connected business systems.")

