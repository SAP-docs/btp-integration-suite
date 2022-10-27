<!-- loioc90b8952e25441d581cbe852284cb4ee -->

# Create a Policy

Define a policy to set rules on the API, for example, to enforce security or control API traffic.



## Prerequisites

-   You have a thorough understanding on Policies and the various Flows it can be attached to. For more information, see [Policies](policies-7e4f3e5.md).

-   You are familiar with the different types of policies supported by SAP Integration Suite. For more information see, [Policy Types](policy-types-c918e28.md).

-   You have the payload of the policy you want to create.



## Procedure

**Context**: You are creating an API proxy and want to add a policy to it.

1.  While creating an API proxy, choose *Policies* on the details screen.
2.  Select a Flow on which you want to apply the policy.

    > ### Note:  
    > Flows are available in the top left section of the *Policy Designer*. You can select an existing flow or create a conditional Flow. To create a conditional Flow, choose the icon + beside the *ProxyEndpoint* or *TargetEndpoint* depending on which endpoint you want to assign the policy. Enter a name for the conditional Flow.

3.  From the *Policies* section right hand side, choose the icon + \(*Add*\) beside the required policy.
4.  In the *Create Policy* pop-up, enter a name for your policy.
5.  From the *Stream* drop-down, select the processing pipeline where this policy should be assigned:
    -   *Incoming Request*
    -   *Outgoing Response*

6.  Choose *Add*.

    The specified policy is created and denoted in the Policy Designer. A sample payload for the selected policy is added in the editor.

7.  In the *Conditional String* field, specify the condition on which this policy should be executed.
8.  In the editor below, provide the payload for the selected policy.
9.  Choose *Save*.

    The policy now appears under the *Created Policies* section. The count beside the Flow to which this policy was assigned, is incremented.

    If required, the policy name can be edited in the policy editor. However, If you edit the policy name, then you need to change the policy name at instances where the policy name is referred.


