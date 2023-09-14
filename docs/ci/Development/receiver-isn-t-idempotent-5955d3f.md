<!-- loio5955d3fa4f0944609454faa291d85694 -->

# Receiver Isn't Idempotent

The receiver system isn't idempotent. That means: The receiver isn't able to identify and discard duplicate messages. Therefore, the middleware needs to handle duplicate messages.



Usually, the duplicate check is done as close as possible to the application that uses the data. Ideally, the receiver handles duplicates. That means, the duplicate handling and the operation writing or updating data is done within the same transaction in the receiver system. This design ensures that if an application error occurs, the system rolls back persistence of the message ID in an idempotent repository. Therefore, a retry of the same message isn't considered as duplicate.

Let's assume that the receiver system isn't idempotent. That means: The receiver isn't able to identify and discard duplicate messages. In this case, the middleware \(Cloud Integration\) needs to handle duplicate messages. Although usually Exactly Once can be ensured, there's a marginal residual risk of error situations if this isn't the case. For instance, if the message has been successfully delivered to the receiver, however, the technical acknowledgment got lost in between due to network issues. In this case, the middleware treats the call as not successful, and a retry of the message isn't seen as duplicate. Finally, this behavior results in an At Least Once quality of service.

**Related Information**  


[Protocol Contains Unique ID](protocol-contains-unique-id-751c2c9.md "")

