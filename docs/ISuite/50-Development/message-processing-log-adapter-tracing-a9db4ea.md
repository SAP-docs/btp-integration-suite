<!-- loioa9db4eab676443ec999e8f7f5b760c2e -->

# Message Processing Log - Adapter Tracing

The adapter tracing is part of the regular tracing feature and the payloads are recorded if you have set the log level to `Trace`.

The adapter tracing is only possible for adapters that transform the message either before sending or upon reception, such as *AS2*, *Ariba*, *LDAP*, *Mail*, *SuccessFactors* and *HTTP/HTTPS*. You also get tracing information for integration flows containing *CFX* based adapters such as*IDOC*, *SOAP*, *SAPRM*, but in this case you have to redeploy the integration flow to get the tracing data recorded in the regular tracing feature and displayed.

Adapter tracing is not possible for *SMS*, *SFTP*, *Facebook*, *Twitter* and *Process direct*, as they do not modify the payload.

> ### Remember:  
> For log level `Trace` , detailed information is recorded for all steps and in addition, the message content is tracked . The trace function expires after a certain time \(default value: 10 minutes\). After expiry the log level switches back to the log level set before. The recorded message content is also retained for a certain time \(default value: 1 hour\).

To show the trace information details, select an integration flow from the overview list, go to the*Log*section and open the link by clicking the log level.

In the integration flow model, the trace entries are displayed as little filled envelopes.

If the payload was recorded for a specific step of an adapter, you can open it the *Message Content* of the details page of the processing step. The payload is displayed with header and content. You can also download it by clicking on the *Download* button on top right corner. This povides a zip file containg one header and one payload file.

