<!-- loioec72fcf90ff346f0bba20256017fbb10 -->

# Parameters

Create and maintain parameters for your company profile/subsidiary.



## Context

The application also allows you to maintain dynamic parameters for the company profile. These parameters can be helpful when:

-   You use a custom integration flow.

-   You need to provide parameters for the main mapping step in an integration flow.
-   When you use a GS1 XML type system in your agreement and that requires dynamic parameters. For GS1 XML type systems, you can define the following parameters:
    -   SAP\_EDI\_REC\_Sender\_Partner\_Type

    -   SAP\_EDI\_REC\_Receiver\_Partner\_Type
    -   SAP\_EDI\_REC\_Header\_Version
    -   SAP\_EDI\_REC\_Multiple\_Type
    -   SAP\_EDI\_REC\_Message\_Business\_Scope\_Type
    -   SAP\_EDI\_REC\_Message\_Busines\_Scope\_Instance
    -   SAP\_EDI\_REC\_Message\_Business\_Scope


To do so, you need to create/upload the parameters to your company profile.



## Procedure

1.  Go to *Design* \> *B2B Scenarios* and open the relevant company profile.

2.  Navigate to the *Parameters* tab of the company profile.

3.  You can **create** or **import** dynamic parameters in the system.

    -   If you choose *Create*, maintain the following fields:

        -   Enter a key in the *Parameter Key* field.

        -   Enter the value for the key in the *Value* field.
        -   Optionally, enter a description for the key in the *Description* field.

        When you're done, choose *Save*. The parameter is added to the list.

    -   If you choose *Import*, maintain the following fields:

        -   In the *Import File* dialog, choose *Browse* to select and upload a CSV file.
        -   Choose a type of the CSV file under the *Type* field.
        -   Select the field separator of the CSV file from the drop-down list of the field *Field Separator in CSV*.

        Choose *Next* and review the preview of the parameters in the CSV file. If you're satisfied, choose *Import*. The parameters are added to the company profile.


4.  As the next step, maintain your security-related configurations by following the steps mentioned under [Security](security-08f956a.md).


