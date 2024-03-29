<!-- loioda1eeb1d4cf744e6ab0b230254a23a9e -->

# Renewal of User and Password

In this use case, the user \(through which a sender calls the tenant\) is replaced by a new user \(and password\).

Security artifact renewal has to be performed in the following sequence:

1.  SAP: Informs the sender administrator that the sender back-end system should use new user/password for communication with the tenant.
2.  Sender administrator: Changes the user and password in the HTTPS sender client \(sender back-end\).
3.  Sender administrator: Informs SAP that user has been changed in the sender client.

