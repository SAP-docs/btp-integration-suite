<!-- loio1d92d5c2a8514b4baa54ae99c28fc556 -->

# Partner Directory Data



<a name="loio1d92d5c2a8514b4baa54ae99c28fc556__context_vlc_z1v_dwb"/>

## Context

The Partner Directory allows you to store information about communication partners and to parameterize integration flows using this information.

*What is a Partner Directory*

Partner Directory is a database that stores information about the trading partner agreement such as the trading partner details, identifiers and other important parameters. This information is then used in generic integration flows. These integration flows contain parameterized components which extract information from the partner directory during runtime. In short, Partner Directory allows you to create one integration flow with dynamic processing based on the invoked parameters related to a specific partner ID.

It helps you to set up a communication network between many communication partners efficiently.

*Partner Directory Data* tab helps you in resolving issues faced by the customers by checking the partner directory data.

> ### Caution:  
> Only Trading Partner related content is visible in the *Partner Directory Data* tab and the information is read-only.
> 
> The maximum number of Business Transaction Activities that you can conduct per tenant is 10,000. To know more, see [Partner Directory Information](https://help.sap.com/docs/integration-suite/sap-integration-suite/parameterizing-integration-flows-using-partner-directory?version=CLOUD).

When a trading partner agreement gets activated, the complete agreement information gets pushed into the partner directory. An entry is created in the partner directory for each business transaction activity in the agreement and for each Interchange Envelope extraction \(depending on the adapter type\). The Interchange Extraction is nothing but an XSLT script that extracts the required parameters from the type system headers and writes those details into a camel exchange header object.



<a name="loio1d92d5c2a8514b4baa54ae99c28fc556__steps_ipy_z1v_dwb"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose *Design* \> *B2B Scenarios.*

3.  Navigate to the *Partner Directory Data* tab. The tab displays all the partner directory ID that are created in the system. The partner directory ID starts with the convention *SAP\_TPM*. You can also view the following details:

    -   *Activity Plain ID*: This is the unique activity ID assigned to the business transaction activity in an agreement. The ID is the concatenated value of various head paramaters configured in the agreement. To know more, see [Understanding the Basic Concepts](../understanding-the-basic-concepts-74c068d.md).

    -   *Agreement Link*: This column displays the link to the related agreement. Choosing this link will open the corresponding transaction activity in the agreement.

        > ### Note:  
        > If you want to navigate back to the Partner Directory tab, choose *View Data* option from the *Inbound* or *Outbound* button provided in the agreement transaction.

    -   *Created Date*: Displays the date when the agreement was activated.
    -   *Last Modified Date*: Displays the date when the activated agreement was modified.

4.  You can search for a specific partner directory data using the *Search* bar.

5.  Choose and open the required partner directory entry. The resulting screen displays the *String Parameters* and the *Binary Parameters* of the agreement.

    The *String Parameters* comprises of information such as the receiver interchange, receiver parameters and communication parameters.

    The *Binary Parameters* comprises of information such as interchange assembly, interchange extraction, and Integration Advisor generated runtime artefacts for processing.


