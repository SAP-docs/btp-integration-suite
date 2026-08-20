<!-- loiobaed0e32b88c4467a796b4e957c2b65f -->

# Activating a Trading Partner Agreement

Activate your trading partner agreement to push the agreement details into the SAP Cloud Integration partner directory.

The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network. See [Partner Directory Concepts](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/f917d6eb5e8949378b8e58784a32e450.html).

To activate your trading partner agreement, perform the following steps:

1.  Log on to SAP Integration Suite.
2.  Choose *Design* \> *B2B Scenarios*.
3.  Navigate to the *Agreements* tab. The tab displays the list of agreements created in the system. The *Status* column displays the activation status of the agreements.
4.  Search for and open the agreement that you want to activate.
5.  Choose *Activate* and select one of the following **activation modes** to decide how the system manages referenced objects during the activation:

    -   *Default*: Activate the agreement and communication channels. The system doesn't try to activate any security configurations, identifier groups, or custom rules used.

        If identifier groups, security configurations, or custom rules are still inactive, the activation fails.

    -   *Full*: Activate the agreement and all referenced communication channels, identifier groups, security configurations, and custom rules, even if they're already active.

    Confirm your choice with *Activate*.

    A successful activation sends the agreement details to the Partner Directory.

    If the activation fails, choose the *Failed* status to learn more about the activation failure.

    > ### Note:  
    > Company-side AS2 inbound decryption configurations must always be activated manually since they have no direct relation with any agreement.

6.  In the *B2B Scenarios* tab, you can view the partner directory details for each transaction using the *Partner Directory Data* field available next to the transactions. Depending on the transaction type, the field displays either *Inbound* or *Outbound*.

    Whrn you choose the drop-down next to these buttons, you can select the following:

    -   *Copy PID* copies the partner directory ID of the transaction.
    -   *View Data* directs you to the *Partner Directory Data* tab. See [Partner Directory Data](partner-directory-data-1d92d5c.md).




<a name="loiobaed0e32b88c4467a796b4e957c2b65f__section_esh_gtb_jtb"/>

## Updating an Agreement

To modify an activated agreement and reactivate it, perform the following steps:

1.  In your active agreement, choose *Edit*.

2.  Make the necessary changes in your transaction activities and choose *Save*.
3.  Select one of the following **activation modes** to decide how the system manages referenced objects during the update:

    -   *Default*: Activate the agreement and communication channels. The system doesn't try to activate any security configurations, identifier groups, or custom rules used.

        If identifier groups, security configurations, or custom rules are still inactive, the activation fails.

    -   *Full*: Activate the agreement and all referenced communication channels, identifier groups, security configurations, and custom rules, even if they're already active.

    > ### Note:  
    > Company-side AS2 inbound decryption configurations must always be activated manually since they have no direct relation with any agreement.

4.  Next, from the list of transactions associated with the agreement, select the transaction that you want to update.
5.  Confirm your choices with *Update*.

**Related Information**  


[Export Data](export-data-c387134.md "")

[Integration Flow Configuration](integration-flow-configuration-0ff6229.md "Configure your integration flows to test the end to end scenario in SAP Integration Suite.")

