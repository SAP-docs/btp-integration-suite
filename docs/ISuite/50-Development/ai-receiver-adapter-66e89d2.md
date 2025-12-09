<!-- loio66e89d2883fd46e7bcef39fe347cd462 -->

# AI Receiver Adapter

AI Adapter for SAP Integration Suite facilitates and accelerates connectivity to Generative AI Hub \(SAP AI Core\) and other AI providers. The AI Adapter is available in AICore-GenAIHub and Custom-OpenAI-REST variants.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio66e89d2883fd46e7bcef39fe347cd462__section_bhw_cmj_aiadapter"/>

## How the AI Adapter works

AI Adapter functions as a receiver adapter, after configuring the AI Adapter, data exchange is performed as follows at runtime:SAP Integration Suite tenant sends the operation request to GenAIHub, AI Adapter works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio66e89d2883fd46e7bcef39fe347cd462__section_lx1_zmj_k2c"/>

## Configuring the AI Adapter



### *AICore-GenAIHub*

**Connection**


<table>
<tr>
<th valign="top">

*Parameter*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Specify the GenAIHub Address.

Example: `https://api.ai.{tenant_name}.ml.hana.ondemand.com`

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Client Credentials*

</td>
<td valign="top">

Specify the name of the OAuth2 Client Credentials security artifact.

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

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

</td>
</tr>
<tr>
<td valign="top">

*Socket Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

*Parameter*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation from the dropdown.

</td>
</tr>
<tr>
<td valign="top">

*Orchestration Deployment ID*

</td>
<td valign="top">

Specify the Deployment ID for this Orchestration.

</td>
</tr>
<tr>
<td valign="top">

*AI Resource Group*

</td>
<td valign="top">

Specify the AI Resource Group configured for the specific orchestration deployment.

</td>
</tr>
<tr>
<td valign="top">

*Request Payload Source*

</td>
<td valign="top">

Select an option to specify the source for request payload:

-   *Exchange Body* allows you to specify required structure and values.
-   *UI Configurable* provides user friendly fields to create the payload automatically.



</td>
</tr>
<tr>
<td valign="top">

*Model*

</td>
<td valign="top">

Select the required AI model for your operation.

> ### Note:  
> To verify and check availability of models, see[Availability of Generative AI Models](https://me.sap.com/notes/3437766).



</td>
</tr>
<tr>
<td valign="top">

*Role*

</td>
<td valign="top">

Specify the role to be assumed:

-   *assistant*
-   *system*
-   *user*



</td>
</tr>
<tr>
<td valign="top">

*Input*

</td>
<td valign="top">

Specify the content containing the instruction to be carried out.

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
</table>



### *Custom-OpenAI-REST*

**Connection**


<table>
<tr>
<th valign="top">

*Parameter*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Specify the OpenAI Address.

Example: `https://api.openai.com`

</td>
</tr>
<tr>
<td valign="top">

*API Key Alias*

</td>
<td valign="top">

Specify the API Key alias.

> ### Note:  
> The value of API Key Alias must be a combination of `{Bearer }` and `{API Key provided by OpenAPI}.`

Example: `Bearer sk-proj-xxxxxx`

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

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

</td>
</tr>
<tr>
<td valign="top">

*Socket Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

*Parameter*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Configuration Type*

</td>
<td valign="top">

Select the required configuration type:

-   *Basic* to use the dropdowns and parameter text fields.
-   *Advanced* to specify the relative URL.



</td>
</tr>
<tr>
<td valign="top">

*Category*

</td>
<td valign="top">

Select the API based on which the API is selected:

-   *Chat Completions*
-   *Platform*
-   *Responses*



</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Select the entity based on which the operation will be performed.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the desired operation from the dropdown.

</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the name of the file for upload.

</td>
</tr>
<tr>
<td valign="top">

*Model*

</td>
<td valign="top">

Specify the required AI model for your operation.

> ### Note:  
> This field is editable; you can also specify other models if your preferred model is not available in the dropdown.



</td>
</tr>
<tr>
<td valign="top">

*Request Payload Source*

</td>
<td valign="top">

Select an option to specify source for request payload:

-   *UI Configurable* provides user friendly fields to create the payload automatically.
-   *Exchange Body* allows you to specify required structure and values.



</td>
</tr>
<tr>
<td valign="top">

*Mask Attachment Name*

</td>
<td valign="top">

Specify an additional image file whose fully transparent areas indicate where image should be edited.

> ### Note:  
> It must be a valid PNG file, less than 4MB, should have the same dimensions as image.



</td>
</tr>
<tr>
<td valign="top">

*Include*

</td>
<td valign="top">

Specify additional information to be included in the transcription response.

Example: `logprobs`

> ### Note:  
> For multiple values, use comma-separated values.



</td>
</tr>
<tr>
<td valign="top">

*Language*

</td>
<td valign="top">

Specify the language of the input audio in ISO-639-1 format.

Example: `en`

</td>
</tr>
<tr>
<td valign="top">

*Input*

</td>
<td valign="top">

Specify the text for the input body field.

</td>
</tr>
<tr>
<td valign="top">

*Voice*

</td>
<td valign="top">

Select the voice to be used to generate the audio.

</td>
</tr>
<tr>
<td valign="top">

*Instructions*

</td>
<td valign="top">

Control the voice of your generated audio with additional instructions.

</td>
</tr>
<tr>
<td valign="top">

*Prompt*

</td>
<td valign="top">

Specify the content containing the instruction to be carried out.

</td>
</tr>
<tr>
<td valign="top">

*Number of Images*

</td>
<td valign="top">

Specify the number of images to be generated. The value ranges from 1 to 10.

</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

Specify the output format.

Example: `srt,url`

</td>
</tr>
<tr>
<td valign="top">

*Temperature*

</td>
<td valign="top">

Specify the sampling temperature. This value must be between 0 and 1.

Example: `0.8`

</td>
</tr>
<tr>
<td valign="top">

*Timestamp Granularities*

</td>
<td valign="top">

Specify comma-separated values to timestamp output at the segment, word level, or both.

</td>
</tr>
<tr>
<td valign="top">

*Speed*

</td>
<td valign="top">

Specify the speed of the generated audio.

</td>
</tr>
<tr>
<td valign="top">

*Size*

</td>
<td valign="top">

Select the image size from the dropdown.

</td>
</tr>
<tr>
<td valign="top">

*User*

</td>
<td valign="top">

Specify the unique identifier representing your end-user.

Example: `user_9121`

</td>
</tr>
<tr>
<td valign="top">

*Purpose*

</td>
<td valign="top">

Select a value from the dropdown to indicate the purpose of the uploaded file.

</td>
</tr>
<tr>
<td valign="top">

*Operation Parameters*

</td>
<td valign="top">

Specify the *Name* and *Value* in case the resource path includes parameters.

Example: Set *Name* as `propertyKey` and *Value* as `76548`

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

</td>
<td valign="top">

Select the required HTTP method from the available dropdown.

</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

</td>
<td valign="top">

Specify the endpoint path, excluding the Host.

Example: `/v1/files/file-abc123/content`

</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the query that should be transferred with the HTTP request.

Example: `param1=value1&param2=value2`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
</table>

