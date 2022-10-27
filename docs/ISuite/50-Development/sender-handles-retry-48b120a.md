<!-- loio48b120a03f524f9d9f4d497f392b46da -->

# Sender Handles Retry

The sender supports message retry.

It's assumed that the message ID remains the same for all retries. If the call fails at first place, the sender retries until the message is successfully delivered

**Related Information**  


[Receiver Is Idempotent](receiver-is-idempotent-f5b22ba.md "The receiver is idempotent. This means that the receiver is able to detect and ignore duplicate messages.")

[Receiver Isn't Idempotent](receiver-isn-t-idempotent-c6104e5.md "The receiver system isn't idempotent. That means: The receiver isn't able to identify and discard duplicate messages. Therefore, the middleware needs to handle duplicate messages.")

