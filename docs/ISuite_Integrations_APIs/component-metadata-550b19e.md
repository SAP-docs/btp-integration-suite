<!-- loio550b19e79c564534832f4166e7730852 -->

# Component Metadata

Component metadata specifies the attributes of sender and receiver adapters used to define the UI. Each tab can contain multiple attributes. You can group the attributes into multiple attribute groups within the tabs. You can use the same attribute across the sender and receiver adapters by using attribute reference.



## Component Metadata

This set of metadata allows you to define components details.

> ### Note:  
> If you'd like to use the adapter on an Edge Integration Cell runtime, you have to add additional metadata as explained under [Additional Metadata to Support Edge Integration Cell](additional-metadata-to-support-edge-integration-cell-f87349e.md).

**Component Metadata**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Datatype

</th>
<th valign="top">

Cardinality

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ComponentId

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

Specifies a unique Id for the component. The following are technical identifiers and should not contain any space or special character.

Example: `ctype::Adapter/cname::sap:dropbox/version::1.0.0` 

ctype is type of component, which is adapter in this particular example

cname is component name, which is sap:dropbox in this example. Here, sap is vendor and dropbox is name

</td>
</tr>
<tr>
<td valign="top">

ComponentDisplayName

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

Specifies display name of the component.

</td>
</tr>
<tr>
<td valign="top">

Variant

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Different variants for a specific component type - for example: Sender and Receiver variants of an adapter

</td>
</tr>
<tr>
<td valign="top">

gen:RuntimeComponentBaseUri

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

This attribute specifies the name with which the component is identified. If not added, then the baseUri value is taken from TP \(Transport Protocol\).

Example for specifiying attribute in the CMD:

> ### Sample Code:  
> ```
> <ComponentMetadata ComponentId="ctype::Adapter/cname::sap:sampleadapter/version::1.0.0" 
> ComponentName="sap:sampleadapter" 
> UIElementType="Adapter" IsDefaultGenerator="true" 
> hci:RuntimeComponentBaseUri="dropbox">
> ```
> 
> Example for generated bean.xml containing camel:from
> 
> > ### Sample Code:  
> > ```
> > <camel:from id="MessageFlow_1_1435812482630" uri="dropbox:foo?path=/input/test.txt&amp;
> > method=get&amp;sendEmptyMessageWhenIdle=false&amp;
> > initialDelay=1000&amp;greedy=false&amp;startScheduler=false&amp;timeUnit=MILLISECONDS&amp;
> > useFixedDelay=false&amp;delay=500&amp;runLoggingLevel=TRACE"/>
> > ```



</td>
</tr>
<tr>
<td valign="top">

IsRequestResponse

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

This attribute is used for enabling the component to allow the service call for Request Reply. Default value is false.

Henceforth, you should define it at **variants** level only.

</td>
</tr>
<tr>
<td valign="top">

hci:FirstUriPart

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

Specifies the initial part of the URI. Customer can provide custom values for the first part of the URI string. Default value is 'foo'.

</td>
</tr>
<tr>
<td valign="top">

adapterInstanceID

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

Use cluster lock to prevent same message being processed by different runtime nodes simultaneously.

> ### Note:  
> You must define the following property at the endpoint.
> 
> > ### Sample Code:  
> > ```
> > <Metadata>
> >     <AdditionalMetadata>
> >         <Name>requiredIntegrationFlowProperties</Name>
> >         <Value>adapterInstanceID</Value>
> >         <GuiLabels>
> >             <Label language="en"/>
> >         </GuiLabels>
> >     </AdditionalMetadata>
> > </Metadata>
> > ```
> 
> Use the above parameter as the lock name in the cluster lock API.



</td>
</tr>
</table>

> ### Note:  
> IsDefaultGenerator and Metadata Version must always be true and should never be set to false. Metadata Version attribute is generated with default value as 2.0.



## Variants

This set of metadata allows you to define variants for a component.

**Variants**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Datatype

</th>
<th valign="top">

Cardinality

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Id

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

Provides a unique Id for the component variant.

Example: `ctype::AdapterVariant/cname::sap:dropbox/tp::dropbox/mp::dropbox/direction::Sender`

tp stands for transport protocol

mp stands for message protocol

direction refers to Sender or Receiver system

</td>
</tr>
<tr>
<td valign="top">

Groups

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies collection of attributes defining metadata.

</td>
</tr>
<tr>
<td valign="top">

VariantDisplayName

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

Specifies display name of the variant.

</td>
</tr>
<tr>
<td valign="top">

Input Content

