<!-- loio8be5a7b5876a498799470a4ab495091a -->

# Handling Faults using FaultRules and DefaultFaultRule

When servicing a request, an API proxy may encounter various error conditions. These errors occur when a policy is unable to perform its intended function. In this section, we will explore the utilization of FaultRules and DefaultFaultRule to create a customized fault handling branch for handling such errors.

By default, SAP API Management provides the client application with an Error code \(HTTP Status\) and fault message when an error occurs. The specific Error and HTTP status codes for each policy can be found in the documentation provided by help.sap. To illustrate, let's consider the [Verify API Key](verify-api-key-4d15a04.md) policy as an example.

**Error Code**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

HTTP Status

</th>
</tr>
<tr>
<td valign="top">

DeveloperStatusNotActive

</td>
<td valign="top">

401

</td>
</tr>
<tr>
<td valign="top">

FailedToResolveAPIKey

</td>
<td valign="top">

401

</td>
</tr>
<tr>
<td valign="top">

InvalidApiKey

</td>
<td valign="top">

401

</td>
</tr>
<tr>
<td valign="top">

InvalidApiKeyForGivenResource

</td>
<td valign="top">

401

</td>
</tr>
<tr>
<td valign="top">

invalid\_client-app\_not\_approved

</td>
<td valign="top">

401

</td>
</tr>
</table>

Customizing the error message and providing additional information can help consumers better understand and resolve errors, as the default error message may be unclear. It is also recommended to return custom headers or HTTP status codes when necessary. In certain situations, it may be necessary to execute a series of policies, such as logging the error and returning a custom message.

To raise custom HTTP codes and/or messages, the[Raise Fault](raise-fault-c7f2e8d.md) policy can be used. However, for implementing a common error handling pattern, FaultRules and DefaultFaultRule are typically used.



<a name="loio8be5a7b5876a498799470a4ab495091a__section_bss_jdh_kbc"/>

## FaultRules and DefaultFaultRule

When an API proxy encounters an error, it deviates from the normal processing pipeline and enters an error state. In this error state, the API Proxy follows a specific order to execute FaultRules and DefaultFaultRule.

-   **FaultRules**: Contains the necessary logic to trigger custom error messages and other policies based on specific conditions.

-   **DefaultFaultRule**: Contains the logic to trigger custom error messages and other policies when no FaultRule is executed or when the *AlwaysEnforce* element is set to true.


> ### Note:  
> An API proxy enters the error state only when the *continueOnError* attribute is set to *false* on a policy or when the Raise Fault policy is executed.
> 
> In the Proxy Endpoint, FaultRules are evaluated from bottom to top, while in the Target Endpoint, they are evaluated from top to bottom.
> 
> Only the first matching FaultRule is executed.



<a name="loio8be5a7b5876a498799470a4ab495091a__section_a2h_fnz_lbc"/>

## Create the <FaultRule\> that will trigger the policy

In the `<ProxyEndpoint>` or `<TargetEndpoint>` sections of the proxy configuration, you will add a `<FaultRules>` XML block that contains one or more individual `<FaultRule>` sections. Each FaultRule represents a different error that you want to handle. In the folowing example, we will use only one FaultRule to demonstrate its composition:

You should also include a `<DefaultFaultRule>` to provide a custom general error message in case none of your FaultRules are executed.

Example:

> ### Sample Code:  
> ```
> <faultRules>
>   <faultRule>
>      <name>"invalid_key_rule"</name>
>      <condition>(fault.name = "FailedToResolveAPIKey")</condition>
>       <steps>
>           <step>
>              <policy_name>invalid-key-message</policy_name>                    
>              <sequence>1</sequence>
>           </step>
>       </steps>
> </faultRule>
> </faultRules>
>     <defaultFaultRule>
>         <name>"default-fault"</name>
>         <steps>
>             <step>
>                 <policy_name>Default-message</policy_name>
>                 <sequence>1</sequence>
>             </step>
>         </steps>
>     </defaultFaultRule>
> 
> ```

**Key points:**

