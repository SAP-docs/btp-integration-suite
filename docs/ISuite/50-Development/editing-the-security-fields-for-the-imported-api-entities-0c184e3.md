<!-- loio0c184e3cb4bd4b46a0320f03f1172d0f -->

# Editing the Security Fields for the Imported API Entities

To use the imported API entities, the security fields for these entities, which carried dummy values during the import due to security reasons must be replaced with the actual values.



## Context

In the destination subaccount, for the imported API entity, replace the dummy certificate attached to the API provider with a genuine certificate. Replace the dummy Key Value Map \(KVM\) values with authentic values. For different Connection types, replace the dummy values in the username and password fields with valid details.



## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Replace the dummy certificate in the API provider with a genuine certificate.

    1.  Choose the API provider and choose *Connection*.
    2.  Make a note of the certificate name displayed under *Key Store Certificate* and *Trust Store*.
    3.  Navigate back to the *Configure* \> *APIs* page, and look for the certificate on the *Certificates* tab.
    4.  Delete the certificate, and with the same name create a new certificate. For more information, see [Manage Certificates](manage-certificates-c665875.md).

4.  Replace the dummy value in the encrypted Key Value Map that got imported along with the API proxy with authentic values:

    1.  Navigate to the *Configure* \> *APIs* page, and choose the *Key Value Maps* tab.
    2.  Choose the imported Key Value Map and choose *Edit*.
    3.  Delete the dummy value from the *Value* field and enter an authentic value.

    > ### Note:  
    > For nonencrypted Key Value Maps, dummy values aren’t imported. You can use the value of the nonencrypted Key Value Map as is.

5.  To replace the dummy values in the *Open Connector*, *Cloud Integration*, *On Premise*, and *Internet* type of API providers, perform the following steps:

    -   *Open Connector* : Choose the API provider , navigate to the *Connection* tab, and choose *Edit*. Replace the dummy values in the *Organization Secret* and *User Secret* fields with real values.

    -   For *Cloud Integration* type:

        -   If authentication type is selected as *Basic*, then remove the dummy values and add valid information in the *Username* and *Password* fields.

        -   If authentication type is selected as *OAuth2ClientCredentials*, then replace the dummy values in the *Client ID*, *Client Secret*, and *Token URL* fields with real values.

        -   If authentication type is selected as *ClientCertificate*, then make a note of the certificate names displayed under *Key Store Certificate* and *Trust Store*. Navigate back to the *Configure* page, look for the certificate on the *Certificates* tab. Delete the certificate, and with the same name create a new certificate.


    -   In case of *On Premise* and *Internet* type of API providers, if *Authentication type* is set as *Basic* in *Catalog Service Settings*, then you've to remove the dummy values and add valid information in the *Username* and *Password* fields.





<a name="loio0c184e3cb4bd4b46a0320f03f1172d0f__result_bxg_fxk_t4b"/>

## Results

All the dummy values that got imported along with the API proxy during the transport has been replaced with authentic values. You can start using the imported API proxy.

