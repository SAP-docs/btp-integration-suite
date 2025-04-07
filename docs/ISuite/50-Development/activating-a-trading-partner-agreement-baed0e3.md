<!-- loiobaed0e32b88c4467a796b4e957c2b65f -->

# Activating a Trading Partner Agreement

Activate your trading partner agreement to push the agreement details into the SAP Cloud Integration partner directory.

The Partner Directory is a tenant-specific storage option that allows you to store information on business partners that are connected to the tenant in the context of a larger business network. To know more, see [Partner Directory Concepts](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/f917d6eb5e8949378b8e58784a32e450.html).

Follow the procedure below to activate your trading partner agreement

1.  Log on to SAP Integration Suite .
2.  Choose *Design* \> *B2B Scenarios*.
3.  Navigate to *Agreements* tab. The tab displays the list of agreements created in the system. The *Status* column displays the activation status of the agreements.

4.  Search for and open the agreement that you want to activate.
5.  Choose *Activate*.

    > ### Note:  
    > All the business transaction activities created under the *B2B Scenarios* tab will get activated and the agreement details are sent to the partner directory.
    > 
    > If the activation fails, choose the *Failed* status to know more about the activation failure.

6.  You can also view the partner directory details under your B2B transactions using the *Partner Directory Data* field available next to the transacations.
7.  Depending on the transaction type, the *Partner Directory Data* field displays the following button:
    -   Inbound

    -   Outbound

8.  Choose the drop-down next to these button and select either *Copy PID* or *View Data*.
9.  *Copy PID* will copy the partner directory ID of the transaction.
10. *View Data* will direct you to the *Partner Directory Data* tab. To know more, see [Partner Directory Data](partner-directory-data-1d92d5c.md)



<a name="loiobaed0e32b88c4467a796b4e957c2b65f__section_esh_gtb_jtb"/>

## Updating an Agreement

If you want to modify an activated agreement and reactivate it, you can do so by,

1.  Choose *Edit* button in your active agreement.

2.  Make the necessary changes in your transaction activities and choose *Save*.
3.  Choose *Update*. The *Select Transaction* dialog appears with the list of transaction activities associated with the agreement.
4.  Select the transaction from the list that you want to update and choose *Update*.

    Now, only the selected transaction will get reactivated and updated in the Partner Directory. You can check the status of the update under the *Status* field.


**Related Information**  


[Export Data](export-data-c387134.md "")

[Integration Flow Configuration](integration-flow-configuration-0ff6229.md "Configure your integration flows to test the end to end scenario in SAP Integration Suite.")

