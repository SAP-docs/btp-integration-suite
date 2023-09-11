<!-- loiocb36c97bb1bf44fb875b7f173d807fae -->

# Validation in the OData Model Editor

Validation in the OData Model Editor ensures that your OData model adheres to the CSDL schema and does not deviate from logical or semantic specifications.

After validation, lines of code with errors are highlighted with a red icon in the code editor.

Let us look at an example of how validation works.



## Example

In any OData model, remove the value corresponding to the **Name** attribute in an **EntityContainer** element.

Since **Name** is a mandatory attribute, the corresponding line of code is highlighted with a red icon in the code editor. You can see the error message in a tooltip when you hover the mouse over the red icon.

