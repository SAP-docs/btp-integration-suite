<!-- loio4dc1b9cbe4af4715b53ba944f59344c3 -->

# Create a Questionnaire

To create a new questionnaire under *Settings* tab, do the following:

1.  Select \(*Create*\).

2.  In the *Create new Questionnaire* dialog, specify a name, a description, and a request type \(either *Business Solution Request* or *Interface Request*\).

3.  Select *Submit*. The status of the questionnaire is *Draft*.

    > ### Note:  
    > The SAP pre-defined questionnaires \(indicated as *Maintained by SAP*\) cannot be customized.

4.  When you select the questionnaire created, the details provided will be displayed. To add a question section to the questionnaire, choose \(*Create*\).

5.  From the *Create Section*dropdown, select one of the following options:

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
    
    Allows you to copy a section from a predefined questionnaire.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Add Attachment Section*

    \(only when you select *Integration Request* as the *Request Type*\)
    
    </td>
    <td valign="top">
    
    Add a section for attachments if any.
    
    </td>
    </tr>
    </table>
    
6.  To add questions to a *Questions* section, select the section and choose \(*Create*\).

    You can either copy existing questions from a predefined questionnaire or create new questions.

    To copy pre-defined questions, select *Copy existing Questions*, select from the list of pre-defined questions and choose *Copy*.

    To create a new question, provide the question and answer source and click *Create*.

7.  Provide the question under the *Question* section.
8.  Choose an *Answer Source* from the list below and click *Create*. The created question will be displayed under the *Questions* section. Click *Done* once you have created the list of questions. To go back and create new questions, you can click *Edit*.

    ****


    <table>
    <tr>
    <th valign="top">

    Answer Source
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Free Text*
    
    </td>
    <td valign="top">
    
    You can enter free text in the placeholder provided.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Characteristic*
    
    </td>
    <td valign="top">
    
    The possible answers to the question are given by a key characteristic.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Custom Options*
    
    </td>
    <td valign="top">
    
    You can specify the type as Multiple select or Single select.
    
    </td>
    </tr>
    </table>
    
9.  To provide additional parameters and description to the question, select the question and specify the following parameters depending on the answer source chosen under the *Properties* section.

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
    
    Define whether the question is mandatory or not by choosing *Yes \(mandatory\)* or *No \(Not mandatory\)*.
    
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
    </table>
    
    -   Below is the list of *Type*selections for different *Answer Source* selected:


        <table>
        <tr>
        <th valign="top">

        Answer Source
        
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
        
        You can choose from the following options:

        -   *Single Select*

        -   *Multiple Select*



        
        </td>
        </tr>
        </table>
        
    -   Under *Answer Options*, you can add answer options to the question by clicking on *Create*. Select from the list of pre-populated table *Add Answer Option*.


10. Go to the questionnaire *Properties* page and select *Activate*, click *Confirm* to activate the questionnaire. The status of the questionnaire created is changed to *Active*.

    > ### Note:  
    > There can be only one questionnaire of one type with status *Active*. While activating a questionnaire, the old questionnaire of the same type is automatically set to status *Deprecated*.


