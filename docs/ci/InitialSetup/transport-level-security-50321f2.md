<!-- loio50321f2ec03f48fd9a92a92eed4dc1bc -->

# Transport Level Security

**SAP Cloud Integration Inbound Connection**


<table>
<tr>
<th valign="top">

Protocol



</th>
<th valign="top">

Related Adapters



</th>
<th valign="top">

Authentication Method



</th>
<th valign="top">

Required Certificates



</th>
<th valign="top">

Where to Get Required Certificates



</th>
<th valign="top">

CERT Usage in Customer Sender or Receiver Systems



</th>
<th valign="top">

Customer-CA Signed CERT Required?



</th>
<th valign="top">

CERT Usage in Cloud Integration Keystore



</th>
</tr>
<tr>
<td valign="top">

HTTPS



</td>
<td valign="top">

HTTP, SOAP, IDoc, OData and other HTTP based sender adapters



</td>
<td valign="top">

Basic Authentication



</td>
<td valign="top">

Root CA of SAP Cloud Integration/Load Balancer



</td>
<td valign="top">

You can use the self-service provided by SAP



</td>
<td valign="top">

Need to import Root CA of SAP SAP Cloud Integration/Load Balancer in the backend system's key store



</td>
<td valign="top">

No



</td>
<td valign="top">

Not required

**Note:** Users requiring basic authentication must be have the role *ESBMessaging.send* role in SAP Cloud Integration tenant. It needs to be assigned on the IFLMAP node.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

HTTPS



</td>
<td valign="top" rowspan="2">

HTTP, SOAP, IDoc, OData and other HTTP based sender adapters



</td>
<td valign="top" rowspan="2">

Certificate based client authentication



</td>
<td valign="top">

Root CA of SAP Cloud Integration/Load Balancer



</td>
<td valign="top">

You can use the self-service provided by SAP



</td>
<td valign="top">

Need to import Root CA of SAP Cloud Integration/Load Balancer in the backend system's key store



</td>
<td valign="top">

No



</td>
<td valign="top">

Not required



</td>
</tr>
<tr>
<td valign="top">

Public key for certificate based client authentication



</td>
<td valign="top">

Customer must generate a key pair using any tool, generate CSR \(certificate signing request\) and get it signed by CA. List of allowed CAs are mentioned in the operations guide.



</td>
<td valign="top">

Customer needs to import the signed key pair along with Root CA in their sender's system keystore.



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Not Required

**Note:** Customer needs to provide the public key of the signed CA client certificate in the integration flow configuration on sender system after selecting authentication type as certificate based.



</td>
</tr>
</table>

**Cloud Integration Outbound Connection**


<table>
<tr>
<th valign="top">

Protocol



</th>
<th valign="top">

Related Adapters



</th>
<th valign="top">

Authentication Method



</th>
<th valign="top">

Required Certificates



</th>
<th valign="top">

Where to Get Required Certificates



</th>
<th valign="top">

CERT Usage in Customer Sender or Receiver Systems



</th>
<th valign="top">

Customer-CA Signed CERT Required?



</th>
<th valign="top">

CERT Usage in Cloud Integration Keystore



</th>
</tr>
<tr>
<td valign="top">

HTTPS



</td>
<td valign="top">

HTTP, SOAP, IDoc, OData and other HTTP based sender adapters



</td>
<td valign="top">

Basic Authentication



</td>
<td valign="top">

Root and intermediate CAs of the customer



</td>
<td valign="top">

Root and intermediate CAs should be provided by the customer



</td>
<td valign="top">

Not required



</td>
<td valign="top">

Yes



</td>
<td valign="top">

The root and intermediate certificates of the CA approved certificate needs to be added to the SAP Cloud Integration keystore. You can use the self-service to add it to the keystore.

**Note:** Users needing basic authentication must be deployed as user credentials on SAP Cloud Integration and name of this credential should be specified in the respective technical adapter settings



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

HTTPS



</td>
<td valign="top" rowspan="2">

HTTP, SOAP, IDoc, OData and other HTTP based sender adapters