Tag used <InputContent\>

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Input content specifies the type of data the adapter processes.


<table>
<tr>
<th valign="top">

Properties

</th>
<th valign="top">

Attributes/Child Elements

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ContentType

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Actual content type

Supported content types: Xml, String, Boolean, Base64Encoded, Any, Json, Binary, Zip, GZip, Integer, NonXml, None and Text.

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

Output Content

</td>
<td valign="top">

 

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Output content specifies the type of data the adapter produces. Example: XML.


<table>
<tr>
<th valign="top">

Properties

</th>
<th valign="top">

Attributes/Child Elements

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ContentType

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Actual content type

<ManifestEntries\> <ManifestEntry\> <Name\>Import-PackageSupported content types: Xml, String, Boolean, Base64Encoded, Any, Json, Binary, Zip, GZip, Integer, NonXml, None and Text. <ManifestEntries\> <ManifestEntry\> <Name\>Import-Package</Name\> <Value\>com.sap.gateway.core.service.ljs.registry;resolution:=optional,com.sap.gateway.core.ljs;resolution:=optional</Value\> </ManifestEntry\> </ManifestEntries\>

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

Metadata

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Helps to add additonal metadata in the component. Specifies the display name of transport protocol and message protocol.

Example for specifiying attribute in the CMD:

> ### Sample Code:  
> ```
> 
> <Metadata>
>    <AdditionalMetadata>
>          <Name>mp</Name>
>          <GuiLabels guid="e7fa4f1d-ec6a-4248-9752-920ea9616bc9" >
>               <Label language="EN" >AS2</Label>
>                <Label language="DE" >AS2</Label>
>           </GuiLabels>
>    </AdditionalMetadata>
>    <AdditionalMetadata>
>          <Name>tp</Name>
>          <GuiLabels guid="e7fa4f1d-ec6a-4248-9752-920ea9616bc9" >
>               <Label language="EN" >HTTPS</Label>
>                <Label language="DE" >HTTPS</Label>
>           </GuiLabels>
>    </AdditionalMetadata>
> </Metadata>
> 
> ```

> ### Note:  
> You should refer message protocol as *mp* and transport protocol as *tp*.



</td>
</tr>
<tr>
<td valign="top">

ManifestEntries

</td>
<td valign="top">

 

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies which manifest entries you can add in manifest file. You can add or update *Import-Package* entries in manifest files.

Example for specifiying attribute in the CMD:

> ### Sample Code:  
> ```
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

Allowed Headers

</td>
<td valign="top">

 

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies which headers can be passed in the integration flow pipeline from sender component.

Example for specifiying attribute in the CMD:

> ### Sample Code:  
> ```
> 
> <AllowedHeaders>
>  Header1,Header2
> </AllowedHeaders>
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

hci:FirstUriPart

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

Specifies the initial part of the URI. Customer can provide custom values for the first part of the URI string.

</td>
</tr>
<tr>
<td valign="top">

IsRequestResponse

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

This attribute is used for enabling the variant to allow the service call for Request Reply

</td>
</tr>
<tr>
<td valign="top">

supportsPolling

</td>
<td valign="top">

xsd:boolean

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

This attribute depicts if the component has the polling behavior. \(supportsPolling\). It also helps in populating the timer icon at design time when IFlow is decorated. Default value is false. It is applicable for sender channel only.

</td>
</tr>
<tr>
<td valign="top">

AttachmentBehavior

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Attribute

</td>
<td valign="top">

This attribute helps to identify the component behavior towards attachment.

-   Modify - Create or update an attachment

-   Preserve - Pass through for the attachments
-   Drop - Attachment will be lost

If attachment behavior is not specified; system considers that the component lost the attachment.

</td>
</tr>
<tr>
<td valign="top">

ReferencedComponents

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies the reused component to be referred by the adapter.

</td>
</tr>
</table>

> ### Note:  
> If you want to rename a variant id or delete a variant from adapter, first undeploy the adapter with old variants and then deploy updated adapter.
> 
> You can still view the older variants if you do not undeploy the adapter with old variants.



## Tabs

This set of metadata allows you to specify tab pages for the adapter configuration user interface.

**Tabs**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Datatype

</th>
<th valign="top">

Cardinality

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Id

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies the tab identifier.

</td>
</tr>
<tr>
<td valign="top">

GuiLabels

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies a language-specific GUILabel. Sample GUILabel is shown below:

```
<GuiLabels> 
<Label language="EN">Address</Label> 
</GuiLabels> 
```

