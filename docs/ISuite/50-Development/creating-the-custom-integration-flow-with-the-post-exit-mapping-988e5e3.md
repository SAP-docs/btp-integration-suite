<!-- loio988e5e3149a045a388d45a5d0027743c -->

# Creating the Custom Integration Flow with the Post-Exit Mapping

> ### Note:  
> This section is targeted at the customer who is doing a mapping extension.

This integration flow is kept very simple.

![](images/CUSTOMINTEGRATIONFLOW_dcb78f1.png)

-   The sender shape in this model represents the standard integration flow \(which is the source integration or producer integration flow\). The custom integration flow receives the message from the producer integration flow through the ProcessDirect adapter \(as both integration flows are deployed on the same tenant\).

-   The post-exit message mapping step contains the mapping as explained under [Post-Exit Mapping](post-exit-mapping-0f17497.md).


**Related Information**  


 <?sap-ot O2O class="- topic/link " href="274e4d0ac4774d7792e5812d6aa98041.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/cdm1692607551357/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/988e5e3149a045a388d45a5d0027743c.xml" ?> 

[Configuring the ProcessDirect Sender Adapter](configuring-the-processdirect-sender-adapter-4787d80.md "")

[Creating the Custom Mapping](creating-the-custom-mapping-4af8ea7.md "")

