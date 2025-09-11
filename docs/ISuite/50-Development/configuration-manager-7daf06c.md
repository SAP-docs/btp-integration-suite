<!-- loio7daf06ceece84dc09d3ca63fc62d0a61 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configuration Manager



<a name="loio7daf06ceece84dc09d3ca63fc62d0a61__section_x2f_xb2_jzb"/>

## Custom Search Attributes

The *B2B Scenarios* tab under the *Monitor* section allows you to monitor the interchanges that are created during a B2B transaction. The interchanges are displayed in a list with a list of filters using which helps you find a specific interchange easily. These search filters are provided in a standard format. There could be scenarios where you need to search for an interchange using a filter that is not provided in general. In such cases, the *Configuration Manager* allows you to create and use custom search fields. To do so, follow the following procedure:

1.  Login to your application and navigate to *Design* \> *B2B Scenarios*.

2.  Select the *Configuration Manager* tab and choose *Create* to create your custom search attribute.

    > ### Note:  
    > You can create a maximum of 10 custom search attributes.

3.  Enter a meaningful name in the *Name* field and provide a description in the *Description* field.
4.  Choose *Save*. The custom search attribute has been created successfully.

After creating your custom attribute, you need to assign these attributes to a transaction for it to reflect in the B2B monitor. To know more, see [Trading Partner Agreement](trading-partner-agreement-9bd43c9.md).

*How are the custom search attributes consumed*

Once your create and define the custom search attributes, you need to use them in the necessary B2B transactions in an agreement. These attributes are then pushed into the partner directory upon activation of the agreement. The incoming payload consists of the search values in XPath format and when the payload is parsed, the values are read and displayed in the B2B monitor.



<a name="loio7daf06ceece84dc09d3ca63fc62d0a61__section_y5v_1rb_bzb"/>

## Retry Configuration

The integration flows once deployed, run the transaction activity and try to deliver the message. Sometimes, they fail due to unknown errors. In such cases, you can provide an option to re-trigger the integration flows. With *Retry Configuration*, you can now define the maximum number of retries for failed integration flows. This is applicable for *Step 2 - Interchange Processing Flow* and *Step 3 - Receiver Communication Flow*. Follow the following procedure to know how to maintain the retry entries.

1.  Navigate to the *Configuration Manager* in your application.

2.  In the *Retry Configuration* section, choose *Edit*.
3.  Set the *Maximum Retry* count for the fields *Interchange Processing Flow* and *Receiver Communication Flow*.
4.  There could be messages that end up failing even after reaching the maximum retry count. These messages are then removed from the JMS queue. If you choose to keep them, you can do so by enabling the **Dead Letter Queue** where these messages will be maintained after getting removed from the JMS queue.

    To enable the dead letter queue, select the checkbox of the field *Dead-Letter Queue* for the fields *Interchange Processing Flow* and *Receiver Communication Flow*.

5.  Choose *Save*. Saving the values will immediately push the data into Partner Directory. Choose *OK*.



<a name="loio7daf06ceece84dc09d3ca63fc62d0a61__section_oxc_bhw_wcc"/>

## Acknowledgment Configuration

When the messages are processed in a transaction, the Functional Acknowledgments and Technical Acknowledgments could take time to be received depending on various factors. The *Maximum Waiting Time* feature enables users to set a customizable timeout threshold for receiving functional and technical acknowledgments. In the event that functional or technical acknowledgments are not received within the specified waiting time, the system will automatically update the message processing status to *Acknowledgment Overdue*. This status change can be viewed in detail in the Monitor tab \(see [Monitor Interchanges](monitor-interchanges-42c1199.md)\).

Follow the following procedure to set the maximum waiting time for the acknowledgments.

1.  Navigate to the *Configuration Manager* in your application.

