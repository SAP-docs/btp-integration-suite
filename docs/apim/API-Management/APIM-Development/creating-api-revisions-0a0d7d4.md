<!-- loio0a0d7d41222e42e4834b30c89609f400 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Creating API Revisions

Create API revisions to make nonbreaking API changes in a safe and controlled manner.



## Context

-   When you create and save an API proxy, a draft gets created.

-   You can deploy a draft and yet continue to have a working copy of the same.

-   You can save this draft as a revision and then deploy this revision.

-   Every time you edit and save a revision, a draft gets created.

-   You can restore any of the previous revisions using the revert action. The revert action creates a new revision, which is a copy of the prevision version you’re trying to restore.


Refer the block diagram to understand the flow:

![](images/Revision_Flow_Diagram_a91e57d.png)

For visual intructions on how to get started with API Revisions, refer the following [Tutorial](https://developers.sap.com/tutorials/api-mgmt-revisioning.html).

To create a new revision, execute the following steps:



<a name="loio0a0d7d41222e42e4834b30c89609f400__steps_r3n_sj3_1yb"/>

## Procedure

1.  Log on to the API portal.

2.  Choose the navigation icon on the left and choose *Develop*.

3.  Choose *Create*.

4.  Fill in the details in the *Create API* dialog and choose *Create*.

    To create an API proxy from scratch, see [Create an API](create-an-api-c0842d5.md).

5.  Select the appropriate tabs to edit the API. You can choose from the following:


    <table>
    <tr>
    <th valign="top">

    Tab


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Overview* 


    
    </td>
    <td valign="top">
    
    You can edit the following:

    -   Name of the API

    -   API Base Path

    -   API State

    -   API Description


    > ### Note:  
    > You aren’t allowed to edit the Host Alias.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Endpoint* 


    
    </td>
    <td valign="top">
    
    You can add the proxy endpoint and the route rules.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Target Endpoint* 


    
    </td>
    <td valign="top">
    
    You can choose URL, API Provider, or API Proxy, as the target endpoint as well as enter target endpoint rules.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Resources* 


    
    </td>
    <td valign="top">
    
    You can add resources, or change already existing ones.


    
    </td>
    </tr>
    </table>
    
6.  Once the changes are made, choose *Save*.

    A draft gets created under the *Revisions* tab.

7.  To continue to have a working copy of the draft, choose *Edit*.

    Choose *Save* after making all the changes.

8.  You can also choose to deploy this draft by selecting the <span class="SAP-icons"></span> icon and choosing the *Deploy* option from the list.

9.  If you want to convert this draft into a revision, select the draft, and choose *Save as Revision* from the inline action.

10. In the *Save as Revision* dialog, provide a revision name and a description, and choose *Save*.

    > ### Note:  
    > The revision name must be unique and cannot be named "Draft" as it is a reserved term. Instead, you can use alphanumeric characters \(both lowercase and uppercase\), as well as the special characters '\_', '.', '-', and '\(\)'. The name should not exceed 50 characters.

    A new revision gets created. You can now edit, delete, and deploy the new revision of the API.

    > ### Note:  
    > If you edit this revision and then save the changes you've made, a draft gets created out of this latest revision.

    > ### Note:  
    > By default, the maximum number of revisions you can create is 20. However, this number is configurable. If you proceed with the *Save as Revision* action once you've reached the maximum limit, the oldest revision \(which isn’t deployed\) gets deleted from the list. However, if the oldest revision is already deployed, you'll not be allowed to save the draft as a revision.

    > ### Note:  
    > You can’t delete a draft if both the working and the deployed copy of the draft are the same. If only one revision exists at any given point in time, you can’t delete the same from the inline actions button. In such a scenario, you need to delete the API proxy. You can do so by choosing the *Delete* option from the *Additional Options* on the top-right corner of the page.

11. If you want to work on any of the previous revisions, select the revision and choose *Revert* from the inline action.

    The *Revert* action replaces the existing draft \(if any\), create a new revision that can be deployed. The new revision is a copy of the previous revision that you’re trying to restore.

    > ### Note:  
    > API revisions can affect the following actions:
    > 
    > 
    > <table>
    > <tr>
    > <th valign="top">
    > 
    > Actions
    > 
    > 
    > 
    > </th>
    > <th valign="top">
    > 
    > Behavior
    > 
    > 
    > 
    > </th>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Publishing of products
    > 
    > 
    > 
    > </td>
    > <td valign="top">
    > 
    > When you create a product, you link it to one or more APIs. Also, the same API can be linked to multiple products. After you’ve linked an API to a product, all attributes of the API such as API resources, and API documentation become an implicit part of the product. Now, if the product has an API proxy that has multiple revisions, and the deployed revision of the API proxy isn’t the latest revision; if you try to publish such a product, the deployed revision of the API proxy gets published. For more information, see [Publish APIs](publish-apis-75a4a11.md).
    > 
    > 
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Importing an API proxy
    > 
    > 
    > 
    > </td>
    > <td valign="top">
    > 
    > When you import an API, a new revision of the API gets created. If your API has an existing draft, the draft gets replaced by the new revision created during the import. For more information, see [Import an API](import-an-api-9342a93.md).
    > 
    > 
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Transporting APIs and its related artifacts
    > 
    > 
    > 
    > </td>
    > <td valign="top">
    > 
    > When you transport an API, a new revision of the API is created. If your API has an existing draft, the draft gets replaced by the new revision created during the transport.
    > 
    > If there are multiple revisions of an API, only the latest revision gets transported. For more information, see [Transporting an API Proxy from Source to Destination](transporting-an-api-proxy-from-source-to-destination-2fe1aa2.md).
    > 
    > 
    > 
    > </td>
    > </tr>
    > </table>




<a name="loio0a0d7d41222e42e4834b30c89609f400__result_mzc_3l3_1yb"/>

## Results

You’ve created a new revision, created a draft out of the latest revision, used the revert action to create the latest revision of the API proxy from a previous revision.

