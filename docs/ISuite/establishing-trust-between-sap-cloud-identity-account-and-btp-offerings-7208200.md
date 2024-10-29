<!-- loio72082006fdbd440faa915cde7e1eb53d -->

# Establishing Trust between SAP Cloud Identity Account and BTP Offerings

Connect SAP Cloud Identity services with the BTP offerings.



## Context

To configure and establish trust between SAP Cloud Identity and BTP offerings, follow the steps below:



## Procedure

1.  Log on to the SAP BTP Cockpit.

2.  Navigate to *Trust*. In the *Local Service Provider* tab:

    1.  Select *Custom* in the *Configuration Type* field.

    2.  Click *Generate Key Pair*.

    3.  Click *Save*.

    4.  Click *Get Metadata* to generate the metadata. This metadata will need to be imported into SAP Cloud Identity.


3.  Log on to the SAP Cloud Identity Admin Cockpit \(`https://<yourscitenant>.ondemand.com/admin/`\).

4.  From the left navigation pane, choose *Applications*, scroll down to the bottom of the page and choose *Add*.

5.  On the *Add Application* dialog, provide an application name, \(for example: SAP APIM\), and then choose *Save*.

6.  In the newly created application, under the *Trust* tab, choose the *SAML 2.0 Configuration* option.

7.  In the *Define from Metadata* tab, click *Browse* and upload the SAML metadata downloaded from Step 2, and then choose *Save*.

8.  Navigate to *Assertion Attributes* of the SAML 2.0 configurations, and then provide the mapping between the SAML Assertion values. The developer needs these configurations for onboarding on the Developer Hub.

    The following table contains the mapping between the user attribute and the assertion attribute fields:


    <table>
    <tr>
    <th valign="top">

    User Attribute
    
    </th>
    <th valign="top">

    Assertion Attribute
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Last Name
    
    </td>
    <td valign="top">
    
    last\_name
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Display Name
    
    </td>
    <td valign="top">
    
    display\_name
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    E-Mail
    
    </td>
    <td valign="top">
    
    mail
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    First Name
    
    </td>
    <td valign="top">
    
    first\_name
    
    </td>
    </tr>
    </table>
    

**Related Information**  


[Establishing Trust between SAP HANA Cloud Platform Account and SAP Cloud Identity](establishing-trust-between-sap-hana-cloud-platform-account-and-sap-cloud-identity-c597708.md "Connect SAP HANA Cloud Platform account with the SAP Cloud Identity services.")

