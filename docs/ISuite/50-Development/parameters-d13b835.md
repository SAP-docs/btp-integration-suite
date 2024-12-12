<!-- loiod13b83593205423f8584f5afdededb0c -->

# Parameters

Create or upload the parameters to your trading partner profile.



## Context

The application also allows you to maintain Dynamic Parameters under the trading partner profile. These parameters can be helpful when:

-   You use custom integration flow.

-   You need to provide parameters for the main mapping step in a integration flow.
-   When you use GS1 XML type system in your agreement and that requires dynamic parameters. These are the following parameters that you can define for GS1 XML type system:
    -   SAP\_EDI\_REC\_Sender\_Partner\_Type

    -   SAP\_EDI\_REC\_Receiver\_Partner\_Type
    -   SAP\_EDI\_REC\_Header\_Version
    -   SAP\_EDI\_REC\_Multiple\_Type
    -   SAP\_EDI\_REC\_Message\_Business\_Scope\_Type
    -   SAP\_EDI\_REC\_Message\_Busines\_Scope\_Instance
    -   SAP\_EDI\_REC\_Message\_Business\_Scope


To create/upload the parameters to your trading partner profile, follow the procedure below:



## Procedure

1.  Navigate to the *Parameters* tab of the trading partner profile.

2.  You can create or import dynamic parameters in the system.

3.  If you chose *Create*:

    1.  Enter a key in the *Parameter Key* field.

    2.  Enter the value for the key in the *Value* field.
    3.  Choose *Save*. The parameter is now successfully added to the list.

4.  If you chose *Import*:

    1.  In the *Import File* dialog, choose *Browse* to select and upload a csv file.
    2.  Choose a type of the csv file under the *Type* field.
    3.  Select the field seperator of the csv file from the drop-down list of the field *Field Seperator in CSV*.
    4.  Choose *Next*. The next screen displays a preview of the parameters in the csv file.
    5.  Choose *Import*. The parameters are now successfully added to the trading partner profile.

5.  For the next step, see [Security](security-eb83a51.md).


