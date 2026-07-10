<!-- loiodd49f1fc27f44f068b3c3d6f3c8809d5 -->

# Specific Use Cases for LDAP Adapter



## Using Input Type Java \(JNDI\) Attributes

The LDAP adapter supports input via JNDI attributes. If you choose this as the input type, you use a script step to obtain values to attributes that are then passed to the LDAP service.

For example, consider this script being used in a *Script* step.

```
importClass(com.sap.gateway.ip.core.customdev.util.Message);
importClass(java.util.HashMap);
importClass(javax.naming.directory.Attribute);
importClass(javax.naming.directory.BasicAttribute);
importClass(javax.naming.directory.BasicAttributes);
importClass(javax.naming.directory.Attributes);
 
function processData(message) {
	var body = message.getBody();
	var dn= "cn=Markus,ou=users,dc=testcompany,dc=com";
	var givenNameAttr = new BasicAttribute("givenName", "Jack");
	var displayNameAttr = new BasicAttribute("displayName", "Reacher");
	var telephoneNumberAttr = new BasicAttribute("telephoneNumber", "100-100-100");
	var attributes = new BasicAttributes();
	attributes.put(givenNameAttr);
	attributes.put(displayNameAttr);
	attributes.put(telephoneNumberAttr);
     attr =new BasicAttribute("title", "Developer");
     attributes.put(attr);
     attr =new BasicAttribute("sn", "Brutus");
     attributes.put(attr);
	var resultingMap = new HashMap();
	resultingMap.put("dn", dn);
	resultingMap.put("attributes", attributes);
	message.setBody(resultingMap);
	return message;
}

```

In the script, the values for attributes `givenName`, `displayName` and `telephoneNumber` are declared in the script before they are passed to the LDAP adapter. Similarly, you can also create a script where these values are dynamically fetched during runtime.



## Adding Attributes to Template Schema

The example schema contains a set of attributes for a given record. In case you want the schema to contain additional attributes, you can manually edit the schema before using it in the mapping step.

For example, if you want to add a field, telephone number, you can add an element in the schema under the `sequence` element.

Here’s how the edited schema will look like:

```
<?xml version="1.0" encoding="UTF-8"?>
<schema xmlns="http://www.w3.org/2001/XMLSchema">
    <element name="Schema">
        <complexType>
            <sequence>
            <element name="DistinguishedName" maxOccurs="1" minOccurs="1" type="string"/>
            <element name="ObjectClass" maxOccurs="1" minOccurs="0" type="string"/>
                <element name="Attributes" maxOccurs="1" minOccurs="1">
                    <complexType>
                        <sequence>
                            <element name="sAMAccountName" type="string"></element>
                            <element name="sn" type="string"></element>
                            <element name="givenName" type="string"></element>
                            <element name="displayName" type="string"></element>
                            <element name="name" type="string"></element>
                            <element name="telephoneNumber" type="string"></element>
					   <!--The above element has been added to the schema. If you want to add or remove elements, ensure that you make changes within the sequence tag-->	
                        </sequence>
                    </complexType>
                </element>
            </sequence>
        </complexType>
    </element>
</schema>

```



## Add Additional Attributes to the Message after Mapping using Script

Let us consider a scenario where you want to add an attribute to the message \(payload\) that you are sending to the LDAP service. For example, you want to add a password attribute. Due to security concerns, you should encode the password before you add it.

You can achieve this by adding a *Script* step after the mapping step in the integration flow. Here's an example of the script that you can use in the *Script* step:

```
import com.sap.gateway.ip.core.customdev.util.Message;
import java.util.HashMap;
import javax.xml.bind.DatatypeConverter;
import javax.naming.directory.Attribute;
import javax.naming.directory.Attributes;
import javax.naming.directory.BasicAttribute;
import javax.naming.directory.BasicAttributes;

def Message processData(Message message) 
{
	Attributes attributes = new BasicAttributes();
	String quotedPassword = '"'+"Initial@1"+'"';
     byte[] unicodePasswordByteArray = quotedPassword.getBytes("UTF-16LE");
	attributes.put(new BasicAttribute("unicodePwd", unicodePasswordByteArray));
	message.setHeader("SAP_LDAPAttributes",attributes);
	return message;
}
```



## Using Modify Operation to Change DN

You can use the *Modify* operation to change the DN of an LDAP record. You can do this by adding the tag `<DistinguishedName_Previous>` to the input payload with the old DN. Specify the modified DN in `<DistinguishedName>` tag and perform the *Modify* operation.

Here's an example that shows a sample input payload for modiying the DN of an LDAP record:

```
<?xml version="1.0" encoding="UTF-8"?>
<Schema xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
            <DistinguishedName>CN=CMD ABC,CN=Users,DC=dev109,DC=dev-wdf,DC=sap,DC=corp</DistinguishedName>
            <DistinguishedName_Previous>CN=CMD,CN=Users,DC=dev109,DC=dev-wdf,DC=sap,DC=corp</DistinguishedName_Previous>
            <ObjectClass>user</ObjectClass>
            <Attributes>
                        <mail>123@xyz.com</mail>
                        <telephoneNumber>123456789</telephoneNumber>
            </Attributes>
</Schema> 

```

