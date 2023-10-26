<!-- loio3db463e24d9547a5bcc0a7d22d5e8b1a -->

# Runtime Artifacts and Error Information Example Requests



<a name="loio3db463e24d9547a5bcc0a7d22d5e8b1a__section_wws_3k5_r4b"/>

## Get Runtime Artifacts in Status Error

Perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

/IntegrationRuntimeArtifacts?$filter=Status eq 'ERROR'

</td>
</tr>
</table>

To get all integration artifacts in status `ERROR`, send the following GET request:

`https://<host address>/api/v1/IntegrationRuntimeArtifacts?$filter=Status eq 'ERROR'`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

To get error information related to the integration artifact with Id `Mail_Sender_Integration_Flow`, send the following GET request:

`https://<host address>/api/v1/IntegrationRuntimeArtifacts('Mail_Sender_Integration_Flow')/ErrorInformation`

You get the following response:

```
<entry ...>
    <id>https:<host address>/api/v1/RuntimeArtifactErrorInformations('Mail_Sender_Integration_Flow')</id>
    <title type="text">RuntimeArtifactErrorInformations</title>
    <updated>2021-03-18T11:19:04.598Z</updated>
    <category term="com.sap.hci.api.RuntimeArtifactErrorInformation" scheme="http://schemas.microsoft.com/ado/2007/08/dataservices/scheme"/>
    <link href="RuntimeArtifactErrorInformations('Mail_Sender_Integration_Flow')" rel="edit" title="RuntimeArtifactErrorInformation"/>
    <link href="RuntimeArtifactErrorInformations('Mail_Sender_Integration_Flow')/$value" rel="edit-media" type="application/octet-stream"/>
    <content type="application/octet-stream" src="RuntimeArtifactErrorInformations('Mail_Sender_Integration_Flow')/$value"/>
    <m:properties>
        <d:Id>Mail_Sender_Integration_Flow</d:Id>
    </m:properties>
</entry>
```

To get the error information in JSON format \(for this example\), send the following GET request:

`https://<host address>/api/v1/IntegrationRuntimeArtifacts('<artifact name>')/ErrorInformation/$value`

