<!-- loio69a8b9b430dc48209125ce17431635e6 -->

# Checking the Default Trace \(in the Neo Environment\)

To analyze runtime errors, you can check the default trace.



To do that, open the *Operations* view and click the *System Log Files* tile. Check out the latest files starting with `ljs_trace_` \(which you can also download to your computer\). You notice that there are multiple entries with a similar same time stamp \(*Updated At*\).

> ### Note:  
> One log is written for each runtime node started on the tenant.

More information:

[Monitoring System Log Files, Neo Environment](monitoring-system-log-files-neo-environment-aac82bd.md)

[Cloud Integration – System Log Download](https://blogs.sap.com/2018/02/12/cloud-integration-system-log-download/) \(SAP Community blog\)

For a detailed instruction how to analyze the default trace in the context of inbound connection issues, check out the following SAP Community blog: [Cloud Integration – How to Setup Secure HTTP Inbound Connection with Client Certificates](https://blogs.sap.com/2017/06/05/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client-certificates/).

