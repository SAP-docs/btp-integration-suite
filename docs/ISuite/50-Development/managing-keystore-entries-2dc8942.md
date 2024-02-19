<!-- loio2dc8942e02de4be59bd2afaa3bfdc591 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Keystore Entries

The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries \(X.509 certificates and key pairs\).



## Context

Connections between a Cloud Integration tenant and a remote system can be secured using client certificate authentication \(with X.509 certificates\). The key pairs and certificates required to implement this authentication option are stored in a keystore.

A keystore typically contains entries that belong to the tenant administrator \(customer\) and entries that are owned by SAP. Each entry is uniquely identified by an alias.

The operations you can perform on a keystore entry depend on whether it's owned by SAP or the tenant administrator. You \(as tenant administrator\) can, for example, only delete or back up entries that are owned by the tenant administrator. Vice versa, SAP can't access or download any keystore entries owned by the tenant administrator.

The following GIF gives you a brief overview of the *Keystore* tile and its functions:

![](images/Manage_Key_Store_Entries_346d35a.gif)

Keystore entries are identified by an alias.

There are the following entry types:

-   *Key Pair* entry

    Consists of a private key and its X.509 certificate chain.

    All private keys of a keystore are encrypted with the same password. This password is also used as the keystore password \(for checking the integrity of the keystore\). The keystore is never stored in the same database as the encrypted/signed application data. The password is stored in a separate database.

    The certificate chain typically consists of the public key certificate and the intermediate certification authority \(CA\) certificate with which the signature of the public key certificate can be verified.

-   *Certificate* entry

    In many cases this is an X.509 root certificate.


More information: [Keystore](../40-RemoteSystems/keystore-b163513.md)

> ### Caution:  
> Note the following restrictions when managing keystore entries:
> 
> The maximum size of a keystore is 6 MB.
> 
> -   The 6 MB limit corresponds to around 6000 X.509 certificates.
> 
> -   A key pair with a chain of three X.509 certificates consumes about 3 KB, so if the keystore only contains key pairs of this type, then you can store around 1800 key pairs in the keystore.
> 
> 
> If you upload a whole keystore \(`.jks` file\) to the tenant, the maximum keystore size is limited to 2 MB.
> 
> A locking mechanism prevents different users from changing or deleting entries of the keystore at the same time. If a user is changing the content of a keystore, the keystore is locked for other users during that time.
> 
> Private keys can't be downloaded from a keystore.



## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Select the target runtime \(*Runtime* parameter\).

    This information is only relevant for Edge Integration Cell runtime.

    For more information on how to manage the keystore for Edge Integration Cell, see [Manage Keystore for Edge Integration Cell](../manage-keystore-for-edge-integration-cell-39eb101.md).

3.  Choose the *Keystore* tile in the *Manage Security* section.

4.  The *Current* tab shows the keystore entries available for the tenant.

    For each keystore, the single entries are displayed \(by alias\).

    The Keystore Monitor shows all keystore entries in a table. For each entry, the following attributes are displayed:


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
    
    > ### Note:  
    > SAP-owned entries are indicated by a lock icon. You can't change, delete, or back them up.




<a name="loio2dc8942e02de4be59bd2afaa3bfdc591__postreq_m25_frw_m1b"/>

## Next Steps

The Keystore Monitor also gives you the following options:

**Actions**


<table>
<tr>
<td valign="top">

*Create*

</td>
<td valign="top">

To create a Key Pair or an SSH Key Pair, select *Create* and specify the artifact. Fill in the necessary details.

See also[Creating a Key Pair/SSH Key Pair](creating-a-key-pair-ssh-key-pair-b8a8601.md).

</td>
</tr>
<tr>
<td valign="top">

*Add*

</td>
<td valign="top">

To upload an entry to the keystore or to add a keystore, select *Add*.

You can upload individual entries to an existing keystore. In the latter case, you can overwrite existing entries or keep them.

SAP-owned keystore entries are indicated by a lock icon. You can't change or delete them.

There are the following options:

-   *Add* \> *Certificate*

    See: [Uploading a Certificate](uploading-a-certificate-03cf78a.md)

