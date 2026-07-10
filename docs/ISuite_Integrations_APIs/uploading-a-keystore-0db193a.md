<!-- loio0db193a325a94675928e717c9310734a -->

# Uploading a Keystore

Upload a new keystore. You can replace an existing keystore completely or update an existing one by adding new entries. In the latter case, you can overwrite existing entries or keep them.



## Context

> ### Note:  
> You cannot upload keystore entries with aliases starting with `sap_` or `hcicertificate`. Theses aliases are reserved for SAP-owned keystore entries.



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, above the table, choose *Add* \> *Keystore*.

3.  Choose *Browse* and select the keystore on your local disk.

    Upload of keystores supports the following formats:

    -   JKS format \(file extension `.jks`\) for Java keystores

    -   PKCS\#12format \(file extension `.pfx` or `.p12`\)

        A `.pfx` or `.p12` file can contain one or more keys. In case the file contains only one key, you can also upload it as single key pair \(via *Add* \> *Key Pair*\).

        After the import of a `.pfx` or `.p12` file, the root certificates of all keys contained in the keystore will be displayed separately in the keystore overview \(in Web UI *Monitoring* under *Manage Security* in the *Keystore* tab\).


4.  Enter the keystore password.

5.  In the *Action* field, select one of the following options:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Add*
    
    </td>
    <td valign="top">
    
    Adds the entries from the uploaded keystore so that they are merged with the ones in the existing keystore.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Replace*
    
    </td>
    <td valign="top">
    
    Replaces the whole keystore with the uploaded one. You need to confirm the replacement of the existing keystore.

    > ### Note:  
    > Exception: SAP-owned entries are preserved as they cannot be changed or deleted by the tenant administrator.


    
    </td>
    </tr>
    </table>
    
6.  If you have selected *Add* \(in the *Action* field\), you can specify whether existing entries are to be overwritten by uploaded entries with the same alias.

7.  Choose *Deploy*.




<a name="loio0db193a325a94675928e717c9310734a__postreq_ex2_kd5_xz"/>

## Next Steps

A dialog is displayed showing a summary of the added, preserved, and overwritten entries. If any entries could not be uploaded, information is provided to explain why \(for example, you tried to upload a keystore entry with an alias starting with `sap`\).

