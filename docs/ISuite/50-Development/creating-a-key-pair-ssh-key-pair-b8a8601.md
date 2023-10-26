<!-- loiob8a8601bbb8b4a85ba3f245c91d97589 -->

# Creating a Key Pair/SSH Key Pair

Create a key pair or a Secure Shell \(SSH\) key pair.



## Context

You create a key pair to use it for SSL, decryption, signature, and client certificate authentication.

You create an SSH key pair to connect to the SFTP server.



## Procedure

1.  In the Operations view, choose *Manage Security* \> *Keystore*.

2.  In the *Current* tab, choose *Create* \> *Key Pair* or *Create* \> *SSH Key* depending upon your requirement.

3.  In the next screen, enter the required information.


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
    
    Alias for the artifact that you want to create. The alias must be unique. You can't create an alias that is already existing in the tenant for another key pair or SSH key.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Type* 
    
    </td>
    <td valign="top">
    
    The available options are:

    -   RSA

    -   EC

    -   DSA \(only for key pair\)



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Size* 
    
    </td>
    <td valign="top">
    
    Pick a key-bit value of your choice from the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signature Algorithm* 
    
    </td>
    <td valign="top">
    
    Pick a hash algorithm of your choice from the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Common Name \(CN\)* 
    
    </td>
    <td valign="top">
    
    Provide a common name for the technical user. You use this common name while deploying an OAuth2 credential.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Organizational Unit \(OU\)* 
    
    </td>
    <td valign="top">
    
    \(Optional\): Enter the department name within your organization.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Organization \(O\)* 
    
    </td>
    <td valign="top">
    
    \(Optional\): Enter the name of your organization.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location \(L\)* 
    
    </td>
    <td valign="top">
    
    \(Optional\): Enter the name of the city or town.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *State or Province \(ST\)* 
    
    </td>
    <td valign="top">
    
    \(Optional\): Enter the name of your state or province.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Country/Region \(C\)* 
    
    </td>
    <td valign="top">
    
    Enter the two-letter ISO code for the country.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *E-Mail \(E\)* 
    
    </td>
    <td valign="top">
    
    \(Optional\): Enter the email address associated to the user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Valid From* 
    
    </td>
    <td valign="top">
    
    Enter the date from which you want the key pair to be active.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Valid Until* 
    
    </td>
    <td valign="top">
    
    Enter the date until which you want the key pair to be active.
    
    </td>
    </tr>
    </table>
    
    For more information on certificates, see [X.509 Certificates](../40-RemoteSystems/x-509-certificates-8d38a83.md).

4.  Choose *Create*.


**Related Information**  


[Uploading a Key Pair](uploading-a-key-pair-083911e.md "Upload a private/public key pair to the tenant keystore.")

[Updating a Key Pair](updating-a-key-pair-4ceda24.md "Update a key pair keeping the alias of the keystore entry unchanged.")

