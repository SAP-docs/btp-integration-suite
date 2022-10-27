<!-- loioc918e2803dfd4fc487e86d0875e8462c -->

# Policy Types

Policies define a set of rules \(such as, enforce security, control traffic, and so on\) that is applied on the API.

Before you start defining policies, it is important to understand some common attributes that all policies share:

-   `enabled`: This attribute determines whether a policy is switched on or off. Set this attribute to `true` to switch the policy on. A policy that has enabled set to `false` is not executed at runtime.

-   `continueOnError`: Determines whether a policy should continue processing the message if the policy execution fails. For quota policies where the errors indicate that the policy limit has exceeded, this field should be set to `false`.
-   `async`: Set `async=true` if you want the policy to run in a different thread that is isolated from the regular thread that services the request or response Flow.


The following is the list of prebuilt policies supported by Integration Suite:

-   Access Control
-   Access Entity
-   Assign Message
-   Basic Authentication
-   Extract variables
-   Invalidate Cache
-   JavaScript
-   JSON to XML
-   Key Value Map Operations
-   Lookup Cache
-   Message Logging Policy
-   OAuth v2.0
-   OAuth v2.0 GET
-   OAuth v2.0 SET
-   Populate Cache
-   Python Script
-   Quota
-   Raise Fault
-   Reset Quota
-   Service Callout
-   Spike Arrest
-   SAML Assertion Policy
-   SOAP Message Validation Policy
-   Verify API Key
-   XML to JSON
-   XSL Transform
-   XML Threat Protection
-   Regular Expression Protection
-   JSON Threat Protection
-   Response Cache
-   Statistics Collector Policy

For more information on Security policies, see [https://blogs.sap.com/2017/08/22/sap-cloud-platform-api-management-api-security-best-practices/](https://blogs.sap.com/2017/08/22/sap-cloud-platform-api-management-api-security-best-practices/)

