<!-- loio1d93850b43504c50b87c6c62ef0ffc5a -->

# Configure the Slack Sender Adapter

Enables SAP Integration Suite to receive search-related information from the Slack storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a sender channel and selected the Slack sender adapter, you can configure the following attributes.

Select the *General* tab to access the following parameters.

**General**


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

*Name* 

</td>
<td valign="top">

Enter the name of the Slack channel.

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

Shows *Slack* as adapter type.

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

Shows *HTTPS* as transport protocol.

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

Shows *REST* as message protocol.

</td>
</tr>
</table>

You can provide more information in the *Description* field.

Select the *Connection* tab and provide values in the fields as follows.

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

*App Token Alias* 

</td>
<td valign="top">

Name of the *Secure Parameter* artifact that contains the app token credentials.

See: [Deploying a Secure Parameter Artifact](deploying-a-secure-parameter-artifact-4641d6c.md)

</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

There is no explicit support for response format in Slack Sender. By default, the value is JSON.

</td>
</tr>
</table>

