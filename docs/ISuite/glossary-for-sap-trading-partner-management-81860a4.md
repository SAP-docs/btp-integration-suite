<!-- loio81860a47c05e4fee8051170edc859392 -->

# Glossary for SAP Trading Partner Management

**Legal Entities**


<table>
<tr>
<th valign="top">

Term

</th>
<th valign="top">

Definition

</th>
</tr>
<tr>
<td valign="top">

Trading Partner

</td>
<td valign="top">

A Trading Partner is a business entity that participates in a business transaction. The participation can be either in the role of an Initiator of a transaction or as a Responder to a transaction initiated by another trading partner.

A trading partner has a Trading Partner Profile.

A trading partner may have subsidiaries.

</td>
</tr>
<tr>
<td valign="top">

Subsidiary

</td>
<td valign="top">

A Subsidiary can be a sub-organization, sub-division, or a department of a Trading Partner which legally belongs to the Trading Partner.

A Subsidiary is a trading partner and can participate in a business transaction and has its own profile.

Subsidiaries won't have nested subsidiaries.

</td>
</tr>
<tr>
<td valign="top">

Company

</td>
<td valign="top">

A Company is a specialization used to define the ownership of other entities and data defined in the context of a tenant.

A tenant is associated with exactly one company and the company owns that tenant. A company is a trading partner and can participate in business transactions.

A Company can conduct business with many Trading Partners.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Profile

</td>
<td valign="top">

A Trading Partner Profile is a class representing the common information that forms the profile of a real-world business entity that participates in a business transaction. The profile in itself is not the business entity but belongs to a business entity.

The class holds the following information

-   System details

-   Identifier
-   Business Context
-   Contact information



</td>
</tr>
<tr>
<td valign="top">

Identifier

</td>
<td valign="top">

An Identifier represents a public identification mechanism offered by an authorized body. It is used to identify the initiating and responding trading partner in a business transaction.

</td>
</tr>
<tr>
<td valign="top">

Business Context

</td>
<td valign="top">

The Business Context has several entities representing categories such as business domains, areas of business and the geolocation of the trading partner.

The business context is useful for categorization, search, analytics and also to get proposals for the business transactions. The set of business context categories is

-   Business Process Role
-   Industry Classification

-   Product Classification
-   Trading Partner Role
-   Geopolitical identification



</td>
</tr>
<tr>
<td valign="top">

Business Process Role

</td>
<td valign="top">

The Business Process Role describes the aspects of a business situation that are specific to a trading partner within the business process. A trading partner can play different roles in different B2B scenarios. A business process role is specified by using a value or set of values from the business partner roles list.

</td>
</tr>
<tr>
<td valign="top">

Industry Classification

</td>
<td valign="top">

The Industry Classification context provides a description of the industry or sub-industry where the trading partner’s B2B scenarios take place. The classification is specified by using a value or set of values from the industry classification list provided by SAP.

</td>
</tr>
<tr>
<td valign="top">

Product Classification

</td>
<td valign="top">

The product classification describes the aspects of a business scenario related to the goods or services being exchanged in the diverse B2B scenarios defined by the trading partner. A product classification is specified by using a value or set of values from the product classification list provided by UNSPSC.

</td>
</tr>
<tr>
<td valign="top">

Country/Region

</td>
<td valign="top">

Country/Region defines the geopolitical area or areas where a trading partner performs B2B scenarios. This can be continent, country, region.

</td>
</tr>
<tr>
<td valign="top">

Contact Person

</td>
<td valign="top">

The contact person provides the details of the trading partner responsible for operating and maintaining the content for B2B data exchange and the systems. The partners can be approached for all relevant queries.

</td>
</tr>
<tr>
<td valign="top">

Address

</td>
<td valign="top">

The address represents the physical location of the company or subsidiary.

</td>
</tr>
<tr>
<td valign="top">

Contact Channel

</td>
<td valign="top">

