<!-- loio50b63c69028643b18016d6795003392d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating OAuth Client Credentials for Cloud Foundry Environment

You can create OAuth client credentials to access your SAP Cloud Integration tenant hosted on the Cloud Foundry environment.



<a name="loio50b63c69028643b18016d6795003392d__prereq_i3h_ngn_p4b"/>

## Prerequisites

-   You’ve access to a subaccount in the SAP BTP cockpit.

-   You’ve activated the Process Integration service or the Cloud Integration capability of SAP Integration Suite in your subaccount.




## Procedure

1.  Log into the SAP BTP cockpit and navigate to your subaccount.

2.  Choose *Services* \> *Service Instances* on the navigation sidebar.

3.  Choose *Create Instance*.

4.  In the *New Instance* dialog box, enter the following values:

    1.  In the *Service* field, select *Process Integration Runtime*.

    2.  In the *Service Plan* field, select *api*.

    3.  Enter a name for your instance in the *Instance Name* field and choose *Next*.


5.  On the next screen, specify the configuration parameter for the instance.

    -   Enter the following configuration parameter inline in JSON format.

        > ### Source Code:  
        > ```
        > {
        > "roles":[
        > "WorkspacePackagesEdit"
        > ]
        > }
        > 
        > ```

    -   Optional: Choose *Browse* to upload the JSON file containing the configuration parameter.

6.  Choose *Next* to review and verify the instance details.

7.  Choose *Create Instance*.

8.  Choose <span class="SAP-icons-V5"></span> \(Actions\) and then select *Create Service Key* on the service instance created in the previous step.

9.  In the *New Service Key* dialog box, enter a value in the *Service key name* field and choose *Create*.

    The service key is created successfully. You can view the service key under the *Service Keys* section.

10. Choose <span class="SAP-icons-V5"></span> \(Actions\) and then select *View* on the service key to display the details.

    The service key details containing the OAuth client credentials including the clientid, clientsecret, and token url are displayed.

11. Choose *Download* or *Copy JSON* to use the client credentials in the *Destination Configuration* section of your subaccount.


