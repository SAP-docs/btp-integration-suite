<!-- loioaa8222e5d5de41d88395805fee68bcb9 -->

# Azure Cosmos DB Receiver Adapter

The Azure Cosmos DB receiver adapter connects SAP Integration Suite to Azure Cosmos DB. The Azure Cosmos DB adapter helps you exchange data between the two systems. Azure Cosmos DB database is a platform as a service and a cloud-based NoSQL database by Azure.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loioaa8222e5d5de41d88395805fee68bcb9__ashweq30223"/>

## How the Azure Cosmos DB Receiver Adapter Works

If you have configured the Azure Cosmos DB receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Azure Cosmos DB \(this is a receiver system\), Azure Cosmos DB works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loioaa8222e5d5de41d88395805fee68bcb9__section_qgq_3t4_rdc"/>

## Configure the Azure Cosmos DB Receiver Adapter

Once you have created a receiver channel and selected the Azure Cosmos DB Receiver adapter, you can configure its parameters as shown below:

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Specify the address that includes the port of host.

Example: `https://{databaseaccount}.documents.azure.com:443/`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the type of key for connecting to the Azure Cosmos DB account:

-   `Master Key Token`
-   `Resource Token`

    > ### Note:  
    > For more information, see [Access Control in Azure Cosmos DB](https://learn.microsoft.com/en-us/rest/api/cosmos-db/access-control-on-cosmosdb-resources).




</td>
</tr>
<tr>
<td valign="top">

*Key Alias*

</td>
<td valign="top">

Specify the key alias for connecting to the Azure Cosmos DB account.

</td>
</tr>
<tr>
<td valign="top">

*Token Alias*

</td>
<td valign="top">

Specify the Resource token alias for connecting to the Azure Cosmos DB account.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable this property to reuse the connection.

> ### Note:  
> This field is applicable to a scenario when *Processing Mode* is set to `Single`. *Processing Mode* is available in *Processing* tab.



</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the connection timeout in milliseconds. The timeout controls the maximum waiting time for the connection to Azure Cosmos DB.

> ### Note:  
> This field is applicable to a scenario when *Processing Mode* is set to `Single`.



</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the response timeout in milliseconds. The timeout controls the maximum waiting time until a response message is received.

> ### Note:  
> This field is applicable to a scenario when *Processing Mode* is set to `Single`.



</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Processing Mode*

</td>
<td valign="top">

Select the type of processing mode:

-   `Single`
-   `Bulk`



</td>
</tr>
<tr>
<td valign="top">

*Version*

</td>
<td valign="top">

Select the API version.

> ### Note:  
> This field is editable and can be updated to use the latest API version available in Azure Cosmos DB.



</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Select the entity for the operation to be performed:

-   `Database`
-   `Container`
-   `Document`



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the type of operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*Patch Operation*

</td>
<td valign="top">

Select the type of bulk patch operation for Document.

</td>
</tr>
<tr>
<td valign="top">

*Database*

</td>
<td valign="top">

Specify the ID of the Database.

> ### Note:  
> This can be a valid string.



</td>
</tr>
<tr>
<td valign="top">

*Container*

</td>
<td valign="top">

Specify the ID of the Container.

> ### Note:  
> This can be a valid string.



</td>
</tr>
<tr>
<td valign="top">

*Document*

</td>
<td valign="top">

Specify the ID of the Document.

> ### Note:  
> This can be a valid string.



</td>
</tr>
<tr>
<td valign="top">

*Partition Key*

</td>
<td valign="top">

Specify the partition key for the operation.

> ### Note:  
> -   This field is mandatory only for some specific versions. For more info, see [Azure Cosmos DB documentation](https://learn.microsoft.com/en-us/rest/api/cosmos-db/common-cosmosdb-rest-request-headers).
> -   This is required if you are performing operation when *Processing Mode* is set to `Single`.



</td>
</tr>
<tr>
<td valign="top">

*Partition Key Path*

</td>
<td valign="top">

Specify the path of the partition key.

Example: `/partitionkey`

</td>
</tr>
<tr>
<td valign="top">

*Path*

</td>
<td valign="top">

Specify the path value of the bulk patch operation.

Example: `/address/city`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to send to the target system. By default, no custom headers are sent. Use an asterisk\(\*\) to send all custom headers to the target system. Alternatively, you can dynamically pass on the values by defining a property that includes a list of headers.

> ### Note:  
> This is applicable only when *Processing Mode* is set to `Single`.



</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an asterisk\(\*\) to receive all the headers from the target system, which is also the default value

</td>
</tr>
</table>

