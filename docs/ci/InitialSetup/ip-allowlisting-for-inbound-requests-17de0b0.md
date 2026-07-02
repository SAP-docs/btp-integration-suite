<!-- loio17de0b08d7a3404a992dc14e8148b2e6 -->

# IP Allowlisting for Inbound Requests

To protect Cloud Integration against unwanted inbound requests, you can configure IP allowlisting.

> ### Tip:  
> IP allowlisting is a security measure that restricts access to a system based on a predefined list of approved IP addresses. Only connections originating from these approved IP addresses are allowed, all others are blocked.



<a name="loio17de0b08d7a3404a992dc14e8148b2e6__section_htl_jkm_j1c"/>

## Cloud Foundry Environment

Currently, you need to configure IP allowlisting by integration flow design. The following SAP Community blog provides a solution using the header `x-forwarded-for` in a script that blocks requests from a particular IP address: [IP Allowlisting in SAP Cloud Integration](https://community.sap.com/t5/technology-blogs-by-sap/ip-allowlisting-in-sap-cloud-integration/ba-p/13364519).



<a name="loio17de0b08d7a3404a992dc14e8148b2e6__section_ivz_lkm_j1c"/>

## Neo Environment

Configure IP allowlisting on platform level by setting up custom domains as explained under [Configuring Custom Domains](../Operations/configuring-custom-domains-7230b9f.md).

