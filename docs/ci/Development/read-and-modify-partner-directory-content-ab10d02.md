<!-- loioab10d02667fe48309bd2d5cd5e06e4f3 -->

# Read and Modify Partner Directory Content

You can use the Script step to address Partner Directory content.

The `PartnerDirectoryService` interface allows you to address Partner Directory content.

> ### Note:  
> For more information about the Partner Directory and how to use scripting in this context, see:
> 
> -   [Parameterizing Integration Flows Using the Partner Directory](parameterizing-integration-flows-using-the-partner-directory-b7812a5.md): contains an introduction to the Partner Directory
> 
> -   [Partner Authorization \(Inbound\)](partner-authorization-inbound-c0c9950.md): explains the partner authorization check
> 
> -   [Use the Partner Directory Appropriately](use-the-partner-directory-appropriately-6e00412.md): contains integration flow design guidelines about using the Partner Directory
> 
> 
> -   [Cloud Integration – Partner Directory – Step-by-Step Example](https://blogs.sap.com/2017/07/25/cloud-integration-partner-directory-step-by-step-example/)
> 
> -   [Cloud Integration – Partner Directory – Partner Dependent XML Structures and IDs](https://blogs.sap.com/2017/08/22/cloud-integration-partner-directory-partner-dependent-xml-structures-and-ids/)
> 
> -   [Cloud Integration – Partner Directory – Sender Partner Connecting with Client Certificate Authentication](https://blogs.sap.com/2017/08/24/cloud-integration-partner-directory-sender-partner-connecting-with-client-certificate-authentication/)
> 
> -   [Cloud Integration – Partner Directory – Partner Dependent User Credential Selection](https://blogs.sap.com/2017/08/25/cloud-integration-partner-directory-partner-dependent-user-credential-selection/)
> 
> -   [Cloud Integration – Partner Directory – Mass Configuration](https://blogs.sap.com/2017/08/25/cloud-integration-partner-directory-mass-configuration/)

The following table provides code snippets that show how to use the Script step with this interface. For an example script, see the section below the table.

****


<table>
<tr>
<th valign="top">

Use Case

</th>
<th valign="top">

Example Requestsand More Information

</th>
</tr>
<tr>
<td valign="top">

Get partner ID

</td>
<td valign="top">

You can apply the following method to get the partner ID for the triple scheme, agency, alternative partner ID:

`getPartnerId(String agency, String scheme, String alternativePartnerId)`

Check out the following example code snippet:

```
/**
     * Looks-up the partner ID for the triple scheme, agency, alternative
     * partner ID. The partner ID is needed for the other methods in this class.
     *
     * @param agency
     *            issuing agency of the external partner ID
     * @param scheme
     *            identification scheme
     * @param alternativePartnerId
     *            alternative partner ID
     * @return partner ID, or <code>null</code>, if no partner ID exists for the
     *         specified triple
     * @throws PartnerDirectoryException
     *             if an error occurs
     * @throws IllegalArgumentException
     *             if an input argument is <code>null</code> or empty
     *
     */
    String getPartnerId(String agency, String scheme, String alternativePartnerId) throws PartnerDirectoryException;
 

```

See also: [Use an Alternative Partner Id to Retrieve Partner Information](use-an-alternative-partner-id-to-retrieve-partner-information-01a784c.md).

</td>
</tr>
<tr>
<td valign="top">

Get alternative partner ID

</td>
<td valign="top">

You can apply the following method to get the alternative partner ID for the triple scheme, agency, partner ID:

`getAlternativePartnerId(String agency, String scheme, String partnerId)`

For more information on the partner ID and the alternative partner ID, see [Partner Directory Concepts](partner-directory-concepts-f917d6e.md).

Check out the following example code snippet:

```
    /**
     * Looks-up the alternative partner ID for the triple scheme, agency,
     * partner ID.
     *
     * @param agency
     *            issuing agency of the external partner ID
     * @param scheme
     *            identification scheme
     * @param partnerId
     *            partner ID
     * @return alternative partner ID, or <code>null</code>, if no alternative
     *         partner ID exists for the specified triple
     * @throws PartnerDirectoryException
     *             if an error occurs
     * @throws IllegalArgumentException
     *             if an input argument is <code>null</code> or empty
     *
     */
    String getAlternativePartnerId(String agency, String scheme, String partnerId) throws PartnerDirectoryException;

```



</td>
</tr>
<tr>
<td valign="top">

Get the partner-specific value of a Partner Directory parameter

</td>
<td valign="top">

You can apply the following method:

`getParameter(String parameterId, String partnerId, Class<T> type)`

Check out the following example code snippet:

```
    /**
     * Returns the partner specific value of a partner directory parameter.
     *
     * @param parameterId
     *            ID of the Partner Directory parameter
     * @param partnerId
     *            ID of the partner
     * @param type
     *            the type of the parameter, supported types are
     *            <code>java.lang.String.class</code> for String parameters,
     *            <code>com.sap.it.api.pd.BinaryData.class</code> for Binary
     *            Data parameters
     * @return value of the parameter, or <code>null</code> if the parameter
     *         does not exist in the Partner Directory
     * @throws PartnerDirectoryException
     *             if an error occurs
     * @throws IllegalArgumentException
     *             if an input argument is <code>null</code> or the given
     *             <code>type</code> is not a supported type or if
     *             <tt>parametrId</tt> or <tt>partnerId</tt> is empty
     *
     */
    <T> T getParameter(String parameterId, String partnerId, Class<T> type) throws PartnerDirectoryException;

```



</td>
</tr>
<tr>
<td valign="top">

Get an X.509 certificate for a binary parameter

</td>
<td valign="top">

You can apply the following method:

`getCertificateParameter(String parameterId, String partnerId)`

Check out the following example code snippet:

```
 /**
     * Returns a X.509 certificate for a binary parameter with content type
     * "crt".
     *
     * @param parameterId
     *            ID of the Partner Directory parameter
     * @param partnerId
     *            ID of the partner
     * @return java.security.cert.X509Certififate instance, or <code>null</code>
     *         if the parameter does not exist in the Partner Directory
     * @throws PartnerDirectoryException
     *             if the parameter is not a certificate parameter, or another
     *             error occurs
     * @throws IllegalArgumentException
     *             if an input argument is <code>null</code> or the given
     *             <code>type</code> is not a supported type or if
     *             <tt>parametrId</tt> or <tt>partnerId</tt> is empty
     */
    Certificate getCertificateParameter(String parameterId, String partnerId) throws PartnerDirectoryException;

```



</td>
</tr>
<tr>
<td valign="top">

Get Partner ID to which an authorized user is assigned

</td>
<td valign="top">

You can apply the following method:

`getPartnerIdOfAuthorizedUser(String authorizedUser)`

Check out the following example code snippet:

```
/**
     * Returns the Partner ID to which a authorized user was assigned to. Or null if the user does not exist.
     *
     * @param authorizedUser
     *            authorized User
     * @throws PartnerDirectoryException
     *             if an error occurs
     * @throws IllegalArgumentException
     *             if the input argument is <code>null</code> or empty
     */
    String getPartnerIdOfAuthorizedUser(String authorizedUser) throws PartnerDirectoryException;

```



</td>
</tr>
<tr>
<td valign="top">

Get the authorized users of a partner

</td>
<td valign="top">

You can apply the following method:

`getAuthorizedUsers(String partnerId)`

Check out the following example code snippet:

```
    /**
     * Returns the authorized users of a partner.
     * 
     * The authorized user names will be returned with lower case characters (Locale.English).
     *
     * @param partnerId
     * @return list of users or empty list if no authorized user exists
     * @throws PartnerDirectoryException
     *             if an error occurs
     * @throws IllegalArgumentException
     *             if the input argument is <code>null</code> or empty
     */
    List<String> getAuthorizedUsers(String partnerId) throws PartnerDirectoryException;

```



</td>
</tr>
<tr>
<td valign="top">

Store binary data \(as byte array\) and the associated content type for Partner Directory binary parameters

</td>
<td valign="top">

Check out the following example code snippet:

```
/**
 * Container to store store binary data (as byte array) and the associated
 * content type for Partner Directory Binary Parameters.
 */
public class BinaryData {
    private final byte[] data;
    private final String contentType;
 
    public BinaryData(byte[] data, String contentType) {
        if (data == null) {
            throw new IllegalArgumentException("Parameter 'data' is null");
        }
        if (contentType == null) {
            throw new IllegalArgumentException("Parameter 'contentType' is null");
        }
        this.data = data;
        this.contentType = contentType;
    }
 
    /** Returns the binary data. Cannot be <code>null</code>. */
    public byte[] getData() {
        return data;
    }
 
    /** Returns the content type. Cannot be <code>null</code>. */
    public String getContentType() {
        return contentType;
    }

```



</td>
</tr>
</table>



<a name="loioab10d02667fe48309bd2d5cd5e06e4f3__section_e4l_1pj_5bb"/>

## Example Script

The following example script shows how to perform partner authentication end-to-end.

It checks if the partner ID associated with the logged-in user is consistent with the partner ID that can be derived from the message content.

It is assumed that the alternative partner ID of the message has already been set in the `AlternativePartnerID` property.

```
import com.sap.gateway.ip.core.customdev.util.Message;
import com.sap.it.api.pd.PartnerDirectoryService;
import com.sap.it.api.pd.BinaryData;
import java.util.Map;
import java.security.cert.X509Certificate;

import com.sap.it.api.ITApiFactory;
import  javax.security.auth.Subject;
import  java.security.Principal;
import java.util.Set;
def Message processData(Message message) {
   
    // get the logged-in user from header 'SapAuthenticatedUserName'
	map = message.getHeaders();
	String user = map.get("SapAuthenticatedUserName");
	if (user == null || user.isEmpty()){
	  throw new IllegalStateException("Logged-in user not available in header SapAuthenticatedUserName.");
	}
	
	// look-up Partner Directory Service
	def service = ITApiFactory.getApi(PartnerDirectoryService.class, null); 
    if (service == null){
      throw new IllegalStateException("Partner Directory Service not found");
    }
    
    // get partner ID from user
	String pid = service.getPartnerIdOfAuthorizedUser(user);
    if (pid == null){
		   throw new IllegalStateException("No partner ID found for user "+user);
	}
	
	// alternative partner ID from property which has been filled before from the message
    map = message.getProperties();
	def apid = map.get("AlternativePartnerID");	
	if (apid == null || apid.isEmpty()){
	      throw new IllegalStateException("Property AlternativePartnerID does not contain a value");
	}
	
	// look-up parter ID for the alternative partner ID
	def partnerIdForAlternativePid =    service.getPartnerId("companies", "company_scheme",apid);
	if (partnerIdForAlternativePid == null || partnerIdForAlternativePid.isEmpty()){
	     throw new IllegalStateException("No partner ID found for alternative partner ID "+apid);
	}
	 
	// compare the two partner IDs
	if (!partnerIdForAlternativePid.equals(pid)){
	    throw new IllegalStateException("User "+user+" is not authorized to send messages with ID "+apid);
	}
	
    // set pid as property
    message.setProperty("PartnerID",pid);
    
    
   
	return message;
}

```

