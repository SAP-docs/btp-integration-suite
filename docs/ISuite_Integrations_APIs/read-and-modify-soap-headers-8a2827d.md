<!-- copy8a2827d030b345f998199774266b9810 -->

# Read and Modify SOAP Headers

You can use the Script step to address SOAP headers.

The `Message` interface allows you to address SOAP headers.

The following table provides examples of how to use the Script step with this interface.

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

Access SOAP headers

</td>
<td valign="top">

You can apply the following methods on an instance of `Message` to set a SOAP header, retrieve, or delete all SOAP headers:

`setSoapHeaders(List<SoapHeader> headers)`

`getSoapHeaders()`

`clearSoapHeaders()`

The following Groovy Script allows you to set a SOAP header:

```
import com.sap.gateway.ip.core.customdev.util.Message;
import java.util.ArrayList;
import java.util.List;
import javax.xml.namespace.QName;
import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import org.apache.cxf.binding.soap.SoapHeader;
import org.w3c.dom.Document;
import org.w3c.dom.Element;
import com.sap.it.api.ITApiFactory;
import com.sap.it.api.securestore.SecureStoreService;
import com.sap.it.api.securestore.UserCredential;

def Message processData(Message message) {

   // First fetch user name and password which must be entered into the SOAP header from the secure store service.
   // This is not necessary if your SOAP header does not require data from the secure store service.
   def service = ITApiFactory.getApi(SecureStoreService.class, null);
   def credential = service.getUserCredential("partner1_credential_alias");
   if (credential == null){
      throw new IllegalStateException("No credential found for alias 'partner1_credential_alias'");
   }
   String userName = credential.getUsername();
   String password = new String(credential.getPassword());

   // Create Soap Header as DOM Element;  the attributes "actor" and "mustUnderstand" must not be added;
   // these attributes can be added later see below.
   // The following lines create the DOM Element.
   //<AuthHeader xmlns=http://www.Test.com/><ClientId>"+userName+"</ClientId><Password>"+password+"</Password></AuthHeader>"
   DocumentBuilderFactory dbf = DocumentBuilderFactory.newInstance();
   dbf.setNamespaceAware(true);
   dbf.setIgnoringElementContentWhitespace(true);
   dbf.setValidating(false);
   DocumentBuilder db = dbf.newDocumentBuilder();
   Document doc = db.newDocument();
   Element authHeader = doc.createElementNS("http://www.Test.com/", "AuthHeader");
   doc.appendChild(authHeader);
   Element clientId = doc.createElementNS("http://www.Test.com/", "ClientId");
   clientId.setTextContent(userName);
   authHeader.appendChild(clientId);
   Element passwordEl = doc.createElementNS("http://www.Test.com/", "Password");
   passwordEl.setTextContent(password);
   authHeader.appendChild(passwordEl);

   // Create SOAP header instance.
   SoapHeader header = new SoapHeader(new QName(authHeader.getNamespaceURI(), authHeader.getLocalName()), authHeader);
   header.setActor("actor_test");
   header.setMustUnderstand(true);

   // Add the SOAP header to the header list and set the list to the message header "org.apache.cxf.headers.Header.list".
   List  headersList  = new ArrayList<SoapHeader>();
   headersList.add(header);
   message.setHeader("org.apache.cxf.headers.Header.list", headersList);
   
   return message;
}
```

The resulting SOAP header is \(as part of an example SOAP message\):

```
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
   <soap:Header>
       <AuthHeader soap:actor="actor_test" soap:mustUnderstand="1" xmlns="http://www.Test.com/">
          <ClientId>username</ClientId>mustUnderstand 
          <Password>password</Password>
       </AuthHeader>
   </soap:Header>
   <soap:Body>
      <test:TestMessage xmlns:test="http://hci.sap.com/ifl/test">
         <MessageContent>customer1</MessageContent>
      </test:TestMessage>
   </soap:Body>
</soap:Envelope>
```

You can find an example scenario using GroovyScript in this SAP Community blog: [Cloud Integration – Accessing and Setting SOAP Headers in an Integration Flow](https://blogs.sap.com/2019/04/08/cloud-integration-accessing-and-setting-soap-headers-in-an-integration-flow/).

See also: [Setting and Getting SOAP Headers](setting-and-getting-soap-headers-65c70da.md).

</td>
</tr>
</table>

