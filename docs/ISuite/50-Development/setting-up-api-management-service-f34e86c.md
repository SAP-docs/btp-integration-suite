<!-- loiof34e86cafb274d4bbef725a610ed225d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Setting Up API Management Service

To create APIs, build API proxies as a service provider, or use APIs and other convenient services, you need to first set up the API Management service.



<a name="loiof34e86cafb274d4bbef725a610ed225d__context_zzc_psj_ltb"/>

## Context

After enabling the API Management capability, you need to configure the service. For a first-time user, only the *Configure* tab appears on the *Settings* page.



## Procedure

1.  Choose *Settings* \> *API* from the left navigation pane.

    A *Configure the API Management Service* screen appears.

2.  In the *Account* section, select the *Account Type*.

    -   Select *Non-Production* account type for, nonbusiness critical activities, integrating test systems, testing new scenarios, performance testing, and sandbox activities.
    -   Select *Production* account type for business critical usage, integrating production systems, and productive APIs.

3.  In the *Virtual Host* section, enter the *Host Alias*.

    Virtual hosts are the base URLs of an API Proxy that identifies your organization. Once you enter the host alias, your API Proxy would appear in the default API Management domain as shown here:

    Example: https://<virtualHost\>.apimanagement.hana.ondemand.com.

4.  Provide an e-mail ID in the *Notification Contact* field to receive updates. You can also add multiple e-mail IDs. To add more than one e-mail ID, press the `Tab` button on the keyboard.

5.  Select the *Make <User ID\> API Portal administrator* checkbox to assign the `APIPortal.Administrator` role to the mentioned user. Assigning administrator role helps the user to access API portal user interface and services.

6.  Choose *Set Up*.

7.  In the *Set-up Confirmation*window, review the provided details and choose*Confirm* to start the onboarding process.

    You're now navigated to a progress window, which states *API Management Service Setup In Progress*.

    The *Configuration* process is triggered, where the necessary resources are provisioned for you, followed by *Testing the Setup* process, where a simple API Proxy is deployed and invoked to check that everything is set up properly.

    As and when the processes complete the indicators turn green to indicate that the processes are successful. Then, a *Release Notification* mail is sent out to the e-mail IDs provided in the *Configure the API Management Service* screen. This e-mail contains details of the newly set up API Management service on your account.




<a name="loiof34e86cafb274d4bbef725a610ed225d__result_f22_2qj_ltb"/>

## Results

API Management Service is now configured. You can now create APIs, build API proxies as a service provider, or use APIs and other convenient services.



<a name="loiof34e86cafb274d4bbef725a610ed225d__postreq_u4y_l3k_ltb"/>

## Next Steps

After completing the setup, logout of the Integration Suite application and login again. The *Connections* tab appears on the *Settings* page.

To publish the Integration Suite API portal content on the **API business hub enterprise**, you must establish a connection. Choose *Test Connection* and see the *Connection Status* change to *Success*.

> ### Note:  
> You can navigate to the **API business hub enterprise** by choose the <span class="SAP-icons"></span> Explore our Ecosystem icon on the header bar.

