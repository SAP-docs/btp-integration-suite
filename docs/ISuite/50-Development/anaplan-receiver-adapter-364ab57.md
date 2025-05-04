<!-- loio364ab5763690404babc3be42123d4838 -->

# Anaplan Receiver Adapter

The Anaplan receiver adapter connects SAP Integration Suite to Anaplan. Anaplan is a cloud-based platform for business planning and performance management. The Anaplan adapter helps you exchange data between the two systems.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio364ab5763690404babc3be42123d4838__section_z2t_lfd_bdc"/>

## How the Anaplan Receiver Adapter Works

If you have configured the Anaplan receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Anaplan \(this is a receiver system\), Anaplan works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio364ab5763690404babc3be42123d4838__section_trk_cgd_bdc"/>

## Configure the Anaplan Receiver Adapter

Once you have created a receiver channel and selected the Anaplan adapter, you can configure its parameters as shown below:

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

Specify the recipient’s endpoint URL \(Uniform Resource Locator\) for Anaplan.

Example: `https://api.anaplan.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the required mode of authentication:

-   *Basic Auth*: Authentication token is obtained via username and password credentials.
-   *Authorization Code:* OAuth2 Authorization Code to authenticate connection to Anaplan.



</td>
</tr>
<tr>
<td valign="top">

*Authentication Host*

</td>
<td valign="top">

Specify the Anaplan authentication host.

Example: `https://auth.anaplan.com`

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the user credential to be stored as a security artifact in *Security Material*.

</td>
</tr>
</table>

The *Processing* tab contains all operation related configurations for the Anaplan Receiver adapter.

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

*API Version*

</td>
<td valign="top">

Select the API version to be used for this interaction with Anaplan. The latest API 2.0 version is supported.

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

*Resource*

</td>
<td valign="top">

Select the resource endpoint.

</td>
</tr>
<tr>
<td valign="top">

*Workspace ID*

\(Only available if *Operation* is selected as *Export & Download* or *Upload & Import*\)

</td>
<td valign="top">

Specify the Workspace ID where the operation should be performed.

Example: `8a8b8c8d8e8f8g8i`

</td>
</tr>
<tr>
<td valign="top">

*Model ID* 

\(Only available if *Operation* is selected as *Export & Download* or *Upload & Import*\)

</td>
<td valign="top">

Specify the Model ID for the operation to be performed.

Example:`FC12345678912343455667`

</td>
</tr>
<tr>
<td valign="top">

*Action ID* 

\(Only available if *Operation* is selected as *Export & Download* or *Upload & Import*\)

</td>
<td valign="top">

Specify the Action ID for the operation to be performed.

Example: `117000000019`

</td>
</tr>
<tr>
<td valign="top">

*Source ID*

\(Only available if *Operation* is selected as *Export & Download* or *Upload & Import*\)

</td>
<td valign="top">

Specify the Source ID for the operation to be performed.

Example: `113000000238`

</td>
</tr>
<tr>
<td valign="top">

*Chunk Size*

</td>
<td valign="top">

Specify the chunk size \(in KB\) into which the message should be split while sending data to Anaplan. Maximum value allowed is `50000`.

Example: `10000`

</td>
</tr>
<tr>
<td valign="top">

*Resource Parameters*

</td>
<td valign="top">

Specify the parameter *Name* and *Value* in case resource path includes parameters.

Example: Set *Name* to `id` and *Value* to `14239432`.

</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the query to be sent with the HTTP request.

Example: `param1=value1&param2=value2`

</td>
</tr>
<tr>
<td valign="top">

*Wait until Completed*

\(Only available if *Operation* is selected as *Start an Action*\)

</td>
<td valign="top">

Enable to wait until the task is completed. If disabled, the step will end after starting the task in Anaplan.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Wait Time* 

</td>
<td valign="top">

Specify the maximum duration \(in seconds\) for which the adapter will continue checking the task state.

Example: `600`

</td>
</tr>
<tr>
<td valign="top">

*Wait Retry Interval*

</td>
<td valign="top">

Specify the interval \(in seconds\) when the adapter performs task state checks. This interval should be shorter than the *Maximum Wait Time*.

Example: `10`

</td>
</tr>
<tr>
<td valign="top">

*Input format*

</td>
<td valign="top">

Select the payload format of the request body:

-   JSON

-   TEXT



</td>
</tr>
<tr>
<td valign="top">

*Output format*

</td>
<td valign="top">

Select the payload format of the response body:

-   JSON

-   TEXT
-   XML



</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Specify a list of custom headers, separated by a pipe \(|\), to be sent to the target system. By default, no custom headers are sent. Use an asterisk \(\*\) to send all custom headers to the target system.

> ### Note:  
> You can dynamically pass on the values by defining a property that includes a list of headers.



</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Specify a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

