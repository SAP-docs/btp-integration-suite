<!-- loioc5d1872acd0746a0ab135fa6dbeef69f -->

# Create a Policy Template

Create a policy template add it to an API proxy.



## Prerequisites

-   You have a thorough understanding of policies and the various flows they can be attached to. For more information, see [Policies](policies-7e4f3e5.md).

-   You are familiar with the different types of policies supported by SAP Integration Suite. For more information, see [Policy Types](policy-types-c918e28.md).

-   You have the payload of the policy you want to create.



## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

    A list of APIs appears in the catalog.

3.  In the list, click the API for which you want to create the policy template.

4.  On the details screen, choose *Policies*.

5.  On the *Policy Editor* screen, choose *Policy Template* \> *Create*.

6.  In the *Create Policy Template* window, proceed as follows:

    -   Enter a name for the template in the *Name* field.
    -   Enter a description for the template in the *Description* field.
    -   Select the required policies from the *Policies Available* list.

        > ### Note:  
        > Please ensure that you don't choose Concurrent Rate Limit policy, as this policy is being decommissioned.

        > ### Note:  
        > If there are any default fault rules or a post-client flow available within the API proxy, they will also be appended to the policy template.


7.  Choose *OK*.

    To view the policy template that you have just created, navigate from the API portal home page to *Configure* \> *APIs* -\>*Policy Templates*.


**Related Information**  


[Apply a Policy Template](apply-a-policy-template-2ceab71.md "Apply a policy template to an API.")

