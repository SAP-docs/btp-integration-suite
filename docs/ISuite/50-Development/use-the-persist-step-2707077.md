<!-- loio27070775a7c443dfb724f3b5bb66d13e -->

# Use the Persist Step

In successful scenarios, you use the Persist step to store the message at certain positions in the message processing sequence. Messages are stored only in case message processing is accomplished successfully.

The data can be accessed and analyzed after message processing \(for example, for auditing purposes\). Usually, the message is stored at the beginning \(inbound message\) and at the end \(outbound message\) of the message processing sequence.

More information: [Persist Messages](persist-messages-8c35f3f.md)

The logical storage location used by the Persist step is the Message Store. Physically, the Message Store uses the same tenant database as the Data Store and the storage locations for message processing logs, tracing data, and deployed artifacts \(see also: [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md)\).



<a name="loio27070775a7c443dfb724f3b5bb66d13e__section_y1x_qx4_2nb"/>

## Implementation

To illustrate how to use the Persist step, the following integration flow is available:*Modeling Basics - Use the Persist Step*.

This integration flow reads product details for a given product identifier from the WebShop using the OData adapter. The scenario contains two Persist steps that store the message at 2 different positions in the message processing sequence.

-   The 1st Persist step stores the inbound message \(received by the HTTP client\).

-   The 2nd Persist step stores the message after the WebShop has been called.

    > ### Note:  
    > To motivate a real life use case, you can imagine that the integration flow can be enhanced in the following way: The final message received from the WebShop \(containing the product details\) is sent to a receiver system. The 2nd Persist step is then storing the outbound message of the scenario.


For convenience, the HTTP client gets a response message with information on how to access the Message Store entries for the actual message processing run.

The integration flow *Modeling Basics - Use the Persist Step* is designed in the following way.

![](images/Use_Persist_Step_a095f60.png)

The integration flow performs the following steps:

1.  A message is received from an HTTP client \(Postman\) through the HTTPS sender channel. The payload contains a product identifier.

2.  The Persist step *Persist inbound message* stores the inbound message in the Message Store. As *Step ID*, the following value is specified: `PersistInbound`.

    For a dedicated product identifier, the stored message has the following structure.

    ```
    <message>
    <productId>HT-1000</productId>
    </message>
    ```

3.  The Content Modifier *Store product identifier as property* defines the following Exchange property \(see *Exchange Property* tab\).


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Value
    
    </th>
    <th valign="top">

    Purpose
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    productIdentifier
    
    </td>
    <td valign="top">
    
    XPath
    
    </td>
    <td valign="top">
    
    //productId
    
    </td>
    <td valign="top">
    
    Product identifier contained in the inbound message.

    This property is used in the OData channel query when reading the product details from the WebShop.
    
    </td>
    </tr>
    </table>
    
4.  The OData channel request product details from the WebShop component for the product identifier.

    The OData receiver channel contains the following query:

    `$select=ProductId,Category,CategoryName,CurrencyCode,Price,Name&$filter=ProductId eq '${property.productIdentifier}'`

5.  The Persist step *Persist outbound message* stores the message in the Message Store. As *Step ID*, the following value is specified: `PersistOutbound`.

    For a dedicated product identifier, the stored message has the following structure.

    ```
    <Products>
        <Product>
          <CurrencyCode>EUR</CurrencyCode>
          <Category>Notebooks</Category>
          <Price>956.000</Price>
          <CategoryName>Notebooks</CategoryName>
          <ProductId>HT-1000</ProductId>
          <Name>Notebook Basic 15</Name>
        </Product>
      </Products>
    
    ```

