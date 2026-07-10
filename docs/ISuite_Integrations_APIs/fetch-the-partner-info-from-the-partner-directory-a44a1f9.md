<!-- loioa44a1f9617ab4536b652979535957ba6 -->

# Fetch the Partner Info from the Partner Directory

Fetch the partner info from the Partner Directory, by passing the autthorized user.

To illustrate this rule, check out the *Partner Directory - Authorized User* integration flow. It is modeled as shown in the figure.

![](images/Guidelines_Partner_Directory_Authorized_User_1871812.png)

The integration flow performs the following steps:

1.  It receives a request from the corresponding Postman collection with the following request body.

    > ### Sample Code:  
    > ```
    > <Order>
    > 	<Header>
    > 	</Header>
    > 	<Items>
    > 		<item>
    > 			<ProductId>Product</ProductId>
    > 			<Description>Description</Description>
    > 			<Price>10.00</Price>
    > 			<Qtty></Qtty>
    > 		</item>
    > 	</Items>
    > </Order>
    > ```

2.  The Groovy Script step *LookUp PD* executes the following script.

    > ### Sample Code:  
    > ```
    >     import com.sap.gateway.ip.core.customdev.util.Message;
    >     import java.util.HashMap;
    >     import com.sap.it.api.pd.PartnerDirectoryService;
    >     import com.sap.it.api.ITApiFactory;
    > 
    > def Message processData(Message message) {
    > 
    >     def service = ITApiFactory.getApi(PartnerDirectoryService.class, null); 
    >     if (service == null){
    >         throw new IllegalStateException("Partner Directory Service not found");
    >     }
    > 	
    >     // Partner Authorization
    >     def headers = message.getHeaders();
    >     def user = headers.get("SapAuthenticatedUserName");
    >     if (user == null){
    >         throw new IllegalStateException("User is not set in the header 'SapAuthenticatedUserName'")      
    >     }
    >     def Pid = service.getPartnerIdOfAuthorizedUser(user);
    >     if (Pid == null){
    > 		throw new IllegalStateException("No partner ID found for user "+user);
    >     }
    >     message.setProperty("pid", Pid);    
    > 
    >     return message;
    > }
    > ```

3.  The Content Modifier *Define context for monitoring purposes* sets the `context` and `receiver` headers for the subsequent *Generic Receiver* integration flow.

    The headers are defined with the following expressions:

    ****


    <table>
    <tr>
    <th valign="top">

    Header
    
    </th>
    <th valign="top">

    Expression
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    context
    
    </td>
    <td valign="top">
    
    `PartnerDirectory-AuthorizedUser`
    
    </td>
    <td valign="top">
    
    Defines the Data Store name. In this case, the name reflects this guideline.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    receiver
    
    </td>
    <td valign="top">
    
    `Partner ${property.pid}` 
    
    </td>
    <td valign="top">
    
    Defines the Data Store entry ID. In this case, the value is given by the partner ID from the Partner Directory.
    
    </td>
    </tr>
    </table>
    
4.  Finally, the integration flow calls the *Generic Receiver* integration flow.


> ### Note:  
> When your tenant is connected to an identity provider, note the following:
> 
> Make sure that when you initially create the Partner Directory entities \(see: [First Steps - Create Entities in the Partner Directory](first-steps-create-entities-in-the-partner-directory-d32359a.md)\), for the definition of the authorized user you specify the user ID, for example, an S-user \(and not an alias\).
> 
> Using a tenant with connected identity provider offers you various options to log in: for example, via a user ID, an alias, or an email address. However, the message is always processed using the user ID. Therefore, make sure that for the authorized user mapping as `cpi_username` you enter the user ID.

To process the integration flow, perform the following steps:

1.  Deploy the integration flows *Partner Directory - Authorized User* and *Generic Receiver*.

2.  Start the Postman Runner and select collection *CPI Partner Directory Example Flows*.

3.  Select folder *Authorized User* in the folder structure for the relevant cloud environment *CF Environment* \> *Integration Flows \(CF\)*\).

4.  Start the Postman runner for this folder.


On successful processing, the integration flow creates the following Data Store entry:

-   Data Store name: *PartnerDirectory-AuthorizedUser*

-   Data Store entry ID: *Partner <PID\>*


