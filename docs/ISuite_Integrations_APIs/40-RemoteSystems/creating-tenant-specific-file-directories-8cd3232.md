<!-- loio8cd3232e7e444c7fb1868a4dc3f2cd71 -->

# Creating Tenant-Specific File Directories

A PGP Secret Keyring and a PGP Public Keyring have to be maintained for each tenant that uses OpenPGP. The GPA tool cannot maintain several PGP Secret or Public Keyrings at the same time. Therefore, you have to create a separate directory for each tenant, where you have to configure GPA and the launching of GPA separately \(otherwise, keys from different tenants will be stored in the same keyring\).



## Context

The following procedure shows how you can achieve the described setup using Gnu Privacy Assistant. To facilitate the usage of the software, we provide a set of simple configuration files to download.

> ### Caution:  
> The following description, together with the configuration files, show a possible way how to use Gnu Privacy Assistant. We cannot give any guarantee that the software \(in combination with the configuration files\) works in the desired way.

Start Gnu Privacy Assistant \(separately for each tenant\).



## Procedure

1.  For each tenant \(using OpenPGP\), create a separate file directory for maintaining the keyrings.

2.  Copy the following three files into this file directory:

    -   `gpa.conf` 
    -   `gpg.conf` 
    -   `run_gpa.bat` 

    You can download the files at:

    [Files for OpenPGP Key Management](https://help.sap.com/http.svc/download?deliverable_id=20612251)

    Download the `.zip` file and extract the content on your computer.

3.  Adapt the file `run_gpa.bat` by entering the path to the tenant-specific directory.

    These files are required to configure the usage of the GPA tool.

    The file `run_gpa.bat` sets the shell variable GNUPGHOME to the tenant-specific directory.

    The files `gpa.conf` and `gpg.conf` contain configurations for GPA and GPG. The file `gpg.conf`, for example, determines the strength of the applied encryption. Read the comments in the configuration files for further details.




## Next Steps

You can now start creating keys.

