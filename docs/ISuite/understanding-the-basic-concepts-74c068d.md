<!-- loio74c068dd9ff34c588797a694d6bfad4e -->

# Understanding the Basic Concepts

This chapter provides an overview of the concepts that make up the trading partner management.

*B2B Scenario*

A B2B scenario covers the choreography of a number of business transactions, that are necesary to fullfill a specific business process between the involved trading partners in an agreed business context.

*Business Message*

A business message \(also called as a business document\) represents the specific business data payload that is sent from a source \(sender\) system or received by a target \(receiver\) system through a business transaction step. A source system can submit one or more business messages in a single business transaction step and the target system can receive one or more business message through a single business transaction step.

*Business Transaction*

A business transaction is an entity in a B2B scenario. It results in a synchronized state in both initiating and reacting information systems by exchanging business information or items according to the predefined quality of services \(QoS\). These are the following kinds of business transaction

-   **One-way business transactions**

    The initiating trading partner reports an already effective and irreversible state change that the reacting trading partner accepts.

-   **Two-way business transactions**

    The initiating trading partner sets the business transaction into an interim state by sending a business information or item to the reacting authorized trading partner through the sender side business transaction step. The final state is decided and reported by the reacting authorized trading partner through the receiver side business transaction step.


These types of business transactions are defined by the provided business transaction patterns.

*Business Transaction Activity*

A Business Transaction Activity \(BTA\) is a concrete interchange between a Company and its trading partner which converts all the necessary configurations for transfering one business document from one side to the other. A two-way Business Transaction contains two Business Transaction Activity, while a one-way Business Transaction only contains one Business Transaction Activity

*Business Transaction Pattern*

A business transaction pattern provides the pattern of one-way or two-way business transactions with its specific business semantic, the use, boundary conditions and especially the specific quality of services related to the pattern. It also considers the involved components that are necessary for a correct processing of the business information within each business transaction steps.

*Business Transaction Step*

A business transaction step is a single step within a one-way or two-way business transaction. It defines how the business information should be exchanged between the initiating and reacting trading partner or vice versa \(just two-way business transaction\). It includes all necessary and involved components for exchanging a specific business infromation or item between the two involved trading partners for fullfilling a specific state of the business transaction. A business transaction step could be from company's point of view in outbound or inbound direction. These components are:

-   Source \(sender\) system including the message implementation guidelines for the submitting payloads of business messages

-   Source communication protocol
-   Source interchange
-   Mapping
-   Target \(receiver\) interchange and if a functional acknowledgement is required
-   Target communication protocol and if a message delivery notification is required
-   Target system including the Message Implementation Guidelines for the receiving payloads of business messages, and if a application acknoweledgement is required

*Inbound Direction*

The inbound direction is the flow of the business message from the trading partner to the company in a business transaction step.

*Outbound Direction*

The outbound direction is the flow of the business message from the company to the trading partner in a business transaction step.

*Initiating Trading Partner*

The initiating trading partner is the trading partner who is authorized to initiate a business transaction, which has to be reacted by the reacting trading partner.

*Reacting Trading Partner*

The reacting trading partner is the trading partner who is authorized to react to a business transaction, which was initiated by the initiating trading partner.

*Interchange*

An interchange is a part of the business transaction and covers all components necessary for exchange the B2B-related payload data excluding the communication protocol data within a business transaction step. These are:

-   Interchange envelopes

-   Functional group envelopes

-   One or more business message including the header and trailer information related to the buisness message

The assembly of an interchange depends on the rules and conditions of the type system, which is used for this interchange.

*UN/CEFACT's Modeling Methodology*

UN/CEFACT's modeling methodology\(UMM\), is a methodology that specifically captures the business requirements of collaborative business processes between companies which are represented by trading partners. UMM is developed by the international standardization body United Nations Center for Trade Faclilitation and Electronic Business. The main focus of UMM is the platform independent representation of these collaborative business processes so that the rights, obligations, and agreements between the trading partners will be unambiguously considered. These aspects will be covered in the B2B scenario, its choreography of business transactions and their quality of services.

*Identifier*

An identifier is used to uniquely identify the trading partner when exchanging messages and also defines how to exchange documents. The identifier consists of a group of fields that help with the identification of a particular trading partner during the B2B transactions. They are:

-   *Identification*

    A name or value that identifies the trading partner within the given identification scheme.

-   *Type System*

    The type system defines how to exchange the business documents in a transaction. The types include

    -   ASC X12

    -   SOAP
    -   UN/EDIFACT
    -   IDoc

    Selecting the type determines the B2B standard based on which the B2B transaction takes place.

-   *Scheme Name* and *Scheme Code*

    This constitutes the reference framework within which the trading partners are uniquely identified. In general, a trading partner can be identified in many different ways, for example, by their name, by their identification number or by their employee details. But to be able to identify the trading partner uniquely, we need to have a frame of reference that suggests that the number that is displayed is the identification numer. That is where the *Scheme Name* and *Scheme Code* comes into play.

-   *Agency Name* and *Agency Code*

    Defines the identification scheme and issues names for the trading partners to be identified.


An identifier can be referred as the sender or receiver identifier depending on the inbound or outbound direction of the business transaction activity.

*Partner Directory*

The Partner Directory allows you to store information about communication partners and to parameterize integration flows using this information. On storing the information of the communication partner in the directory, the parameterized components read this information during runtime. To know more, see [Partner Directory](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/e7fa1e2cd16049b7bfefe938355a574c.html).

*Alias*

An Alias is a user provided, tenant independent identifier for artifacts, that can be used to maintain referential integrity in cross tenant use cases like transport. The application allows you to maintain an alias for the following entities:

-   Identifier

-   System Instance
-   Communication Channel

To know more about the terms and glossaries used in the application, see [Glossary for SAP Trading Partner Management](glossary-for-sap-trading-partner-management-81860a4.md)

