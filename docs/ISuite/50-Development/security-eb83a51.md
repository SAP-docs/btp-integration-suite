<!-- loioeb83a51ee7f045a99b335082c649bc94 -->

# Security

Create and maintain security related configuration for your partner profile.



## Context

When you use AS2 adapters in your agreements, you need to maintain few decryption configurations. To do so, follow the steps below:



## Procedure

1.  Navigate to the *Security* tab and choose *Create*.

2.  Maintain the following fields:

    1.  *AS2 Partner ID*: Enter the ID of the AS2 Partner.

    2.  *Alias*: Maintain an alias for the configuration.
    3.  *Signature*: Select the signature mode for the configuration from the drop-down list.\\
    4.  *Public Key Alias*: This field appears only when you choose the option *Trusted Certificate* for *Signature*. Select a certificate from the drop-down list.

        > ### Note:  
        > You need to maintain the certificates in the *Certificates* tab of the trading partner profile in order to set the public key Alias.

    5.  *Verify MIC\(MDN Only\)*: Select this checkbox if you want to enable the Message Integrity Check \(MIC\). This applies only for AS2 MDN.

3.  Choose *Save* after maintaining all the fields. These configurations should be activated in order to be used in an Agreement. Select the toggle button below the *Activation Status* header to activate your configuration.

    Once activated, the AS2 Partner ID details are pushed into the Partner Directory.

    > ### Note:  
    > If you maintain the following ID entries and use them in an agreement, then on activating the agreement, the IDs could interefere and overwrite the existing AS2 partner ID based scenarios that are configured outside the Trading Partner Management solution. To avoid this, it is suggested to use a different partner ID.

    **AS2 Partner ID Data**


    <table>
    <tr>
    <th valign="top">

    Partner Directory ID
    
    </th>
    <th valign="top">

    Adapter
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Defined by the system
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Authentication
    
    </td>
    <td valign="top">
    
    AS2 Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Authentication mode for Asynchronous MDN
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Mdn\_Verify\_Mic
    
    </td>
    <td valign="top">
    
    AS2 MDN Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    If verify MIC for MDN is required
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Mdn\_Verify\_Signature
    
    </td>
    <td valign="top">
    
    AS2 MDN Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    If verify signature for MDN is required
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Proxy\_Type
    
    </td>
    <td valign="top">
    
    AS2 Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Proxy Type for Asynchronous MDN
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Signature\_Encoding
    
    </td>
    <td valign="top">
    
    AS2 Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Signature encoding for MDN
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Verify\_Signature
    
    </td>
    <td valign="top">
    
    AS2 Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    If signature verification is required for EDI. This value overwrite the PD entries with ID AS2\_inbound\_verify\_signature
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_MDN\_CredentialName
    
    </td>
    <td valign="top">
    
    AS2 Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Credential Name for Basic Authentication in Asynchronous MDN
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_MDN\_LocationId
    
    </td>
    <td valign="top">
    
    AS2 Sender
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Location ID for On-Premise in Asynchronous MDN
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP\_AS2\_Inbound\_Public\_Key
    
    </td>
    <td valign="top">
    
    AS2 Sender/AS2 MDN Sender
    
    </td>
    <td valign="top">
    
    Binary
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Public key for signature verification for EDI / MDN
    
    </td>
    </tr>
    </table>
    
4.  For the next step, see [Number Ranges](number-ranges-6616307.md).