-   *Add* \> *Key Pair*

    See: [Uploading a Key Pair](uploading-a-key-pair-083911e.md)

-   *Add* \> *SSH Key*

    See: [Uploading an SSH Key](uploading-an-ssh-key-8bf9ae4.md)

-   *Add* \> *RSA Key*

    See: [Uploading an RSA Key](uploading-an-rsa-key-b8ba4a3.md)

-   *Add* \> *Keystore*

    See: [Uploading a Keystore](uploading-a-keystore-0db193a.md)




</td>
</tr>
<tr>
<td valign="top">

*Download*

</td>
<td valign="top">

To download the public content of a keystore or a single keystore entry, select *Download*.

See also:

-   [Downloading a Keystore](downloading-a-keystore-c6b910b.md)

-   [Downloading Single Keystore Entries](downloading-single-keystore-entries-ca8a663.md)




</td>
</tr>
<tr>
<td valign="top">

*Back Up*

</td>
<td valign="top">

To back up key store entries, see: [Backing Up Keystore Entries](backing-up-keystore-entries-b8e03b7.md)

</td>
</tr>
<tr>
<td valign="top">

*Download Back Up*

</td>
<td valign="top">

To download backed-up keystore entries, select *Back Up*. See also: [Downloading Backed-Up Keystore Entries](downloading-backed-up-keystore-entries-3a67f8a.md).

</td>
</tr>
<tr>
<td valign="top">

*Delete*

</td>
<td valign="top">

To delete an artifact, go to *Monitor* \> *Managing Security Material* and choose *Delete* after the selecting the artifact in the table. See also:

-   [Deleting Keystore Entries](deleting-keystore-entries-a483eef.md)

-   [Managing Security Material](managing-security-material-b8ccb53.md)




</td>
</tr>
<tr>
<td valign="top">

*Restore*

</td>
<td valign="top">

To restore backed-up keystore entries, see: [Restoring Backed-Up Keystore Entries](restoring-backed-up-keystore-entries-bfbbf91.md) 

</td>
</tr>
<tr>
<td valign="top">

*Update*

</td>
<td valign="top">

To update an artifact, see:

-   [Updating a Key Pair](updating-a-key-pair-4ceda24.md)

-   [Updating a Key Pair with a Signing Response](updating-a-key-pair-with-a-signing-response-4242f01.md)

-   [Updating an RSA Key](updating-an-rsa-key-ee6bf92.md)

-   [Updating a Certificate](updating-a-certificate-1fa04fa.md)

-   [Changing the Alias of a Keystore Entry](changing-the-alias-of-a-keystore-entry-72b0f88.md)




</td>
</tr>
</table>

**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

[Displaying Properties of a Keystore Entry](displaying-properties-of-a-keystore-entry-24585ba.md "Display properties of a selected keystore entry.")

[Certificate Management](../40-RemoteSystems/certificate-management-feb9c2f.md "")

[Client Certificate Authentication and Certificate-to-User Mapping (Inbound), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/4b5afdd6bcbd4bc8a3d50d9ad2ef6482.html "This option includes an authentication step based on a digital client certificate and the mapping of the certificate to a user.") :arrow_upper_right:

[Client Certificate Authentication (Inbound), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/c1eeeab4877147ffa6a5997c76eaaaca.html "This option includes an authentication step based on a digital client certificate.") :arrow_upper_right:

[Client Certificate Authentication \(Outbound\)](../40-RemoteSystems/client-certificate-authentication-outbound-c4e4a15.md "")

[Managing the Lifecycle of Keys](managing-the-lifecycle-of-keys-7d24b61.md "To enable secure communication between the tenant and connected remote systems, the system keystore that is deployed on the tenant must contain the up-to-date keys owned by the tenant administrator and SAP.")

[Creating a Key Pair/SSH Key Pair](creating-a-key-pair-ssh-key-pair-b8a8601.md "Create a key pair or a Secure Shell (SSH) key pair.")

[Cloud Integration – Keystore Monitor now available for Tenant Administrator](https://blogs.sap.com/2017/06/19/cloud-integration-keystore-monitor-now-available-for-tenant-administrator/)