2.  In the *Acknowledgement Configuration* section, choose *Edit*.
3.  Set the maximum waiting time for the fields *Technical Acknowledgement* and *Functional Acknowledgement*. The waiting time is recorded in minutes.
4.  Choose *Save*. Saving the data will push it to the Partner Directory. In the *Save Acknowledgement Configuration* dialog, choose *OK*.



<a name="loio7daf06ceece84dc09d3ca63fc62d0a61__section_cnz_nk4_jfc"/>

## Custom Rules

In the section *Custom Rules*, you can create rules for message interchange to enable the agreement lookup in the Partner Directory. Rules must be assigned in the agreement.



### Use Case

The B2B scenario at the core of trading partner agreements \(TPA\) covers a variety of business documents to be exchanged according to the agreements with the respective business partners. The business transaction activity within a B2B scenario is the elementary artifact from which a Partner Directory entry is generated and stored in the Partner Directory. If a trading partner agreement is activated, one Partner Directory entry is saved in the Partner Directory for each business transaction activity of this agreement. Each Partner Directory entry is uniquely identified by a Partner Directory identifier \(PID\). This identifier is computed from the configured values in the business transaction activity, such as sender communication channel, type system, type system version, sender ID, receiver ID, and message type. Each Partner Directory entry contains all relevant parameters and runtime artifacts created from configurations in the individual activity steps.

During the runtime processing of the generic integration flows of Trading Partner Management, the corresponding values are extracted from the header and converted into a Partner Directory identifier for incoming sender interchange payloads. The system then checks whether an entry with the corresponding PID is stored in the Partner Directory. If this is the case, processing is performed according to the parameters and artifacts listed there.

Processing the payload consists of the following steps:

1.  Cloud Integration receives a sender communication message from the sender system based on the communication protocol configured in the activity step *Sender Communication Channel*.
2.  The message body includes one or more source interchange payloads. In the runtime, this source interchange payload is unwrapped and extracts the header values relevant for computing the PID are extracted to find the correct entry in the Partner Directory.
3.  This source interchange payload \(with the PID\) is handed over to the processing step. If there's a match between the computed PID from the source interchange payload and one of the entries persisted in the Partner Directory, you obtain the PD entry from the Partner Directory. The processing continues according to the configured parameters and artifacts of this Partner Directory entry.

These processing steps are elementary for the extraction of the key values, sender communication channel, type system, type system version, sender ID, receiver ID, and message type. However, businesses require more key fields to obtain a clear differentiation for various business transaction activities.

For example, a trading partner has different plants located in different countries, but this trading partner is using the same sender ID for all these plants. They also need different trading partner activities and business transaction activities with different mapping guidelines for these plants. To distinguish the plants, the trading partners need to extract further values from the sender interchange payload, such as the country code or the plant identifier. This can be achieved by using custom rules.



### Creating a Custom Rule

Create a custom rule by following these steps:

1.  Go to *Design* \> *B2B Scenarios* \> *Configuration Manager*.
2.  In the section *Custom Rules*, choose *Create*.
3.  Enter a *Name* for the rule.
4.  Select a *Type System* from the list. The type systems currently supported are `GS1 XML`, `SAP S/4HANA Cloud SOAP`, and `SAP S/4HANA On Premise IDoc`.
5.  For the message types the custom rule applies to, either select *All*, or *Selected*. If you choose *Selected*, you can select multiple entries from a list of messages.
6.  Finally, save your new custom rule.
7.  Before you can activate the custom rule, it needs at least one custom key. Custom keys define what element of a message is used to determine the correct association of the configured trading partner agreement and business transaction activity.

    To create a custom key, open the custom rule, and in the section *Custom Keys*, choose *Create*. A wizard opens.

8.  In the wizard, first enter the *MIG Name* and *MIG Version* for a sample MIG. The sample MIG is used to select a specific element in the message structure using XPath for your custom key. The MIGs listed are part of the type system that you selected previously.

    Choose *Next*.

