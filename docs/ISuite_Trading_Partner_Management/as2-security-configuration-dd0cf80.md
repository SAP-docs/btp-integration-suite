<!-- loiodd0cf807c6204427a719d50ce1f6a6e0 -->

# AS2 Security Configuration

Know more about the security configurations required for AS2 and AS2 MDN sender adapters.

Trading Partner Management uses integration flows for its runtime and provides a way to use simplified, reusable configurations in these integration flows. To achieve this, the system defines a fixed set of SAP delivered integration flows that execute all the defined Business Transaction Activities configured by the end user.

Configuration reuse is achieved by storing all configurations in SAP Cloud Integration Partner Directory and the integration flows consume them at runtime. To know more about these integration flows, see [Integration Flow Configuration](integration-flow-configuration-0ff6229.md).

Certain security related configurations have to be maintained when AS2 sender and AS2 MDN sender adapters are used.

> ### Remember:  
> The tenant does not store any sensitive security material. Information such as User Credentials and Private Keys are defined in the *Security Material* in the *Monitor* tab. To know more, see [Managing Security Material](https://help.sap.com/docs/integration-suite/sap-integration-suite/managing-security-material). You can only upload public certificates in the *Certificates* tab of your Company/Trading Partner profile.

The following table explains the security configurations relevent for the AS2 and AS2 MDN sender adapters. The term *Company* here refers to the Company Profile who ideally owns the B2B system.

**Security Configuration**


<table>
<tr>
<th valign="top">

Topic

</th>
<th valign="top">

Concept

</th>
<th valign="top">

Where it is configured in the B2B Design

</th>
</tr>
<tr>
<td valign="top">

Decryption

\(Inbound\)

</td>
<td valign="top">

1.  The Company owns \(typically\) one public-private key pair. The public key is shared with partners.

2.  Partners while sending sensitive content, encrypt the payload using the public key. Only the owner of the private key can decrypt it.
3.  Company uses the private key to decrypt.



</td>
<td valign="top">

The private key alias is configured in the *Security* tab of the Company Profile against the user whose details will be used to send messages to the integration flows at runtime.

</td>
</tr>
<tr>
<td valign="top">

Signature verification \(Inbound for both messages & MDN\)

</td>
<td valign="top">

1.  The Trading partner owns \(typically\) one key pair. The public key / certificate is shared with the Company.

2.  While sending messages, the partner creates a message digest & signature using their private key and attaches it to the message.
3.  After receiving the message, the Company uses the public key of the partner to verify the signature.



</td>
<td valign="top">

The public certificate is uploaded to the *Certificate* tab of the Trading Partner profile and the signature verification configuration is defined in the *Security* tab of the Profile against the AS2 Partner ID that the partner will use.

</td>
</tr>
<tr>
<td valign="top">

Encryption \(Outbound\)

</td>
<td valign="top">

1.  The Company encrypts the data using the public key shared by the partner.

2.  On the Partner’s side, the private key is used to decrypt the message.



</td>
<td valign="top">

AS2 Receiver Communication configuration under *Systems* tab of the Company/Trading Partner Profiles.

</td>
</tr>
<tr>
<td valign="top">

Signing \(Outbound for both messages & MDN\)

</td>
<td valign="top">

1.  The Company creates a message digest and signature using its own Private key.

2.  The Partner uses the public key of the Company to validate the signature.



</td>
<td valign="top">

AS2 Receiver Communication configuration under *Systems* tab of the Company/Trading Partner Profiles.

</td>
</tr>
</table>

The way the security configuration is defined for the sender side differs from the configuration for the receiver side. This is because the AS2 Sender Adapter needs to access the sender side configuration directly from PD \(Partner Directory\) even before the system can match the incoming message to the correct agreement configuration.

On the Receiver side the configuration access is simpler since the Agreement is already matched. So, in the receiver side all configurations can directly be defined in the Receiver communication configuration in the *Systems* tab of the Company/Trading Partner Profiles.



<a name="loiodd0cf807c6204427a719d50ce1f6a6e0__section_os3_zbg_tzb"/>

## AS2 Sender Configuration

The Partner Directory ID resolution process in the AS2 sender adapter used to depend solely on the user ID used for sending the message to integration flows. The Partner in PD that has the same user defined as the Associated User is used as the corresponding ID for all dynamic configurations.

The limitation of the user-based Partner resolution is that different users need to be defined to have different configurations for different Trading partners. For large customers who have huge list of partners, this can lead to tedious user management requirements.

Recently, the AS2 Sender adapter was enhanced to support more dynamic configuration based on the incoming AS2 Partner ID in the AS2 headers. In our generic integration flows, the *Partner ID Resolution* \> *Source* attribute in the *Processing* tab of AS2 Sender, is set *Dynamic*. To know more, see [Configure the AS2 Sender Adapter](https://help.sap.com/docs/integration-suite/sap-integration-suite/configure-as2-sender-adapter).

With this configuration, a two-step partner resolution process is done by the AS2 Sender Adapter:

1.  In the first step, the AS2 Sender & AS2 MDN Sender both use the inbound user ID to resolve the associated Partner in PD.

2.  Once this is resolved, the AS2 Sender checks for a String property `SAP_AS2_Pid_Resolution_Mode` under this resolved Partner. This property can have 2 values: `authorizedUser` or `as2PartnerId`.
3.  If the value is set to `authorizedUser`, the Trading Partner specific AS2 Sender security configuration is searched under the same resolved Partner.
4.  If the value is set to `as2PartnerId`, then the AS2 Sender looks up the Trading Partner specific AS2 Sender security configuration under a new Partner whose value is equal to the AS2 Partner ID in the incoming AS2 headers.

This two-step Partner resolution allows the customer to share the same user for multiple trading partners.

The above generic behavior of AS2 Sender Adapter is used in Trading Partner Management as follows:

1.  The Company side Private alias required for decryption is always stored under the User based Partner and the AS2 adapter picks this up when needed.

2.  When AS2 Sender & AS2 MDN Communications channels are defined, it is possible to specify a *Security Configuration Mode*. When this mode is set to *Channel*, all trading partner specific security configuration is directly stored under the incoming User based Partner in PD.

    1.  Since the Signature validation certificate is specific to each trading partner, this means the customer must define and maintain a different user for each trading partner when opting for *Channel* mode for Security Configuration.


3.  If the Security Configuration Mode is set to *Profile*, then the Trading Partner specific configuration must be defined under *Trading Partner Profile* \> *Security* against unique AS2 Partner IDs. When activating such configuration, a new Partner in PD is created using the AS2 partner ID value and stores the security configuration under this Partner.

    1.  This also necessitates that the AS2 Partner IDs across trading partners must be unique to avoid accidental overwriting of PD data.

    2.  To support Value Added Network \(VAN\) scenarios, you can define a communication partner profile and define the AS2 Partner ID under this profile. Then, you can reuse this ID in multiple agreements across trading partners.

        > ### Tip:  
        > To build such scenarios, use the Process Direct Sender in Trading Partner Management.



