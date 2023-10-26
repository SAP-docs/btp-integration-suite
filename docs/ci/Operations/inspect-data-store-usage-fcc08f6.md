<!-- loiofcc08f6a450543b7bbed16e7de81e70e -->

# Inspect Data Store Usage

Inspect data store usage of the tenant database for a given time period \(as selected with the *Time* parameter\).

> ### Tip:  
> Each SAP Cloud Integration tenant is associated with a physical database that has a limited size. This database is used by certain steps during the runtime of integration flows .

The data store is a logical storage that consumes tenant database volume. It can be accessed to by certain integration flows steps \(read and write access\) to read and write the message payload or variables during runtime. There are two kinds of data stores:

-   Local data store: Can be accessed explicitly by a single integration flow

-   Global data store: Can be accessed by all integration flows deployed on a tenant


There are certain integration flow steps that allow you to write data to the data store and to read the data from it \(see [Define Data Store Operations](../Development/define-data-store-operations-79f63a4.md)\).

These integration flows, consequently, use tenant database volume.

The database usage is plotted in a bar graph against time.

The bar height shows the data volume \(in MB\) used by data stores for a given time period \(as selected with the *Time* parameter\).

A blue bullet represents the data volume \(in MB\) used specifically by global data stores.

The level of usage is indicated by the bar height and color \(from green for low usage, up to red for critical usage\). The thresholds are based on the entitlement for storage consumption in the tenant database.


<table>
<tr>
<th valign="top">

Level of Usage

</th>
<th valign="top">

Bar Color

</th>
<th valign="top">

Database Connection Usage

</th>
</tr>
<tr>
<td valign="top">

Critical

</td>
<td valign="top">

Red

</td>
<td valign="top">

More than 90%

</td>
</tr>
<tr>
<td valign="top">

Warning

</td>
<td valign="top">

Orange

</td>
<td valign="top">

Between 70% and 90%

</td>
</tr>
<tr>
<td valign="top">

OK

</td>
<td valign="top">

Green

</td>
<td valign="top">

Less than 70%

</td>
</tr>
</table>

The default value of the entitlement is 35 GB, as documented at [What Is SAP Cloud Integration?](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/what-is-sap-cloud-integration).

If the entitlement is exceeded there is a risk of overloading the database storage, which might eventually cause problems in the database management system and impact message processing.

The duration covered by a bar represents the average usage during:

-   One hour when *Past Day* is selected as *Time* 

-   One day when *Past Week* or *Past Month* is selected as *Time* 


Click a bar to get more context information and to get access to the following functions \(the results are filtered according to the setting of the *Time* parameter\):

-   *Show Messages*

    Navigate to the *Monitor Message Processing* screen for the selected time period \(see [Monitor Message Processing](monitor-message-processing-314df3f.md)\).

-   *Inspect Usage*

    Navigate to the *Top Data Stores* screen that allows you to inspect tenant database usage by data stores in more detail.


*Zoom Out* and *Zoom In* to extend/reduce the selected time period. 

> ### Note:  
> The system reads the resource consumption once per hour. That means, that there can be a maximum lag of 1 hour between the processing of an integration flow consuming data store resources and the *Inspect* feature to show the impact of this integration flow.



<a name="loiofcc08f6a450543b7bbed16e7de81e70e__section_tqd_3w1_bxb"/>

## Top Data Stores

On the *Top Data Stores* screen, you can find more details in the following sections:


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

*Top Local Data Stores by Usage* 

</td>
<td valign="top">

Shows those local data stores that are identified as top consumers of the tenant database for a specific time period \(as selected by the *Time* parameter\).

Click a cell to display more context information for the selected integration flow \(result filtered according to the setting of the *Time* parameter\):

See: [Inspect Top Local Data Stores by Usage](inspect-top-local-data-stores-by-usage-55670e6.md)

</td>
</tr>
<tr>
<td valign="top">

*Top Global Data Stores by Usage* 

</td>
<td valign="top">

Shows those global data stores that are identified as top consumers of the tenant database for a specific time period \(as selected by the *Time* parameter\).

Click a cell to display more context information for the selected integration flow \(result filtered according to the setting of the *Time* parameter\):

See: [Inspect Top Global Data Stores by Usage](inspect-top-global-data-stores-by-usage-00431bf.md)

</td>
</tr>
</table>



<a name="loiofcc08f6a450543b7bbed16e7de81e70e__section_vgy_pw5_ywb"/>

## What to Do In Critical Situations

If there's a critical situation with a data store, check if the data store is used at all in any integration scenario. Also check if you can reduce the setting for *Expiration Time*.

Check if the data stores shown as main consumers contain many overdue entries. In this case, check why these entries are not being consumed in a timely manner, and consider deleting the overdue entries if they are no longer required, in order to free up storage space.

In order to reduce storage consumption by large data stores, consider reducing the *Expiration Period* \(see [Define Data Store Write Operations](../Development/define-data-store-write-operations-46260ee.md)\). 

It is not recommended to use data stores for monitoring purposes, for example, by storing all failed messages for inspection. Data stores are intended as temporary storage for transactional data.

If you are using the *Data Store Write* integration flow steps for development and testing purposes, this means, if you want to inspect how messages are being processed, use the integration flow tracing feature \(see [Guidelines and Best Practices for Message Monitoring](guidelines-and-best-practices-for-message-monitoring-6f598b4.md)\).

More information:

-   [Define Data Store Operations](../Development/define-data-store-operations-79f63a4.md)

-   [Store/Retrieve Messages in/from the Data Store](../Development/store-retrieve-messages-in-from-the-data-store-604f7b1.md)

-   [Anticipate Message Throughput When Choosing a Storage Option](../Development/anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md)

-   [Using Data Storage Features When Designing Integration Flows](../Development/using-data-storage-features-when-designing-integration-flows-a836b4e.md)

-   [Define Transaction Handling](../Development/define-transaction-handling-2a5d4bc.md)


