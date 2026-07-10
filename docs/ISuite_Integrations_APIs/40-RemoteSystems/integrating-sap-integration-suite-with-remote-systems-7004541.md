<!-- loio7004541069814b1990862a71dbea40d2 -->

# Integrating SAP Integration Suite with Remote Systems

You can set up the technical connection between a tenant and different kinds of remote systems \(in many cases located in the customer landscape\).

You can set up connections to implement the following use cases:

-   Enable a sender system to call an integration flow endpoint.

-   Enable SAP Integration Suite to send messages \(processed by an integration flow\) to a receiver system.


Throughout this documentation we assume the following basic setup of technical components and communication paths: A remote system \(which is not specified\) is being connected to one of the tenants that are assigned to the customer. The remote system can act either as a sender or a receiver of messages. The setup and the detailed configuration procedure differ according to the communication direction that is being set up: whether a remote system is supposed to send a message to the integration platform or the other way round.

Throughout this documentation, the terms *inbound* and *outbound* reflect the perspective of the integration platform.

-   **Inbound** refers to message processing from a remote system \(in many cases, located in the customer landscape\) to Cloud Integration. Here, the integration platform is the server.
-   **Outbound** refers to message processing from the integration platform to a remote system \(where the integration platform is the client\).

