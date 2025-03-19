<!-- loio7c00e9bf1d0e41d99e4ba5d770e9bd4a -->

# Naming Conventions

The naming conventions defined in the following chapter are meant as a recommendation. Naming conventions are subjective and can be applied in multiple ways. However, the guidelines defined here are a good starting point and, if necessary, can be extended or modified.



It's important to have a logical system behind the naming patterns applied. This system helps you to quickly organize and identify all the numerous objects related in an integration environment. In the following guidelines, the case for an organization with multiple subsidiaries is considered. In case some objects depend on a specific subcompany, the placeholder `<Business Unit>` is used. However, when the objects don't specify a business unit but a whole group, then use the constant `<Global>` instead. The multicompany use case can be extrapolated to other distributions, like divisions, countries/regions, areas, and so forth. If this classification isn't needed, it can be omitted. Also, a good practice is to use CamelNotation in any of the placeholders used. The square brackets indicate an optional part of the naming convention, which may not be required in all use cases.



### Integration Packages

The Integration Package is the folder containing or organizing your integration content \(integration flows, value mappings, APIs, and so forth\). Right now, an integration package is the minimum unit that can be transported. See [Creating an Integration Package](creating-an-integration-package-9126d79.md).

The naming convention for custom integration packages is as follows:

`[<CompanyPrefix>]_<BusinessUnit|Global> _<IntegrationScenario>_[<InvolvedSystems>]_[<AdditionalInformation>]` 

Packages that contain reusable objects across different integration packages should be named by a standardized identifier, for example, COMMON, REUSE.

Example:

`[<CompanyPrefix>]_<BusinessUnit|Global>_<IntegrationScenario>_COMMON`

**Naming Guidelines for Custom Integration Package**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Tenant

The Integration Package is the uppermost unit in Cloud Integration. The name must be unique for the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Company Prefix \(Optional\)*: 3 or 4 letter prefix for your company. Ease distinction between own custom-built content and pre-packaged content from SAP and partners.

-   *Business Unit*: Business Unit to which the package belongs to \(example: SubsidiaryA\)

-   *Global*: Constant used if the package isn't bound to a specific business unit, but to the entire group.

-   *Integration Scenario*: The integration scenario groups the objects of the package by end-to-end scenarios or business processes \(example: OrderIntegration, E-Invoicing, HR\).

-   *Involved Systems \(Optional\)*: In some cases, it's helpful to have information about the systems involved. However, never use technical nor environment-dependent names, but generic names \(example: Ariba, SuccessFactors\).

-   *Additional Information \(Optional\)*: Country key \(2-digit\), Object \(in CamelCase notation\), or any other description not included in the integration scenario, which is needed to specify the package \(example: DE/GB/CH, Payroll, and so forth\)

-   *Integrated Products*: Two or more products between which the integration takes place.


In case, an integration package is to be copied, then follow the next rules: Use the tag `<AdditionalInformation>` at the end to differentiate the new package from the copied one. For example, use the country key.

</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `XYZ_Global_CentralSourcing_Ariba` 

-   `XYZ_SubsidiaryB_PayrollReplication` 

-   `Global_HR_SuccessFactors` 

-   `SubsidiaryA_CustomerInformation_CRM` 

-   `Global_ErrorHandling_COMMON` 




</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 255.

</td>
</tr>
</table>

> ### Note:  
> For standard packages, you can't define names as they are already predefined. If you need more than 1 version of the same standard package, differentiate between your standard packages with the help of suffixes when copying them. In this case, the same naming conventions apply as for custom packages. Use abbreviations to shorten package names to keep them readable.
> 
> Examples:
> 
> -   `SAP SuccessFactors - Employee Availability Integration with SAP S/4HANA Cloud.SubsidiaryA_HR_DE`
> 
> -   `SAP SuccessFactors - Employee Availability Integration with SAP S/4HANA Cloud.Global_HR`



### Integration Flow

An integration flow allows you to specify how a message is processed on a tenant.

The naming convention is as follows:

`BusinessUnit|Global>_<BusinessObject>_[<Sender>_to_<Receiver>]_[<AdditionalInformation>]`

**Naming Guidelines for Integration Flow**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Package/Tenant

Integration flows are organized in integration packages. However, the ID must be unique for the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Business Unit*: Business Unit to which the package belongs to \(Example: SubsidiaryA\)