Here, Label language = "EN" represents that the text of guilabel is in english. Address is the text for the attribute name.

Currently, guilabel supports only English language.

</td>
</tr>
</table>



## Attribute Group

This set of metadata allows you to group adapter attributes.

**Attribute Group**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Datatype

</th>
<th valign="top">

Cardinality

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

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Id

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies the attribute group identifier.

Examples:

`Dropbox Endpoint`

`Dropbox Security Settings`

</td>
</tr>
<tr>
<td valign="top">

AttributeReference

</td>
<td valign="top">

 

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies ReferenceName, ErrorMessage, Restriction, and Description

</td>
</tr>
<tr>
<td valign="top">

GuiLabels

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies a language-specific GUI label.

</td>
</tr>
<tr>
<td valign="top">

Value - Datatype

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Datatype for value

xsd:string

xsd:integer

xsd:boolean

xsd:long

xsd:password

xsd:id

xsd:idref

> ### Note:  
> If an attribute is marked with *xsd:id* in metadata, then its value should be unique across elements of integration flow, during design time.
> 
> If an attribute is marked with *xsd:idref*then it specifies a reference to another resource. If resource path starts with */<folder\_name\>/<resource\_name\>*, then checks will validate if specific resource path exists in *src\\main\\resource* folder of project or not.



</td>
</tr>
</table>

The sample attribute group is shown below:

```

<AttributeGroup id = "Connection Details">
	        <GuiLabels>
		     <Label language="EN">Connection Details</Label>
	        </GuiLabels>
	        
		   <AttributeReference>
		     <ReferenceName>address</ReferenceName>
	          <!-- Restriction tag defines java regular expression for field value -->      
	         <Restriction>Constraint.isValidRegex([A-Za-z]+[0-9_~\\-\\.]*)</Restriction>
	         <!-- This tag defines message to be displayed if field value is invalid -->	
		    <ErrorMessage>Enter a valid address. E.g. /file</ErrorMessage>
		    <!-- Description tag defines tool tip for field value -->		
		    <description>Relative endpoint address on which..</description>
	        </AttributeReference>

	        <AttributeReference>
		    <ReferenceName>wsdlURL</ReferenceName>
		    <Restriction>Constraint.isValidRegex(^(https://){1}(.)+)</Restriction>
		    <ErrorMessage>Enter a valid URL. E.g. /wsdl/abc.wsdl;</ErrorMessage>
		    <description>URL to the WSDL.</description>
	        </AttributeReference>

	        <AttributeReference>
		     <ReferenceName>cxfOnewayRobust</ReferenceName>
		     <description>Used for reliable one-way message exchanges.</description>
	        </AttributeReference> 
</AttributeGroup>

```



## Attribute Reference

**Attribute Reference Table**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Cardinality

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ReferenceName

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">

Specifies that in the CMD there is an attribute definition associated with this reference name.

</td>
</tr>
<tr>
<td valign="top">

description

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">

Brief description of the attribute, which is shown as the tool tip.

</td>
</tr>
<tr>
<td valign="top">

Restriction

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">

Details given below in the table.

</td>
</tr>
<tr>
<td valign="top">

ErrorMessage

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">

If the constraint specified in the restriction tag fails, the system shows the error message set in this tag. If this field is not set, then the system shows a default error message at the time of check failure.

</td>
</tr>
</table>

**List of Constraints that are supported for Restriction tag**


<table>
<tr>
<th valign="top">

Constraint

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

isValidRegex

</td>
<td valign="top">

Method will check a value against a passed regex. Returns true in case value matches regex

