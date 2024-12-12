<!-- loio735300cf6618483fb9eb79b8ef22b477 -->

# Consuming HTTP Assets

Learn how to initiate contract negotiations and transfer HTTP assets from a provider's catalog.

If the asset you want to consume is an **HTTP** asset, complete the following steps:

1.  You've already discovered the asset you want to consume from a provider's catalog.

    See [Discovering Offers Through a Catalog](discovering-offers-through-a-catalog-90f3619.md).

2.  Next, trigger a contract negotiation with the provider of the asset. Once you've reached an agreement, start the transfer process of the asset.

    See [Triggering Contract Negotiations and Transferring Assets with EDR Management APIs](triggering-contract-negotiations-and-transferring-assets-with-edr-management-apis-eace95e.md).

3.  Once the transfer process is finished, you can continue with consuming the HTTP asset.

    See [Consuming Assets](consuming-assets-f6b27ac.md).


The following diagram illustrates the data exchange between consumer and provider of an HTTP asset:

![The diagram illustrates the interactions between consumer and provider with regards to contract agreements. The consumer discovers the provider's offers in the catalog and initiates negotiation between them. After successful negotiation, the consumer receives an agreement ID from the provider, which they can use to initiate the transfer process. The consumer then calls the target URL and gets the asset provided by the provider.](images/Dataspace_Integration_Consumption_Process_cfeb40e.png)

