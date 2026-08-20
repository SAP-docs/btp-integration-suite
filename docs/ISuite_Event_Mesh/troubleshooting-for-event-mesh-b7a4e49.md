<!-- loiob7a4e4935533473e9e6e1d71848153fc -->

# Troubleshooting for Event Mesh

Information on troubleshooting incidents and errors related to Event Mesh in SAP Integration Suite, and support information.

**Common Issues and Resolutions**


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Event Mesh activation failed

</td>
<td valign="top">

When trying to activate the Event Mesh in SAP Integration Suite, the *Failed* status is displayed. On the *Queues* tab, the message *Event Mesh activation failed. Please try again.*appears. This occurs when the subaccount used to subscribe to the Event Mesh capability already has the standalone SAP Event Mesh service \(default plan\) enabled — the two cannot coexist in the same subaccount.

</td>
<td valign="top">

Refer to SAP KBA [3527095](https://launchpad.support.sap.com/#/notes/3527095).

You must:

1.  Remove the Event Mesh default plan instance from the subaccount.
2.  Deactivate the Event Mesh capability in SAP Integration Suite.
3.  Reactivate the Event Mesh capability.

See [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?version=CLOUD&ai=true).

</td>
</tr>
<tr>
<td valign="top">

Event Mesh shell navigation is missing

</td>
<td valign="top">

After subscribing to SAP Integration Suite and activating the Event Mesh capability, the menu options for Event Mesh are not visible. This typically occurs when the required user access and role collections have not been assigned, preventing the user from viewing or navigating to Event Mesh functionalities.

</td>
<td valign="top">

Ensure the user has the correct role collections and permissions assigned in the subaccount.

1.  Assign the required role collections \(e.g., Event Mesh administrator/developer roles\). See [Configuring User Access to SAP Integration Suite](https://help.sap.com/docs/integration-suite/sap-integration-suite/configuring-user-access?version=CLOUD&ai=true) \> *Event Mesh*
2.  Log out and log back in to refresh the shell navigation.

Also see, [Tasks and Permissions in Event Mesh](tasks-and-permissions-in-event-mesh-b497c6d.md).

</td>
</tr>
<tr>
<td valign="top">

Topic subscription CRUD operations failing with 404.

</td>
<td valign="top">

When performing Create, Update, Read, or Delete operations on topic subscriptions \(via the Queue Subscriptions to Topics API\), the call fails with a *404 Not Found*error. The API response indicates *"Queue subscription not found"* or *"Queue not found"*. This typically occurs because topics in Event Mesh are managed as subscriptions bound to a queue — not as standalone resources. The 404 is returned when the queue does not exist, the subscription \(topic pattern\) is not bound to the specified queue, or the queue/topic name is not URL-encoded correctly.

</td>
<td valign="top">

Verify the queue, topic subscription, and request format before retrying.

Steps:

1.  Confirm the correct API base URL: `https://<hostname>/sap-event-mesh/rest/api/v1`.
2.  Use the correct endpoint: `/queues/{queue}/subscriptions/{topic}` \(topic CRUD is performed via queue subscriptions\).
3.  Ensure both the queue name and topic pattern are URL-encoded \(e.g., `/` encoded as `%2F`\).
4.  Validate that the queue exists before creating or updating a subscription on it.
5.  Confirm the topic pattern matches the required schema \(`TopicPattern` — max 150 characters, allowed characters `[A-Za-z0-9-.]`, `+`, `/`, `*`\).

See, [Queue Subscriptions to Topics API](https://api.sap.com/api/MgmtRestAPI/resource/Queue_Subscriptions_to_Topics).

</td>
</tr>
<tr>
<td valign="top">

Event Mesh message client instance creation failed

</td>
<td valign="top">

When initiating the message broker in Event Mesh, the creation of the message client instance fails.

This typically occurs due to:

-   Missing or incorrect broker configuration
-   Insufficient entitlements in the subaccount
-   Incomplete prerequisites required to provision the message client instance



</td>
<td valign="top">

Verify the broker configuration and subaccount entitlements before retrying the initiation.

1.  Ensure the required entitlements for Event Mesh are assigned to the subaccount.
2.  Verify the broker specifications on the *Initiate Event Mesh* screen are correct. See [Initiating the Message Broker](initiating-the-message-broker-61eb5dd.md)
3.  Confirm no conflicting Event Mesh instances \(e.g., default plan\) exist in the same subaccount.
4.  Retry the message broker initiation.



</td>
</tr>
<tr>
<td valign="top">

Queue CRUD operations failing

</td>
<td valign="top">

When performing Create, Read, Update, Delete, or Purge operations on queues via the Manage Queues API, calls may fail with:

-   *400 Bad Request* \(*"if the given parameters have invalid values"*\)
-   403 Forbidden
-   404 Not Found \(response: `{"code": "404", "message": "Queue not found"}`\).

Common causes include:

-   Invalid queue configuration values \(e.g., exceeding the allowed range for `maxDeliveredUnackedMsgsPerFlow`, `maxMessageSizeInBytes`, `maxQueueSizeInBytes`, `maxRedeliveryCount`, or `maxTtl`\)
-   Non-URL-encoded queue names
-   The queue not existing on the target Event Mesh instance.



</td>
<td valign="top">

Verify the request payload, queue name encoding, and authorization before retrying.

Steps:

1.  Ensure the queue name in the path is URL-encoded and matches the `QueueName` schema pattern.
2.  Validate the request body against the `QueueP` schema:
    -   `accessType`: `EXCLUSIVE` or `NON_EXCLUSIVE` \(default: `NON_EXCLUSIVE`\).
    -   `maxDeliveredUnackedMsgsPerFlow`: 1–1,000,000 \(default: 10,000\).
    -   `maxMessageSizeInBytes`: 1–30,000,000 \(default: 10,000,000\).
    -   `maxQueueSizeInBytes`: rounded up to a multiple of 1,048,576 \(default: 1,572,864,000\).
    -   `maxRedeliveryCount`: 0–255 \(default: 0; applies only to AMQP 1.0\).
    -   `maxTtl`: 1–2,592,000 seconds \(default: 2,592,000\); value of 0 disables expiry.
    -   `deadMsgQueue`: name of an existing queue for expired/max-redelivered messages.

3.  To change `accessType` on a durable queue, first disable client access to the queue.
4.  For `GET`, `PUT`, `DELETE`, and Purge Queue operations, confirm the queue exists to avoid `404 Queue not found`.
5.  For Purge Queue, a successful call returns `204 No Content`.

See, [Manage Queues API](https://api.sap.com/api/MgmtRestAPI/resource/putQueueSubscription).

</td>
</tr>
<tr>
<td valign="top">

API calls failing with 401 or 403.

</td>
<td valign="top">

When performing operations via the Event Mesh REST APIs \(such as the Manage Queues API or the Queue Subscriptions to Topics API\), calls may fail with:

-   401 Unauthorized: A 401 indicates that the OAuth2 token is missing, expired, or malformed.
-   403 Forbidden: A 403 indicates that the token is valid but lacks the required scopes or permissions to perform the requested operation.



</td>
<td valign="top">

Verify the OAuth2 credentials and ensure the required scopes are assigned before retrying.

Steps:

1.  Confirm that a valid OAuth2 token is included in the `Authorization` header of the request.

2.  If the token has expired, log out and log back in to obtain a new token.

3.  Verify the token includes the required scopes: `read` \(for GET operations\), `write` \(for POST/PUT operations\), or `manage` \(for DELETE/Purge operations\).

4.  If scopes are missing, update the service binding or OAuth2 client configuration to include the necessary scopes and regenerate the token.




</td>
</tr>
<tr>
<td valign="top">

SSL Connection Error / Untrusted Certificate

</td>
<td valign="top">

When attempting to establish a secure connection, the system displays an SSL Connection Error or reports an Untrusted Certificate.

This typically occurs when the target server's SSL/TLS certificate is not trusted by the client. This could be because:

-   The certificate is self-signed, expired
-   Issued by an unrecognized Certificate Authority \(CA\)
-   The required root/intermediate certificates are missing from the client's trust store \(keystore\).



</td>
<td valign="top">

Refer to SAP Knowledge Base Article [3619034 - SSL Connection Error](https://me.sap.com/notes/3619034).

</td>
</tr>
<tr>
<td valign="top">

WebSocket connection error in S/4HANA

</td>
<td valign="top">

When attempting to establish a WebSocket connection to Event Mesh from S/4HANA, the connection setup fails with the error message: *WebSocket connection set up has failed with error text: 500 Internal Server Error.* 

This typically occurs when the service instance created for Event Mesh is not correctly configured — for example, the service descriptor JSON file may contain:

-   An invalid namespace
-   Missing or malformed publish/subscribe rules
-   Incorrect resource unit definitions

All these prevent the message client from establishing a valid connection.

</td>
<td valign="top">

Review and correct the service descriptor JSON file used to create the Event Mesh service instance. Ensure the namespace, rules, and resource attributes conform to the required syntax and guidelines as described in [Service Descriptor Syntax](https://help.sap.com/docs/integration-suite/isuite-event-mesh/service-descriptor-syntax). After updating the service descriptor, recreate or update the service instance and retry the WebSocket connection.

</td>
</tr>
<tr>
<td valign="top">

Invalid handshake response / connection limit exceeded

</td>
<td valign="top">

Connection to SAP Event Mesh cannot be established because the connection limit for the Event Mesh service instance has been reached.

Error messages may include: *connection to broker failed \(220012\) \[connection rejected \(too much connections\)\], or session is closed*.

This occurs because each Event Mesh service instance limits the number of AMQP and MQTT connections that can be established.

When multiple consumers \(for example, several Integration Flows across multiple Cloud Integration worker node instances\) share the same service instance, the connection limit can be exhausted. The number of connections required may also temporarily double during regular Cloud Integration updates.

</td>
<td valign="top">

Estimate the total number of connections required by your scenario.

The AMQP adapter establishes one connection per Integration Flow usage per Cloud Integration worker node instance, with a temporary peak of double this value during regular Cloud Integration updates.

Configure the Event Mesh service instance accordingly by adjusting the resource units allocated to it. Refer to SAP Knowledge Base Article [3469356 - Connection limit exceeded](https://me.sap.com/notes/3469356) for detailed guidance on sizing and updating the service instance.

After updating the configuration, recreate or update the service instance and retry the connection.

</td>
</tr>
</table>



<a name="loiob7a4e4935533473e9e6e1d71848153fc__section_w4n_ngz_pcc"/>

## Reporting an Incident

If you find an issue with Event Mesh, you can report an incident or error through the [SAP Support Portal](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fsupport.sap.com%2Fen%2Findex.html). For more information, see [Product Support](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fsupport.sap.com%2Fen%2Fmy-support%2Fproduct-support.html).

Please use the following component for your incident:


<table>
<tr>
<th valign="top">

Support Component

</th>
<th valign="top">

Capability

</th>
</tr>
<tr>
<td valign="top">

`BC-CP-EM-MES`

</td>
<td valign="top">

For issues related to Event Mesh queues, topics, and webhooks.

</td>
</tr>
</table>

When you submit the incident, we recommend including the following information:

-   Landscape information \(Canary, EU10, US10\)

-   The URL of the page where the incident or error occurs

-   The steps or clicks used to replicate the error

-   Screen grabs, videos, or the code being inputted


