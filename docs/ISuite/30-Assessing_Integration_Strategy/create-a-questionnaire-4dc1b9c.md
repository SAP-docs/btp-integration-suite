<!-- loio4dc1b9cbe4af4715b53ba944f59344c3 -->

# Create a Questionnaire

To create a new questionnaire under *Settings* tab, do the following:

1.  Select \(*Create*\).

2.  In the *Create new Questionnaire* dialog, specify a name, a description, and a request type \(either *Business Solution Request* or *Style Request*\).

    If you choose *Style Request* as the *Request Type*, you also need to define the *Style* parameter. You can choose among the integration styles as described in [Integration Styles and Integration Use Case Patterns](integration-styles-and-integration-use-case-patterns-770909d.md).

3.  Select *Submit*.

4.  To add a question section to the questionnaire, choose \(*Create*\).

5.  From the dropdown, select one of the following options:

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

    Create a new section.


    
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

    \(only when you select *Style Request* as the *Request Type*\)


    
    </td>
    <td valign="top">

    Add a section for attachments.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Add Integration Content Section*

    \(only when you select *Style Request* as the *Request Type*\)


    
    </td>
    <td valign="top">

    Add a section for integration content.


    
    </td>
    </tr>
    </table>
    
6.  To add questions to a question section, choose \(*Create*\).

    You can either copy existing questions from a predefined questionnaire or create new questions.

    To create a new question, provide a name and answer source and click *Submit*.

    You can choose from the following answer sources:

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
    
7.  Finalize the definition of the question by editing the question and defining whether the question is mandatory or not.

    Depending on the chosen answer source, you need to specify different parameters.

    -   For *Free Text*, specify the following parameters:


        <table>
        <tr>
        <th valign="top">

        Parameter


        
        </th>
        <th valign="top">

        Description


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        *Type*


        
        </td>
        <td valign="top">

        You can choose from the following options:

        -   *Free Text Field*

        -   *Date Selection*



        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Placeholder*


        
        </td>
        <td valign="top">

        Placeholder is a field that can hold a possible answer or example. The output will be shown in light grey color.


        
        </td>
        </tr>
        </table>
        
    -   For *Key Characteristic*, specify the following parameters:


        <table>
        <tr>
        <th valign="top">

        Parameter


        
        </th>
        <th valign="top">

        Description


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        *Type*


        
        </td>
        <td valign="top">

        You can choose from the following options:

        -   *Single Select*

        -   *Multiple Select*


        See: [Questionnaires](questionnaires-da3f7d8.md)


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Key Characteristic*


        
        </td>
        <td valign="top">

        Select the key characteristic.

        See: [Key Characteristics](key-characteristics-c16258e.md)


        
        </td>
        </tr>
        </table>
        
        The *Answer Options* are added automatically.

    -   For *Custom Options*, specify the following parameters:


        <table>
        <tr>
        <th valign="top">

        Parameter


        
        </th>
        <th valign="top">

        Description


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        *Type*


        
        </td>
        <td valign="top">

        You can choose from the following options:

        -   *Single Select*

        -   *Multiple Select*


        See: [Questionnaires](questionnaires-da3f7d8.md)


        
        </td>
        </tr>
        </table>
        
        Under *Answer Options* you can add custom answer options to the question.


8.  Select *Activate* to activate the questionnaire.

    > ### Note:  
    > Only one active questionnaire is allowed. Deactivate the questionnaire before adding a new one.


