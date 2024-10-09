<!-- loiof3d983aabf0349e8975db3e92a0c537e -->

# Create a Business Solution Request and Interface Request



<a name="loiof3d983aabf0349e8975db3e92a0c537e__context_jvx_j4v_jcc"/>

## Context

Integration Assessment involves orchestration across different personas. Creating a business solution request is the task of the business domain expert, see [Personas for Integration Assessment](60-Security/personas-for-integration-assessment-5df5af1.md).



<a name="loiof3d983aabf0349e8975db3e92a0c537e__steps_q2n_m4v_jcc"/>

## Procedure

1.  Log in to Integration Assessment and navigate to the *Requests* section.

2.  Choose the *Business Solution Request* tile.

3.  Choose *Create* to create a new business solution request.

4.  Provide a name for the request and select *Create*. The status of the request appears as *Draft*.

    > ### Note:  
    > The status of the business solution request and interface request are maintained separately.

5.  In the *General* tab, provide the business background in the questionnaire that appears. There might be additional explanations available for some questions. In this case a hint icon provides further information.

6.  In the *Interface Requests* tab, choose *Create* to add the interface request details.

7.  Provide the following details for creating the interface request:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Provide a name for the interface request.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Source Application Instance* 
    
    </td>
    <td valign="top">
    
    Select a source application instance and choose *Select*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Target Application Instance*
    
    </td>
    <td valign="top">
    
    Select a target application instance and choose *Select*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Style*
    
    </td>
    <td valign="top">
    
    Select the integration style.

    See: [Integration Styles and Integration Use Case Patterns](integration-styles-and-integration-use-case-patterns-770909d.md)
    
    </td>
    </tr>
    </table>
    
8.  Select *Next Step*. In the *Attachments* tab, provide attachments or diagrams. This action is optional.

9.  Select *Done* to save your settings.

10. Select *Submit*. The status of the business solution request changes to *New* after filling all the mandatory fields. The interface request status changes to *Requirement Analysis*.

    > ### Note:  
    > If you want to make any changes to the General section of the business solution request, select *Edit* and perform the operation. You can also create new interface requests, edit or delete the existing ones in the *New* status.

    An interface request can have the following status values:


    <table>
    <tr>
    <th valign="top">

    Status
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Requirement Analysis*
    
    </td>
    <td valign="top">
    
    When you fill out the questionnaire for the interface request.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Technology Selection* 
    
    </td>
    <td valign="top">
    
    When you select the technology.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Completed*
    
    </td>
    <td valign="top">
    
    When the technology has been determined.
    
    </td>
    </tr>
    </table>
    
11. Select the interface request and fill the questionnaire. Once you've filled in all information, choose *Done*.

12. Select *Go to Technology Selection*. The status of the interface request changes to *Technology Selection*.

    > ### Note:  
    > To make changes to the questionnaire, select *Back to Questionnaire*. In the questionnaire section, select *Edit* and the status is reset to *Requirement Analysis*.

13. Select *Select Technology* and choose the instance based on the recommendation. Choose *Select*.

14. After the technology selection is complete, select *Submit*. The status of the interface request changes to *Completed*.

    To export the completed interface request as a PDF file, open the request and choose *Download*.

    > ### Note:  
    > After completing the interface request, if you want to make any changes, select the interface request and select *Reopen*. This resets the status of the request to *Technology Selection*. You can edit the technology selection by choosing *Select Technology*.
    > 
    > To edit the questionnaire, select *Back to Questionnaire*. The status is reset to *Technology Selection*. Choosing *Edit* changes the status to *Requirement Analysis*.
    > 
    > Reopening and editing an interface request may impact the technology recommendation.

15. Go to the Request section and select the business solution request. The status is still *In Progress* whereas the statuses of interface requests should be *Completed*. Select *Complete Request* to complete the business solution request.

    > ### Note:  
    > You can only set the business solution request to complete once the involved interface requests are completed. There should be at least one interface request associated with the business solution request.

16. A business solution request can have the following status values:


    <table>
    <tr>
    <th valign="top">

    Status
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Draft*
    
    </td>
    <td valign="top">
    
    The request hasn't been submitted yet.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *New* 
    
    </td>
    <td valign="top">
    
    The request has been submitted and all interface requests are in *Requirement Analysis* status.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *In Progress*
    
    </td>
    <td valign="top">
    
    At least one interface request has *Technology Selection* or *Completed* status.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Completed*
    
    </td>
    <td valign="top">
    
    The business solution request is completed.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > After completing the business solution request, if you want to make any changes, select the business solution request and select *Reopen*. This resets the status of the request to *In Progress*. You can edit the technology selection by choosing *Select Technology*. You can edit the questionnaire, or edit the interface requests by selecting *Edit*.




<a name="loiof3d983aabf0349e8975db3e92a0c537e__result_t31_rpv_jcc"/>

## Results

You have now successfully created a business solution request and interface requests.

