<!-- loiod1c7bfe00b7c448ab56d7b4d454475f9 -->

# Auditing and Logging Information for Cloud Integration

Here you can find a list of the security events that are logged by Cloud Integration.



**Security Events Written in Audit Logs**


<table>
<tr>
<th valign="top">

Event grouping

</th>
<th valign="top">

What events are logged

</th>
<th valign="top">

How to identify related log events

</th>
<th valign="top">

Additional information

</th>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Import integration package manually

</td>
<td valign="top">

-   action: Package\_Import\_Started/Package\_Import\_Completed

-   objectType: Package


Example:

When importing a package manually, the following events are written:

> ### Output Code:  
> ```
> "{"action":"Package_Import_Started","objectType":"Package",
> "objectId":"new package.zip","attributes":{},"changedAttributes":{}}" 
> on 2021-06-21T11:02:00.190Z. Security event was related to user "SAP".
> ```

> ### Output Code:  
> ```
> "{"action":"Package_Import_Completed","objectType":"Package",
> "objectId":"new package.zip","attributes":{},"changedAttributes":{}}" 
> on 2021-06-21T11:02:01.367Z. Security event was related to user "SAP".
> ```



</td>
<td valign="top">

[Working with Integration Packages](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/45423ba590094233a4c82f94390df096.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Transport integration package

</td>
<td valign="top">

-   action: Package\_Transport\_Started/Package\_Transport\_Completed

-   objectType: Package




</td>
<td valign="top">

[Content Transport](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e3c79d65aa604b80992e20609881ad7a.html "Reuse content across multiple tenants. Export integration content from one (source) tenant and import it on another (target) tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Transport integration artifact

</td>
<td valign="top">

-   action: Artifact\_Transport\_Started/Artifact\_Transport\_Completed

-   objectType: <depends on artifact type\>




</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Create integration artifact

</td>
<td valign="top">

-   action: Creation\_of\_Artifact\_Initiated/Creation\_of\_Artifact\_Completed

-   objectType: <depends on artifact type\>


Example:

When creating an integration flow, the `objectType` parameter is `IntegrationFlow`, and the following events are written:

> ### Output Code:  
> ```
> "{"action":"Creation_of_Artifact_Initiated","objectType":"IntegrationFlow",
> "objectId":"My_Flow","attributes":{},"changedAttributes":{}}" on 2021-06-21T11:06:51.751Z. 
> Security event was related to user "SAP".
> ```

> ### Output Code:  
> ```
> "{"action":"Creation_of_Artifact_Completed","objectType":"IntegrationFlow",
> "objectId":"My_Flow","attributes":{},"changedAttributes":{}}" on 2021-06-21T11:06:51.819Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

Covers the following kinds of integration artifacts: integration flow, value mapping, OData API, SOAP API, REST API, integration adapter.

[Creating an Integration Flow](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/da53d93cd8fb47ff9ea55b6b278cd85e.html "Add an integration flow to an integration package.") :arrow_upper_right:

[Developing an OData API Project](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d961654cd36b46ad83b668e4434c9f04.html "") :arrow_upper_right:

[Working with Script and Script Collection](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e60f7061fe4b45d69d028b24d5a76901.html "Cloud Integration lets you create and upload scripts, assemble them into script collection artifacts, and reuse them across different integration artifacts.") :arrow_upper_right:

[Creating Message Mapping as an Artifact](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1d52a7ba8c71438d90f3ea0d8e13a052.html "Helps you to reuse message mapping resources in different integration scenarios by directly accessing the mapping artifacts.") :arrow_upper_right:

[Develop API-Based Integration Artifacts](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/997501da152d419d96c92f7bfbd7b6f3.html "Develop REST, SOAP, and OData API-based integration scenarios, deploy, and manage your artifacts in one place.") :arrow_upper_right:

[Developing Custom Adapters](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7392cc44de7c4450a65b8cd8f1042420.html "Develop adapters tailored for your specific requirements.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Update integration artifact

</td>
<td valign="top">

-   action: Update\_of\_Artifact\_Initiated/Update\_of\_Artifact\_Completed

-   objectType: <depends on artifact type\>


Example:

When updating a value mapping, the `objectType` parameter is `ValueMapping`, and following events are written:

> ### Output Code:  
> ```
> "{"action":"Update_of_Artifact_Initiated","objectType":"ValueMapping",
> "objectId":"testvm","attributes":{},"changedAttributes":{}}" on 2021-06-25T13:58:23.615Z. 
> Security event was related to user "SAP".
> ```

> ### Output Code:  
> ```
> "{"action":"Update_of_Artifact_Completed","objectType":"ValueMapping",
> "objectId":"testvm","attributes":{},"changedAttributes":{}}" on 2021-06-25T13:58:23.709Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

