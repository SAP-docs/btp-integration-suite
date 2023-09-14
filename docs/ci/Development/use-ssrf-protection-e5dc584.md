<!-- loioe5dc58436c5d43639131a0079b7094ad -->

# Use SSRF Protection

Learn to protect your systems from server-side request forgery \(SSRF\).

Server-Side Request Forgery is an attack where an application receives a malicious request from a user, and the application then uses unverified malicious data to fetch or interact with a secondary resource \(such as another app or service endpoint\). This attack results in a scenario where an attacker can force an application to take unwanted action, or retrieve data that a user would otherwise be unauthorized to interact with. You can find more information [here](https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/).



<a name="loioe5dc58436c5d43639131a0079b7094ad__section_ypj_vry_lyb"/>

## How the Attack Works

![](images/SSRF_Attack_d5602ef.png)

There are adapters in Cloud Integration that support dynamic address field. While processing an integration flow that uses such receiver adapters with a dynamic address field, a dynamic URL is generated to communicate with an external system. Such generated URL could be processed, resolved, and finally is able to fetch or pass on data to the external system. If there are vulnerabilities, access from the Internet to the external system takes place that otherwise would be unauthorized.

See [Parameters That Support Dynamic Configuration](parameters-that-support-dynamic-configuration-c9bba0e.md) to know the adapters that support dynamic address field. Search for the term "address" in the table.



<a name="loioe5dc58436c5d43639131a0079b7094ad__section_lcy_cdz_lyb"/>

## Recommendations to Avoid SSRF Attacks

-   Always validate untrusted input used to generate URLs for creating system to system interactions:

    -   Headers must be checked against an allowlist before passing to the adapters to initiate network communication \(e.g. to DB, caching service, document service etc.\)

    -   Check for allowed protocols. For example, allow `https://` but reject `//`, `file://`, `ldap://`, `gopher://`, `http://`, and port numbers.

    -   Add scripts to validate headers after the sender channel or just before receiver channel.


-   Check against a configurable list of allowed IP addresses and domain names of destinations that you want Cloud Integration to access:

    -   Use a preconfigured IP address or destination not using parameters like `CamelHttpUri` for secure implementations.

    -   Validate if the generated URL is compliant to an allowlist .


-   Enforce authentication and authorization checks for all endpoints that expose data. Be careful when designing an integration flow with authorization for lower inbound privilege and offers egress with more powerful credentials that can access dynamic endpoints.

-   Before returning data to a client, validate if a fetched resource's response body matches the expected content. If it doesn't, design your integration flow to fail the execution.


