<!-- loio45b2a0772db94bd9b0e57bc82d8d3797 -->

# Externalize Parameters of an Integration Flow



## Context

Use the *Externalize* feature to declare a parameter as a variable and reuse it across multiple components in the same integration flow. You can define multiple parameters for each field, but you can only assign a single value for each parameter. If a value contains common strings that can be reused, then you can split the value and assign the strings to different parameters.

The Externalization Parameters value field of an integration flow has been defined as following:

1.  **Default value:**The parameter value defined by editing it in the integration flow is called as the parameter's default value. It's a predefined integration value that can be modified by integration developer.

2.  **Configured Value:**The value configured from the configuration view is defined as the configured value of a parameter.

3.  **Description:**The information about the parameter provided by the integration developer.


> ### Note:  
> Don't use the following characters while defining an externalization parameter:
> 
> -   ,
> -   ?
> -   /
> -   ' and "
> -   < and \>
> -   ; and :
> -   \[ and \]
> -   Special characters like: ! @ \# $ % & \* \( \) = +

> ### Example:  
> Assume that in an integration flow you're configuring a communication channel with HTTPS sender adapter. Here let us externalize the *Address* field. In the externalization dialog box, you define the parameter as `{{HostPort}}` and its value as `https://localhost:8080/dir`. Now, you've declared a variable for *Address* parameter that can be reused in different components in the same integration flow.
> 
> Remember that you can assign only one value to a parameter. But if you have a requirement to reuse a specific string in a value, then we recommended to split the value into multiple strings and define them to individual parameters as shown in the table.
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Define Parameter
> 
> </th>
> <th valign="top">
> 
> Define Value
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> `{{Host}}` 
> 
> </td>
> <td valign="top">
> 
> `localhost` 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `{{Port}}` 
> 
> </td>
> <td valign="top">
> 
> `8080`
> 
> </td>
> </tr>
> </table>

> ### Note:  
> You can’t reuse the same parameter name more than once for the same field, and defining multiple parameters for the same field or column aren’t supported for tables.

The integration flow must be in *Edit* mode to perform the steps.



### To create a new parameter in the Externalization Editor:

1.  Select an integration flow component.

2.  Choose *Externalize* to define a new parameter.

3.  Enter the parameter in curly brackets in the relevant field and use [Tab\].

    > ### Example:  
    > \{\{Parameter\_1\}\}

4.  Choose the *<Define Value\>* tag, and provide a default value for the parameter in the dialog box.

    > ### Note:  
    > You can only view configured value at this step. To configure the value of a parameter choose *Configure*.

5.  Choose *OK* to save the changes.


> ### Note:  
> You can remove the externalization of a field by manually removing the parameter.



### To create a new parameter for a cell in the table:

1.  In the relevant table cell, enter the parameter in curly brackets and use [Tab\].

2.  Choose the *<Define Value\>* tag, and provide a default value for the parameter in the dialog box.

3.  Choose *OK* to save the changes.

    > ### Note:  
    > -   If you need to remove the externalization of a parameter select the delete option.
    > 
    > -   You aren’t allowed to split a value into multiple strings.




### To externalize text area

1.  Select an integration flow component.

2.  Choose *Externalize* to define a new parameter and default value for the text area.

3.  Enter the parameter in curly brackets in the text-area field and use [Tab\].

    > ### Example:  
    > -   \{\{header\_message\}\}
    > 
    > -   \{\{header\_queryresponse\}\}

4.  Enter the value of the parameter under the *Parameter Value* field in the table that appears on the right side of the editor.

    > ### Note:  
    > The table allows you to define the values for multiple parameters at the same time.

5.  Choose *OK* to save the changes.

    > ### Note:  
    > You can select *Preview* under the property sheet to view the resolved value of the parameter.
    > 
    > The *Preview* button will be enabled only after externalizing a text area attribute.




### To create a new parameter in the property sheet of an integration component

1.  Select an integration flow component.

2.  In the relevant component field define a parameter in curly brackets, and use [Enter\].

    > ### Example:  
    > \{\{parameter\_1\}\}

3.  Choose the *<Define Value\>* tag, and provide a default value for the parameter in the dialog box.

4.  Choose *OK* to save the changes.