9.  Next, select the XPath, which is the single leaf node from the sample MIG to be used for the rule key. To do so, expand the superior nodes to select the single entries. Choose *Next*.
10. Now, configure the XPath and XPath key as follows:

    -   *XPath*: The default value is taken from the leaf node that you selected before, but you can still edit it for your custom key.

        For example, the XPath is an absolute XPath that can only work for a dedicated message type, but you want to apply this XPath to multiple message types. In this case, you can change this XPath to a relative XPath, like `IDOC/E1EDL20/E1EDL24/WERKS`.

    -   *XPath Key*: Enter an XPath key, which is a human-readable key used to uniquely differentiate the extracted values at runtime. You can't use the same XPath key twice in the same custom rule.
    -   *Node ID*: The default value is taken from the leaf node that you selected before, but you can still edit it.
    -   *Node Name*: The default value is taken from the leaf node that you selected before, but you can still edit it.
    -   *Description*: Optionally, provide a meaningful description for the custom key.

    Choose *Next*.

11. Now, review the configurations. Once you're satisfied, choose *Finish* to create the custom key.
12. Since your new custom rule is still in draft mode, you have to activate it to push its configurations to the Partner Directory.

    In the *Custom Rules* section, choose *Activate* for your custom rule.

    > ### Note:  
    > You can only activate custom rules that have at least on custom key.

    > ### Note:  
    > If your agreement uses custom rules, you must first activate the custom rules in the configuration manager, then activate the agreement. Otherwise, the agreement activation fails.

    If you no longer need a custom rule, choose *Deactivate* to remove it from the Partner Directory. You can only deactivate a custom rule if it's not used by any agreements in status *Active* or *Update Pending*.




### Changing the Evaluation Sequence

If you have multiple custom rules for one type system, in the Partner Directory, the custom rules are executed in the order in which they were activated by default. In the custom rules table, the column *Sequence* designates the rule's position in the order.

> ### Example:  
> If you have the custom rules `A`, `B`, and `C`, and you activated them in the creation order, the sequence in the Partner Directory is the following:
> 
> 1.  A
> 2.  B
> 3.  C

To change the order in which the custom rules are applied in the Partner Directory, perform the following steps:

1.  In *Configuration Manager* \> *Custom Rules*, choose <span class="SAP-icons-V5"></span> Change Sequence for a custom rule in status *Active* or *Update Pending*.
2.  Choose <span class="SAP-icons-V5"></span> Up or <span class="SAP-icons-V5"></span> Down until you're satisfied with the sequence of the custom rules.

3.  Save your changes. The updated sequence is active immediately.



### Using Custom Rules in Agreements

You can assign custom rules with custom keys to an agreement as follows:

1.  Go to *Design* \> *B2B Scenarios* \> *Agreements* and open the agreement.
2.  In the tab *B2B Scenarios*, choose *Edit* for the correct transaction, and go to the tab *Custom Rules*.
3.  Here, select a custom rule from the drop-down list and maintain the expected value from the payload for each custom key.
4.  Save your changes.

In most cases, **editing** a custom rule that's used in an agreement means you have to reactivate or update the agreement itself. If you only change the following values, you don't need to update the agreement: message type, description, custom key's node ID, node name, or description.

> ### Note:  
> The supported custom key XPath version is inline with the XPath 3.1 Enterprise Edition \(EE\). To learn more about XPath 3.1, visit the [Saxon](https://www.saxonica.com/documentation12/documentation.xml) documentation published by Saxonica.
> 
> If the XPath contains a namespace prefix, this prefix must be declared in the incoming payload with the same prefix value. For example, if your custom key XPath value is `//sh:StandardBusinessDocumentHeader/sh:DocumentIdentification`, your incoming payload must contain its declaration as follows: `xmlns:sh=“http://www.unece.org/cefact/namespaces/StandardBusinessDocumentHeader”`
> 
> You must always use the same namespace prefix for the same namespace. For example, if your XPath uses `//sh1:StandardBusinessDocumentHeader` while your incoming payload’s namespace prefix is `sh`, errors occur.

