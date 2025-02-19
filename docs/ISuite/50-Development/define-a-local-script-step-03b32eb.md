<!-- loio03b32eb2c5c249f0a59bcd27c44d1e4e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define a Local Script Step

Learn how to use a script step that’s specific to an integration artifact to create custom scripts \(JavaScript or Groovy Script\).



<a name="loio03b32eb2c5c249f0a59bcd27c44d1e4e__prereq_ulb_qjf_2jb"/>

## Prerequisites

Groovy Script and JavaScript are supported with the following versions.

**Version Details**


<table>
<tr>
<th valign="top">

Software

</th>
<th valign="top">

Version

</th>
</tr>
<tr>
<td valign="top">

Groovy Runtime

</td>
<td valign="top">

2.4.21

</td>
</tr>
<tr>
<td valign="top">

JavaScript Engine \(Rhino\)

</td>
<td valign="top">

1.7.14

Supports ECMAScript standards.

</td>
</tr>
</table>



## Context

Cloud Integration provides a Java API to support scripting.

> ### Note:  
> The Java standard libraries of Java 8 can be used.
> 
> Cloud Integration supports the XML Document Object Model \(DOM\) to process XML documents.



## Procedure

1.  If the Script step is present in the integration flow, select it to edit the properties.

2.  If you want to add a Script step to the integration flow, perform the following substeps:

    1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Transformers\)and then choose <span class="SAP-icons-V5"></span> \(Script\).

    2.  Choose *Groovy Script* or *JavaScript*.

    3.  Place *Script* step in the integration process.



You can write the code manually or upload a script.

3.  To write your code manually, do the following:

    1.  To open the script editor, select *Create* next to the Script step shape.

        ![](images/Script_Step_Create_dd8d09c.png)

    2.  In the script editor, write the script according to the requirements of your scenario.


4.  To upload a script from your computer, do the following:

    1.  Double-click the script step to launch the properties sheet.

    2.  In the *Processing* tab, choose *Select*.

    3.  In the *Local Resources* tab, upload a script file from your file system.

        Alternatively, in the *Global Resources* tab, you can refer to an already existing script in a Script Collection artifact. By doing so, any changes to the source script are made available for all referencing script steps.

    4.  Choose the script file to launch it in the script editor.

    5.  In the script editor, edit the script according to the requirements of your scenario.


5.  Improve the script with the available tools in the editor:

    -   Include the recommendations provided in the *Problems* view. For more information, see: [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md).
    -   Use *Optimize* to enhance the script with AI. For more information, see: [Optimize Groovy Scripts](optimize-groovy-scripts-3b7a5a1.md).

        > ### Note:  
        > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).


6.  When you've finished the definition of your script, choose *Apply*.

7.  Optional: In the *Script Function* field, enter the name of the function that you want to call by default from the script. Make sure that you enter the function name without any arguments

    The field helps you define a default function when there are multiple functions defined in the script file. However, if the script contains the function *processData*, which is the default function created in the script, you can leave the field empty.

8.  Save the integration flow.




<a name="loio03b32eb2c5c249f0a59bcd27c44d1e4e__postreq_drj_gs4_p4b"/>

## Next Steps

When using the Script step, make sure that you follow guidelines about secure usage of the related script programming language.

To make sure that your scenario meets the highest standards with regard to security and other aspects, follow the design guidelines, in particular, the following ones:

-   [Apply the Highest Security Standards](apply-the-highest-security-standards-201fd43.md)

-   [Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md)


To mention one particular aspect of scripting, note the following:

Any application that parses XML data is prone to the risk of XML External Entity \(XXE\) Processing attacks. More information can be found on the webpage [XML External Entity \(XXE\) Processing](https://owasp.org/www-community/vulnerabilities/XML_External_Entity_(XXE)_Processing) .

To overcome this issue, you must take one of the following measures:

-   Don't use XML parsing \(for example, DocumentBuilderFactory\) at all.

-   Switch off the processing of external entities as explained on the webpage [XML External Entity Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html).


**Related Information**  


[Script Use Cases](script-use-cases-148851b.md "")

