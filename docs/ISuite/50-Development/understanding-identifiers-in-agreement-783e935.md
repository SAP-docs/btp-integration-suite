<!-- loio783e93516b484ce89781cd5bd9a5b4b6 -->

# Understanding Identifiers in Agreement

Ler us learn how identifiers work in a trading partner agreement.

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

Let us take a look at the Trading Partner Agreement in detail to understand further. A trading partner agreement is defined as a binding agreement between Company and the Trading Partner for transacting messages over a specific B2B protocol. Here both the Company and the Trading Partner can be the initiator or reactor of an agreement.

While creating a trading partner agreement, you come across fields such as *Identifier*, *Identifier as Company* and *Identifier as Trading Partner*. What are they and how do we define them?

Say, for example, we have an agreement Purchase Order with Company Sample Company1 and Trading Partner Demo Company. Now the company sets its identifier as *1111 | Duns Plus Suffix | ASC X12* which means:

-   1111 stands for the company's Identification

-   Duns Plus Suffix represents the scheme name
-   ASC X12 represents the B2B standard or the message encoding that would be used for sending messages from the company

Now the trading partner has set its identifier as *SO\_675 | GS1 | UNEDIFACT* where

-   SO\_675 stands for trading partner identification

-   GS1 is the scheme name
-   UNEDIFACT is the B2B standard or the message encoding that B would use for sending messages.

![](images/Initial_Trading_Partner_Agreement_f558948.png)

Since we have two different message encoding for both the parties in the agreement, we need to set another identifer for both the company and trading partner so that receiving messages from one another can be made easy. This is where the field *Identifier as Trading Partner* and *Identifier as Company* comes into play for the company and trading partner respectively.

For the company, you need to set the field *Identifier as Trading Partner* with the encoding same as that of the identifier of the trading partner which is UNEDIFACT. Similarly, for the trading partner, you need to set the field *Identifier as Company* with the encoding same as that of the identifier of the company which is ASC X12.

Now the agreement overview would look like this:

![](images/Identifier_in_Trading_Partner_Agreement_eacb712.png)

