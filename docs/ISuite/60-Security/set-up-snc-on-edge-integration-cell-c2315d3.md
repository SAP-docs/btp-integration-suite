<!-- loioc2315d3d3949423fa190aefb7e797e4f -->

# Set Up SNC on Edge Integration Cell

Set up SNC on Edge Integration Cell to establish secure connections with SAP and third-party systems, ensuring authentication, integrity, and confidentiality. Follow the steps to enable and configure SNC communication in the RFC Adapter.



<a name="loioc2315d3d3949423fa190aefb7e797e4f__prereq_uv3_trj_y2c"/>

## Prerequisites

-   You have enabled SNC for the Edge Integration Cell solution in the Edge LM UI. You can do this during the solution deployment or afterward by using the *Modify Configuration* option. For more information, see [Deploy the Edge Integration Cell Solution](../deploy-the-edge-integration-cell-solution-ab81b84.md).
-   You have assigned a keystore to the Edge Integration Cell runtime. For more information, see [Interact with Keystores from Edge Integration Cell](../interact-with-keystores-from-edge-integration-cell-d4972b8.md).
-   You have downloaded the SAP Cryptographic Library \(SAPCRYPTOLIB\) for Linux on x86\_64 from the[SAP Software Center](https://me.sap.com/softwarecenter): *Support Packages & Patches* \> ** *By Category* \> ** *SAP Cryptographic Software* \> ** *SAPCRYPTOLIB* \> ***COMMONCRYPTOLIB 8* .
-   You have extracted the SAPCRYPTOLIB SAR archive using SAPCAR. For more information, see SAP KBA[2632047](https://me.sap.com/notes/2632047) .
-   You have administrative access to the Kubernetes cluster using the command-line tool kubectl.



## Context

You need to enable Secure Network Communication \(SNC\) when using the RFC adapter, especially in production environments, as it is essential for securing RFC connections between the Edge Integration Cell and other SAP systems, as well as third-party systems. SNC offers three levels of security protection:

-   Authentication only
-   Integrity protection
-   Confidentiality protection

The steps below will guide you through the process of setting up SNC on Edge Integration Cell, which is a prerequisite for enabling SNC in the RFC Adapter.



## Procedure

1.  In your command-line interface \(CLI\) navigate to the local directory where you've extracted the crypto library SAPCRYPTOLIB.

2.  To copy the *libsapcrypto.so* file to the Worker pod, run the following command: `kubectl cp libsapcrypto.so edge-icell/<worker-pod>:/var/lib/worker/snc/lib -c worker`. Replace the placeholder `<worker-pod>` with the name of a Worker pod. If you have multiple Worker pods, you can select one at random.

3.  To copy the `sapgenpse` executable file from the same local directory to the Worker pod, run the following command: `kubectl cp sapgenpse edge-icell/<worker-pod>:/var/lib/worker/snc/lib -c worker`. The cryptography tool SAPGENPSE is essential for managing the PSE \(Personal Security Environment\) files, which facilitate secure connections.

4.  To verify the files have been copied successfully, open a shell session to the Worker pod by running the following command: `kubectl exec -c worker -it -n edge-icell -- /bin/sh`. Execute the following command within the shell session to list the contents of the SNC\_LIB directory: `ls /var/lib/worker/snc/lib`. Ensure the output contains the *libsapcrypto.so* and *sapgenpse* files.

5.  In the *Manage Keystore* section create a new key pair or upload an existing one into the keystore that is assigned to the Edge Integration Cell runtime. Create an alias named *snc.edge.key* for the key pair. This key pair is crucial because it establishes secure communication with SNC partners. For more information, see [Creating a Key Pair/SSH Key Pair](../50-Development/creating-a-key-pair-ssh-key-pair-b8a8601.md), [Uploading a Key Pair](../50-Development/uploading-a-key-pair-083911e.md).

6.  Choose *Download Certificate* to download the public certificate of the key pair and import it into the SNC partners’ Personal Security Environments \(PSEs\) \(that is, the PSE of the ABAP or third-party system\). Sharing this public certificate is necessary to establish trust and enable secure communication. For more information, see [Downloading Single Keystore Entries](../50-Development/downloading-single-keystore-entries-ca8a663.md).

7.  Choose *Add Certificate* to import the public certificates of the SNC partners into the keystore assigned to the Edge Integration Cell runtime. Specify aliases prefixed with *snc*, \(e.g., `snc.partner1`, `snc.partner2`\). This approach ensures that the Edge Integration Cell can authenticate and establish secure connections with those partners.




<a name="loioc2315d3d3949423fa190aefb7e797e4f__result_x5c_32q_y2c"/>

## Results

You have enabled SNC on the Edge Integration Cell. You can now proceed to enable and configure SNC communication in the RFC Sender and Receiver adapter. For more information, see [RFC Sender Adapter for Edge Integration Cell](../50-Development/rfc-sender-adapter-for-edge-integration-cell-f5568be.md) and [RFC Receiver Adapter](../50-Development/rfc-receiver-adapter-5c76048.md).

**Related Information**  


[Managing Keystore Entries](../50-Development/managing-keystore-entries-2dc8942.md "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).")