-   *Global*: Constant used if the package isn't bound to a specific business unit, but to the entire group

-   *Sender\_to\_Receiver \(Optional\)*: In some cases, it's helpful to have information of the sender and receiver of an integration flow. However, never use technical nor environment-dependent names, but generic names \(example: S4\_to\_SuccessFactors\).

-   *Sender/Receiver*: In some cases, it's helpful to have information of the sender or receiver of an integration flow. However, never use technical nor environment-dependent names, but generic names \(example: SAP S/4HANA, SAP SuccessFactors, BW\).

-   *Additional Information \(Optional\)*: Country key \(2-digit\), Identifier or any other additional information relevant for the integration flow




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `SubsidiaryA_PurchaseOrderReplication_S4_to_Ariba_US`

-   `Global_PlanningData_ID00312`

-   `BusinessUnitA_PayrollReplication_SuccessFactors_to_ERP`

Standard integration flows maintain their original names.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 120.

</td>
</tr>
</table>



### Script Collection

A Script Collection contains a bundle of scripts. Create a script collection within an integration package so that you create scripts in it and then reuse the bundle of scripts across any number of integration artifacts in your tenant. See [Creating a Script Collection](creating-a-script-collection-824bff0.md)

The naming convention is as follows:

`SC_<BusinessUnit|Global>_<Description>`

**Naming Guidelines for Script Collection**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Package

The script collections are organized in integration packages. The id must be unique for the entire tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Business Unit*: Business Unit to which the script collection belongs \(example: SubsidiaryA\)

-   *Global*: Constant used if the script collection isn't bound to a specific business unit, but to the entire group

-   *Description*: Meaningful description of the intended use of the script collection




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `SC_SubsidiaryA_ErrorHandling`

-   `SC_Global_MappingUtils`


Standard Integration Flows maintain their original names.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 120.

</td>
</tr>
</table>



### OData, SOAP, and Rest APIs

Cloud Integration supports API-based integration development exposing integration flows as either OData, SOAP, or RESTful services. For example, OData APIs can be consumed by SAP Fiori apps, SAP Mobile Services, or any other custom app, to implement user-centric scenarios. See [Develop API-Based Integration Artifacts](develop-api-based-integration-artifacts-997501d.md).

The naming convention is as follows:

`<BusinessUnit|Global>_<Resource>_<SourceSystem>_[<AdditionalDescription>]` 

**Naming Guidelines for API-Based Integration Development**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Package/Tenant

The APIs are organized in integration packages. However, the ID must be unique for the entire tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Business Unit*: Business Unit to which the package belongs to \(example: SubsidiaryA\)

-   *Global*: Constant used if the package isn't bound to a specific business unit, but to the entire group

-   *BusinessProcess*: Business process where all the objects of the package can be classified \(example: Purchasing, HumanResources, MM, OrderToCash or any other possible area\)

-   *Sender/Receiver*: In some cases, it's helpful to have information of the sender or receiver of an integration flow. However, never use technical nor environment-dependent names, but generic names \(example: SAP S/4HANA, SAP SuccessFactors, BW\).

-   *InterfaceDescription*: Use a meaningful name in camel notation, including object/business case. As OData usually include several operations, it is not needed to include the operation \(example: PurchaseOrder, PlanningData, EmployeeAbsence, Payroll\). In case additional information is still needed to identify the Integration Flow, add it here \(for example, Country, Interface Id, …\).




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `SubsidiaryA_MM_PurchaseOrder`

-   `SubsidiaryA_PM_S4Hana_PlanningDataID00123`

-   `SubsidiaryA_FI_SuccessFactors_PayrollDE`

-   `Global_MM_PurchaseOrder`



</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 120.

</td>
</tr>
</table>



### Participants in Integration Flows

You define a participant of an integration flow as a sender or receiver. The senders and receivers typically represent the customer systems that are connected to the tenant and exchange messages with each other. See [Elements of an Integration Flow](elements-of-an-integration-flow-e49dbee.md).

The naming convention is as follows:

-   `<IntegrationType>_<Application>`

**Naming Guidelines for Sender/Receiver**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Flow

Participants of different integration flows can have the same name. This naming convention for participants is just for documentation and readability purposes. It has no technical impact during deployment and doesn't collide with participants of other already deployed integration flows.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

Integration Type:

