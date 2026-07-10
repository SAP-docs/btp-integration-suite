<!-- loio682ca615f0234421b10e5c04ede3074b -->

# Security Artifact Renewal for SFTP-Based Communication

Using SSH File Transfer Protocol \(SFTP\), the basic set up is that an SFTP client is connected to an SFTP server from which the client pulls data or to which the client pushes data. Secure SFTP communication is enabled by the usage of public/private key pairs as well as a trust relationship between client and server implemented by known\_hosts files.

In scenarios using SFTP, the tenant is always an SFTP client either pushing files to the SFTP server or pulling files from it.

Where the SFTP is hosted, depends on the scenario.

In SFTP security artifact renewal processes, the following roles are involved:

-   SFTP server administrator
-   Tenant administrator \(is always the *SFTP client administrator*\)
-   Integration developer

The following security artifacts can be subject to change and underly a renewal process:

-   Public/private key pair \(of either SFTP server or tenant\)
-   User who either pushes files to SFTP server or pulls files from it

