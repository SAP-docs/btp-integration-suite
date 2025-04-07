<!-- loio02600be570a14b69ba84d2836c50cad4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Copying a Trading Partner Agreement

Follow the procedure below to copy a trading partner agreement.



## Context

There can be scenarios where you might want to reuse an existing agreement . You can now use the copy feature provided in the application and reuse the agreements instead of a creating the agreement again. There are few things to be considered before copying an agreement:

-   You can directly copy an agreement that is in *Draft* status without any Partner Directory ID \(PID\) assigned to it.

-   If the agreement that you are trying to copy is *Active*, then you can only copy that agreement by choosing a different trading partner. This is because every PID is linked to the trading partner associated with a particular active trading partner agreement. So you need to copy that agreement with a different trading partner so that on activating that copied agreement would not overwrite the existing the agreement details in the Partner Directory.
-   The feature also provides an option *Open Draft* that allows you to view the agreement in a draft state so that you can modify or fill in the details before copying.



## Procedure

1.  Log on to SAP Integration Suite .

2.  Choose *Design* \> *B2B Scenarios*.

3.  Navigate to the *Agreements* tab.

4.  Choose the Copy <span class="SAP-icons-V5"></span> button provided under the *Actions* column of the agreement that you wish to copy.

    You can also open an agreement and select the *Copy* button.

5.  This will open the *Copy Agreement* dialog box with a field displaying the name of the copied agreement. Provide a name for the agreement and choose *Save*.

    You can also use the *Open Draft* option to edit and modify the details and choose *Save*.

    1.  If the agreement is in *Draft* status, then a new agreement gets created.

    2.  If the agreement is in *Active* status, then choosing *Save* triggers a validation check and displays another field *Trading Partner*. Choose another trading partner from the drop-down list and choose *Save* again.



