<!-- loioe49c1def3f5d445fa0ea820eb0771eb0 -->

# LeanIX Receiver Adapter

The LeanIX receiver adapter connects SAP Integration Suite to SAP LeanIX and allows data exchange between the two systems. SAP LeanIX is a SaaS application that allows you to manage and optimize enterprise architecture.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loioe49c1def3f5d445fa0ea820eb0771eb0__section_vyg_c5v_42c"/>

## How the LeanIX Receiver Adapter Works

If you have configured the LeanIX receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to SAP LeanIX \(this is a receiver system\), SAP LeanIX works on the request and sends the data back to the SAP Integration Suite tenant.

The adapter supports the following variants:

-   GraphQL

-   REST



<a name="loioe49c1def3f5d445fa0ea820eb0771eb0__section_mbp_w5v_42c"/>

## Configure the LeanIX Receiver Adapter



### GraphQL

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

Specify the address of LeanIX to be used for the connection.

Example: `https://sample1-eu-1.leanix.net`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select your Authentication Mechanism. Currently, only *LeanIX OAuth* is Supported.

</td>
</tr>
<tr>
<td valign="top">

*API Token Alias*

</td>
<td valign="top">

Specify the Secure Parameter alias representing API token of Technical user.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) while establishing a connection with LeanIX.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) \) for a response to be received from LeanIX.

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

*Operation*

</td>
<td valign="top">

Select the operation to be performed:

-   *Advanced Query*
-   *Archive*
-   *Create*
-   *Get All*
-   *Get By Id*
-   *Recover*
-   *Update*



</td>
</tr>
<tr>
<td valign="top">

*GraphQL Query*

</td>
<td valign="top">

Specify the GraphQL query for operation to be performed.

> ### Sample Code:  
> ```
> {
>   factSheet(id: "2efa37b5-18aa-48d8-9d70-1328c0d856d7") {
>     id \n
>     name \n
>     type \n
>   } \n 
> }
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Select the entity type. Currently only *FactSheet* is only available.

</td>
</tr>
<tr>
<td valign="top">

*FactSheet ID*

</td>
<td valign="top">

Specify the id of the entity.

Example: `dff6a026-7aa5-4317-b8c1-08j8c12b01f0`

</td>
</tr>
<tr>
<td valign="top">

*Comment*

</td>
<td valign="top">

Specify the comment while using *Operation* as *Archive* or *Recover*.

</td>
</tr>
<tr>
<td valign="top">

*FactSheet Type*

</td>
<td valign="top">

Specify the FactSheet type.

</td>
</tr>
<tr>
<td valign="top">

*Fields*

</td>
<td valign="top">

Specify the fields required in response for Asset Type.

Example: `Computer,Mouse,DisplayName`

</td>
</tr>
</table>





### REST



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

Specify the address of LeanIX to be used for the connection.

Example: `https://sample1-eu-1.leanix.net`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select your Authentication Mechanism. Currently, only *LeanIX OAuth* is Supported.

</td>
</tr>
<tr>
<td valign="top">

*API Token Alias*

</td>
<td valign="top">

Specify the Secure Parameter alias representing API token of Technical user.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) while establishing a connection with LeanIX.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) \) for a response to be received from LeanIX.

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

Select the entity type:

-   *Bookmarks*
-   *BookmarkShares*
-   *Exports*
-   *Features*
-   *Integration API*
-   *Models*
-   *Settings*
-   *Suggestions*



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*Id*

</td>
<td valign="top">

Specify the ID of the deployed script.

Example: `65e5f779-b7f0-4a1f-9c88-9f0e4ke9bed9`

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify the value of the Query parameter.

Example: `bookmarkType=INVENTORY&groupKey=sampleGroup`

</td>
</tr>
<tr>
<td valign="top">

*FactSheet Type*

</td>
<td valign="top">

Specify the FactSheet type.

Example: `Application`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system.

All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value.

All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
</table>

