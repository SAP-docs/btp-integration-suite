<!-- loiod9aade6b9b494ce79f624188ca1c8577 -->

# Create a Role Collection

Create a role collection to access the Edge Lifecycle Management UI.



<a name="loiod9aade6b9b494ce79f624188ca1c8577__prereq_tfb_qfh_jgc"/>

## Prerequisites

Create all the users who should have access to the Edge Lifecycle Management. For more information, see [Configuring User Access to SAP Integration Suite | SAP Help Portal](https://help.sap.com/docs/integration-suite/sap-integration-suite/configuring-user-access?version=CLOUD&q=users)



## Procedure

1.  Open the SAP BTP cockpit.

2.  Navigate to *Security* \> *Role Collections*.

3.  Choose *Create New Role Collection*.

4.  Enter a name and a description.

5.  Choose *Create*.

6.  Choose *Edit* and use the search option to find the *EdgeLMAccess* role.

7.  Navigate to *Security* \> *Users*. Select the users who need access to the Edge LM UI and assign them the newly created role collection.

8.  Also assign the role collection *Cloud Connector Administrator* to the users.

9.  *Save* your changes.


