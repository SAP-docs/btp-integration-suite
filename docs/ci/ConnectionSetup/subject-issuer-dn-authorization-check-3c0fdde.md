<!-- loio3c0fddecb3304e3c85c314dbdbb3ed82 -->

# Subject/Issuer DN authorization check

It is checked \(for a specific integration flow\) if the subject/issuer distinguished name \(DN\) of the assigned certificate matches the incoming certificate.

If yes, this specific integration flow can be processed. The authorization check is performed based on the distinguished name \(DN\) of the client certificate. The DN has to be specified when configuring the relevant integration flow.

