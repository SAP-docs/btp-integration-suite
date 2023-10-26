<!-- loioa43d59e7e2c44534a3e357cc315703b5 -->

# Get Message Store Entry Properties

Get message store entry properties.



To get message store entry properties, you need to perform two subsequent calls:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
<th valign="top">

Purpose

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`​/MessageProcessingLogs('{MessageGuid}')​/MessageStoreEntries` 

</td>
<td valign="top">

Get all message store entries created during the processing of an integration flow \(for a dedicated `MessageGuid`\).

</td>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`​/MessageStoreEntries('{MessageStoreEntryId}')` 

</td>
<td valign="top">

Get entry properties for an individual message store entry \(identified by `MessageStoreEntryId`\).

</td>
</tr>
</table>

In detail, perform the following subsequent calls \(example\).

1.  Get all message store entries created during the processing of an integration flow.

    Note that each Persist step in an integration flow creates a message store entry.

    Each message processing run is identified by a *Message ID* that you can find when selecting the associated integration flow using the *Monitor* application \(under *Monitor Message Processing*\).

    To get message store entries for a dedicated message processing run \(for example, with a message ID `ABCD1234XYZ`\), send the following GET request:

    `https://<host address>/api/v1/MessageProcessingLogs('ABCD1234XYZ')/MessageStoreEntries`

    The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

    As a response, you get a message that contains for each message store entry a passage with the following structure:

    ```
    <m:properties>
                <d:Id>sap-it-abcd-1234-uvw</d:Id>
                <d:MessageGuid>ABCD1234XYZ</d:MessageGuid>
                <d:MessageStoreId>Persist1</d:MessageStoreId>
                <d:TimeStamp>2021-02-25T12:49:48.83</d:TimeStamp>
                <d:HasAttachments>false</d:HasAttachments>
            </m:properties>
    ```

    The property `Id` uniquely identifies the message store entry.

2.  To get entry properties for an individual message store entry, perform a second call. To get properties for the message store entry with Id `sap-it-abcd-1234-uvw`, you perform the following GET request:

    `https://<host address>/api/v1/MessageStoreEntries('sap-it-abcd-1234-uvw')/Properties`

    As response, you get a message with an entry for each message header with the following part \(example for message header `myheader`\):

    ```
    <content type="application/xml">
                <m:properties>
                    <d:MessageId>sap-it-abcd-1234-uvw</d:MessageId>
                    <d:Name>myheader</d:Name>
                    <d:Value>myheader_value</d:Value>
                </m:properties>
    </content>
    ```


**Related Information**  


[Use the Persist Step](use-the-persist-step-2707077.md "In successful scenarios, you use the Persist step to store the message at certain positions in the message processing sequence. Messages are stored only in case message processing is accomplished successfully.")

