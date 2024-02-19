<!-- loio360dc70c9e3940e9af133813ff1ffbae -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Validating Message Payload against XML Schema

The XML validator validates the message payload in XML format against the configured XML schema.



## Prerequisites

You have the XML schema \(XSD files\) added in the .src.main.resources.xsd location of your integration flow project. If you do not have the specified location in your project, you need to create one first and then add the XSD files.



## Context

You use this procedure to assign XML schema \(XSD files\) to validate the message payload in a process step. The validator checks the message payload against configured XML schema, and report discrepencies in message payload. If the validation fails, the Cloud Integration system stops the whole message processing by default.

> ### Note:  
> The XML Validator 2.0 version allows you to validate XML files against an XML schema. It supports validation of XSD 1.1 specification along with XSD 1.0 specification.



<a name="loio360dc70c9e3940e9af133813ff1ffbae__steps_avh_bxz_ts"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(List of Validators\), and then choose *XML Validator*.

2.  Under the *General* tab, enter an appropriate validator flow step name in the *Name* field.

3.  Under the *Validation* tab, select a source from the drop-down list provided in the *Source* field.

4.  If you select the option

    1.  *Integration Flow*, choose *Select* in the *XML Schema* field and select an xsd file from the list that you want to use to validate the format. You can also upload a local xsd file using the *Upload from File System* option.

        > ### Note:  
        > -   You can have references to other XSDs within the same project. XSDs residing outside the projects cannot be referred.
        > 
        > -   You can enter a value less than 5000 for attribute *maxOccurs*, in input xsd. You can also enter `unbounded`, if you do not want to check for max occurrence but would like to support any number of nodes.
        > 
        > -   If there are any validation errors in the payload, the details of the error is visible in MPL attachment. The link for the attachment is available in MPL log.
        > 
        > -   Use `${property.SAP_XmlValidationResult}` to get more details on validation excecptions.

    2.  *Header*, enter the name of the header in the *Header Name* field.


5.  If you want to continue the processing even if the system encounters error while validating, then select the check box *Prevent Exception on Failure*.

    > ### Note:  
    > If an exception occurs, then the error payload is added to *SAP\_XmlValidationResult* property.

6.  Save the changes.


