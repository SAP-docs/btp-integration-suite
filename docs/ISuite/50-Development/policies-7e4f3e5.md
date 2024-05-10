<!-- loio7e4f3e590f164996994cddc8e48bf7f5 -->

# Policies

Policy definition and types of policies supported by SAP Integration Suite.

SAP Integration Suite provides capabilities to define the behavior of an API by using 'policies.' A policy is a program that executes a specific function at runtime. They provide the flexibility to add common functionalities on an API without having to code them individually each time. Policies provide features to secure APIs, control the API traffic, and transform message formats. You can also customize the behavior of an API by adding scripts and attaching them to policies.

You can apply a policy on the request or response stream. You can also specify if it's applicable on the proxy endpoint or target endpoint. For information on the types of policies supported by Integration Suite, see [Policy Types](policy-types-c918e28.md).



## Defining Policies using Policy Designer

Use the policy designer to create policies. The set of prebuilt policies supported by SAP Integration Suite is available in the top-right pane. To create a policy, first select the [Flow](flow-08b40d9.md) segment on which this policy is applicable. Then create the policy by adding the policy details in the editor. You also add a conditional string that ensures that the policy is executed only if the condition is met.

A sequence of policies can be applied on the desired Flow segment. The system executes the policies in the same order in which they're applied. The list of policies created in the Integration Suite is available in the bottom-right pane of the policy designer.

When you create a policy using the designer, you provide a name to the policy. Furthermore, mention whether it must be attached to the incoming or outgoing stream of the selected Flow.

There are few policies that work as expected only when associated with multiple flows.

For example, Response Cache policy must be attached to both request and response Flow of an API proxy. In such cases, you can add Response Cache policy to a request flow & then attach the same to the response flow.

To attach a policy to multiple flows, click "+" against the required policy in the *Created Policies* area.