-   **`<Name>`**: FaultRule name.
-   **`<policy_name>`**: The name of the policy to be executed. The name is derived from the policy's name attribute on the parent element.
-   **`<Condition>`**: API Management evaluates the condition and executes the policy only if the condition is true. If multiple FaultRules evaluate to true, API Management will execute the first one that is true. It is important to note that the order in which the FaultRules are evaluated, top to bottom or bottom to top, differs between the TargetEndpoint and ProxyEndpoint. If you don't include a condition, the FaultRule is automatically considered true. However, this is not considered a best practice. It is recommended that each FaultRule has its own condition specified.
-   **`<DefaultFaultRule>`**: If no custom FaultRule is executed, the `<DefaultFaultRule>` is triggered, and it sends a more generic custom message instead of the default API Management-generated message. A `<DefaultFaultRule>` can also have a `<Condition>`, but in most cases, you would not include one because you want it to execute regardless of any specific conditions, serving as a last resort.

    The `DefaultFaultRule` is typically used to return a generic error message for any unexpected error. For instance, it can include contact information for technical support. This default response serves the dual purpose of providing developer-friendly information while also obfuscating backend URLs or other information that might be used to compromise the system.




<a name="loio8be5a7b5876a498799470a4ab495091a__section_txx_pbf_qbc"/>

## Multiple FaultRules and Execution Logic

This section describes the logic API Management uses in handling FaultRules, from how it arrives at a single FaultRule to execute to how "inner" Step conditions are handled when their FaultRule is triggered. Additionally, it provides guidance on when to define FaultRules in the `<ProxyEndpoint>` versus the `<TargetEndpoint>`.



### FaultRules Execution

**Outer and Inner Conditions**: Now, let us refer to "outer" and "inner" conditions, which can also be called "FaultRule" and "Step" conditions, respectively. It is crucial to understand the difference between these two types of conditions. Here is an example of a FaultRule that includes both an outer FaultRule condition and an inner step condition. We will explore the differences further below.

> ### Sample Code:  
> ```
> <FaultRule name="over_quota">
>             <Step>
>                 <Name>developer-over-quota-fault</Name>
>                 <!-- Inner (Step) condition. Only gets executed if 
>                      the FaultRule is executed. -->
>                 <Condition>(ratelimit.developer-quota-policy.exceed.count GreaterThan "0")</Condition>
>             </Step>
>             <!-- Outer (FaultRule) condition. API Management evaluates this 
>                  to determine whether or not to execute 
>                  the FaultRule. -->
>             <Condition>(fault.name = "QuotaViolation")</Condition>
>         </FaultRule>
> ```

In brief, here's the logic that API Management uses when an API proxy goes into an error state. It is important to note that there is a slight difference in the evaluation of FaultRules between the ProxyEndpoint and the TargetEndpoint:

1.  API Management evaluates the FaultRules in either the ProxyEndpoint or TargetEndpoint, depending on where the error occurred:

    -   **ProxyEndpoint**: API Management starts from the bottom `<FaultRule>` in the configuration XML and proceeds upwards, evaluating the `<Condition>` of each `<FaultRule>` \(the "outer" condition, not the "inner" `<Step>` conditions\).

    -   **TargetEndpoint**: API Management starts from the top `<FaultRule>` in the configuration XML and proceeds downwards, evaluating the `<Condition>` of each `<FaultRule>` \(the "outer" condition, not the "inner" `<Step>` conditions\).


2.  Executes the first FaultRule whose condition is true. If a FaultRule has no condition, it's true by default.

    -   When a FaultRule is executed, all Steps within the FaultRule are evaluated sequentially, from top to bottom in the XML configuration. Steps that do not have conditions are automatically executed, meaning their policies are executed, and Steps that have a `<Condition>` element that evaluates to "true" are executed, while those with conditions that evaluate to "false" are not executed.

    -   If a FaultRule is executed, but none of the Steps in the FaultRule are executed \(due to their conditions evaluating to "false"\), the API Management-generated default error message is returned to the client application. The `<DefaultFaultRule>` is not executed because API Management has already executed its own FaultRule.

        > ### Note:  
        > The exception to this is if the `<DefaultFaultRule>` has the child element `<AlwaysEnforce>true</AlwaysEnforce>`, which executes the DefaultFaultRule even if a FaultRule was executed.
        > 
        > However, there's one instance where this isn't the case. If a FaultRule other than the DefaultFaultRule invokes a RaiseFault policy, the DefaultFaultRule does not execute, even if the `<AlwaysEnforce>` element in the `<DefaultFaultRule>` tag is true.