> ### Sample Code:  
> ```
> 
> <AttributeReference>
>      <ReferenceName>stepid</ReferenceName>
>      <Restriction>Constraint.isValidRegex([a-zA-Z0-9]+)</Restriction>
>      <ErrorMessage>StepID not defined for Persist Message step</ErrorMessage>
> </AttributeReference>
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

isAlphaNumeric

</td>
<td valign="top">

Checks whether the pass value is alphanumeric

</td>
</tr>
<tr>
<td valign="top">

isStartsWithLetter

</td>
<td valign="top">

Checks the passed value starts with Letter

</td>
</tr>
<tr>
<td valign="top">

isValidURIString

</td>
<td valign="top">

Returns true if it is valid URI String. It can start with http\(s\), ftp, file or ldap

</td>
</tr>
<tr>
<td valign="top">

isValidXMLString

</td>
<td valign="top">

Returns true if passed string is a valid XML String

</td>
</tr>
<tr>
<td valign="top">

isValidNCName

</td>
<td valign="top">

Return true if passed string value is valid NCName

</td>
</tr>
<tr>
<td valign="top">

isValidXpath

</td>
<td valign="top">

Returns true if passed string value is valid xpath expression

</td>
</tr>
</table>



## Attribute Metadata

This set of metadata allows you to define the details of all adapter attributes. This includes the definition of fixed values for input help, and the kind of user interface element used for an adapter attribute \(for example if it is a checkbox or a dropdown list\).

The sample attribute metadata should be as shown below:

```
<AttributeMetadata>
              <Name>address</Name>
              <Usage>true</Usage>
              <Default>/BSN/paymentOrder</Default>
              <DataType>xsd:string</DataType>
              <isparameterized>true</isparameterized>
              <Length>200</Length>
              <FixedValues>
                     <FixedValue>
                           <Value>Atleast Once</Value>
                           <GuiLabels>
                                  <Label language="EN">Atleast Once</Label>
                           </GuiLabels>
                     </FixedValue>
              </FixedValues>
              <GuiLabels>
                     <Label language="EN">Address</Label>
              </GuiLabels>
       </AttributeMetadata>

```

**Attribute Metadata**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Datatype

</th>
<th valign="top">

Cardinality

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

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies the parameter id.

Example: `address`

</td>
</tr>
<tr>
<td valign="top">

Usage

</td>
<td valign="top">

xsd:boolean

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies if the field is mandatory or not. If the value is true then usage of field is mandatory. If the value is false then usage of field is not mandatory.

</td>
</tr>
<tr>
<td valign="top">

Default

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies a default value.

Example: <code><code>/BSN/paymentOrder</code></code> 

</td>
</tr>
<tr>
<td valign="top">

Datatype

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies the datatype for the value.

Examples:

`xsd:string`

`xsd:integer`

</td>
</tr>
<tr>
<td valign="top">

Length

</td>
<td valign="top">

xsd:integer

</td>
<td valign="top">

 

</td>
<td valign="top">

Specifies the maximum character length for field values.

</td>
</tr>
<tr>
<td valign="top">

Minlength

</td>
<td valign="top">

xsd:integer

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies the minimum character length for field values.

</td>
</tr>
<tr>
<td valign="top">

HelpService

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Helps to configure specified resources in adapters.

Example for specifiying attribute in the CMD:

> ### Sample Code:  
> ```
> 
> <HelpService>
>  <HelpServiceName>
>   resourceLookupService
>  </HelpServiceName>
>  <HelpServiceQueryAttributes>
>   <HelpServiceQueryAttribute>
>    <Name>
>     Type
>    </Name>
>    <Value>
>     xml
>    </Value>
>   </HelpServiceQueryAttribute>
>   <HelpServiceQueryAttribute>
>    <Name>
>     ResourceLocation
>    </Name>
>    <Value>
>     edmx
>    </Value>
>   </HelpServiceQueryAttribute>
>  </HelpServiceQueryAttributes>
> </HelpService> 
> 
> ```

Once you add the above code, then a *Browse* button gets enabled. You can click on the button and select resource file from the project of file system.

*ResourceType* specifies resource extension. Currently, only one extension can be specified.

*ResourceLocation* specifies relative path to project from where files are read or written.

</td>
</tr>
<tr>
<td valign="top">

GUILabel

</td>
<td valign="top">

 

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies a language-specific GUI label.

</td>
</tr>
<tr>
<td valign="top">

FixedValue\(s\)

</td>
<td valign="top">

 

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies a fixed list of allowed values.


<table>
<tr>
<th valign="top">

Properties

</th>
<th valign="top">

Attributes/Child Elements

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

FixedValue

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Specifies fixed list of allowed values. Multiple FixedValue tags together are called a combo.

</td>
</tr>
<tr>
<td valign="top">

isEditable

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

If the element is set to 'true', then the dropdown and combo fields are editable.

</td>
</tr>
<tr>
<td valign="top">

Sort

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

If the element is set to 'true', then the values are arranged either in ascending or descending order. Use the following formats to arrange the values:

-   To arrange the values in ascending order, use `<Sort order="ascending">true</Sort>`

-   To arrange the values in descending order, use `<Sort order="descending">true</Sort>`


> ### Note:  
> If the element is set to 'false', then the values are arranged as per the order defined in the cmd.



</td>
</tr>
</table>



</td>
</tr>
</table>

**Attribute Reference Table**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Cardinality

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

AttributeName

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Name of the attribute

</td>
</tr>
<tr>
<td valign="top">

AttributeValue

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Value of the attribute

</td>
</tr>
<tr>
<td valign="top">

AndCondition

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Attribute Reference Property

This is complex constraint that is used when there are two or more complex or basic constraints that need to be satisfied to achieve certain criteria.

Example of Complex condition

> ### Sample Code:  
> ```
> <AndCondition>
> <EditCondition>
>                 <AttributeName>reference1</AttributeName>
>                 <AttributeValue>reference1value</AttributeValue>
> </EditCondition>
> <EditCondition>
>                 <AttributeName>reference2</AttributeName>
>                 <AttributeValue>reference2value</AttributeValue>
> </EditCondition>
> </AndCOndition>
> 
> ```

As you can see in the above example AndCondition is complex condition that contains two or more EditConditions\(basic conditions\) and for the condition to be satisfied both of these basic conditions is satisfied.

</td>
</tr>
<tr>
<td valign="top">

OrCondition

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Attribute Reference Property

This is complex constraint that is used when satisfaction of any one of the nested complex or basic constraint is required to achieve certain criteria

The structure of OrCondition is similar to And condition, with only change from <AndCondition\> to <OrCondition\>.

</td>
</tr>
<tr>
<td valign="top">

NotCondition

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Attribute Reference Property

This is complex constraint that is mostly used with other complex constraints, this constraint reverses the result returned by the nested complex or basic condition

Not condition can contain only one edit condition but multiple complex conditions. These complex conditions can be used with each other.

> ### Sample Code:  
> ```
> <AndCondition>
>                  <OrCondition>
>                          <EditCondition></EditCondition>
>                          <EditCondition></EditCondition>
>                  </OrCondition>
>                   <NotCondition>
>                          <EditCondition></EditCondition>
>                  </NotCondition>
>         </AndCondition>
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

