<!-- copy5ef271f466034cf9b9c0653a9ea41f88 -->

# Update a Rate Plan

Update a rate plan using the SAP Integration Suite.



<a name="copy5ef271f466034cf9b9c0653a9ea41f88__prereq_iqk_hsp_bz"/>

## Prerequisites

You are assigned the admin role.



<a name="copy5ef271f466034cf9b9c0653a9ea41f88__context_e1q_vj1_d1b"/>

## Context

You are updating a rate plan.



<a name="copy5ef271f466034cf9b9c0653a9ea41f88__steps_f1q_vj1_d1b"/>

## Procedure

1.  Log on to the SAP Integration Suite.

2.  From the navigation bar, choose *Monetize*.

3.  On the *Monetize* screen, choose *RATE PLANS*.

4.  On the *RATE PLANS* scree, select the rate plan that you want to update.

5.  Choose *Edit*.

    You can update the following fields only :

    -   **Name**: Name of the rate plan.
    -   **Description**: Outline of the plan.
    -   **Frequency**: Monthly
    -   **Currency**: Euro
    -   **Basic Charge**: Minimum bill amount paid by the user after subscribing to the product associated with this rate plan.
    -   **Rate per API Call**: Amount in euros for one API call.
    -   **Plan Type**: Choose either *Basic* or *Tier*.
        -   **Basic**: In Basic rate plan type, the rate charged per API call is fixed.
        -   **Tier**: In Tier based rate plan type, the rate charged per API call varies based on the number of API calls.

            > ### Example:  
            > Tier based rate plan

            **Tier based rate plan**


            <table>
            <tr>
            <th valign="top">

            API Calls From
            
            </th>
            <th valign="top">

            API Calls To
            
            </th>
            <th valign="top">

            Rate per API Call
            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            0
            
            </td>
            <td valign="top">
            
            5000
            
            </td>
            <td valign="top">
            
            0.0
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            5001
            
            </td>
            <td valign="top">
            
            10000
            
            </td>
            <td valign="top">
            
            0.5
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            10001
            
            </td>
            <td valign="top">
            

            
            </td>
            <td valign="top">
            
            0.7
            
            </td>
            </tr>
            </table>
            
            In the above example, for initial 5000 calls the rate charged is 0.0 per API call. For the next 5000 calls the rate charged is 0.5 per API call and for 10000 + calls the rate charged is 0.7 per API call. For instance, if 8000 calls are made, then the rates per API call is 0.0 for 0-5000 calls and 0.5 for the remaining 3000 calls.

            > ### Note:  
            > If the *API Call To* field is left empty, then the system considers the field value to be unlimited.



6.  Choose *Save*.

    > ### Note:  
    > Updated rate plan is applicable for new subscriptions only.


**Related Information**  


 <?sap-ot O2O class="- topic/link " href="cfe6a30600f148a39a7920dbc7fa1ab2.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/lze1710737251935/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/5ef271f466034cf9b9c0653a9ea41f88.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

 <?sap-ot O2O class="- topic/link " href="b8c1e6b68be74ead8700f7f8be9baa8b.xml" text="" desc="" xtrc="link:2" xtrf="file:/home/builder/src/dita-all/lze1710737251935/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/5ef271f466034cf9b9c0653a9ea41f88.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

 <?sap-ot O2O class="- topic/link " href="d4181ad418e4446e830c498d672204ff.xml" text="" desc="" xtrc="link:3" xtrf="file:/home/builder/src/dita-all/lze1710737251935/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/5ef271f466034cf9b9c0653a9ea41f88.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