</td>
<td valign="top" rowspan="2">

Certificate based client authentication



</td>
<td valign="top">

Root and intermediate CAs of the customer



</td>
<td valign="top">

Root and intermediate CAs should be provided by the customer



</td>
<td valign="top">

Not required



</td>
<td valign="top">

Yes



</td>
<td valign="top">

The root and intermediate certificates of the CA approved certificate needs to be added to the SAP Cloud Integration keystore. You can use the self-service to add it to the keystore.



</td>
</tr>
<tr>
<td valign="top">

SAP Cloud Integration Public Key for certificate based client authentication



</td>
<td valign="top">

You can use the self service to manage keystore.



</td>
<td valign="top">

Public Key \(or client certificate should be imported in customer server's keystore. Root and intermediate certificate should be imported in the customer server trust keystore.



</td>
<td valign="top">

No \(yes only if customer wants to use own key pair for client authentication\)



</td>
<td valign="top">

SAP will generate the signed certificate and will upload it in the keystore of SAP Cloud Integration tenant \(or will store the certificates provided by customer\). Customer would need to mention the alias name of the certificate in adapter settings.



</td>
</tr>
<tr>
<td valign="top">

HTTP



</td>
<td valign="top">

HTTP



</td>
<td valign="top">

Basic Authentication



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
</tr>
<tr>
<td valign="top">

LDAP



</td>
<td valign="top">

LDAP



</td>
<td valign="top">

Simple Authentication



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
<td valign="top">

NA



</td>
</tr>
</table>


<table>
<tr>
<th valign="top">

Direction



</th>
<th valign="top">

Protocol



</th>
<th valign="top">

Related Adapters



</th>
<th valign="top">

Authentication Method



</th>
<th valign="top">

Required Certificates



</th>
<th valign="top">

Where to Get Required Certificates



</th>
<th valign="top">

CERT Usage in Customer Sender or Receiver Systems



</th>
<th valign="top">

Customer-CA Signed CERT Required?



</th>
<th valign="top">

CERT Usage in Cloud Integration Keystore



</th>
</tr>
<tr>
<td valign="top" rowspan="2">

SAP Cloud Integration inbound/outbound



</td>
<td valign="top" rowspan="2">

SSH



</td>
<td valign="top" rowspan="2">

SFTP \(Poll from SAP Cloud Integration\)



</td>
<td valign="top" rowspan="2">

Certificate based client authentication



</td>
<td valign="top">

Public key for certificate based client authentication



</td>
<td valign="top">

SAP generates a key pair and shares the public key with the customer. If you wants to use your own key pair, you can use the self service to generate it and add it to the keystore.



</td>
<td valign="top">

You have to import/add this public key in designated location at SFTP server



</td>
<td valign="top">

Optional



</td>
<td valign="top">

SAP cloud ops team will generate a key pair and create an alias "id rsa" or "id dsa" in keystore and will deploy it on SAP Cloud Integration tenant. Public key from this key pair will be provided to the customer.



</td>
</tr>
<tr>
<td valign="top">

Public key fingerprint of SFTP server



</td>
<td valign="top">

Public key fingerprint of SFTP server will be provided by SFTP administrator or SAP cloud ops team.



</td>
<td valign="top">

 



</td>
<td valign="top">

Optional



</td>
<td valign="top">

Public key of SFTP sever must be mentioned in "known host" file and deployed on Cloud IntegrationSAP Cloud Integration. Customer must provide it to SAP and this task will be done by SAP cloud ops.



</td>
</tr>
<tr>
<td valign="top">

SAP Cloud Integration Outbound



</td>
<td valign="top">

SMTP



</td>
<td valign="top">

Mail



</td>
<td valign="top">

Basic Authentication/CEAM-MD5



</td>
<td valign="top">

Root and intermediate CAs from the mail server for TLS



</td>
<td valign="top">

Root and intermediate CAs from the mail server for TLS



</td>
<td valign="top">

Not required



</td>
<td valign="top">

Yes



</td>
<td valign="top">

You can manage your keystore using the self-service.



</td>
</tr>
</table>

