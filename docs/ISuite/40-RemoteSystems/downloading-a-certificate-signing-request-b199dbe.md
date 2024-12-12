<!-- copyb199dbe8c59e49ac933f29337c853d6e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Downloading a Certificate Signing Request

Download a certificate signing request to send to a certification authority.



<a name="copyb199dbe8c59e49ac933f29337c853d6e__context_N10014_N10011_N10001"/>

## Context

When a certificate is originally created, it is self-signed. It has to be signed by a certification authority \(CA\) before it can be used for productive scenarios. To get a certificate signed by a CA, you first need to download a certificate signing request \(CSR\) in the Keystore Monitor.

> ### Note:  
> This option is not available for key pairs with the alias id\_dsa or id\_rsa, or SAP key pairs.



## Procedure

1.  Open the SAP Integration Suite *Monitor* application.

2.  Choose the *Keystore* tile in the *Manage Security* section.

3.  On the *Current* tab, select a key pair.

4.  Choose the <span class="SAP-icons-V5"></span> \(Actions\)icon, then select *Download Signing Request*. Alternatively, you can click the key pair alias to open the key pair details, and then choose *Download* \> *Signing Request*.

5.  A file with the name `<alias>.csr` is downloaded.




## Results

You have downloaded a CSR to your computer.



<a name="copyb199dbe8c59e49ac933f29337c853d6e__postreq_j1n_sqf_gfb"/>

## Next Steps

You send the CSR to a certification authority, who will provide a signing response.

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="5490ca7917b64ef3803d9f34c542db70.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/b199dbe8c59e49ac933f29337c853d6e.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

[Updating a Key Pair with a Signing Response](../50-Development/updating-a-key-pair-with-a-signing-response-4242f01.md "Upload a signing response from a certification authority and use it to update the key pair in your keystore, keeping the alias of the keystore entry unchanged.")