### To reuse an existing externalized parameter:

1.  Select an integration flow component.

2.  Choose *Externalize* to reuse a parameter.

3.  Enter the parameter that you want to reuse in curly brackets in the relevant field.

    > ### Example:  
    > \{\{Parameter\}\}.

    > ### Note:  
    > By entering `{{` in the parameter field, the auto-suggest displays existing parameters.

4.  To edit the parameter value, choose the *<Define Value\>* tag.

5.  Enter the new value of the parameter in dialog box.

    > ### Note:  
    > -   Modifying the parameter value may change the configuration of other integration flow components that use the same parameter.
    > 
    > -   You can use only valid value format. For example, string value field doesn't support in the integer field.

6.  Choose *OK* to save the changes.

    > ### Note:  
    > -   You can update a value from the property sheet and *Externalization* editor for any externalized parameter.
    > 
    > -   You can only remove the externalization of a field by manually deleting the parameter from the *Externalization* editor.




### Configure Externalized Parameters

For more information on configuring externalized parameter, see: [Configure Externalized Parameters of an Integration Flow](configure-externalized-parameters-of-an-integration-flow-462a478.md)

> ### Note:  
> When the integration flow is validated, deployed, and executed the configured value always precedes the default value of the parameter. The default value in the integration flow editor can be updated by the integration developer, however, it won’t take precedence over the configured value.



### Compare default and configured values

You can use Externalized Parameter view in comparing the default and configured value for the quality assurance purpose. For more information, see: [Externalized Parameters View](externalized-parameters-view-27a0216.md)



### Download integration flow

For more information on downloading integration flow, see: [Working with an Integration Package](working-with-an-integration-package-c433ce2.md) 



### Types of Controls

Checkbox, drop down, help service, string, scheduler, text area, integer, and individual cells of a table are the supported controls in the *Externalization*.

**Let Us Experience the Externalization Enrichments in Detail.**


<table>
<tr>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Checkbox

</td>
<td valign="top">

You can define a new parameter for the *Checkbox* control in the *Externalization* view. Once you provide name for the parameter value and update the value, it indicates that the checkbox control is externalized.

Choose token of the checkbox control, it opens a *Parameter value update* dialog, to provide a default value for this newly created parameter. You can update the default value of parameter.

> ### Note:  
> If the parameter isn’t configured from the *Configure* View, the Configured value is flagged as `<No Value Configured>`

After updating the configured value from *Configure* view, configured value of parameter will be seen in the token of the checkbox control, which was externalized.

</td>
</tr>
<tr>
<td valign="top">

Dropdown

</td>
<td valign="top">

You can define a new parameter for *Dropdown* control in the *Externalization* view. Once you tab out of the parameter column, a token is created on dropdown control. It indicates that control is externalized.

By selecting the token, parameter update dialog opens which shows the default value of parameter.

You can configure dropdown control from the *Configure* view.

Upon configuration from *Configure* view, the configured value shows in the parameter update dialog when you select the dropdown control token.

</td>
</tr>
<tr>
<td valign="top">

Text area control

</td>
<td valign="top">

You can define a new parameter for *Text area* control in the *Externalization* view. You can also modify the default value of parameter. After configuring the parameter from the *Configure* view, the parameter update dialog shows both the default and configured value.

</td>
</tr>
<tr>
<td valign="top">

Table cell

</td>
<td valign="top">

You can define a new parameter for *Table cell* in the *Externalization* view. User can add or edit the default value of parameter by choosing the token in parameter update dialog.

</td>
</tr>
<tr>
<td valign="top">

Help Service

</td>
<td valign="top">

You can select or browse the resource using *Help Service* control.

> ### Note:  
> If the help service control is externalized, the select the corresponding field will be disabled. It's only available to browse the resource if the control isn't externalized.

Choose the token of the help service control to define the default value of parameter. When the parameter is configured, you can see in the parameter update dialog.

</td>
</tr>
<tr>
<td valign="top">

Scheduler

</td>
<td valign="top">

You can define a new parameter for dropdown control in the *Externalization* view. Select *Configure* view to modify the *Scheduler* control. You can find the details of configured value by selecting *Show*.

</td>
</tr>
</table>

