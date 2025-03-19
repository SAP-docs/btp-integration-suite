<!-- loio4dc1b9cbe4af4715b53ba944f59344c3 -->

# Create a Questionnaire

To create a new questionnaire go to *Settings* \> *Questionnaires* and do the following:

1.  Select *Create*.

2.  In the *Create new Questionnaire* dialog, specify a name, description, and request type for *Business Solution Request*, or specify a name, description, request type, and integration style for *Interface Request*.

3.  Select *Create*. The status of the questionnaire is *Draft*.

4.  On the questionnaire details page, select *Edit*.

5.  To add a question section to the questionnaire, choose *Create*.

6.  From the *Create Section* dropdown, select one of the following options:

    ****


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Create Question Section*
    
    </td>
    <td valign="top">
    
    Create a new section by providing *Name* and *Description* for the question section.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Copy Question Section*
    
    </td>
    <td valign="top">
    
    Allows you to copy a section from an existing questionnaire.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Add Attachment Section*

    \(only when you select *Interface Request* as the *Request Type*\)
    
    </td>
    <td valign="top">
    
    Add a section for attachments.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Add Integration Content Section* \(only when you select *Interface Request* as the *Request Type*\)
    
    </td>
    <td valign="top">
    
    Add integration content.
    
    </td>
    </tr>
    </table>
    
7.  To add questions to a *Questions* section, select the section and choose *Create*.

    You can either copy questions from another questionnaire or create new questions.

    To copy questions, select *Copy existing Questions*, select from the list of existing questions and choose *Copy*.

    To create a new question, provide the question and answer source and choose *Create New Question*.

8.  In the dialogue that opens, define the properties for your questions.
9.  Choose *Done* once you have created the list of questions. To go back and create new questions, you can choose *Edit*.

10. Go to the questionnaire page and select *Activate*, choose *Confirm* to activate the questionnaire. The status of the questionnaire created is changed to *Active*.

    > ### Note:  
    > There can be only one questionnaire of one type with status *Active*. While activating a questionnaire, the old questionnaire of the same type is automatically set to status *Deprecated*.




<a name="loio4dc1b9cbe4af4715b53ba944f59344c3__section_rj4_zkp_42c"/>

## Parameters

The following parameters can be defined for your questions.

****


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Question*

</td>
<td valign="top">

Populated from the question chosen.

</td>
</tr>
<tr>
<td valign="top">

*Question Description*

</td>
<td valign="top">

Provide a detailed description for the question as some questions may need additional explanations.

</td>
</tr>
<tr>
<td valign="top">

*Mandatory*

</td>
<td valign="top">

Define whether the question must be answered by choosing *Yes \(mandatory\)* or *No \(Not mandatory\)*.

</td>
</tr>
<tr>
<td valign="top">

*Answer Source*

</td>
<td valign="top">

Populated from the answer source provided during question creation.

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Depending on the Answer Source selected, the type field changes.

</td>
</tr>
<tr>
<td valign="top">

*Applicable*

</td>
<td valign="top">

Specify when the question is applicable. The default is *Always*. If it is applicable only when a certain answer was given to a previous question choose *Set Condition* and select the corresponding section, question and answer option.

</td>
</tr>
</table>

-   The following is a list of the *Answer Source* options and their available *Type* selections.


    <table>
    <tr>
    <th valign="top">

    Answer Source
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Type
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Free Text*
    
    </td>
    <td valign="top">
    
    You can enter free text in the placeholder provided.
    
    </td>
    <td valign="top">
    
    You can choose from the following options:

    -   *Free Text Field*

    -   *Date Selection*



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Characteristic*
    
    </td>
    <td valign="top">
    
    The possible answers to the question are given by a key characteristic.
    
    </td>
    <td valign="top">
    
    You can choose from the following options:

    -   *Single Select*

    -   *Multiple Select*


    See: [Questionnaires](questionnaires-da3f7d8.md)

    For *Key Characteristic* answer source, select the key characteristic from the list.

    See: [Key Characteristics](key-characteristics-c16258e.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Custom Options*
    
    </td>
    <td valign="top">
    
    You can specify the type as Multiple select or Single select.
    
    </td>
    <td valign="top">
    
    You can choose from the following options:

    -   *Single Select*

    -   *Multiple Select*



    
    </td>
    </tr>
    </table>
    
-   Under *Answer Options*, you can add answer options to the question by choosing *Create*. Select from the list of pre-populated table *Add Answer Option*.


