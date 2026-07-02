<!-- loio4242f01c191640e0a258212f82b8462c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Updating a Key Pair with a Signing Response

Upload a signing response from a certification authority and use it to update the key pair in your keystore, keeping the alias of the keystore entry unchanged.



<a name="loio4242f01c191640e0a258212f82b8462c__prereq_fkf_gts_gfb"/>

## Prerequisites

You have created a certificate signing request \(CSR\) for the key pair and used this to request a signed certificate from a certification authority \(CA\). The certification authority has provided a signing response.



<a name="loio4242f01c191640e0a258212f82b8462c__context_l2n_slq_4lb"/>

## Context

This option is not available for keystore entries owned by SAP.



<a name="loio4242f01c191640e0a258212f82b8462c__steps_w1v_nts_gfb"/>

## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, select the key pair that the signing response was created for.

3.  Choose the <span class="SAP-icons-V5"></span> \(Actions\) icon, then select *Update Signing Response*. Alternatively, you can click the key pair alias to open the key pair details, and then choose *Update* \> *Signing Response*.

4.  Browse to the signing response file that you want to upload.

    > ### Note:  
    > The following signing response formats are supported:
    > 
    > -   PKCS\#7 in binary or PEM or base64 textual encoding \(\*.p7c\)
    > 
    > -   Chain of DER-PEM encoded X.509 certificates in one file \(\*.\*\)
    > 
    > -   X.509 PKI path \(sequence of certificates with top CA certificate at index 0\) \(\*.pkipath\)
    > 
    > -   Software Publisher Certificate \(SPC\) \(\*.spc\)

5.  Choose *Update*.

    > ### Note:  
    > Currently, the upload size limit for signing responses is at 30720 bytes.




<a name="loio4242f01c191640e0a258212f82b8462c__result_l5b_w5s_gfb"/>

## Results

The key pair is updated in the keystore. The key pair can now be used to set up secure connections to external receiver back ends.

**Related Information**  


[Cloud Integration – How to Setup Secure Outbound HTTP Connection using Keystore Monitor](https://blogs.sap.com/2017/06/19/cloud-integration-how-to-setup-secure-outbound-http-connection-using-keystore-monitor/)