-   OP: On-premise system

-   B2B: For Business Partners

-   CP: For Cloud Providers


Application:

Generic name in capital letters for the systems involved in the scenario. No technical names. Examples: SAP S/4HANA, SAP ERP, SAP SuccessFactors, SAP Cloud for Customer, SAP Solution Manager.

</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `CP_SFSF`

-   `OP_ERP`

-   `B2B_WEBSHOP`




</td>
</tr>
</table>



### Channels

An integration flow channel allows you to specify which technical protocols are to be used to connect a sender or a receiver to the tenant. See [Configure Adapter in Communication Channels](configure-adapter-in-communication-channels-1f06633.md).

The naming convention is as follows:

-   `<Protocol>_<Direction>_<OperationDefinition>`


**Naming Guidelines for Channels**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Flow

Channels of different integration flows can have the same name.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Protocol*: SOAP, HTTP, SFTP… \(in capital letters\)

-   *Direction*: SND or RCV

-   *OperationDefinition*: Use a meaningful name in camel notation, including object/business case and operation \(examples: PurchaseOrderCreation, PlanningDataRead, EmployeeAbsenceSend, PayrollReplication\)




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `SOAP_SND_PurchaseOrderRead`

-   `HTTP_RCV_PurchaseOrderCreate`

-   `RFC_SND_EmployeeGroupLookup`




</td>
</tr>
</table>



### Mappings

Mappings are programs that enable you to define an association between fields of messages with different structuring. See [Working with Mapping](working-with-mapping-68d816a.md).

The naming convention is as follows:

-   `<Mapping Type>_<SourceMessage>[<Format>]_to_<TargetMessage>[<Format>]`

-   `<Mapping Type>_<Message>[<Format>]_<Transformation>` \(if source and target message is the same, but a transformation is needed\)


**Naming Guidelines for Mappings**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Flow

Mappings of different integration flows can have the same name.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Mapping Type*: OM \(Operation Mapping – just if imported from SAP Process Orchestration\), MM \(Message Mapping\), XSL \(XSLT mapping\)

-   *Source/Target Message*: Meaningful name used to identify the message. Similar to Message Type in SAP Process Orchestration. If the object has several operations, then add it.

-   *Transformation*: Description of the transformation needed. Examples: Split, DateConversion, …

-   *Format*: Format type of the message \(optional\). Example: JSON|XML




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `MM_PurchaseOrderERP_to_PurchaseOrderC4C`

-   `MM_PurchaseOrderCreateERP_to_PurchaseOrderCreateC4C`

-   `MM_PurchaseOrderERPXML_to_PurchaseOrderC4CJSON`

-   `XSL_PayrollIndia_to_PayrollUS`

-   `XSL_PurchaseOrder_Split`

-   `XSL_PurchaseOrderXML_Split`




</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 120.

</td>
</tr>
</table>



### Value Mappings

A value mapping is an artifact that acts as a bidirectional lookup table. See [Creating Value Mapping](creating-value-mapping-25eff9b.md).

The naming convention is as follows:

`VM_<BusinessUnit|Global>_<Object>_[<AdditionalInformation>]`

**Naming Guidelines for Value Mappings**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Package

The value mappings are organized in integration packages. The id must be unique for the entire tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Business Unit*: Business Unit to which the value mapping belongs \(example: SubsidiaryA\)

-   *Global*: Constant used if the package isn't bound to a specific business unit, but to the entire group

-   *Object*: Refers to the specific object or set of data of the value mapping, \(example: CountryKeys, UnitOfMeasurement, CurrencyConversion\)

-   *Additional Information*: Meaningful description if needed to split the value mapping




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `VM_SubsidiaryA_UnitConversions`

-   `VM_SubsidiaryA_CountryKeys`

-   `VM_Global_CurrencyConversions`




</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 120.

</td>
</tr>
</table>



### Scripts

Scripts are tasks inside an integration flow to execute custom Java script or Groovy script for message processing. See [Define a Local Script Step](define-a-local-script-step-03b32eb.md).

The naming convention is as follows:

-   Logging script: `log<BusinessObject>_<context>`

-   Transformation script: `<TypeOfScript>_<operation|purpose><BusinessObject>`


**Naming Guidelines for Scripts**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Flow

Scripts of different integration flows can have the same name.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Context*: Context in which the script appears within the integration flow. Example: after mapping, before mapping, ...

