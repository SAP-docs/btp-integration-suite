<!-- loioc5977080232f44a2b3dc6c88eb2f8c85 -->

# Establishing Trust between SAP HANA Cloud Platform Account and SAP Cloud Identity

Connect SAP HANA Cloud Platform account with the SAP Cloud Identity services.



## Context

To configure and establish trust between SAP HANA Cloud Platform and SAP Cloud Identity, follow the steps below:



## Procedure

1.  Download the SAML metadata from the *SAP Cloud Identity* by navigating to *Tenant Settings* \> *SAML 2.0 Configurations*.

2.  In the *SAML 2.0 Configurations* window, scroll down to the bottom of the page and choose *Download Metadata File*.

3.  Log on to the SAP HANA Cloud Platform Cockpit.

4.  Navigate to *Trust* \> *Trusted Identity Provider*, and choose *Add Trusted Identity Provider*.

5.  In the *Trusted Identity Provider* window, for the *Metadata File* field, click *Browse* and upload the SAML metadata that was downloaded from Steps 1 and 2.

6.  In the *Trusted Identity Provider* window, navigate to the *Attributes* tab, and then add the attributes value.

    The following table contains the maping between the assertion attribute and the principal attribute:


    <table>
    <tr>
    <th valign="top">

    Assertion Attribute
    
    </th>
    <th valign="top">

    Principal Attribute
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    first\_name
    
    </td>
    <td valign="top">
    
    firstname
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    last\_name
    
    </td>
    <td valign="top">
    
    lastname
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    mail
    
    </td>
    <td valign="top">
    
    email
    
    </td>
    </tr>
    </table>
    
7.  Now, you can navigate to the API portal or Developer Hub, and login using your SAP Cloud IDP users.


**Related Information**  


[Establishing Trust between SAP Cloud Identity Account and BTP Offerings](establishing-trust-between-sap-cloud-identity-account-and-btp-offerings-7208200.md "Connect SAP Cloud Identity services with the BTP offerings.")

