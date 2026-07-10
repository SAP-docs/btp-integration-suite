<!-- loio58b75fc62bc2461180bb1b48eb4c7159 -->

# MongoDB Receiver Adapter

The MongoDB receiver adapter connects SAP Integration Suite to MongoDB. The MongoDB adapter helps you exchange data between the two systems. MongoDB is an open-source, document-oriented NoSQL database designed to store and manage data in a flexible, scalable, and high-performance way.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio58b75fc62bc2461180bb1b48eb4c7159__ashweq30223"/>

## How the MongoDB Receiver Adapter Works

If you have configured the MongoDB receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to MongoDB \(this is a receiver system\), MongoDB works on the request and sends the data back to the SAP Integration Suite tenant.



## Configure the MongoDB Receiver Adapter

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

Specify the Cluster address to connect to MongoDB Database.

You can find your Cluster address in MongoDB Atlas by navigating to *Connect \> Compass*. Select *I have MongoDB Compass installed* and select version *1.11 or earlier*. Ensure that you copy the host address and port only as shown in below example.

> ### Note:  
> Currently, only *Standard Connection String* is supported.

Example: `ac-utuhakc-shard-00-00.xqxxotp.mongodb.net:27017,ac-utuhakc-shard-00-01.xqxxotp.mongodb.net:27017,ac-utuhakc-shard-00-02.xqxxotp.mongodb.net:27017`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the Authentication Type to connect to MongoDB server. Currently only *LDAP \(PLAIN\) Authentication* is supported.

</td>
</tr>
<tr>
<td valign="top">

*Credentials Name*

</td>
<td valign="top">

Specify the User Credentials security artifact alias that stores the username-password pair.

</td>
</tr>
<tr>
<td valign="top">

*Connection Options*

</td>
<td valign="top">

Specify the optional parameters for the MongoDB connection string to customize connection preferences, such as authentication, timeouts, and read/write options, etc.

> ### Note:  
> The `ssl=true` parameter must be included to establish the secure connection using SSL.

Example: `ssl=true&authSource=admin`

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Socket Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) to get a response.

Example: `60000`

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

*Entity*

</td>
<td valign="top">

Select the required Entity:

-   *Collections*
-   *Document*
-   *Databases*



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation to be performed on the selected entity.

</td>
</tr>
<tr>
<td valign="top">

*Database*

</td>
<td valign="top">

Specify the name of the Database.

> ### Note:  
> You will be able to find it inside your Cluster.



</td>
</tr>
<tr>
<td valign="top">

*Collection*

</td>
<td valign="top">

Specify the name of the MongoDB collection on which the operation is to be performed.

> ### Note:  
> You will be able to find it inside your Cluster.



</td>
</tr>
<tr>
<td valign="top">

*Filter Query*

</td>
<td valign="top">

Specify the expression to modify the matching documents from the collection.

Example: `{“department”:"IT"}`

</td>
</tr>
<tr>
<td valign="top">

*Projection*

</td>
<td valign="top">

Specify the fields to be returned in the response.

Example: `{"field1": 1, "field2": 0}`. Use 1 to include a field, 0 to remove implicitly included fields, and fields not mentioned are excluded from the response.

</td>
</tr>
<tr>
<td valign="top">

*Sort By*

</td>
<td valign="top">

Specify the fields based on which sorting is need to be performed. You can specify one or more fields and set the sort order for each field.

Example: `{"field1": 1, "field2": -1}`, in this example, sorting is done first by the field1 in ascending order \(1\) and then by the field2 in descending order \(-1\).

</td>
</tr>
<tr>
<td valign="top">

*Update Fields*

</td>
<td valign="top">

Specify the operator for the fields to be modified along with their values.

Example: `{"$set":{"Salary":“78000"}}`

</td>
</tr>
<tr>
<td valign="top">

*Array Fields*

</td>
<td valign="top">

Specify one or more array filter documents to identify which elements inside an array should be updated during the operation. Array filters are used with the $\[<identifier\>\] syntax in your update statement and allow updates to only those array elements that match the specified conditions.

Example: `[ { "element": { $gte: 100 } } ]`. In this example, values are greater than or equal to 100.

</td>
</tr>
<tr>
<td valign="top">

*Enable Transaction*

</td>
<td valign="top">

Enable to execute the operation as a transaction. If enabled, either all the operations in the transaction are successfully applied, or none.

</td>
</tr>
<tr>
<td valign="top">

*Order Execution*

</td>
<td valign="top">

Enable to stop execution on the first failure and return without processing the remaining documents. If disabled, continue processing despite failures and complete execution.

</td>
</tr>
<tr>
<td valign="top">

*Multi Update*

</td>
<td valign="top">

Enable to update all documents that match with the filter criteria. When disabled, only the first matching document will be updated.

</td>
</tr>
<tr>
<td valign="top">

*Multi Delete*

</td>
<td valign="top">

Enable to delete all documents that match with the filter criteria. When disabled, only the first matching document will be deleted.

</td>
</tr>
<tr>
<td valign="top">

*Upsert*

</td>
<td valign="top">

Enable to insert a new document if there is no document that matches the query. If a match is found, the document\(s\) will be updated.

</td>
</tr>
<tr>
<td valign="top">

*Replace Document*

</td>
<td valign="top">

Specify the document to be inserted or replaced.

</td>
</tr>
<tr>
<td valign="top">

*Return Document*

</td>
<td valign="top">

Select to specify if the document must be returned before or after the modification:

-   *Before*: Before any modification is made to the document.
-   *After*: After any modification is made to the document.



</td>
</tr>
<tr>
<td valign="top">

*Query Options*

</td>
<td valign="top">

Enable to display advanced query options.

</td>
</tr>
<tr>
<td valign="top">

*Document Count*

</td>
<td valign="top">

Enable to return the number of documents matching the filter query.

</td>
</tr>
<tr>
<td valign="top">

*Estimated Document Count*

</td>
<td valign="top">

Enable to return the approximate count of documents in the collection.

</td>
</tr>
<tr>
<td valign="top">

*Batch Size*

</td>
<td valign="top">

Specify the maximum number of documents that must be processed in each batch of a query result.

Example:`5`

</td>
</tr>
<tr>
<td valign="top">

*Number of Documents to Skip*

</td>
<td valign="top">

Specify the number of documents to be skipped.

Example: `10`

</td>
</tr>
<tr>
<td valign="top">

*Limit*

</td>
<td valign="top">

Specify the maximum number of documents to be returned.

Example: `3`

</td>
</tr>
<tr>
<td valign="top">

*Max Time \(in ms\)*

</td>
<td valign="top">

Specify the maximum amount of time \(in milliseconds\) for the query to be completed.

Example: `30000`

</td>
</tr>
<tr>
<td valign="top">

*Command*

</td>
<td valign="top">

Specify the command to execute an operation.

Example: `{"insert":"mycollection", "name_of_document":[{"field1":"value1", "field2": value2}]}`

</td>
</tr>
</table>