EditCondition

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Attribute Reference Property

Constraint to be executed, this is on top of base constraint defined at Attribute Level Environment Variables: If the Attribute Name starts with $ then next part is considered as an Environment variable. There can be two types of variables:

a\) $PROFILE.NAME - environment variables starting with profile are properties fetched on profile configured for project

b\) $ENV.VARIABLE - environment variables starting with env are system properties for vm

</td>
</tr>
<tr>
<td valign="top">

AttributeBehavior

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">

Child Element

</td>
<td valign="top">

If you assign *AttributeBehavior* as `SecureAlias` for a particular field, then the field refers to alias of security parameter artifact.

</td>
</tr>
</table>

**Attribute Table Metadata**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Cardinality

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

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Usage

</td>
<td valign="top">

xsd:boolean

</td>
<td valign="top">



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

HelpService

</td>
<td valign="top">



</td>
<td valign="top">

Child Element

</td>
<td valign="top">

Helps to configure ceritificate in adapters.

Example for specifiying attribute in the CMD:

> ### Sample Code:  
> ```
> 
> <HelpService>
>  <HelpServiceName>
>   certificateLookupService
>  </HelpServiceName>
> </HelpService> 
> 
> ```

Once you add the above code, then a *Browse* button gets enabled. You can click on the button and select certificate file.

This attribute supports *\*.crt* and *\*.cer* types of certificates only.

</td>
</tr>
<tr>
<td valign="top">

AttributeReference

</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

Specifies reference name that is header of the column.

> ### Note:  
> Each reference name constitutes to one column in the table.



</td>
</tr>
<tr>
<td valign="top">

Guilabels

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the label of the table.

</td>
</tr>
</table>

The sample attribute table metadata should be as shown below:

> ### Sample Code:  
> ```
> <AttributeTableMetadata>
>             <Name>clientCertificates</Name>
>             <Usage>true</Usage>
>             <GuiLabels guid="01c2bd59-8dd1-4efb-b795-869851eb979b">
>                 <Label language="EN">Client Certificate Authorization</Label>
>                 <Label language="DE">Client Certificate Authorization</Label>
>             </GuiLabels>
>             <AttributeReference>
>                 <ReferenceName>clientCertificate.subjectDN</ReferenceName>
>             </AttributeReference>
>             <AttributeReference>
>                 <ReferenceName>clientCertificate.issuerDN</ReferenceName>
>             </AttributeReference>
>         </AttributeTableMetadata>
> 
> ```

> ### Note:  
> -   You must not use any special character in the table fields.
> -   You can reload component metadata in the following three ways:
>     -   You can reopen eclipse tool.
> 
>     -   You can reconnect to server.
> 
>     -   You can use ![](images/Icon_5f128d1.png) icon \(on eclipse toolbar\) to manually download it.