-   *Operation/Purpose*: set, get, check,… or meaningful name for the function \(in lowercase\)

-   *Business Object*: Name of the object to be handled. Example: MessageID, Content, Purchase Order, … \(in CamelCase notation\)

-   *Type of Script*: Groovy, JavaScript




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   Logging script: `logPayload_afterMappping`

-   Transformation script: `groovy_setMessageID, jscript_checkContent`




</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 120.

</td>
</tr>
</table>



### Endpoints: Generic Integration Flows

Endpoints are the Url to trigger a specific integration flow.

The naming convention is as follows:

`/<BusinessUnit|Global>/<BusinessProcess>/<InterfaceDescription>`

**Naming Guidelines for Endpoints: Generic Integration Flow**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Tenant

Endpoints must be unique for the entire tenant. The address entered as url can be repeated in sender channels, if they have different protocols, as the protocol forms also the url.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Business Unit*: Business Unit to which the integration flow belongs to \(Example: SubsidiaryA\)

-   *Global*: Constant used if the integration flow isn't bound to a specific business unit, but to the entire group

-   *BusinessProcess*: Business process where all the objects of the package can be classified \(example: Purchasing, HumanResources, MM, OrderToCash or any other possible area\)

-   *InterfaceDescription*: Use a meaningful name in camel notation, including object/business case and operation \(examples: PurchaseOrderCreation, PlanningDataRead, EmployeeAbsenceSend, PayrollReplication\). In case additional information is still needed to identify the Integration Flow, then add it here \(examples:. Country, Interface Id…\).




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `/SubsidiaryA/Purchasing/PurchaseOrderReplication`

-   `/Global/MM/PurchaseOrderReplication`




</td>
</tr>
</table>



### Endpoints: Partner Integration Flow

Endpoints are the Url to trigger a specific integration flow.

The naming convention is as follows:

`/<BusinessUnit|Global>/<Partner>/<BusinessProcess>/<InterfaceDescription>`

**Naming Guidelines for Partner Integration Flow**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Tenant

Endpoints must be unique for the entire tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

This can be used when different partners should call different integration 2flows for the same functionality.

-   *Business Unit*: Business Unit to which the integration flow belongs to \(Example: SubsidiaryA\)

-   *Global*: Constant used if the integration flow isn't bound to a specific business unit, but to the entire group

-   *Partner*: Partner identification

-   *BusinessProcess*: Business process where all the objects of the package can be classified \(examples: Purchasing, HumanResources, MM, OrderToCash or any other possible area\)

-   *InterfaceDescription*: Use a meaningful name in camel notation, including object/business case and operation \(examples: PurchaseOrderCreation, PlanningDataRead, EmployeeAbsenceSend, PayrollReplication\). In case additional information is still needed to identify the integration flow, add it here \(examples: Country, Interface Id, …\).




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `/SubsidiaryA/PartnerB/Purchasing/PurchaseOrderReplication`

-   `/Global/PartnerB/Purchasing/PurchaseOrderReplication`


Standard Integration Flows maintain their original names.

</td>
</tr>
</table>



### Headers & Properties

Headers and properties are parameters that allow you to define sophisticated ways of controlling message processing at runtime. See [About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md).

The naming convention is as follows:

-   Custom Headers & Properties: <camelCase\>

-   Standard Headers: maintain expected notation


**Naming Guidelines for Headers & Properties**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Flow

Headers and properties of different integration flows can have the same name.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

CamelCase: Meaningful name

</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   Custom Headers & Properties: `messageID, elementCounter`

-   Standard Headers: `Content-Type, X-CSRF-Token`




</td>
</tr>
</table>



### Other Elements in Integration Flows

Those are elements that can be used in an integration flow, but they aren't included in the sections above. See [Elements of an Integration Flow](elements-of-an-integration-flow-e49dbee.md).

The naming convention is as follows:

-   `<Description>`


**Naming Guidelines for Other Elements in Integration Flows**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Integration Flow

Elements of different integration flows can have the same name.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

Description: Meaningful step description in camelCase

</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `setContentType`

-   `saveLastExecutionDate`

-   `decryptMessage`

-   `transformMessageCSV2XML`




</td>
</tr>
</table>



### Security Artifacts

Security artifacts are the credentials needed to connect to an external system.

The naming convention is as follows:

