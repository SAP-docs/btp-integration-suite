<!-- loio035a1c917b6149558c3d03f7d02d7b55 -->

# SAP Integration Suite Handles Retry

The sender doesn't retry messages.

Therefore, Cloud Integration needs to carry out the retry of the message delivery if there's an error.

Cloud Integration can handle retries with the following components \(for example\):

-   JMS adapter with JMS queue

-   XI sender adapter


**Related Information**  


[Receiver Is Idempotent](receiver-is-idempotent-9892432.md "The receiver is idempotent. This means that the receiver is able to detect and ignore duplicate messages.")

[Receiver Isn't Idempotent](receiver-isn-t-idempotent-5955d3f.md "The receiver system isn't idempotent. That means: The receiver isn't able to identify and discard duplicate messages. Therefore, the middleware needs to handle duplicate messages.")

