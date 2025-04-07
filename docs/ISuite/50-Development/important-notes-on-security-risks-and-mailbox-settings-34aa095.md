<!-- loio34aa095503aa45109186d01f8733beab -->

# Important Notes on Security Risks and Mailbox Settings

When using the mail sender adapter, be aware of the following in order to avoid any unwanted results.



<a name="loio34aa095503aa45109186d01f8733beab__section_jzm_jcf_kgb"/>

## Security Risks

**It is not possible to authenticate the sender of an e-mail**

Unlike with other adapters, if you are using the sender mail adapter, the SAP Cloud Integration system cannot authenticate the sender of an e-mail.

Therefore, if someone is sending you malware, for example, it is not possible to identify and block this sender in the SAP Cloud Integration system.

To minimize this danger, you can use the authentication mechanism of your mailbox. Bear in mind, however, that this mechanism might not be sufficient to protect against such attacks.

There are three possible threats when processing e-mail content:

-   Danger to a receiver system when forwarding e-mail content

    E-mails can contain malware, such as viruses or Trojan horses.

    These will not affect the SAP Cloud Integration system, but they can cause damage to a receiver system if it doesn't have sufficient protection strategies.

-   Danger to the SAP Cloud Integration system

    E-mail content can be designed to affect the processing runtime of a system.

    Processing this content overloads the system and prevents requests from being fulfilled \(denial of service\).

    The SAP Cloud Integration system is then unavailable until the problem is fixed.

-   Reliability of data

    Sending e-mails is anonymous. It is not possible to verify whether the sender of an e-mail really is who they claim to be.

    Even if your mailbox has an authentication mechanism, this mechanism might not be sufficient.

    Therefore, data contained in an e-mail \(for example, the amount of an order\), is not reliable without further verification.




<a name="loio34aa095503aa45109186d01f8733beab__section_elr_mcf_kgb"/>

## Notes with Regard to Mailbox Settings

The mailbox settings for downloading e-mails can interfere with the settings in the sender mail adapter.

For example: When using POP3 protocol, the post-processing setting Delete/Remove might not work properly. In this case, try to configure the correct behavior in the mailbox.