-   `<BusinessUnit|Global>_<SystemIdentifier>_<AdapterType>_<TypeOfMaterial>`

-   Business Partner System: `<System>_<Partner>_<AdapterType>_<TypeOfMaterial>`


**Naming Guidelines for Security Artifacts**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Tenant

Security artifacts must be unique in the whole tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Business Unit*: Business unit to which the artifact belongs to \(Example: SubsidiaryA\)

-   *Global*: Constant used if the artifact isn't bound to a specific business unit, but to the entire group

-   *System Identifier*: As the security artifacts are environment-dependent \(no transportable objects\), it is helpful to use some kind of technical system id \(like SAPSID\).

-   *Adapter Type*: HTTP, SOAP, OData

-   *Type of Material*: UserCredentials, SAP SuccessFactors, OpenConnectors, OAuth, SecureParameter

-   *Partner Identification*: Partner identification




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `Business UnitA_QASCLNT100_OData_SecureParameter`

-   `SFPART022906_SOAP_SuccessFactors`

-   `QASCLNT100_PartnerA_SOAP_UserCredentials`

-   `Global_QASCLNT100_OData_OAuth`




</td>
</tr>
<tr>
<td valign="top">

*Maximum Character Length* 

</td>
<td valign="top">

The maximum character length for this parameter is 150.

</td>
</tr>
</table>



### Custom Roles

Custom roles can be used in runtime during inbound authorization of an integration flow \(User Roles\) or during monitoring to protect the business data of a subset of artifacts \(Access Policies used\).

See: [Managing User Roles](managing-user-roles-4e86f0d.md) and [Creating Custom Roles for Access Policies](creating-custom-roles-for-access-policies-7db3c87.md).

The naming convention is as follows:

-   Runtime Roles: `ESBMessaging.send_<Expression/InterfaceDescription/QueueName>_RTCustomRole`

-   Monitoring Roles: `<Expression/InterfaceDescription>_AccessPolicy_MONCustomRole`


**Naming Guidelines for Custom Roles**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Tenant

Custom roles must be unique in the whole tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

If the custom role applies just to 1 integration flow, use InterfaceDescription \(see interface description of integration flow\) or QueueName.

Expression: Meaningful expression describing all the integration flows or queues included in the role, in case the custom role applies to a group of integration flows or queues.

</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `ESBMessaging.send_EmployeePayrollRead_RTCustomRole`

-   `ESBMessaging.send_HRData_RTCustomRole`

-   `EmployeePayrollRead_AccessPolicy_MONCustomRole`

-   `HRData_AccessPolicy_MONCustomRole`




</td>
</tr>
</table>



### Message Queues

Messaging Queues enable persistence and asynchronous messaging in integration flows. See [Managing Message Queues](managing-message-queues-cdcce24.md).

The naming convention is as follows:

`<AdapterType>_<IntegrationFlowID>`

**Naming Guidelines for Message Queues**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Tenant

Message Queues must be unique for the entire tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Adapter Type*: AS2, AS4, XI, JMS

    For AS2, AS4 and XI, the queue name is generated automatically.

-   *Integration Flow ID*: See Integration Flow. For JMS, use the ID of the integration flow pushing the message to the queue.




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `AS2_BusinessUnitA_MM_PurchaseOrderReplication_AS2_5b790cac_0cb0_3643_ad87_ba1a0fe1df53`

-   `AS4_BusinessUnitA_MM_PurchaseOrderReplication_c13ee92d_fdea_33c5_8a04_daf49a26abf3`

-   `JMS_BusinessUnitA_MM_PurchaseOrderReplication`




</td>
</tr>
</table>



### JDBC Data Sources

JDBC Data Sources allow persistence in an external data base. See [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

The naming convention is as follows:

-   `<TypeOfDB>_<DataBaseID>`


**Naming Guidelines for JDBC Data Sources**


<table>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Tenant

JDBC Data Sources must be unique for the entire tenant.

</td>
</tr>
<tr>
<td valign="top">

*Definition*

</td>
<td valign="top">

-   *Type Of DB*: SAP HANA, ASE

-   *DataBaseID*: DataBase ID




</td>
</tr>
<tr>
<td valign="top">

*Example*

</td>
<td valign="top">

-   `HANA_DataBase1`

    `ASE_DataBase2`




</td>
</tr>
</table>

