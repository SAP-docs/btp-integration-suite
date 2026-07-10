<!-- loioae419b62dafb4b1ba28e82bfe134da27 -->

# Specifying Service Instance and Service Key Parameters in JSON Format



<a name="loioae419b62dafb4b1ba28e82bfe134da27__section_opz_cn5_1tb"/>

## Service Instance Parameters in JSON Format \(Examples\)

In this example \(for *integration-flow* plan\), role `ESBMessaging.send` and `Client Credentials` grant type is used.

> ### Sample Code:  
> ```
> {
> 	"grant-types":[
> 		"client_credentials"
> 	],
> 	"redirect-uris":[
> 		
> 	],
> 	"roles":[
> 		"ESBMessaging.send"
> 	]
> }
> ```

When you have defined custom roles to protect integration flow endpoints individually, you can also specify multiple roles separated by a comma.

Example:

> ### Sample Code:  
> ```
> {
> 	"grant-types":[
> 		"client_credentials"
> 	],
> 	"redirect-uris":[
> 		
> 	],
> 	"roles":[
> 		"ESBMessaging.send",
> 		"myRole1",
> 		"myRole2"
> 	]
> }
> 
> ```

In this example \(for *api* plan\), role `MonitoringDataRead` and `Client Credentials` grant type is used.

With this role assignment, the API client can access message processing logs on the tenant using the `MessageProcessingLogs` entity.

> ### Sample Code:  
> ```
> {
>     "roles":[
>         "MonitoringDataRead"
>     ],
>     "grant-types":[
>         "client_credentials"
>     ]
> }
> ```

You can also specify a list of multiple roles, for example:

> ### Sample Code:  
> ```
> {
>     "roles":[
>         "MonitoringDataRead",
>         "WorkspaceArtifactsDeploy"
>     ],
>     "grant-types":[
>         "client_credentials"
>     ]
> }
> ```



<a name="loioae419b62dafb4b1ba28e82bfe134da27__section_mqf_2n5_1tb"/>

## Service Key Parameters in JSON Format \(Examples\)

This example shows the JSON content for *Certificate* key type:

> ### Sample Code:  
> ```
> {
> "key-type": "certificate",
> "validity": 365,
> "key-length": 2048
> }
> ```

This example shows the JSON content for *External Certificate* key type:

> ### Sample Code:  
> ```
> {
>     "key-type": "certificate_external",
>     "X.509": "-----BEGIN CERTIFICATE-----MIIHyDCCBrCgAwIB[...]CAq8Tn7kSFDmVnrXe6v8hcQ==-----END CERTIFICATE",
>     "validity": 365,
>     "key-length": 2048
> }
> ```

In this example, the value for the *X.509* parameter is the PEM-encoded certificate to be provided with this service key.

