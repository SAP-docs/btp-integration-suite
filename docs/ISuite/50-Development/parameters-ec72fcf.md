<!-- loioec72fcf90ff346f0bba20256017fbb10 -->

# Parameters

Create and maintain parameters for your company profile/subsidiary.



## Context

The application also allows you to maintain Dynamic Parameters for the company profile. These parameters can be helpful when:

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


To do so, you need to create/upload the parameters to your company profile.



## Procedure

1.  Navigate to the *Parameters* tab of the company profile.

2.  You can create or import dynamic parameters in the system.

3.  If you choose *Create*:

    -   Enter a key in the *Parameter Key* field.

    -   Enter the value for the key in the *Value* field.
    -   Choose *Save*. The parameter is now successfully added to the list.

4.  If you choose *Import*:

    -   In the *Import File* dialog, choose *Browse* to select and upload a csv file.
    -   Choose a type of the csv file under the *Type* field.
    -   Select the field seperator of the csv file from the drop-down list of the field *Field Seperator in CSV*.
    -   Choose *Next*. The next screen displays a preview of the parameters in the csv file.
    -   Choose *Import*. The parameters are now successfully added to the company profile.

5.  As the next step, maintain your security related configurations by following the steps mentioned here: [Security](security-08f956a.md).


