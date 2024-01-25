<!-- loio57a6b6ede47c449aa0808ff9695aec49 -->

# Generating XSD/WSDL for Function Modules Using ESR \(Process Integration\)

Generate an XSD/WSDL file for a function module using the Enterprise Services Repository \(ESR\).



## Procedure

1.  Log on to the remote machine with your credentials.

2.  Open the browser and enter `<host:port>/dir`.

3.  Under *Enterprise Service Repository*, select *Enterprise Service Builder* and log on.

    The repository.jnlp file is downloaded.

4.  Click `repository.jnlp` to launch the Enterprise Services Builder.

5.  Under *Design Objects*, select the appropriate object and expand it.

6.  Right-click *Imported Objects* and select *Import of SAP Objects*.

7.  Provide the appropriate information in the mandatory fields and choose *Continue*.

8.  Under *Select Objects*, expand RFC, search for your function module, and choose *Continue*.

9.  Choose *Finish*.

    The object is imported successfully.

10. On the *Design Objects* tab, navigate to the imported objects under RFC.

11. In the right pane, open *Source \(Read-Only\)* to view the WSDL/XSD file.


**Related Information**  


[RFC Receiver Adapter](rfc-receiver-adapter-5c76048.md "Connects an SAP Cloud Integration tenant to a remote receiver system using Remote Function Call (RFC).")

