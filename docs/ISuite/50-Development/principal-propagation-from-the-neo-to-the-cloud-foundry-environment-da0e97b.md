<!-- loioda0e97bfd821428184159e124123e99c -->

# Principal Propagation from the Neo to the Cloud Foundry Environment



<a name="loioda0e97bfd821428184159e124123e99c__section_mst_zgf_llb"/>

## Prerequisites

-   You have created a Service Key by creating a service instance using the on-premise connectivity plan. For more details, see [Accessing On-Premise Systems through API Management](../accessing-on-premise-systems-through-api-management-2fc7a5b.md).



<a name="loioda0e97bfd821428184159e124123e99c__section_knq_4hq_hlb"/>

## Context

Enable an application in your subaccount in the Neo environment to access an API Management proxy created on a Cloud Foundry based API Management without a user login. For this scenario to work, the Neo subaccount needs to be trusted by the Cloud Foundry subaccount where API Management is enabled. Now, the application on Neo can call API Management proxy using OAuth2SAMLBearer destination.



<a name="loioda0e97bfd821428184159e124123e99c__section_vqw_phq_hlb"/>

## Procedure

1.  Create Trust between the Neo Subaccount and the Cloud Foundry Subaccount. For detailed steps, see [Create Trust between Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6e194f8e919a40bab7e39cd992677cb7.html#loio561b0623e9a34a1c9bfc20efa1e773c5).
2.  Create a Destination to the API Proxy that you want to call using principal propagation.

    **New Destination**


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Technical name of the destination. It can be used later on to get an instance of that destination. It must be unique for the global account.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Enter the API Proxy URL for the proxy you want to call.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    OAuth2SAMLBearerAssertion
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Audience
    
    </td>
    <td valign="top">
    
    Copy the value of entityID property of the SAML 2.0 metadata representing your subaccount in the Cloud Foundry environment.

    > ### Tip:  
    > You can open the metadata of the subaccount in the Cloud Foundry environment using the tokenUrl you obtain from the Service Key:
    > 
    > https://<your subaccount's subdomain\>.authentication.<SAP BTP host\>/saml/metadata
    > 
    > Example:
    > 
    > https://<tenant-specific-route-for-your-business-app\>.sap.hana.ondemand.com/oauth/token

    Example of audience/entityID:

    demo.aws-live-us10
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Key
    
    </td>
    <td valign="top">
    
    Enter the *clientId* obtained from the *Service Key* in the created service instance using on-premise connectivity plan.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Enter the token url obtained from the *Service Key* in the created service instance using on-premise connectivity plan.

    The token service URL is defined in the Location attribute of the element marked as AssertionConsumerService, like this :

    <md:AssertionConsumerService Location="<Token Service URL\>" Binding="urn:oasis:names:tc:SAML:2.0:bindings:URI" index="1"/\>

    > ### Tip:  
    > You can open the metadata of the subaccount in the Cloud Foundry environment using the tokenUrl you obtain from the Service Key:
    > 
    > Example: https://<tenant-specific-route-for-your-business-app\>.sap.hana.ondemand.com/oauth/token


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service Password
    
    </td>
    <td valign="top">
    
    Enter the *clientSecret* obtained from the *Service Key* in the created service instance using on-premise connectivity plan.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    System User
    
    </td>
    <td valign="top">
    
    Empty
    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    If you have not generated the client credentials \(clientId, ClientSecret, tokenUrl and application url\) yet, see [Accessing On-Premise Systems through API Management](../accessing-on-premise-systems-through-api-management-2fc7a5b.md)
    
    </td>
    </tr>
    </table>
    
    For more information on creating a destination, see [here](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6e194f8e919a40bab7e39cd992677cb7.html#loioa4025821716e443a9091c2fa180415ab).

3.  Use the following sample source code to consume the above created destination in your application.

    > ### Sample Code:  
    > ```
    > protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    >              // TODO Auto-generated method stub
    > 
    > 
    >     try {   
    >       // Look up the connectivity configuration API
    >       Context ctx = new InitialContext();
    >       ConnectivityConfiguration configuration = (ConnectivityConfiguration) ctx
    >           .lookup("java:comp/env/connectivityConfiguration");
    > 
    >       // Get destination configuration
    >       DestinationConfiguration destConfiguration = configuration.getConfiguration("APIProxyTest"); //Name of Destination
    > 
    >       if (destConfiguration == null) {
    >         response.sendError(HttpServletResponse.SC_INTERNAL_SERVER_ERROR,
    >             String.format(
    >                 "Destination %s is not found. Hint:" +
    >                                        " Make sure to have the destination configured.",
    >                 "pptest"));
    >         return;
    >       }
    >       
    >       AuthenticationHeaderProvider authHeaderProvider = (AuthenticationHeaderProvider) ctx
    >           .lookup("java:comp/env/myAuthHeaderProvider");
    >       // retrieve the authorization header for OAuth SAML Bearer principal propagation
    >       List<AuthenticationHeader> samlBearerHeader = authHeaderProvider
    >           .getOAuth2SAMLBearerAssertionHeaders(destConfiguration);
    >       LOGGER.debug("JWT token from CF XSUAA: " + samlBearerHeader.get(1).getValue());
    >       response.getWriter().println("JWT token from CF XSUAA: " + samlBearerHeader.get(1).getValue());
    >       String destinationURL = destConfiguration.getProperty("URL");
    >       URL url = new URL(destinationURL);
    >       HttpURLConnection connection = (HttpURLConnection) url.openConnection();
    >       connection.setRequestMethod("GET");
    >       connection.setRequestProperty("Authorization", samlBearerHeader.get(1).getValue());
    >       connection.setConnectTimeout(10000);
    >       connection.setReadTimeout(60000);
    >       int responseCode = connection.getResponseCode();
    >       BufferedReader in = new BufferedReader(
    >           new InputStreamReader(connection.getInputStream()));
    >       String inputLine;
    >       StringBuffer responseBody = new StringBuffer();
    > 
    >       while ((inputLine = in.readLine()) != null) {
    >         responseBody.append(inputLine);
    >       }
    >       connection.disconnect();
    >       response.getWriter().println("Response Status : " + responseCode);
    >       response.getWriter().println("Response Body" + responseBody.toString());
    >       
    >       
    >       response.getWriter().close();
    >     } catch (Exception e) {
    >         // Connectivity operation failed
    >         String errorMessage = e.getMessage();
    >         LOGGER.error("Connectivity operation failed", e);
    >         response.sendError(HttpServletResponse.SC_INTERNAL_SERVER_ERROR, errorMessage);
    >     }
    >        }
    > 
    > ```


Principal propagation from a Neo subaccount to Cloud Foundry Subaccount is established.

