<!-- loioe904119a0910462baa8e2b58e9e48c57 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable Client Applications

Before a client application can access a Graph business data graph, the client application must know certain secrets, known as Graph service credentials \(Graph root URL, security service URL, client ID, and client secret\), as well as the business data graph identifier.

This is done by creating a *Process Integration Runtime* service instance and a service key.

After creation of the *Process Integration Runtime* service instance and service key, Graph API consumers must use service bindings to acquire an access token. The access token can be obtained from a security service during authentication. For more information, see [Authentication](authentication-79aabda.md).

> ### Note:  
> Sharing service bindings enables any client application to consume Graph APIs. From a security perspective, create a dedicated service instance per client application. This helps tracking, auditing, and if necessary, revoking the credentials of a client application, without affecting others.



<a name="loioe904119a0910462baa8e2b58e9e48c57__section_jx5_pg4_jfc"/>

## Prerequisites

You have already configured an entitlement for Graph. For more information, see [Configure Entitlement for Graph](initial-setup-12ad448.md#loio12ad448225ac47049982d9faab7978a3__section_configEntitlement).



<a name="loioe904119a0910462baa8e2b58e9e48c57__section_ayq_mfr_gfc"/>

## Create a Service Instance

With a service instance, you define how to access a certain SAP BTP service. In the context of SAP Integration Suite and Graph, the service instance is configured to authenticate and authorize API requests using OAuth 2.0.

The process of service instance and service key creation consists of 2 steps:

1.  In the SAP BTP cockpit, navigate to the subaccount where you've subscribed to SAP Integration Suite.
2.  From the left navigation panel, choose *Services* \> *Service Marketplace* and then choose *Process Integration Runtime*.

    > ### Note:  
    > To create a service instance of Process Integration Runtime, you must enable Cloud Foundry for Graph.

3.  Choose *Create*. In the *New Instance or Subscription* dialog box, *Process Integration Runtime* is already preselected as a service.
4.  Specify the following parameters:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Input
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Plan
    
    </td>
    <td valign="top">
    
    integration-flow
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Environment
    
    </td>
    <td valign="top">
    
    Cloud Foundry
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Space
    
    </td>
    <td valign="top">
    
    Choose a space, for example *dev*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Instance name
    
    </td>
    <td valign="top">
    
    Enter a meaningful instance name.
    
    </td>
    </tr>
    </table>
    
5.  Specify the OAuth client \(instance\) parameters depending on your use case. You can choose to enter details via either Form or JSON. We recommend using the JSON option. The following options are possible:
    -   If the client is used for service-to-service communication scenarios and performs tasks on its own behalf, not on behalf of a user, the client\_credentials grant must be used:

        ```
        {
            "grant-types": [
                "client_credentials"
            ],
            "redirect-uris": [ ],	// redirect uris are not required for the client_credentials grant
            "token-validity": 3600	// Defines the period of time for which the access token is valid in seconds. Enter any value from 3600 to 86400 (1- 24 hours).
        }
        
        ```

    -   If the client represents the application involving the user authentication, and acts on behalf of the user, the authorization\_code grant must be used:

        ```
        {
        	"grant-types":[
        		"refresh_token",
                		"authorization_code"
        ],
        	"redirect-uris":[
        	"<the callback url of your application>"
        ]
        }
        
        ```


6.  Optional: Choose *Next* to review and verify the instance details.
7.  Choose *Create*.

    > ### Note:  
    > By June 30th, 2025, no new instance of Graph with the API service plan can be created. If you are still using the API service plan from Graph, we recommend you change to updated Graph entitlement. For more information, see *Configure Entitlement in Graph* under [Initial Setup](initial-setup-12ad448.md).




<a name="loioe904119a0910462baa8e2b58e9e48c57__section_qkm_2gr_gfc"/>

## Create a Service Key

To create the service key, do the following:

1.  In the SAP BTP cockpit, navigate to the subaccount where you created the service instance for Process Integration Runtime.
2.  Navigate to *Instances and Subscriptions* and choose the service instance that you created.
3.  Under <span class="SAP-icons-V5"></span>*Actions* choose *Create Service Key*.
4.  In the *New Service Key* dialog, provide a **Service Key Name**. You can use up to 32 characters.
5.  Under *Configure Binding Parameters*, enter your details, either via Form or JSON.

    We recommend choosing Form as the more convenient option.

6.  Specify the following parameters in the Form.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Type*
    
    </td>
    <td valign="top">
    
    There are the following options.

    -   *ClientId/Secret*: Defines a service key that contains a clientId and client secret.
    -   *Certificate*: Provides a x509 certificate issued by SAP.

        Select this option to have SAP BTP generate a client certificate for you.

        Client credentials grant is required to be able to use this key type.

    -   *External Certificate*: Allows mapping an existing x509 certificate to a service key.

        Select this option to use a client certificate generated with another application than SAP BTP.

        Client credentials grant is required to be able to use this key type.


    See: [Service Key Types](https://help.sap.com/docs/integration-suite/sap-integration-suite/service-key-types?version=CLOUD)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *External Certificate*

    \(Applicable if *External Certificate* is the *Key Type*option chosen\)
    
    </td>
    <td valign="top">
    
    Add *External Certificate*: Enter the certificate that you exported from the certificate-generating application to your local computer.

    Enter the PEM-encoded X.509 certificate.

    > ### Tip:  
    > PEM stands for Privacy Enhanced Mail and is a common format for X.509 certificates. It contains base64-encoded text content with the string -----BEGIN CERTIFICATE----- at the beginning and the string -----END CERTIFICATE----- at the end of the character sequence.

    > ### Example:  
    > \-----BEGIN CERTIFICATE-----MIIHyDCCBrCgAwIB\[...\]CAq8Tn7kSFDmVnrXe6v8hcQ==-----END CERTIFICATE-----

    Don't enter the whole certificate chain.

    Make sure that the certificate is signed by a Certification Authority supported by the load balancer. See [Load Balancer Root Certificates Supported by SAP](https://help.sap.com/docs/integration-suite/sap-integration-suite/load-balancer-root-certificates-supported-by-sap?version=CLOUD).

    You can only use a single certificate once across all existing service instances. To assign multiple roles, don't create multiple service instances. Instead, maintain multiple roles within one service instance.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Validity in days*

    \(Applicable only if *Certificate* has been chosen as the *Key Type*\)
    
    </td>
    <td valign="top">
    
    Define the validity in days by selecting a number between 1 and 365.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Size*

    \(Applicable only if *Certificate* has been chosen as the *Key Type*\)
    
    </td>
    <td valign="top">
    
    The default for the key size is set to 2048.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Selecting JSON, you can also pass these parameters in a valid JSON object that contains service-specific configuration parameters, provided either in-line or in a file \(see [Specifying Service Instance and Service Key Parameters in JSON Format](https://help.sap.com/docs/integration-suite/sap-integration-suite/specifying-service-instance-and-service-key-parameters-in-json-format?version=CLOUD)\).

7.  Choose *Create*.
8.  Choose the newly created service key to display the details of the service key. You need the note the values of the service key for later reference.
9.  Depending on the chosen *Key Type*, the service key contains certain parameters. The following table lists the parameters that are required to configure the client application:


    <table>
    <tr>
    <th valign="top" colspan="2">

    Service Key Parameters
    
    </th>
    </tr>
    <tr>
    <th valign="top">

    *Key Type*
    
    </th>
    <th valign="top">

    *Parameters Contained in Service Key*
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *ClientID/Secret*
    
    </td>
    <td valign="top">
    
    -   *clientid*: ClientID is used as credential when requesting the access token from the token server.
    -   **clientsecret**: Client secret is used as password when requesting the access token from the token server.
    -   *tokenurl*: URL of token server that issues the access token.
    -   *url*: URL to address service.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Certificate*
    
    </td>
    <td valign="top">
    
    -   **clientid**

    clientid of service key.

    -   **certificate**

    PEM-encoded certificate chain \(to be used by the sending application to authenticate itself against token server or application\).

    The certificate chain contains a root certificate supported by SAP \(see [Load Balancer Root Certificates Supported by SAP](https://help.sap.com/docs/integration-suite/sap-integration-suite/load-balancer-root-certificates-supported-by-sap?version=CLOUD)\).

    -   **key**

    Private key of SAP-generated key pair.

    -   **tokenurl**

    URL of token server that issues the access token.

    -   **url**

    URL to address service.

    > ### Note:  
    > To enable the related HTTP client to support this authentication option, you need to format the certificate \(including the certificate chain\) and the key accordingly. In particular, make sure to replace all \\n in the SAP-generated certificate or key by line breaks.
    > 
    > A suitable certificate, for example, would then look like the following:
    > 
    > \-----BEGIN CERTIFICATE-----
    > 
    > MIIFtDCCA5ygAwIBAgIQCUFIj6cfjiSfZi/ZvVU6IDANBgkqhkiG9w0BAQsFADB5
    > 
    > ................................................................
    > 
    > ................................................................
    > 
    > ................................................................+
    > 
    > LvHPhNDM3rMsLu06agF4JTbO8ANYtWQTx0PVrZKJu+8fcIaUp7MVBIVZ
    > 
    > \-----END CERTIFICATE-----

    > ### Note:  
    > The generated certificate also contains additional parameters under *certificatedetails*.
    > 
    > When you've chosen *Certificate* as the *Key Type*, the following applies for these parameters:
    > 
    > -   The values for the parameters *issuerdn*, *serialnumber*, and *subjectdn* are determined by SAP.
    > -   The value of parameter *validuntil* is calculated from the entry that you've selected for *Validity in days* when defining the service key.
    > 
    > See: [Service Key Types](https://help.sap.com/docs/integration-suite/sap-integration-suite/service-key-types?version=CLOUD)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **External Certificate**
    
    </td>
    <td valign="top">
    
    -   *clientid*: ClientID of service key.
    -   *certificate*: PEM-encoded certificate \(to be used by the sending application to authenticate itself against token server or application\).
    -   *tokenurl*: URL of token server that issues the access token.
    -   *url*: URL to address service.

    A service key with this *key pair* doesn't contain a private key because the corresponding key pair has been generated with another application than SAP BTP.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You have two options to display these parameters:
    > 
    > 1.  *Form*: Displays content of service key in a user-friendly list easy to consume.
    > 2.  *JSON*: Displays content of service key in JSON format.
    > 
    > You can either:
    > 
    > 1.  Copy these values to your clipboard or to a text editor.
    > 2.  Download the service key.
    > 
    > You need these values when specifying the required credentials or certificate values associated with the sending application.


