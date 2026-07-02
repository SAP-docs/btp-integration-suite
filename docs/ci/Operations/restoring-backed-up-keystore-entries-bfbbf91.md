<!-- loiobfbbf918ecb94e4ea263e1d766ed70ad -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Restoring Backed-Up Keystore Entries

Restore backed-up entries of the keystore \(owned by the tenant administrator\).



## Context

You can restore keystore entries that you have backed up. For example, you can restore entries if you delete them from the active tenant keystore by mistake.

> ### Note:  
> Restored keystore entries from the keystore backup replace all existing entries of the tenant administrator. Therefore, be careful using this feature as you can delete by mistake existing keystore entries.



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Backup* tab, the backed-up keystore entries are displayed in a table.

    The following attributes are displayed for each entry:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Alias* 
    
    </td>
    <td valign="top">
    
    Uniquely identifies the keystore entry.

    A keystore entry can be either be owned by the tenant administrator or by SAP.

    In case a keystore entry it is owned by SAP, the lock icon \(:lock:\) is shown next to the alias. SAP-owned keystore entries provide a reduced set of functions. For example, you cannot update or delete an SAP-owned keystore entry.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type* 
    
    </td>
    <td valign="top">
    
    Indicates whether the entry is a *Certificate* \(X.509 certificate\) or a *Key Pair* \(with public and private key and an X.509 certificate chain\).

    -   Key Pair

        Consists of a private key and its X.509 certificate chain.

    -   Certificate

        In many cases this is an X.509 root certificate.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Valid Until* 
    
    </td>
    <td valign="top">
    
    Indicates the expiration date.

    If keys and certificates have expired, the date is highlighted in red.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Last Modified At* 
    
    </td>
    <td valign="top">
    
    Indicates the date and time the entry was last modified.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Subject DN* 
    
    </td>
    <td valign="top">
    
    Indicates the Subject distinguished name \(DN\) which entails information about the owner of the certificate such as the common name of the certificate owner \(CN\), the organization \(O\), or the country or region \(C\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Issuer DN* 
    
    </td>
    <td valign="top">
    
    Indicates the Issuer distinguished name \(DN\) which entails information about the issuer of the certificate such as common name of the certificate issuer \(CN\), the organization \(O\), or the country or region \(C\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Actions* 
    
    </td>
    <td valign="top">
    
    Choose the <span class="SAP-icons-V5"></span> \(Actions\) button for a key pair or certificate to perform an action. The available actions depend on the type of the keystore entry and whether it is owned by SAP.

    -   *Rename*

    -   *Update*
    -   *Download*
    -   *Delete*
    -   *Download Certificate*
    -   *Download Public OpenSSH Key*
    -   *Update Signing Response*
    -   *Download Certificate Chain*
    -   *Download Root Certificate*
    -   *Download Signing Request*


    
    </td>
    </tr>
    </table>
    
3.  Choose *Restore* \(above the table\).

    The selected entries are restored in the deployed tenant keystore.


**Related Information**  


[Backing Up Keystore Entries](backing-up-keystore-entries-b8e03b7.md "Back up keystore entries owned by the tenant administrator.")

[Cloud Integration – Backup/Restore using Keystore Monitor](https://blogs.sap.com/2017/08/14/cloud-integration-backuprestore-using-keystore-monitor/)

