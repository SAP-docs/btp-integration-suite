<!-- loio6586e51f19d448e5ba0e3c3ffdd62ff7 -->

# Outbound Headers in the RNIF Adapter

You can send custom headers to a trading partner endpoint as HTTP request headers, at the start of the HTTP body, or both.

By default, message headers you define in an integration flow are internal and not sent to the partner. To forward a header, add one or both of the following exchange properties in the *Content Modifier* step that comes before the RNIF receiver channel:


<table>
<tr>
<th valign="top">

Exchange Property

</th>
<th valign="top">

Effect

</th>
</tr>
<tr>
<td valign="top">

`rnifHTTPHeaders`

</td>
<td valign="top">

Adds the listed headers as HTTP request headers.

</td>
</tr>
<tr>
<td valign="top">

`rnifPayloadHeaders`

</td>
<td valign="top">

Places the listed headers at the start of the HTTP body, before the MIME content.

</td>
</tr>
</table>

> ### Note:  
> Both properties accept a pipe-separated \(`|`\) list of header names. The system ignores whitespace around the names and performs case-insensitive matching. If you list a header in both properties, the system sends it to both locations.



<a name="loio6586e51f19d448e5ba0e3c3ffdd62ff7__section_configure"/>

## Configuring Custom Outbound Headers

1.  Select the *Content Modifier* step in the integration flow to open its properties.
2.  Open the *Message Headers* tab and add the following headers:


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Source Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `Date`
    
    </td>
    <td valign="top">
    
    Expression
    
    </td>
    <td valign="top">
    
    `${date:now:EEE, dd MMM yyyy HH:mm:ss Z}`

    > ### Example:  
    > `Mon, 01 Jan 2024 12:00:00 +0000`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Message-ID`
    
    </td>
    <td valign="top">
    
    Expression
    
    </td>
    <td valign="top">
    
    `${header.SAP_MessageProcessingLogID}`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `X-Custom-Ref`
    
    </td>
    <td valign="top">
    
    Constant
    
    </td>
    <td valign="top">
    
    `PARTNER-001`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `X-Trace-ID`
    
    </td>
    <td valign="top">
    
    Constant
    
    </td>
    <td valign="top">
    
    `TRC-9981`
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Headers defined here remain internal to the integration flow until you configure the routing properties in the next step.

3.  Open the *Exchange Properties* tab and add one or both of these routing properties as *Constant* entries.


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Source Value
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `rnifHTTPHeaders`
    
    </td>
    <td valign="top">
    
    Constant
    
    </td>
    <td valign="top">
    
    `X-Custom-Ref | X-Trace-ID`
    
    </td>
    <td valign="top">
    
    Use `rnifHTTPHeaders` for non-standard HTTP headers required by the trading partner. Based on the example above, the outbound HTTP request contains:

    > ### Example:  
    > ```
    > POST /rnif HTTP/1.1
    > Content-Type: multipart/related; ...
    > x-RN-Version: RosettaNet/V02.00
    > x-RN-Response-Type: async
    > X-Custom-Ref: PARTNER-001
    > X-Trace-ID: TRC-9981
    > ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `rnifPayloadHeaders`
    
    </td>
    <td valign="top">
    
    Constant
    
    </td>
    <td valign="top">
    
    `Date | Message-ID | X-Custom-Ref`
    
    </td>
    <td valign="top">
    
    Use `rnifPayloadHeaders` when the partner expects email-style headers immediately before the MIME content.

    > ### Example:  
    > ```
    > Date: Mon, 01 Jan 2024 12:00:00 +0000
    > Message-ID: AG8f...c21
    > X-Custom-Ref: PARTNER-001
    > 
    > --<boundary>
    > Content-Type: multipart/signed; ...
    > ```


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The spaces between characters are optional. The values `X-Custom-Ref|X-Trace-ID` and `X-Custom-Ref | X-Trace-ID` are equivalent.


The RNIF Receiver channel forwards the specified headers to the partner endpoint. Headers listed in `rnifHTTPHeaders` are sent as HTTP request headers. Headers listed in `rnifPayloadHeaders` appear at the start of the HTTP body before the first MIME boundary, in the order in which they are listed.



<a name="loio6586e51f19d448e5ba0e3c3ffdd62ff7__section_standard_headers"/>

## Standard Adapter Headers

The adapter always sends `Content-Type`, `x-RN-Response-Type`, and `x-RN-Version` as HTTP request headers.

Do not redefine these as message headers in the *Content Modifier*. To also include those values at the start of the HTTP body, list them in `rnifPayloadHeaders`.

> ### Example:  
> ```
> Content-Type: multipart/related; ...
> x-RN-Response-Type: async
> x-RN-Version: RosettaNet/V02.00
> Date: Mon, 01 Jan 2024 12:00:00 +0000
> Message-ID: AG8f...c21
> 
> --<boundary>
> Content-Type: multipart/signed; ...
> ...
> ```

> ### Note:  
> Listing a standard adapter header in `rnifHTTPHeaders` has no effect. The adapter already sends it as an HTTP request header and does not send it twice.

The following table shows how each header is sent based on where you list it in your configuration. Use the table to determine the outcome of different combinations:


<table>
<tr>
<th valign="top">

Header Type

</th>
<th valign="top">

In `rnifHTTPHeaders`

</th>
<th valign="top">

In `rnifPayloadHeaders`

</th>
<th valign="top">

Sent as HTTP Header

</th>
<th valign="top">

Sent in Body

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Standard adapter header \(`Content-Type`, `x-RN-Response-Type`, `x-RN-Version`\)

</td>
<td valign="top">

Ignored

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes \(always\)

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Ignored

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes \(always\)

</td>
<td valign="top">

Yes \(adapter-generated value\)

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Custom message header

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
</table>



<a name="loio6586e51f19d448e5ba0e3c3ffdd62ff7__section_troubleshooting"/>

## Troubleshooting

The following table describes problems that can occur when configuring custom outbound headers and how to resolve them:


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Header is not reaching the partner.

</td>
<td valign="top">

Check that the header name is listed in `rnifHTTPHeaders` or `rnifPayloadHeaders`. Defining a message header in the *Content Modifier* alone does not forward it to the partner.

</td>
</tr>
<tr>
<td valign="top">

Header is listed in a routing property but does not appear.

</td>
<td valign="top">

Verify that the name matches a message header defined in the *Message Headers* tab of the *Content Modifier*. Matching is case-insensitive, but the name must otherwise be exact.

</td>
</tr>
<tr>
<td valign="top">

Body headers appear in the wrong order.

</td>
<td valign="top">

Reorder the names in `rnifPayloadHeaders`. The adapter preserves the order in which names are listed.

</td>
</tr>
<tr>
<td valign="top">

A standard adapter header appears in the HTTP body unexpectedly.

</td>
<td valign="top">

This occurs when the header name is listed in `rnifPayloadHeaders`. Remove it from the property if you don't want it included in the body.

</td>
</tr>
</table>