The contact channel identifies the type of communication and its associated number of a company, subsidiary, or a contact person to whom communication should be directed.

</td>
</tr>
<tr>
<td valign="top">

Related Information

</td>
<td valign="top">

Related information provides additional information related to the trading partner, which could be used for setting up and maintenance of trading partner agreements.

The information can be a statement or work in the area of B2B, agreed rules or even guidelines that must be considered while setting up trading partner agreements.

</td>
</tr>
</table>

**Configuration Entities**


<table>
<tr>
<th valign="top">

Term

</th>
<th valign="top">

Definition

</th>
</tr>
<tr>
<td valign="top">

Business Document

</td>
<td valign="top">

Business Document, also called Message Type is a semantical and formal business entity that is transferred between two partners. It defines either the representation at the source or target side.

The agreed and customized structure of a business document is usually provided by a message implementation guideline \(MIG\) from Integration Advisor or possibly in the end of an XSD structure representing the message.

</td>
</tr>
<tr>
<td valign="top">

Interchange

</td>
<td valign="top">

Interchange is a collective structure that specifies an acknowledgment or a collection of one or more Message Types contained within a type system-specific envelope/header at the source and target side. In other words, an interchange is the incoming payload for B2B transactions. Each interchange in the end refers to the actual Business Document inside \(MIG, API etc.\).

The Interchange is always modeled in SAP Integration Advisor and the TPM application stores the Interchange references as a reusable \(CAWF\) resource to avoid redundant or multiple configurations within agreements.

</td>
</tr>
<tr>
<td valign="top">

Functional Group

</td>
<td valign="top">

A functional group is a part of an interchange, which embraces one or more business documents that are based on a same message type.

</td>
</tr>
<tr>
<td valign="top">

System

</td>
<td valign="top">

System hosts one or more concrete end-points that can either send or receive business documents and acknowledgments.

The following 3 broad levels of information are necessary in relation to system configuration in TPM.

1.  *System Landscape Directory*: A directory that holds the details and purposes of available systems in the customer landscapes.

2.  *Technical connectivity configuration*: This defines the technical connectivity details of each system in the landscape such as, host, port, authentication etc.
3.  *Integration specific configuration*: This defines the fixed, semantical information for each system such as, supported type systems, adapter types, services, key sequences etc., that can be used during integration configuration.



</td>
</tr>
<tr>
<td valign="top">

System Type

</td>
<td valign="top">

The system type is meta-data that holds the name for the class of systems. The names are defined by the user.

</td>
</tr>
<tr>
<td valign="top">

System Instance

</td>
<td valign="top">

System instances represent the physical points in the B2B landscape. In a trading partner agreement, a system instance is either a physical starting point at the sender side or a physical ending point at the receiver side.

</td>
</tr>
<tr>
<td valign="top">

Communication Channel

</td>
<td valign="top">

A communication channel defines the communication for sending or receiving messages between the system and the middleware such as Cloud Integration or PO/PI.

</td>
</tr>
<tr>
<td valign="top">

Business Transaction Pattern

</td>
<td valign="top">

A Business Transaction pattern is a technical communication pattern that defines the behavioral aspects. These patterns are shipped as part of the product as boot strap content / configurations.

There are several different patterns that can be supported. The following is a comprehensive list of patterns but not all of them need to be supported in the initial delivery.

-   Notification

-   Broadcast / Information Distribution
-   Request - Response
-   Query - Response
-   Request - Confirmation
-   Commercial Transaction / Offer – Accept



</td>
</tr>
<tr>
<td valign="top">

Interchange Flow

</td>
<td valign="top">

An Interchange Flow defines the direction and cardinality of a flow. It also defines the concrete flow semantics for a single Interchange within the pattern, that involves transferring a payload from a sender to a receiver. A payload here refers to a business document or a functional/application acknowledgment. A payload subsequently brings up mapping requirements, adapter configurations etc.

