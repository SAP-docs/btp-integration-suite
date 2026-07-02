<!-- loioa65d213c1ec74dd581207296899fc142 -->

# Handshake and Its Status

Learn about handshake between Event Mesh and your webhook.

When you create a subscription to a queue with a webhook, Event Mesh makes a handshake request before pushing the messages to the webhook. The handshake request is an OPTIONS call to the webhook with the HTTP header `WebHook-Request-Origin`. The webhook must respond to this handshake request with the HTTP header `WebHook-Allowed-Origin` and the value of this header has to match the value of the request header `WebHook-Request-Origin`. The webhook can also respond with the value `‘*’` which means that the webhook supports event notifications from all origins. After the handshake for the subscription is completed successfully, Event Mesh publishes messages to the webhook.

> ### Example:  
> Handshake call where the webhook URL is protected with basic authentication:
> 
> ```
> OPTIONS <webhook-url>
> 
> Headers:
> Authorization: Basic <base64-encoded-basic-auth-credentials>
> WebHook-Request-Origin: <origin-of-enterprise-messaging-service>
> 
> ```

> ### Example:  
> Handshake call where the webhook URL is protected with OAuth 2.0 authentication:
> 
> ```
> OPTIONS <webhook-url>
> 
> Headers:
> Authorization: Bearer <access-token-received-from-call-to-token-url>
> WebHook-Request-Origin: <origin-of-enterprise-messaging-service>
> 
> ```

After creating a subscription, *Handshake Status* is one of the following:


<table>
<tr>
<th valign="top">

Handshake Status

</th>
<th valign="top">

Explanation

</th>
</tr>
<tr>
<td valign="top">

*Not Initiated*

</td>
<td valign="top">

Event Mesh hasn't triggered the handshake yet

</td>
</tr>
<tr>
<td valign="top">

*Requested*

</td>
<td valign="top">

Event Mesh has requested a handshake and awaiting response from your webhook.

</td>
</tr>
<tr>
<td valign="top">

*Completed*

</td>
<td valign="top">

Event Mesh has completed the handshake.

</td>
</tr>
<tr>
<td valign="top">

*Failed*

</td>
<td valign="top">

Event Mesh requested a handshake and your webhook responsed with different value under `WebHook-Allowed-Origin` that differs from the value that was originally requested with.

</td>
</tr>
<tr>
<td valign="top">

*Exempted*

</td>
<td valign="top">

You've enabled the *Exempt Handshake* option.

</td>
</tr>
</table>