3.  If no FaultRule is executed, API Management executes the `<DefaultFaultRule>`, if present.




### ProxyEndpoint execution

The evaluation of ProxyEndpoint FaultRules is done from bottom to top. Therefore, you should begin reading from the last FaultRule in the following sample and proceed upwards. Finally, consider the DefaultFaultRule as the last one to analyze.

> ### Sample Code:  
> ```
> <ProxyEndpoint name="default">
> ...
>     < faultRules >
> <!-- 3. This FaultRule is automatically TRUE because there is no "outer" 
> 	condition. However, since the FaultRule just below this one 
> 	was executed (due to bottom-to-top evaluation in a ProxyEndpoint),
> 	API Management does not evaluate this FaultRule.
> 	Note that it's not a best practice to have a FaultRule without 
> 	an outer condition, which automatically makes the FaultRule true. -->
> 
> <faultRule>
>             <name> random-error-message </name>
>             <steps>
>                 <step>
>                     <policy_name>Random-fault</policy_name>
>                     <sequence>1</sequence>
>                 </step>
>             </steps>
>         </faultRule>
>   
> 
> <!-- 2. Let's assume this fault is TRUE. The Quota policy has thrown a QuotaViolation
> 	error. Since this is the first FaultRule to be TRUE, it will be executed.
> 	Next, the Steps are evaluated, and for those whose conditions evaluate
> 	to TRUE,their policies are executed. Steps without conditions are
> 	automatically considered true. -->
> 
> <faultRule>
>             <name> over_quota </name>
>             <steps>
>                 <step>
>                     <policy_name> developer-over-quota-fault </policy_name>
>                  <Condition>(ratelimit.developer-quota-policy.exceed.count GreaterThan "0")</Condition>
>                     <sequence>1</sequence>
>                 </step>
>                 <step>
>                     <policy_name>global-over-quota-fault</policy_name>
>                   <Condition>(ratelimit.global-quota-policy.exceed.count GreaterThan "0")</Condition>
>                     <sequence>1</sequence>
>                 </step>
>                   <step>
>                     <policy_name> log-error-message </policy_name>
>                     <sequence>1</sequence>
>              </step>
>               <Condition>(fault.name = "QuotaViolation")</Condition>
>             </steps>
>         </faultRule>
> 
> 
> <!-- 1. Because this is the ProxyEndpoint, API Management evaluates this FaultRule first.
> 	However, let's assume that this FaultRule is FALSE, meaning that a policy did not
> 	throw a FailedToResolveAPIKey error. In such a case, API Management proceeds to
> 	check the next FaultRule.
> 
>   <faultRule>
>             <name> invalid_key_rule </name>
>             <steps>
>                 <step>
>                     <policy_name> invalid-key-message </policy_name>
>                     <sequence>1</sequence>
>                 </step>
>             <Condition>(fault.name = "FailedToResolveAPIKey")</Condition>
>             </steps>
>         </faultRule>
> 
> 
> <!-- If no <FaultRule> is executed, the <DefaultFaultRule> is executed. 
>      If a FaultRule is executed, but none of its Steps are executed,
>      The DefaultFaultRule is not executed (because API Management has already
>      executed its one FaultRule). -->
> 
> <defaultFaultRule>
>         <name>default-fault</name>
>         <alwaysEnforce>true</alwaysEnforce>
>         <steps>
>             <step>
>                 <policy_name>Default-message</policy_name>
>                 <sequence>1</sequence>
>             </step>
>         </steps>
>     </defaultFaultRule>
> 
> ```



### TargetEndpoint execution

The evaluation of TargetEndpoint FaultRules follows a top-to-bottom approach. Therefore, begin reading from the first FaultRule in the following sample and proceed downwards. Finally, consider the DefaultFaultRule as the last one to analyze.

