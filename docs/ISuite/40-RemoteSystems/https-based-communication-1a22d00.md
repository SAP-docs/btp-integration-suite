<!-- loio1a22d0089ba94706a1c3e3baf99bcf2d -->

# HTTPS-Based Communication

Certain adapters support communication based on Hypertext Transfer Protocol Secure \(HTTPS\).

HTTPS uses the Transport Layer Security \(TLS\) protocol.

> ### Note:  
> Mutual TLS \(mTLS\) is equivalent to client certificate authentication. While setting up the TLS connection, client and server exchange certificates. With mTLS, not only server certificates, but also client certificates are validated based on the signatures provided by certification authorities. For more information, see [Client Certificate Authentication \(Outbound\)](client-certificate-authentication-outbound-c4e4a15.md) and [Keystore](keystore-b163513.md).

> ### Note:  
> Note regarding the timeout behavior for HTTP communication:
> 
> In HTTP communication spanning multiple components \(for example, from a sender, through the load balancer, to Cloud Integration, and from there to a receiver\), the actual timeout period is influenced by each of the timeout settings of the individual components that are interconnected between sender and receiver. To be more precise, the timeout is influenced by those components in your landscape that can control the Transmission Control Protocol \(TCP\) session. The component or device with the lowest number set for the idle session timeout defines the timer.
> 
> -   When considering inbound communication \(through HTTP-based sender adapters\), note that in particular the load balancer has an own timeout setting that influences the overall timeout. For the inbound side, SAP recommends that you design your scenario in such a way that no communication that waits for longer than 10 minutes is expected. In general, it is recommended to keep waiting times as short as possible to avoid unnecessary load on the network traffic.
> 
> -   When considering outbound communication, note that you can configure a dedicated timeout in the involved HTTP-based receiver channel. However, the timeout setting has no influence on the TCP timeout when the receiver or any additional component interconnected between Cloud Integration and the receiver has a lower timeout. For example, consider that you have configured a receiver channel timeout of 10 minutes and there's another component involved with a timeout of 5 minutes. If nothing has been transferred for a certain amount of time, the connection is closed after 5 minutes have passed.

**Related Information**  


[Authentication and Authorization Options \(Inbound\)](authentication-and-authorization-options-inbound-983f2a5.md "When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.")

[Authentication Options \(Outbound\)](authentication-options-outbound-58a7537.md "For outbound communication through HTTPS (when the tenant sends a message to a receiver), the following authentication options are supported.")

[Load Balancer Root Certificates Supported by SAP](load-balancer-root-certificates-supported-by-sap-4509f60.md "The load balancer supports a certain list of root certificates.")

