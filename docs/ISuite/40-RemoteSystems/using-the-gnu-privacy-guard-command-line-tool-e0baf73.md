<!-- loioe0baf73b9b824529b4d91af50f30751a -->

# Using the GNU Privacy Guard Command Line Tool

The GNU Privacy Guard command line tool provides additional functions for working with OpenPGP keys.

The CPA graphical tool only contains a subset of functions that might be relevant when configuring scenarios using OpenPGP. Some use cases might require you to remove a subkey or add a new subkey. This can only be done with the command line tool.

When using the command line tool, make sure that you always specify the tenant home directory in the commands, in order to make changes for a specific tenant.

Example:

`gpg --homedir=C:/tenantMyCompany --edit-key MyCompany` 

This command edits the key in the tenant directory ***C:/tenantCiti*** that contains the string ***Citi*** in its user ID.

To consult the manual for further details, run the command: ***gpg --help***.

**Related Information**  


[https://blogs.sap.com/2021/01/19/cloud-integration-import-and-export-pgp-secret-key-change-pgp-secret-key-password/](https://blogs.sap.com/2021/01/19/cloud-integration-import-and-export-pgp-secret-key-change-pgp-secret-key-password/)