> ### Sample Code:  
> ```
> <TargetEndpoint name="default">
> ...
>     <FaultRules>
> <!-- 1. Because this is the TargetEndpoint, API Management looks at this FaultRule
> 	first. Let's assume that this FaultRule is FALSE, indicating that a
> 	policy did not throw a FailedToResolveAPIKey error.
> 	API Management then moves down to the next FaultRule. -->
>           
> <faultRule>
>             <name> invalid_key_rule </name>
>             <steps>
>                 <step>
>                     <policy_name> invalid-key-message </policy_name>
>                     <sequence>1</sequence>
>                 </step>
>             <Condition>(fault.name = "FailedToResolveAPIKey")</Condition>
>             </steps>
>         </faultRule>
> 
> 
> <!-- 2. Let's say this fault is TRUE. The Quota policy threw a QuotaViolation
> 	error. This is the first FaultRule to be TRUE, so it's executed. 
> 	Now the Steps are evaluated, and for the ones whose conditions
> 	evaluate to TRUE, their policies are executed. Steps without
> 	conditions are automatically true. -->
> 
> <faultRule>
>             <name> over_quota </name>
>             <steps>
>                 <step>
>                     <policy_name> developer-over-quota-fault </policy_name>
>                  <Condition>(ratelimit.developer-quota-policy.exceed.count GreaterThan "0")</Condition>
>                     <sequence>1</sequence>
>                 </step>
>                 <step>
>                     <policy_name>global-over-quota-fault</policy_name>
>                   <Condition>(ratelimit.global-quota-policy.exceed.count GreaterThan "0")</Condition>
>                     <sequence>1</sequence>
>                 </step>
>                   <step>
>                     <policy_name> log-error-message </policy_name>
>                     <sequence>1</sequence>
>              </step>
>               <Condition>(fault.name = "QuotaViolation")</Condition>
>             </steps>
>         </faultRule>
> 
> 
> <!-- 3. This FaultRule is automatically TRUE, because there's no "outer" 
> 	condition. But because the FaultRule just above this got
> 	executed (top-to-bottom evaluation in a TargetEndpoint), API Management
> 	doesn't even evaluate this FaultRule.
> 	Note that it's not a best practice to have a FaultRule without 
> 	an outer condition, which automatically makes the FaultRule true. -->
>        
> <faultRule>
>             <name> random-error-message </name>
>             <steps>
>                 <step>
>                     <policy_name>Random-fault</policy_name>
>                     <sequence>1</sequence>
>                 </step>
>             </steps>
>         </faultRule>
>  
> 
> <!-- If no <FaultRule> is executed, the <DefaultFaultRule> is executed. 
>      If a FaultRule is executed, but none of its Steps are executed,
>      The DefaultFaultRule is not executed (because API Management has already
>      executed its one FaultRule). -->
>   
>   <defaultFaultRule>
>         <name>default-fault</name>
>         <alwaysEnforce>true</alwaysEnforce>
>         <steps>
>             <step>
>                 <policy_name>Default-message</policy_name>
>                 <sequence>1</sequence>
>             </step>
>         </steps>
>     </defaultFaultRule>
> 
> ```



<a name="loio8be5a7b5876a498799470a4ab495091a__section_l52_kb4_mbc"/>

## Fault rule order

As you can see in the previous example, the order in which you place your FaultRules is important, depending on whether the error occurs in the ProxyEndpoint versus the TargetEndpoint.


<table>
<tr>
<th valign="top">

ProxyEndpoint order

</th>
<th valign="top">

TargetEndpoint order

</th>
</tr>
<tr>
<td valign="top">

In the following example, since evaluation is performed from bottom to top, FaultRule 3 is executed, which means FaultRules 2 and 1 are not evaluated:

5. FaultRule 1: FALSE

4. FaultRule 2: TRUE

3. FaultRule 3: TRUE

2. FaultRule 4: FALSE

1. FaultRule: 5 FALSE

</td>
<td valign="top">

In the following example, since evaluation is performed from top to bottom, FaultRule 2 is executed, which means FaultRules 3, 4, and 5 are not evaluated:

1. FaultRule 1: FALSE

2. FaultRule 2: TRUE

3. FaultRule 3: TRUE

4. FaultRule 4: FALSE

5. FaultRule: 5 FALSE

</td>
</tr>
</table>

