<!-- loio2ceab71343704de0bfce2145f97c85b1 -->

# Apply a Policy Template

Apply a policy template to an API.



## Prerequisites

-   You have a thorough understanding of policies and the various flows they can be attached to. For more information, see [Policies](policies-7e4f3e5.md).

-   You are familiar with the different types of policies supported by SAP Integration Suite. For more information, see [Policy Types](policy-types-c918e28.md).

-   You have the payload of the policy you want to create.



## Context

You are applying a policy template and want to apply it to an API proxy.

> ### Note:  
> If you attempt to apply a policy template that includes a Statistic Collector policy with the Statistic name='clientIP' to an API proxy, the application of the policy template will fail because 'clientIP' is a reserved word in Cloud Foundry API Management analytics. To address this issue, we have introduced a default prefix, "**custom\_**", which will be automatically appended to all custom metric names. For example, if the Statistic name is "clientIP", it will be displayed as "**custom\_clientIP**".

> ### Remember:  
> If any changes are made to the existing policy, the API proxy must be redeployed.



<a name="loio2ceab71343704de0bfce2145f97c85b1__steps_iq3_3xh_gy"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

    A list of APIs appears in the catalog.

3.  In the list, click the API for which you want to apply the policy template.

4.  On the details screen, choose *Policies*.

5.  On the Policy Editor screen, choose *Edit*-\>*Policy Template* -\>*Apply*.

6.  Select the policy templates you want to apply from the *Apply Policy Template* window.

    You can click a template to view all the policies available and also select the required policies in that template.

    > ### Note:  
    > When applying the policy template, any default fault rules or a post-client flow available within the policy template will also be appended to the API proxy.

7.  If you want to copy only the policies and not the flows, choose *Copy Only*. Otherwise, choose *Apply* to copy both polices and flows.


**Related Information**  


[Create a Policy Template](create-a-policy-template-c5d1872.md "Create a policy template add it to an API proxy.")

