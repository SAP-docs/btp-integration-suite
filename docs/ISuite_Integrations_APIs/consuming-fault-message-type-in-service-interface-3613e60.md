<!-- loio3613e60d65ae44e38d51ab48eb184bf4 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Consuming Fault Message Type in Service Interface

Understand how to consume a fault message type artifact in a service interface artifact.



## Prerequisite

[Creating Fault Message Type](creating-fault-message-type-789b394.md)



## Procedure

1.  Open the service interface artifact in the edit mode.
2.  In the *References* tab, go to *Global* tab.
3.  Choose *Add References* \> *Fault Message Type*.
4.  From *References* dialog, select one or more integration packages from the *Package* drop down.

    You will find a list of available reusable artifacts from the selected packages.

5.  Select one or more artifacts from the table.

6.  Choose *OK* to create reference for the selected reusable artifacts.

7.  In the *Definition* tab, choose *Add Fault* to add a fault message role.

8.  For Fault message role, choose <span class="SAP-icons-V5"></span>.

9.  From the *Add Fault Message* dialog, open the *Global Resources* tab, select one of the fault messages that have been uploaded in *References*.

10. Choose *Save* to save the changes.


**Related Information**  


[Configuring Service Interface](configuring-service-interface-53d5c97.md "A service interface can be defined by using Message Types. This two-layer structure uses Web Service Description Language (WSDL) and is oriented towards maximum reusability. To handle application-specific errors, you have the option of using fault-message types.")

