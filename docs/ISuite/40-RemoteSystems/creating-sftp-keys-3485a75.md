<!-- loio3485a7581fd741ce909950716682e5df -->

# Creating SFTP Keys

You can set up reliable file transfer based on SSH File Transfer Protocol \(SFTP\). SFTP is an enhancement of the Secure Shell \(SSH\) network protocol.



## Context

This section covers all steps to generate the required security artifacts for a tenant to be connected as SFTP client to an SFTP server.



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  In the *Current* tab, choose *Create*.

3.  Choose *SSH Key* from the popup Menu.

4.  Fill out the required data.

    > ### Note:  
    > The recommended Key Size is 4096 bit.

5.  Press *Deploy* to create the SSH key pair.




## Next Steps

You can download the public key in OpenSSH format and configure it as an authorized key for the required user on the SFTP server.

**Related Information**  


[Generating a Key Pair](generating-a-key-pair-abb324d.md "")

