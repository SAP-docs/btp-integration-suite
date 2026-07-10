<!-- loio8dd981e4f1f44d22bee22c174e5c52d0 -->

# Read Security-Related Artifacts

You can use the Script step to address security-related artifacts \(for example, keystore entries\).

The following interfaces allow you to address security-related artifacts.

-   `KeystoreService`: Addresses entries of the tenant keystore such as certificates and key pairs.

-   `SecureStoreService`: Addresses deployed *User Credentials*, *Secure Parameter* artifacts, or access tokens of *OAuth2 Authorization Code* credentials.

-   `AccessTokenAndUser`: Addresses the access token and user name for an *OAuth2 Authorization Code* credential. The access token is fetched from the OAuth2 authorization server via a refresh\_token grant type and cached by the implementation. If the access token expires, then a new access token is fetched.

-   `UserCredential`: Represents a *User Credentials* object.


The `KeystoreException`, `SecureStoreException`, and `CredentialNotFoundException` interfaces handle exceptions if certain artifacts cannot be found.

The following table provides examples of how to use the Script step with these interfaces.

> ### Caution:  
> The sample scripts store security-related information \(for example, a key\) as a header or exchange property. Note that is not a good practice when designing a productive scenario. The reason is that when you store sensible information as a header or property, you take the risk of exposing this data accidentally. For example, a header can be sent to a receiver system if you don't take actions to prevent this. Therefore, use these example scripts for demo or testing purposes only.

****


<table>
<tr>
<th valign="top">

Use Case

</th>
<th valign="top">

Example Requests / More Information

</th>
</tr>
<tr>
<td valign="top">

Access credentials from a *Secure Parameter* or *User Credentials* artifact and retrieve user and password

</td>
<td valign="top">

You can apply the following methods on an instance of `SecureStoreService`:

-   `getUserCredential(String alias)`

-   `getPassword()`

-   `getUsername()`


The following Groovy script reads credentials from a *Secure Parameter* artifact deployed on the tenant and stores the result as a property. An exception is caught if no secure parameter is found for the given alias.

```
def Message processData(Message message) {
    def apikey_alias = message.getProperty("ApiKeyAlias")
    def secureStorageService =  ITApiFactory.getService(SecureStoreService.class, null)
    try{
        def secureParameter = secureStorageService.getUserCredential(apikey_alias)
        def apikey = secureParameter.getPassword().toString()
        message.setProperty("api-key", apikey)
    } catch(Exception e){
        throw new SecureStoreException("Secure Parameter not available")
    }
    return message;
}

```

You can find an example scenario in [Access Secure Parameters in Scripts](access-secure-parameters-in-scripts-fdf4ce3.md).

The `getCredentialProperties()` method provides properties of a deployed *User Credentials* artifact, such as the alias or the user who deployed the credential.

The following Groovy script reads a *User Credentials* artifact \(with an alias given in an exchange property with the name `CredentialAlias`\) and stores the properties of the artifact in another exchange property \(`credentialProperties`\):

```
def Message processData(Message message) {
    def CredentialAlias = message.getProperty("CredentialAlias")
    def secureStorageService =  ITApiFactory.getService(SecureStoreService.class, null)
    def credential = secureStorageService.getUserCredential(CredentialAlias)
    def credentialProperties = credential.getCredentialProperties()
    message.setProperty("credentialProperties", credentialProperties)
    return message;
}
```



</td>
</tr>
<tr>
<td valign="top">

Access a certificate from a tenant keystore

</td>
<td valign="top">

You can apply the `getCertificate(String alias)` method on an instance of `KeystoreService`.

The following Groovy script reads a certificate from the keystore \(for a given alias provided in a property\) and writes it into a property.

```
def Message processData(Message message) {
    def alias = message.getProperty("CertificateAlias")
    def KeystoreService =  ITApiFactory.getService(KeystoreService.class, null)
    try{
        def cert = KeystoreService.getCertificate(alias)
        message.setProperty("certificate", cert)
    } catch(Exception e){
        throw new KeystoreException("Certificate not available")
    }
    return message;
}

```



</td>
</tr>
<tr>
<td valign="top">

Access a certificate chain from a tenant keystore

</td>
<td valign="top">

You can apply the `getCertificateChain(String alias)` method on an instance of `KeystoreService`:

</td>
</tr>
<tr>
<td valign="top">

Access a key from a tenant keystore \(associated with an alias\)

</td>
<td valign="top">

You can apply the `getKey(String alias)` method on an instance of `KeystoreService`:

The following Groovy script reads the public key from a key pair contained in the tenant keystore:

```
def Message processData(Message message) {
    def alias = message.getProperty("KeyAlias")
    def KeystoreService =  ITApiFactory.getService(KeystoreService.class, null)
    try{
        def ke = KeystoreService.getKey(alias)
        message.setProperty("key", ke)
    } catch(Exception e){
        throw new KeystoreException("Key not available")
    }
    return message;
}

```



</td>
</tr>
<tr>
<td valign="top">

Get an access token and user name for an *OAuth2 Authorization Code*credential.

</td>
<td valign="top">

You can apply the `SecureStoreService.getAccesTokenForOauth2AuthorizationCodeCredential(String credentialName)` method on an instance of `KeystoreService`:

The following Groovy script gets the access token and user associated with an OAuth2 Authorization Code artifact deployed on the tenant:

```
def Message processData(Message message) {
        SecureStoreService secureStoreService = ITApiFactory.getService(SecureStoreService.class, null);
     AccessTokenAndUser accessTokenAndUser = secureStoreService.getAccesTokenForOauth2AuthorizationCodeCredential(credential_name);
    String token = accessTokenAndUser.getAccessToken();
    String user = accessTokenAndUser.getUser();   
    message.setHeader("Authorization", "Bearer "+token);
    return message;
}

```

The following SAP Community blog provides an example: [Cloud Integration – Call Microsoft Graph API with OAuth 2.0 Authorization Code](https://blogs.sap.com/2021/01/11/cloud-integration-call-microsoft-graph-api-with-oauth-2.0-authorization-code/)

</td>
</tr>
</table>