An interchange flow contains 2 sides – the sender and the receiver. Depending on an agreement template or a partner agreement, one side or both sides has to be configured. To differentiate the configuration sets between the sender and receiver, TPM uses something called configuration template that groups the transaction steps and related configuration specific to either the sender or the receiver.

The mapping is not part of either of the configuration templates but is in between. Mapping can be finalized only after both the sender and receiver side message types/interchanges are clearly known.

The interchange flow should also specify the quality of service required on the receiver direction.

</td>
</tr>
<tr>
<td valign="top">

Trading Partner Agreement

</td>
<td valign="top">

The Trading partner agreement is a configured and execution ready choreography based on the agreement between exactly two trading partners in where one trading partner is the Initiator and the other trading partner is the Responder. One of the trading partners should be the Company, which is the owner and user of the trading partner profiles and trading partner agreements at their tenant. It is based on a B2B scenario.

</td>
</tr>
<tr>
<td valign="top">

Agreement Template

</td>
<td valign="top">

An Agreement Template is a semantical definition consisting of one or more business transactions. It is by default partially configured for the customer side. Many configurations at the template level serve as defaults which can then be overridden at the trading partner agreement level. The full configuration is completed only at the partner agreement level.

</td>
</tr>
<tr>
<td valign="top">

Business Transaction

</td>
<td valign="top">

A Business Transaction is an instance of a business transaction pattern with business semantics added. It is a technical pattern configured for a specific business purpose. Semantics here means the actual business process names and the business entities/messages.

</td>
</tr>
<tr>
<td valign="top">

Business Transaction Quality of Service

</td>
<td valign="top">

The Business Transaction Quality of Service specifies the configuration of quality of service for a Business Transaction. This can be individually specified on each side of the transaction, either Initiator or Responder. This is an optional configuration.

</td>
</tr>
<tr>
<td valign="top">

Message Exchange

</td>
<td valign="top">

A message exchange defines a single step of a message exchange pattern. This step covers the configuration and processing from the source end-point to the target end-point.

</td>
</tr>
<tr>
<td valign="top">

Business Message

</td>
<td valign="top">

The business message describes the business message/document that gets exchanged at the whole message exchange. It covers the details of this message at business domain level.

</td>
</tr>
<tr>
<td valign="top">

Quality of Service

</td>
<td valign="top">

The following qualities of services describe the measurement and overall performance indicators of a message exchange step at initiators or responder side.

-   Time to Perform

-   Time to Acknowledge Receipt
-   Time to Acknowledge Acceptance
-   Formal or Informal
-   Has Legal Intent
-   Non-repudiation receipt \(on request/response\)
-   Non-repudiation of content and origin \(on request/response\)
-   Receipt Ack/Exception \(on request/response\)
-   Accept Ack/Exception \(on request/response\)
-   Response
-   Notification of Failure Possible
-   Is Guaranteed Message Delivery Required
-   Business Message Security



</td>
</tr>
<tr>
<td valign="top">

Mapping

</td>
<td valign="top">

The mapping describes the mapping from a source structure to a target structure that also provides more details on processing and instructional details related to this mapping.

</td>
</tr>
<tr>
<td valign="top">

Message Exchange Pattern

</td>
<td valign="top">

A Message Exchange Pattern represents the message exchange configuration between exactly two participants. It is important to classify if each configuration belongs to the Initiator or Responder for the following reasons:

-   The Initiator and Responder configurations will be done at different points in time. So, it is necessary for the User Interface to know which set of configurations to present to the end user.

-   The configurations in future Partner configurations will be exposed as a self-service to the actual partners.
-   Some configurations might have different role requirements.



</td>
</tr>
<tr>
<td valign="top">

Configuration Template

</td>
<td valign="top">

The Configuration Template serves the purpose of grouping configurations and adding required meta data to the different configurations of a Message Exchange Pattern. A Message Exchange Pattern needs exactly two Configuration Templates – one each for Initiator and Responder.

</td>
</tr>
</table>

