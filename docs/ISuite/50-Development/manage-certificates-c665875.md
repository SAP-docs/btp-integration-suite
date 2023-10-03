<!-- loioc6658758fa1a4d29a4140a247f5505bb -->

# Manage Certificates

By using certificates, you can ensure that whenever a call is made to your API, there’s a certificate attached to it that confirms the identity of the caller and only if you recognize this identity the API can be processed and return data can be provided.



## Prerequisites

In this procedure, we assume that you’re aware of the process of creating certificates using any tool of your own choice.



## Context

You need to create key store and trust store certificates to configure 2-way SSL \(Secure Sockets Layer\). SSL is the standard security technology for establishing an encrypted link between a web server and a web client, such as a browser or an app. An encrypted link ensures that all data passing between the server and the client remains private. To use SSL, a client makes a secure request to the server by using the encrypted https:// protocol, instead of the unencrypted http:// protocol. In Integration Suite, you can associate the certificates with the API Provider at the time of API provider registration. This process provides more secure way to access API provider.

Whenever the existing certificate expires, you can upload a new certificate and associate the same with the API provider. You can’t upload an expired certificate.

The following are the supported file format for certificates: .cer, .jar \(signed jar\), .der, .pem, .p12, .pkcs

> ### Note:  
> If you face any issues while importing the .pkcs/.p12 certificates, please consider checking for restricted characters in your password.
> 
> If your password for certificates contains any restricted characters \(listed in the table below\), import of such certificates might fail. Therefore, while creating the certificates please choose a password without these restricted characters and try importing again.
> 
> 
> <table>
> <tr>
> <td valign="top">
> 
> Exclamation mark
> 
> 
> 
> </td>
> <td valign="top">
> 
> **!** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Percentage
> 
> 
> 
> </td>
> <td valign="top">
> 
> **%** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Caret
> 
> 
> 
> </td>
> <td valign="top">
> 
> **^** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Ampersand
> 
> 
> 
> </td>
> <td valign="top">
> 
> **&** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Hash
> 
> 
> 
> </td>
> <td valign="top">
> 
> **\#** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Colon
> 
> 
> 
> </td>
> <td valign="top">
> 
> **:** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Slash
> 
> 
> 
> </td>
> <td valign="top">
> 
> **/** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Question mark
> 
> 
> 
> </td>
> <td valign="top">
> 
> **?** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Square brackets
> 
> 
> 
> </td>
> <td valign="top">
> 
> **\[ \]** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> At the rate sign
> 
> 
> 
> </td>
> <td valign="top">
> 
> **@** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Dollar sign
> 
> 
> 
> </td>
> <td valign="top">
> 
> **$** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Single quotation mark
> 
> 
> 
> </td>
> <td valign="top">
> 
> **'** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Parenthesis
> 
> 
> 
> </td>
> <td valign="top">
> 
> **\( \)** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Asterisk
> 
> 
> 
> </td>
> <td valign="top">
> 
> **\*** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Plus sign
> 
> 
> 
> </td>
> <td valign="top">
> 
> **\+** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Comma
> 
> 
> 
> </td>
> <td valign="top">
> 
> **,** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Semicolon
> 
> 
> 
> </td>
> <td valign="top">
> 
> **;** 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Equal sign
> 
> 
> 
> </td>
> <td valign="top">
> 
> **=** 
> 
> 
> 
> </td>
> </tr>
> </table>

> ### Note:  
> Whenever you’re trying to establish a connection between your client and the API Management gateway, certificate pinning ensures that the TLS connection is set up using a particular certificate only. This can help you in situations where you may run into the risk of trusting certificate authorities that you shouldn't. However, the certificate pinning feature isn’t supported currently in API Management.



## Procedure

1.  Log on to Integration Suite .

2.  Choose the navigation icon on the top-left and choose *Configure* \> *APIs*. .

3.  Select the *Certificates* tab.

4.  Choose *Create*.

5.  Select the type of certificate that you want to create.

    -   *Trust Store* - A truststore contains certificates used to verify certificates received as part of SSL handshaking. If the certificate received by an SSL client is signed by a valid certificate authority \(CA\), then the client makes a request to the CA to authenticate the certificate else self-signed certificate can be uploaded in the truststore.

    -   *Key Store* - A keystore contains an SSL certificate and private key used to validate the server during SSL handshaking.

    The examples in this document show the SSL cert and key defined as PEM files, which comply with the X.509 format. If your cert or private key isn’t defined by a PEM file, you can convert it to a PEM file by using utilities such as openssl. However, many .crt files and .key files are already in the PEM format. If these files are text files, and are enclosed in:

    \-----BEGIN CERTIFICATE-----

    \-----END CERTIFICATE----

    and:

    \-----BEGIN ENCRYPTED PRIVATE KEY-----

    ​ -----END ENCRYPTED PRIVATE KEY-----

6.  You can either choose to use an existing store or create a new store and then add a new certificate in that store.

7.  If you choose to create a new store, then enter the following details: store name, certificate name and appropriate description.

8.  If you have chosen to create a key store, then execute the sub-steps below:

    1.  Create a JAR file containing your private key, certificate, and a manifest. For example, the JAR file must contain the following files and directories: `/META-INF/descriptor.properties, <main>.pem, <privateKey>.pem`![](images/API_Cetrificate_4ceb060.png)

        > ### Note:  
        > Ensure to create certificate with unique name. In case if a certificate with the same name exists in your system, then the newly created certificate with overwrite the existing one, and you’ll lose your old certificate data.

        A keystore JAR can contain only one certificate. If you have a certificate chain, all certs in the chain must be appended into a single PEM file, where the last certificate is signed by a CA. The certs must be appended to the PEM file in the correct order, meaning: `cert -> intermediate cert(1) -> intermediate cert(2) -> … -> root`

    2.  In the directory containing your key pair and certificate, create a directory called /META-INF. Then, create a file called descriptor.properties in /META-INF with the following contents: `certFile=<main>.pem` `keyFile=<privateKey>.pem`![](images/API_Certificate_Prop_86b9a54.png)

    3.  Generate the JAR file containing your key pair and certificate: `$ jar -cf myKeystore.jar main.pem privateKey.pem`

    4.  Add descriptor.properties to your JAR file: `$ jar -uf myKeystore.jar META-INF/descriptor.properties`

    5.  Upload the JAR file.


9.  If you have chosen to create a trust store, then upload only the PEM file.

10. Choose *Create*.

    Once you create a certificate, you can then associate it with the API provider at the time of API provider registration.