Covers the following kinds of integration artifacts: integration flow, value mapping, OData API, SOAP API, REST API, integration adapter.

[Creating an Integration Flow](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/da53d93cd8fb47ff9ea55b6b278cd85e.html "Add an integration flow to an integration package.") :arrow_upper_right:

[Developing an OData API Project](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d961654cd36b46ad83b668e4434c9f04.html "") :arrow_upper_right:

[Working with Script and Script Collection](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e60f7061fe4b45d69d028b24d5a76901.html "Cloud Integration lets you create and upload scripts, assemble them into script collection artifacts, and reuse them across different integration artifacts.") :arrow_upper_right:

[Creating Message Mapping as an Artifact](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1d52a7ba8c71438d90f3ea0d8e13a052.html "Helps you to reuse message mapping resources in different integration scenarios by directly accessing the mapping artifacts.") :arrow_upper_right:

[Develop API-Based Integration Artifacts](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/997501da152d419d96c92f7bfbd7b6f3.html "Develop REST, SOAP, and OData API-based integration scenarios, deploy, and manage your artifacts in one place.") :arrow_upper_right:

[Developing Custom Adapters](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7392cc44de7c4450a65b8cd8f1042420.html "Develop adapters tailored for your specific requirements.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Update integration artifact as version

</td>
<td valign="top">

-   action: Update\_of\_Version\_Initiated/Update\_of\_Version\_Completed

-   objectType: <depends on artifact type\>




</td>
<td valign="top">

Covers the following kinds of integration artifacts: integration flow, value mapping, OData API, SOAP API, REST API, integration adapter.

[Creating an Integration Flow](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/da53d93cd8fb47ff9ea55b6b278cd85e.html "Add an integration flow to an integration package.") :arrow_upper_right:

[Developing an OData API Project](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d961654cd36b46ad83b668e4434c9f04.html "") :arrow_upper_right:

[Working with Script and Script Collection](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e60f7061fe4b45d69d028b24d5a76901.html "Cloud Integration lets you create and upload scripts, assemble them into script collection artifacts, and reuse them across different integration artifacts.") :arrow_upper_right:

[Creating Message Mapping as an Artifact](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1d52a7ba8c71438d90f3ea0d8e13a052.html "Helps you to reuse message mapping resources in different integration scenarios by directly accessing the mapping artifacts.") :arrow_upper_right:

[Develop API-Based Integration Artifacts](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/997501da152d419d96c92f7bfbd7b6f3.html "Develop REST, SOAP, and OData API-based integration scenarios, deploy, and manage your artifacts in one place.") :arrow_upper_right:

[Developing Custom Adapters](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7392cc44de7c4450a65b8cd8f1042420.html "Develop adapters tailored for your specific requirements.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Update integration flow configuration

</td>
<td valign="top">

-   action: Update\_of\_Configuration\_Initiated/Update\_of\_Configuration\_Completed

-   objectType: <depends on artifact type\>




</td>
<td valign="top">

[Configure Externalized Parameters of an Integration Flow](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/462a4782db7b485b94ffce5b6fe22c31.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Deploy integration artifact

</td>
<td valign="top">

-   action: Deploy\_of\_Artifact\_Initiated/Deploy\_of\_Artifact\_Completed

-   objectType: <depends on artifact type\>




</td>
<td valign="top">

Covers the following kinds of integration artifacts: integration flow, value mapping, OData API, SOAP API, REST API, integration adapter.

[Creating an Integration Flow](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/da53d93cd8fb47ff9ea55b6b278cd85e.html "Add an integration flow to an integration package.") :arrow_upper_right:

[Developing an OData API Project](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d961654cd36b46ad83b668e4434c9f04.html "") :arrow_upper_right:

[Working with Script and Script Collection](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e60f7061fe4b45d69d028b24d5a76901.html "Cloud Integration lets you create and upload scripts, assemble them into script collection artifacts, and reuse them across different integration artifacts.") :arrow_upper_right:

[Creating Message Mapping as an Artifact](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1d52a7ba8c71438d90f3ea0d8e13a052.html "Helps you to reuse message mapping resources in different integration scenarios by directly accessing the mapping artifacts.") :arrow_upper_right:

[Develop API-Based Integration Artifacts](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/997501da152d419d96c92f7bfbd7b6f3.html "Develop REST, SOAP, and OData API-based integration scenarios, deploy, and manage your artifacts in one place.") :arrow_upper_right:

[Developing Custom Adapters](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7392cc44de7c4450a65b8cd8f1042420.html "Develop adapters tailored for your specific requirements.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Deploy integration artifact \(mass deployment\)

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Delete integration artifact

</td>
<td valign="top">

-   action: Deletion\_of\_Artifact\_Initiated/Deletion\_of\_Artifact\_Completed

-   objectType: <depends on artifact type\>




</td>
<td valign="top">

Covers the following kinds of integration artifacts: integration flow, value mapping, OData API, SOAP API, REST API, integration adapter.

[Creating an Integration Flow](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/da53d93cd8fb47ff9ea55b6b278cd85e.html "Add an integration flow to an integration package.") :arrow_upper_right:

[Developing an OData API Project](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/d961654cd36b46ad83b668e4434c9f04.html "") :arrow_upper_right:

[Working with Script and Script Collection](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/e60f7061fe4b45d69d028b24d5a76901.html "Cloud Integration lets you create and upload scripts, assemble them into script collection artifacts, and reuse them across different integration artifacts.") :arrow_upper_right:

[Creating Message Mapping as an Artifact](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/1d52a7ba8c71438d90f3ea0d8e13a052.html "Helps you to reuse message mapping resources in different integration scenarios by directly accessing the mapping artifacts.") :arrow_upper_right:

[Develop API-Based Integration Artifacts](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/997501da152d419d96c92f7bfbd7b6f3.html "Develop REST, SOAP, and OData API-based integration scenarios, deploy, and manage your artifacts in one place.") :arrow_upper_right:

[Developing Custom Adapters](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7392cc44de7c4450a65b8cd8f1042420.html "Develop adapters tailored for your specific requirements.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Integration design

</td>
<td valign="top">

Download WSDL

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Partner Directory

</td>
<td valign="top">

Read Partner Directory entity

</td>
<td valign="top">

-   action: Read

-   objectType: <depends on Partner Directory entity type\>




</td>
<td valign="top">

[Parameterizing Integration Flows Using the Partner Directory](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b7812a546ab14de6aa0a7c919d8272bb.html "The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Partner Directory

</td>
<td valign="top">

Create Partner Directory entity

</td>
<td valign="top">

-   action: Create

-   objectType: <depends on Partner Directory entity type\>


Example:

Creation of an alternative partner writes the following log event:

> ### Output Code:  
> ```
> "{"action":"Create","objectType":"PD Alternative Partner","objectId":"Agency\u003dAgency;Id\u003dAlternativeID1;Scheme\u003dScheme",
> "attributes":{"Pid":"ID1"},"changedAttributes":{}}" on 2021-06-29T15:00:58.948Z. ..."
> ```



</td>
<td valign="top">

[Parameterizing Integration Flows Using the Partner Directory](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b7812a546ab14de6aa0a7c919d8272bb.html "The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Partner Directory

</td>
<td valign="top">

Update Partner Directory entity

</td>
<td valign="top">

-   action: Change

-   objectType: <depends on Partner Directory entity type\>




</td>
<td valign="top">

[Parameterizing Integration Flows Using the Partner Directory](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b7812a546ab14de6aa0a7c919d8272bb.html "The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Partner Directory

</td>
<td valign="top">

Delete Partner Directory entity

</td>
<td valign="top">

-   action: Delete

-   objectType: <depends on Partner Directory entity type\>


Example:

Deletion of an authorized user writes the following log event:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"PD Authorized User","objectId":"..."",
> "attributes":{},"changedAttributes":{}}" on 2021-06-29T15:00:56.218Z. ..."
> ```



</td>
<td valign="top">

[Parameterizing Integration Flows Using the Partner Directory](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b7812a546ab14de6aa0a7c919d8272bb.html "The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Create keystore entry

</td>
<td valign="top">

-   action: Create

-   objectType: <depends on keystore entry type\>


Example:

When creating an X.509 key pair, the `objectType` parameter is `X.509 Key-Pair`, and the following event is written:

> ### Output Code:  
> ```
> "{"action":"Create","objectType":"X.509 Key-Pair","objectId":"keypair",
> "attributes":{"Subject CN":"mydepartment.com","Issuer CN":"mydepartment.com",
> "Serial Number":"12345678"},"changedAttributes":{}}" on 2021-06-09T10:33:41.421Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

Covers the following kinds of keystore entry: X.509 or SSH key pair, X.509 or SSH key pair.

When restoring a certificate in the *Backup* keystore:

-   action: Create

-   objectType: Backup X.509 Certificate


More information on the keystore:

[Managing Keystore Entries](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/2dc8942e02de4be59bd2afaa3bfdc591.html "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Update keystore entry by uploading a new file

</td>
<td valign="top">

-   action: Create

-   objectType: <depends on keystore entry type\>


Example:

When uploading an X.509 Certificate, the `objectType` parameter is `X.509 Certificate`, and the following event is written:

> ### Output Code:  
> ```
> "{"action":"Create","objectType":"X.509 Certificate","objectId":"mycertificate1",
>                                         "attributes":{"Issuer CN":"OU\u003dSender,C\u003dDE","Subject CN":"OU\u003dSender,C\u003dDE",
>                                         "Serial Number":"6818011987146590924"},"changedAttributes":{}}" on 2021-06-25T17:30:19.687Z. 
>                                         Security event was related to user "SAP".
> ```



</td>
<td valign="top">

Covers the following kinds of keystore entry: X.509 or SSH key pair, X.509, or SSH key pair.

More information on the keystore:

[Managing Keystore Entries](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/2dc8942e02de4be59bd2afaa3bfdc591.html "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Export PGP Keyring

</td>
<td valign="top">

-   action: Read

-   objectType: Public Keyring or Secret Keyring


Exporting PGP public keyring example:

> ### Output Code:  
> ```
> {action=Read, objType=Public Keyring | Secret Keyring, nodeType="Keymanagement Subsystem", isCustomerVisible=true, objName=pubring | secring }
> ```



</td>
<td valign="top">

Covers the following kinds of keystore entry: X.509 or SSH key pair, X.509, or SSH key pair.

More information on the keystore:

[Managing Keystore Entries](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/2dc8942e02de4be59bd2afaa3bfdc591.html "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Download PGP Key

</td>
<td valign="top">

-   action: Read
-   objectType: Public Keyring or Secret Keyring
-   objName: 3A7A899C3435D45C

Example:

Download a specific PGP public key entry output code:

> ### Output Code:  
> ```
> {action=Read, objType=PGP Public Key | PGP Secret Key, nodeType="Keymanagement Subsystem", isCustomerVisible=true, objName=3A7A899C3435D45C}
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Import PGP Key\(s\)

</td>
<td valign="top">

-   action: Change
-   objectType: Public Keyring or Secret Keyring
-   objName: 3A7A899C3435D45C, 2DDE8A220E3D26B4

Example:

Import a PGP Public Keyring output code:

> ### Output Code:  
> ```
> {action=Change, objType=PGP Public Keys | PGP Secret Keys, nodeType="Keymanagement Subsystem", isCustomerVisible=true, objName=3A7A899C3435D45C, 2DDE8A220E3D26B4}
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Delete PGP Key

</td>
<td valign="top">

-   action: Delete
-   objectType: Public Keyring or Secret Keyring
-   objName: 3A7A899C3435D45C

Example:

Deleting a PGP Public Key entry output code:

> ### Output Code:  
> ```
> {action=Delete, objType=PGP Public Key | PGP Secret Key, nodeType="Keymanagement Subsystem", isCustomerVisible=true, objName=3A7A899C3435D45C}
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Rename alias of keystore entry

</td>
<td valign="top">

-   action: Delete/Create

-   objectType: <depends on keystore entry type\>


Example:

Renaming the alias of a certificate from `mycertificate` to `mycertificate1` provides 2 log entries:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"X.509 Certificate","objectId":"mycertificate",
> "attributes":{"Issuer CN":"OU\u003dSender,C\u003dDE","Subject CN":"OU\u003dSender,C\u003dDE",
> "Serial Number":"6818011987146590924"},"changedAttributes":{}}" on 2021-06-09T10:42:36.882Z. 
> Security event was related to user "SAP".
> ```

> ### Output Code:  
> ```
> "{"action":"Create","objectType":"X.509 Certificate","objectId":"mycertificate1",
> "attributes":{"Issuer CN":"OU\u003dSender,C\u003dDE","Subject CN":"OU\u003dSender,C\u003dDE",
> "Serial Number":"6818011987146590924"},"changedAttributes":{}}" on 2021-06-09T10:42:36.847Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

Covers the following kinds of keystore entry: X.509 or SSH key pair, X.509 key pair, or SSH key pair.

More information on the keystore:

[Managing Keystore Entries](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/2dc8942e02de4be59bd2afaa3bfdc591.html "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Delete keystore entry

</td>
<td valign="top">

-   action: Delete

-   objectType: <depends on keystore entry type\>




</td>
<td valign="top">

Covers the following kinds of keystore entry: X.509 or SSH key pair, X.509 key pair, or SSH key pair.

More information on the keystore:

[Managing Keystore Entries](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/2dc8942e02de4be59bd2afaa3bfdc591.html "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Create security material

</td>
<td valign="top">

-   action: PasswordStore

-   objectType: Credential




</td>
<td valign="top">

Covers the following kinds of artifact: User Credentials, OAuth2 Client Credentials, OAuth2 SAML Bearer Assertion, OAuth2 Authorization Code, Secure Parameter.

[Managing Security Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b8ccb53b9ec44652b885476f02184a0f.html "The Manage Security Material area provides an overview of security-related artifacts.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Update security material

</td>
<td valign="top">

-   action: PasswordStore

-   objectType: Credential




</td>
<td valign="top">

Covers the following kinds of artifact: User Credentials, OAuth2 Client Credentials, OAuth2 SAML Bearer Assertion, OAuth2 Authorization Code, Secure Parameter.

[Managing Security Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b8ccb53b9ec44652b885476f02184a0f.html "The Manage Security Material area provides an overview of security-related artifacts.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Delete security material

</td>
<td valign="top">

-   action: PasswordDelete

-   objectType: Credential




</td>
<td valign="top">

Covers the following kinds of artifact: User Credentials, OAuth2 Client Credentials, OAuth2 SAML Bearer Assertion, OAuth2 Authorization Code, Secure Parameter.

[Managing Security Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b8ccb53b9ec44652b885476f02184a0f.html "The Manage Security Material area provides an overview of security-related artifacts.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Upload security material

</td>
<td valign="top">

-   action: PasswordStore

-   objectType: Security Material




</td>
<td valign="top">

Covers the following kinds of artifact: known hosts, PGP public keyring, PGP secret keyring.

[Managing Security Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b8ccb53b9ec44652b885476f02184a0f.html "The Manage Security Material area provides an overview of security-related artifacts.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Undeploy security material

</td>
<td valign="top">

-   action: PasswordDelete

-   objectType: Security Material


Example:

During the undeployment of a PGP secret keyring, the following event is written:

> ### Output Code:  
> ```
> "{"action":"PasswordDelete","objectType":"Security Material","objectId":"secring",
> "attributes":{},"changedAttributes":{}}" on 2021-06-25T17:50:35.701Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

Covers the following kinds of artifact: known hosts, PGP public keyring, PGP secret keyring.

[Managing Security Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b8ccb53b9ec44652b885476f02184a0f.html "The Manage Security Material area provides an overview of security-related artifacts.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Download security material

</td>
<td valign="top">

-   action: Read

-   objectType: Security Material


Example:

For the download of a known hosts file, the following event is written:

> ### Output Code:  
> ```
> "{"action":"Read","objectType":"Security Material","objectId":"known.hosts",
> "attributes":{},"changedAttributes":{}}" on 2021-06-25T17:53:16.589Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

Covers the following kinds of artifact: known hosts, PGP public keyring, PGP secret keyring.

[Managing Security Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/b8ccb53b9ec44652b885476f02184a0f.html "The Manage Security Material area provides an overview of security-related artifacts.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Create access policy

</td>
<td valign="top">

-   action: Create

-   objectType: Access Policy


Example:

For the creation of an access policy, the following event is written:

> ### Output Code:  
> ```
> "{"action":"Create","objectType":"Access Policy","objectId":"101:DemoIntegrationFlows",
> "attributes":{"message":"Successfully created access policy!"},"changedAttributes":{}}" on 2021-06-25T17:57:36.580Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

[Creating Custom Roles for Access Policies](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7db3c87f6c744016b7eed9838912e123.html "Define a custom role to be associated with an access policy.") :arrow_upper_right:

[Creating Custom Roles for Access Policies, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/18f06d4c8c5244d8927c0e2c5dc1c706.html "Create custom roles to define access policies in the Neo environment.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Update access policy

</td>
<td valign="top">

-   action: Change

-   objectType: Access Policy


Example:

For the update of an access policy, the following event is written:

> ### Output Code:  
> ```
> "{"action":"Change","objectType":"Access Policy","objectId":"101:DemoIntegrationFlows_Changed",
> "attributes":{},"changedAttributes":{"message":{"oldValue":"Successfully updated access policy!",
> "newValue":"Successfully updated access policy!"}}}" on 2021-06-25T17:58:50.146Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

[Creating Custom Roles for Access Policies](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7db3c87f6c744016b7eed9838912e123.html "Define a custom role to be associated with an access policy.") :arrow_upper_right:

[Creating Custom Roles for Access Policies, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/18f06d4c8c5244d8927c0e2c5dc1c706.html "Create custom roles to define access policies in the Neo environment.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Delete access policy

</td>
<td valign="top">

-   action: Delete

-   objectType: Access Policy


Example:

If you delete an access policy that includes artifact references, 2 logs are written, 1 for the artifact references and 1 for the access policy object:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Artifact Reference","objectId":"1:my second integration flow",
> "attributes":{"ConditionAttribute_1":"Name","ConditionType_1":"regularExpression","ConditionValue_1":
> "My First Integration Flow","Type_1":"INTEGRATION_FLOW","message":"Successfully deleted artifact references!"},
> "changedAttributes":{}}" on 2021-06-25T18:00:17.523Z. Security event was related to user "SAP".
> ```

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Access Policy","objectId":"51:my second role",
> "attributes":{"message":"Successfully deleted access policy!"},"changedAttributes":{}}" 
> on 2021-06-25T18:00:17.462Z. Security event was related to user "SAP".
> ```



</td>
<td valign="top">

[Creating Custom Roles for Access Policies](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7db3c87f6c744016b7eed9838912e123.html "Define a custom role to be associated with an access policy.") :arrow_upper_right:

[Creating Custom Roles for Access Policies, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/18f06d4c8c5244d8927c0e2c5dc1c706.html "Create custom roles to define access policies in the Neo environment.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Create artifact reference \(for access policy\)

</td>
<td valign="top">

-   action: Create

-   objectType: Artifact Reference


Example:

For the creation of an artifact reference of an access policy, the following event is written:

> ### Output Code:  
> ```
> "{"action":"Create","objectType":"Artifact Reference","objectId":"51:MyFirstIntegrationFlow",
> "attributes":{"ConditionValue":"MyFirstIntegrationFlow","ConditionType":"exactString","ConditionAttribute":"Name",
> "message":"Successfully created artifact references!"},"changedAttributes":{}}" on 2021-06-25T18:03:41.819Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

[Creating Custom Roles for Access Policies](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7db3c87f6c744016b7eed9838912e123.html "Define a custom role to be associated with an access policy.") :arrow_upper_right:

[Creating Custom Roles for Access Policies, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/18f06d4c8c5244d8927c0e2c5dc1c706.html "Create custom roles to define access policies in the Neo environment.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Update artifact reference \(for access policy\)

</td>
<td valign="top">

-   action: Change

-   objectType: Artifact Reference


Example:

For the update of an artifact reference of an access policy, the following event is written:

> ### Output Code:  
> ```
> "{"action":"Change","objectType":"Artifact Reference","objectId":"51:MyFirstIntegrationFlow_Changed",
> "attributes":{"Type_51":"INTEGRATION_FLOW"},"changedAttributes":{"ConditionValue_51":{"oldValue":"MyFirstIntegrationFlow",
> "newValue":"MySecondIntegrationFlow"},"ConditionType_51":{"oldValue":"exactString","newValue":"exactString"},"message":
> {"oldValue":"Successfully updated artifact references!","newValue":"Successfully updated artifact references!"},
> "ConditionAttribute_51":{"oldValue":"Name","newValue":"Name"}}}" on 2021-06-25T18:05:20.279Z. 
> Security event was related to user "SAP".
> ```



</td>
<td valign="top">

[Creating Custom Roles for Access Policies](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7db3c87f6c744016b7eed9838912e123.html "Define a custom role to be associated with an access policy.") :arrow_upper_right:

[Creating Custom Roles for Access Policies, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/18f06d4c8c5244d8927c0e2c5dc1c706.html "Create custom roles to define access policies in the Neo environment.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Delete artifact reference \(for access policy\)

</td>
<td valign="top">

-   action: Delete

-   objectType: Artifact Reference




</td>
<td valign="top">

[Creating Custom Roles for Access Policies](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/7db3c87f6c744016b7eed9838912e123.html "Define a custom role to be associated with an access policy.") :arrow_upper_right:

[Creating Custom Roles for Access Policies, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/18f06d4c8c5244d8927c0e2c5dc1c706.html "Create custom roles to define access policies in the Neo environment.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Deploy JDBC material

</td>
<td valign="top">

-   action: PasswordStore

-   objectType: Data Source


Example:

For the deployment of JDBC material, the following event is written:

> ### Output Code:  
> ```
> "{"action":"PasswordStore","objectType":"Data Source","objectId":"jdbc01","attributes":{},
> "changedAttributes":{}}" on 2021-06-25T18:09:10.084Z. Security event was related to user "SAP".
> ```



</td>
<td valign="top">

[Managing JDBC Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/32ee7cdff9e3492fa755338cadff14eb.html "Learn how JDBC Materials supports SAP Integration Suite for interacting with your database server.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Undeploy JDBC material

</td>
<td valign="top">

-   action: PasswordDelete

-   objectType: Data Source




</td>
<td valign="top">

[Managing JDBC Material](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/32ee7cdff9e3492fa755338cadff14eb.html "Learn how JDBC Materials supports SAP Integration Suite for interacting with your database server.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Create user role \(only Cloud Foundry\)

</td>
<td valign="top">

\(tbd\)

</td>
<td valign="top">

[Managing User Roles](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/4e86f0dcb41f49e99ea43e82a0e99c73.html "The user role monitor allows a tenant administrator to manage user roles which then can be used during inbound authorization of an integration flow execution.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Update user role \(only Cloud Foundry\)

</td>
<td valign="top">

\(tbd\)

</td>
<td valign="top">

[Managing User Roles](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/4e86f0dcb41f49e99ea43e82a0e99c73.html "The user role monitor allows a tenant administrator to manage user roles which then can be used during inbound authorization of an integration flow execution.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage security

</td>
<td valign="top">

Delete user role \(only Cloud Foundry\)

</td>
<td valign="top">

\(tbd\)

</td>
<td valign="top">

[Managing User Roles](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/4e86f0dcb41f49e99ea43e82a0e99c73.html "The user role monitor allows a tenant administrator to manage user roles which then can be used during inbound authorization of an integration flow execution.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Download data store entry

</td>
<td valign="top">

-   action: Read

-   objectType: Message


Example:

Downloading data store entry `HT-1037` of global data store `Products` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Read","objectType":"Message","objectId":"Products/GLOBAL/HT-1037",
> "attributes":{"storeName":"Products","id":"HT-1037"},"changedAttributes":{}}" 
> on 2021-06-29T15:28:47.695Z. 
> ```



</td>
<td valign="top">

[Managing Data Stores](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ac39f1d1bd2f427c97b3694e54370bda.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete data store entry

</td>
<td valign="top">

-   action: Delete

-   objectType: Message


Example:

Deletion of data store entry `126` of global data store `CustomerReviews` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Message","objectId":"CustomerReviews/GLOBAL/126",
> "attributes":{"ids":"[126]","storeName":"CustomerReviews","id":"126"},"changedAttributes":{}}" 
> on 2021-06-29T15:22:30.135Z.
> ```



</td>
<td valign="top">

[Managing Data Stores](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ac39f1d1bd2f427c97b3694e54370bda.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete data store

</td>
<td valign="top">

-   action: Delete

-   objectType: Message


Example:

Deletion of global data store `CustomerReviews` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Message","objectId":"CustomerReviews/GLOBAL/ALL",
> "attributes":{"storeName":"CustomerReviews"},"changedAttributes":{}}" on 2021-06-29T15:26:34.345Z. 
> ```



</td>
<td valign="top">

[Managing Data Stores](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ac39f1d1bd2f427c97b3694e54370bda.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Download variable

</td>
<td valign="top">

-   action: Read

-   objectType: Message


Example:

Download of global variable `timestamp` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Read","objectType":"Message","objectId":"sap_global_store/GLOBAL/timestamp",
> "attributes":{"storeName":"sap_global_store","id":"timestamp"},"changedAttributes":{}}" on 2021-06-30T09:53:31.226Z. 
> ```

Example:

Download of local variable `ProductId` \(related to integration flow `Write_Product_ID` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Read","objectType":"Message","objectId":"sap_global_store/Write_Product_ID/ProductId",
> "attributes":{"qualifier":"Write_Product_ID","storeName":"sap_global_store","id":"ProductId"},"changedAttributes":{}}" 
> on 2021-06-30T10:04:51.569Z. 
> ```



</td>
<td valign="top">

[Managing Variables](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ca93653ec211457190ff8466e42ff9cd.html "The Variables view allows you to monitor variables used in integration flows.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete variable

</td>
<td valign="top">

-   action: Delete

-   objectType: Variable


Example:

Deletion of global variable `timestamp` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Variable","objectId":"sap_global_store/GLOBAL/timestamp",
> "attributes":{"ids":"[timestamp]","storeName":"sap_global_store","id":"timestamp"},"changedAttributes":{}}" 
> on 2021-06-30T09:56:48.985Z. 
> ```

Example:

Deletion of local variable `ProductId` \(related to integration flow `Write_Product_ID` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Variable","objectId":"sap_global_store/Write_Product_ID/ProductId",
> "attributes":{"qualifier":"Write_Product_ID","ids":"[ProductId]","storeName":"sap_global_store","id":"ProductId"},
> "changedAttributes":{}}" on 2021-06-30T10:08:27.385Z. 
> ```



</td>
<td valign="top">

[Managing Variables](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ca93653ec211457190ff8466e42ff9cd.html "The Variables view allows you to monitor variables used in integration flows.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Move messages to another queue

</td>
<td valign="top">

-   action: Move

-   objectType: Message Queue




</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete message queue

</td>
<td valign="top">

-   action: Delete

-   objectType: Message Queue


Example:

Deletion of message queue `MyQueue` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Message Queue","objectId":"MyQueue",
> "attributes":{},"changedAttributes":{}}" on 2021-06-30T10:26:08.601Z. 
> ```



</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete message from message queue

</td>
<td valign="top">

-   action: Delete

-   objectType: Message


Example:

Deletion of a message from message queue `MyQueue` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Delete","objectType":"Message","objectId":"ID:12345-abcde",
> "attributes":{"Queue":"MyQueue"},"changedAttributes":{}}" on 2021-06-30T10:49:47.974Z. 
> ```



</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Download message from message queue

</td>
<td valign="top">

-   action: Read

-   objectType: Message


Example:

Downloading a message from message queue `MyQueue` writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Read","objectType":"Message","objectId":"ID:12345-abcde",
> "attributes":{"Queue":"MyQueue"},"changedAttributes":{}}" on 2021-06-30T10:49:40.913Z.
> ```



</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Retry message from message queue

</td>
<td valign="top">

-   action: Retry

-   objectType: Message




</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Message monitoring

</td>
<td valign="top">

Read / download message payload / header when monitoring integration flow with Trace log level

</td>
<td valign="top">

-   action: Read

-   objectType: Message Payload \(Trace\)


Example:

Reading the message payload writes the following audit log event:

> ### Output Code:  
> ```
> "{"action":"Read","objectType":"Message Payload (Trace)",
> "objectId":"mplId\1234-xyz;traceId\abcd;stepId\u003dEndEvent_2; 
> Odata-Read","attributes":{"message":"Reading Content for Message Payload (Trace) with Id 1353"},
> "changedAttributes":{}}" on 2021-07-05T10:09:35.531Z.
> ```



</td>
<td valign="top">

[Monitor Message Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/314df3f8f4334dd8829c62e865cc6d02.html "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Message monitoring

</td>
<td valign="top">

Read message processing log attachment

</td>
<td valign="top">

-   action: Read

-   objectType: MPL Attachment




</td>
<td valign="top">

[Monitor Message Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/314df3f8f4334dd8829c62e865cc6d02.html "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.") :arrow_upper_right: 

</td>
</tr>
</table>

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

[Audit Logging in the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/02c39712c1064c96b37c1ea5bc9420dc.html)

[Auditing and Logging Information for Edge Integration Cell](https://help.sap.com/docs/integration-suite/sap-integration-suite/auditing-and-logging-information-for-edge-integration-cell?version=CLOUD)