6.  The Content Modifier *Define response message* defines the following response message for the HTTP client.

    ```
    You can access the Message Store entries created by the Persist steps calling the OData API with the following request:\n
    "https://${header.cpi_designtime_url}/api/v1/MessageProcessingLogs('${header.SAP_MessageProcessingLogID}')/MessageStoreEntries"\n
    As response, you get an XML document that contains two Message Store entries, each entry containing an element like the following one (with example value): \n
    <d:Id>sap-it-abcd-1234-5678</d:Id>.\n
    To get the message payload stored by the Persist step (associated with this Message Store entry), open another Postman tab and set up an OData API call with the following URL (using the Id provided for the Message Store entry with the previous request, example: sap-it-abcd-1234-5678):\n
    "https://${header.cpi_designtime_url}/api/v1/MessageStoreEntries('sap-it-abcd-1234-5678')/$value"
    ```

    > ### Note:  
    > To illustrate an auditing use case, the integration flow stores the inbound message and the outbound message \(that, in an enhanced scenario, can be sent to a receiver system\) as separate Message Store entries. To access the content of the Message Store, you need to use the OData API.
    > 
    > The OData API provides an entity \(`MessageStoreEntries`\) that allows you to get all Message Store entries for a dedicated `MessageGuid` value. The `MessageGuid` parameter uniquely identifies a concrete message processing run \(see [Message Stores](https://api.sap.com/api/MessageStore/overview)\).
    > 
    > To make it easy for the user to get the Message Store entries for a given message processing run, the integration flow contains this final step. As HTTP response, the user gets the dedicated URL including the query parameters to get all Message Store entries for the actual message processing run.
    > 
    > -   The header `cpi_designtime_url` contains the URL of your Cloud Integration host.
    > 
    >     You need to specify this header before sending the Postman request to the integration flow.
    > 
    >     When you've opened the Web UI, you get this address when skipping the string `/itspaces`.
    > 
    >     This address is the base address for the OData API calls.
    > 
    >     > ### Note:  
    >     > To make sure that this header is accepted by the integration flow, and it is allowed in the *Runtime Configuration* tab in the *Allowed Header\(s\)* field.
    > 
    > -   The header `SAP_MessageProcessingLogID` contains the value of the actual message processing run written by the Camel framework.
    > 
    > 
    > In other words, when the 2 headers are set correctly, the message body contains the OData API request URL that provides as response the Message Store entries for the actual message processing run.
    > 
    > To get the actual message payload stored by the two Persist steps, further OData API calls are required. These OData API calls are executed by the user after the integration flow has been executed.




<a name="loio27070775a7c443dfb724f3b5bb66d13e__section_sy2_g4x_hnb"/>

## Executing the Scenario

You first need to execute the integration flow *Modeling Basics - Use the Persist Step* and, thereafter, perform a number of requests to the Cloud Integration OData API to get the content of the Message Store entries.

The Postman collection for this guideline \(in folder `PersistStep`\) comes with 4 requests. With the first request, you call the integration flow *Modeling Basics - Use the Persist Step*. With the 3 subsequent requests you call the Cloud Integration OData API successively to get the content of the 2 Message Store entries written during the execution of the integration flow.


<table>
<tr>
<th valign="top">

Postman Request

</th>
<th valign="top">

Purpose

</th>
</tr>
<tr>
<td valign="top">

PersistStep

</td>
<td valign="top">

Calls the integration flow endpoint.

</td>
</tr>
<tr>
<td valign="top">

MessageStoreEntries

</td>
<td valign="top">

Reads the Message Store entries written during the execution of the integration flow. As there are two Persist steps, 2 entries are written. One entry contains the payload of the inbound message, the other one the payload of the outbound message.

</td>
</tr>
<tr>
<td valign="top">

MessageStorePayload Inbound

</td>
<td valign="top">

Reads the \(inbound\) payload stored in the first Message Store entry.

</td>
</tr>
<tr>
<td valign="top">

MessageStorePayload Outbound

</td>
<td valign="top">

Reads the \(outbound\) payload stored in the 2nd Message Store entry.

</td>
</tr>
</table>

> ### Note:  
> **Prerequisites**
> 
> In the URL Postman variable `cpi_designtime_url` is used. You need to maintain this variable in your Postman environment. It holds the Cloud Integration host name of the Web UI. This is the part of the browser address before the string `/itspaces` when you've opened the Cloud Integration Web UI \(for example: `mytenant.tmn.hci.eu1.hana.ondemand.com`\).
> 
> Make sure that API clients are authorized to access the Cloud Integration OData API for your tenant \(see *Related Links*\).

To execute the scenario, perform the following steps.

1.  Deploy the *Modeling Basics - Use the Persist Step* integration flow.

2.  Open Postman and import the Postman collection provided with the integration package.

3.  Open the collection and go to folder `PersistStep`.

4.  Send the first request \(*PersistStep* request\).

    > ### Note:  
    > In the *Body*, the following content is predefined:
    > 
    > `<message><productId>HT-1000</productId></message>`
    > 
    > You can leave it as it is or specify another product identifier \(for which a product exists in the WebShop\).

    The HTTP response contains an instruction on how to set up the subsequent OData API requests \(including the relevant URLs\). You have the option set up and run Postman requests from scratch as described in the instruction.

    However, using the 3 other requests of the Postman collection, this procedure is automated.

5.  To retrieve the content of the Message Store \(written by the integration flow *Modeling Basics - Use the Persist Step*\), perform the 2nd request \(*MessageStoreEntries*\).

    As a response, you get a message that contains 2 Message Store entries in JSON format. Each entry contains a part with the following structure \(example for the Message Store entry created by the first Persist step of the integration flow\):

    ```
    "Id": "sap-it-res:msg:a2ee4d384:28c8aa20-aeda-423b-ac15-847274432c32",
                    "MessageGuid": "AF-P3t5_bmeOSK21lFA_qmVZAo7W",
                    "MessageStoreId": "PersistInbound",
                    "TimeStamp": "/Date(1603264222796)/",
    ...
    ```

    Note that parameter `MessageStoreId` corresponds to the `Step ID` specified for the Persist step in the integration flow model.

6.  To get the inbound message payload stored by the 1st Persist step \(associated with the 1st Message Store entry\), perform the 3rd request \(*MessageStorePayload Inbound*\).

    As response, you get:

    ```
    <message>
        <productId>HT-1000</productId>
    </message>
    ```

7.  To get the outbound message payload stored by the 2nd Persist step \(associated with the 2nd Message Store entry\), perform the 4th request \(*MessageStorePayload Outbound*\).

    As response, you get:

    ```
    <Products>
        <Product>
          <CurrencyCode>EUR</CurrencyCode>
          <Category>Notebooks</Category>
          <Price>956.000</Price>
          <CategoryName>Notebooks</CategoryName>
          <ProductId>HT-1000</ProductId>
          <Name>Notebook Basic 15</Name>
        </Product>
      </Products>
    ```


**Related Information**  


[Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md "An application programming interface (API) allows you to access Cloud Integration data, for example, monitoring data.")

[Setting Up Inbound HTTP Connections (for API Clients), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/fbae09c89d9246f88149c5293c96ab5f.html "") :arrow_upper_right:

