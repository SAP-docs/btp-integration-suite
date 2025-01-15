<!-- loiob927e0182df04208ace0f15c66073317 -->

# Archiving Payload Data

Archive your sender and receiver interchange payloads.

The feature *Archive Sender/Receiver Payload Data* allows you to archive your interchange payloads to backend CMIS system. This is how it works:

-   Each tenant will have one B2B archiving job assigned to it. The initial status of the job would be set to inactive.

-   To activate this, follow the steps mentioned below:
    -   Send a **POST** call to the URL: `https://path-to-odata-api/api/v1/activateB2BArchivingConfiguration` where `path-to-odata-api` is specific to the user's environment.

    -   This call is sent to enable the archiving function. If successful, the call returns a 200 response code with a message stating the activation was successful. You can then enable the checkbox *Archive Sender Payload*/*Archive Receiver Payload* field provided in your agreement for the sender/receiver interchange respectively under *B2B Scenarios* tab.
    -   To check whether archiving is currently configured on a tenant, use the OData API that allows you to query the message processing logs. You can do this by sending a **GET** call to te URL: `https://path-to-odata-api/api/v1/B2BArchivingConfigurations('tenant-name')` where `path-to-odata-api` is specific to the user's environment.

-   The archiving job will be executed once a day and the status of the archiving job can be monitored in the *Monitor* tab. You can also check the overall status of an archiving schedule job execution by calling the KPI OData API `https://path-to-odata-api/api/v1/B2BArchivingKeyPerformanceIndicators` where `path-to-odata-api` is specific to your environment.
-   Each archived interchange will be compressed to one zip file with the naming convention `Business_Document_Data_Content<Interchange ID>.zip`.
-   The archiving job, once activated will archive the payload data upto 7 days before the date of activation. Other payload data created before this time period will not be archived.
-   Each archived interchange is sent to CMIS system in one transaction.
-   There is no retry mechanism for the failed archived interchanges. These interchanges have to wait for the next archiving schedule job execution.
-   Once the archiving job is completed, you need to check your CMIS system to check the archived data as the tenant does not display this information.
-   The archiving feature is supported by the generic integration flow from version 2.3.0 and above.
-   Once the interchange arhive is completed, the monitor backend database will store the data for 90 days post which the data will be deleted automatically. To monitor the archiving status, see [Update Agreements](update-agreements-b5e1fc9.md)

.



<a name="loiob927e0182df04208ace0f15c66073317__section_jrz_rvc_zdc"/>

## CMIS Search Properties

To support the search in CMIS for the archived B2B payload, the following interchange fields are provided as searchable attributes in CMIS:

-   All the standard interchange fields available in B2B Monitor
-   The custom search fields \(maximum of 10\)

The standard interchange search fields available in B2B Monitor and their corresponding CMIS search fields are displayed in a table below:

**CMIS Search Fields**


<table>
<tr>
<th valign="top">

B2B Monitor Search Field

</th>
<th valign="top">

CMIS Search Field

</th>
</tr>
<tr>
<td valign="top">

Status

</td>
<td valign="top">

OverallStatus

</td>
</tr>
<tr>
<td valign="top">

Interchange

</td>
<td valign="top">

Id

</td>
</tr>
<tr>
<td valign="top">

Processing Status

</td>
<td valign="top">

ProcessingStatus

</td>
</tr>
<tr>
<td valign="top">

Receiver Functional Acknowledgement Status

</td>
<td valign="top">

ReceiverFunctionalAckStatus

</td>
</tr>
<tr>
<td valign="top">

Interchange Creation Date Time

</td>
<td valign="top">

DocumentCreationTime

</td>
</tr>
<tr>
<td valign="top">

Receiver Technical Acknwoledgement Status

</td>
<td valign="top">

ReceiverTechnicalAckStatus

</td>
</tr>
</table>

**General Information**


<table>
<tr>
<th valign="top">

B2B Monitor Search Field

</th>
<th valign="top">

CMIS Search Field

</th>
</tr>
<tr>
<td valign="top">

Started At

</td>
<td valign="top">

StartedAt

</td>
</tr>
<tr>
<td valign="top">

Interchange Completion Date Time

</td>
<td valign="top">

EndedAt

</td>
</tr>
<tr>
<td valign="top">

Transaction Type

</td>
<td valign="top">

TransactionTypeName

</td>
</tr>
<tr>
<td valign="top">

Agreement Type Name

</td>
<td valign="top">

AgreementTypeName

</td>
</tr>
<tr>
<td valign="top">

Interchange Name

</td>
<td valign="top">

InterchangeName

</td>
</tr>
<tr>
<td valign="top">

Interchange Direction

</td>
<td valign="top">

InterchangeDirection

</td>
</tr>
<tr>
<td valign="top">

Archiving Status

</td>
<td valign="top">

ArchivingStatus

</td>
</tr>
</table>

**Custom Search Attributes**

In CMIS, for custom search attributes, the search fields are maintained as *SearchField<Value1\>*…... *SearchField<Value10\>* where `Value1` represents the custom search terms that you have created in the system.

**Sender**


<table>
<tr>
<th valign="top">

B2B Monitor Search Field

</th>
<th valign="top">

CMIS Search Field

</th>
</tr>
<tr>
<td valign="top">

Message Type

</td>
<td valign="top">

SenderMessageType

</td>
</tr>
<tr>
<td valign="top">

Gourp Control Number

</td>
<td valign="top">

SenderGroupControlNumber

</td>
</tr>
<tr>
<td valign="top">

Document Standard

</td>
<td valign="top">

SenderDocumentStandard

</td>
</tr>
<tr>
<td valign="top">

Interchange Control Number

</td>
<td valign="top">

SenderInterchangeControlNumber

</td>
</tr>
<tr>
<td valign="top">

Message Number

</td>
<td valign="top">

SenderMessageNumber

</td>
</tr>
<tr>
<td valign="top">

Sender Name

</td>
<td valign="top">

SenderTradingPartnerName

</td>
</tr>
<tr>
<td valign="top">

System ID

</td>
<td valign="top">

SenderSystemId

</td>
</tr>
<tr>
<td valign="top">

Adapter Type

</td>
<td valign="top">

SenderAdapterType

</td>
</tr>
<tr>
<td valign="top">

Sender Identifier

</td>
<td valign="top">

AgreedSenderIdentifierAtSenderSide

</td>
</tr>
<tr>
<td valign="top">

Sender Identifier Qualifier

</td>
<td valign="top">

AgreedSenderIdentifierQualifierAtSenderSide

</td>
</tr>
<tr>
<td valign="top">

Receiver Identifier

</td>
<td valign="top">

AgreedReceiverIdentifierAtSenderSide

</td>
</tr>
<tr>
<td valign="top">

Receiver Identifier Qualifier

</td>
<td valign="top">

AgreedReceiverIdentifierQualifierAtSenderSide

</td>
</tr>
<tr>
<td valign="top">

Sender Communication Partner Name

</td>
<td valign="top">

SenderCommunicationPartnerName

</td>
</tr>
</table>

**Receiver**


<table>
<tr>
<th valign="top">

B2B Monitor Search Field

</th>
<th valign="top">

CMIS Search Field

</th>
</tr>
<tr>
<td valign="top">

Message Type

</td>
<td valign="top">

RecieverMessageType

</td>
</tr>
<tr>
<td valign="top">

Gourp Control Number

</td>
<td valign="top">

RecieverGroupControlNumber

</td>
</tr>
<tr>
<td valign="top">

Document Standard

</td>
<td valign="top">

RecieverDocumentStandard

</td>
</tr>
<tr>
<td valign="top">

Interchange Control Number

</td>
<td valign="top">

RecieverInterchangeControlNumber

</td>
</tr>
<tr>
<td valign="top">

Message Number

</td>
<td valign="top">

RecieverMessageNumber

</td>
</tr>
<tr>
<td valign="top">

Reciever Name

</td>
<td valign="top">

RecieverTradingPartnerName

</td>
</tr>
<tr>
<td valign="top">

System ID

</td>
<td valign="top">

RecieverSystemId

</td>
</tr>
<tr>
<td valign="top">

Adapter Type

</td>
<td valign="top">

RecieverAdapterType

</td>
</tr>
<tr>
<td valign="top">

Sender Identifier

</td>
<td valign="top">

AgreedSenderIdentifierAtRecieverSide

</td>
</tr>
<tr>
<td valign="top">

Sender Identifier Qualifier

</td>
<td valign="top">

AgreedSenderIdentifierQualifierAtRecieverSide

</td>
</tr>
<tr>
<td valign="top">

Receiver Identifier

</td>
<td valign="top">

AgreedReceiverIdentifierAtRecieverSide

</td>
</tr>
<tr>
<td valign="top">

Receiver Identifier Qualifier

</td>
<td valign="top">

AgreedReceiverIdentifierQualifierAtRecieverSide

</td>
</tr>
<tr>
<td valign="top">

Reciever Communication Partner Name

</td>
<td valign="top">

RecieverCommunicationPartnerName

</td>
</tr>
</table>

**Events**

The search term for *Events* in CMIS is *List<BusinessDocumentProcessingEvent\>* where `<BusinessDocumentProcessingEvent>` pertains to events you need such as:

-   Sender Interchange Received
-   Sender Interchange Mapped
-   Receiver Interchange Assembled
-   Receiver Interchange Sent

**Interchange Payload**

The search term for interchange payload in CMIS is *Set<BusinessDocumentPayload\>*.

