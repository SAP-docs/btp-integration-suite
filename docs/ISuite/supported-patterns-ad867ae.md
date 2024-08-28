<!-- loioad867aea1fc749a99abc2cf643c94038 -->

# Supported Patterns

Learn about the patterns that are available in the migration tooling.

With the move from template-based approach to pattern-based approach, the migration tooling where all the flow steps are generated dynamically, which in turn, covers more ICOs for migration. In the template-based approach, there were 30+ templates that were supported which is simplified now to three patterns. While there are only three patterns, these patterns cover not only the 30+ templates but also much more scenarios that were not covered earlier. In summary, the patterns are elastic and can dynamically add flow steps to the migrated integration flow based on the steps used in the ICO.

> ### Note:  
> With the move from template-based approach to pattern-based approach, there are no regressions caused to the previously migrated ICOs using the old templates.

<a name="loio270776550dc34dbe97cb95403810f93f"/>

<!-- loio270776550dc34dbe97cb95403810f93f -->

## Point-to-Point Asynchronous

**Point-to-Point asynchronous interface between 1 sender and 1 receiver decoupled using two integration processes** is the basic version available within the Point-to-Point Asynchronous pattern. By default, the option to decouple the sender and receiver adapters is enabled.

![](images/P2P_ASYNC_0005_f42d898.png)

Either by having more components in your source ICO or by choosing the options available in the Migration Tooling, you can have different versions of the Point-to-Point Asynchronous pattern.

For example:

-   If your source ICO contains at least one message mapping object, the pattern becomes **Point-to-Point asynchronous interface between 1 sender and 1 receiver with 1 message mapping decoupled using two integration processes**.

-   If your source ICO contains at least one message mapping object, you enable the option to decouple the sender and receiver adapters, and you also enable the option to let the receiver adapter ignore duplicate messages, the pattern becomes **Point-to-Point asynchronous interface between 1 sender and 1 receiver with 1 message mapping and and 1 idempotent process decoupled using two integration processes**.


<a name="loioab015e027d85473f81e4323e370ac0a1"/>

<!-- loioab015e027d85473f81e4323e370ac0a1 -->

## Point-to-Point Synchronous

**Point-to-Point synchronous interface between 1 sender and 1 receiver** is the basic version available within the Point-to-Point Synchronous pattern.![](images/P2P_SYNC_0003_3c8e9ef.png)

By having more components in your source ICO, you can have different versions of the Point-to-Point Synchronous pattern.

For example:

-   If your source ICO contains message mapping objects for response and requests, the pattern becomes **Point-to-Point synchronous interface between 1 sender and 1 receiver with message mappings for request and response**.

-   If your source ICO contains XSLT mapping objects for response and requests, the pattern becomes **Point-to-Point synchronous interface between 1 sender and 1 receiver with XSLT mappings for request and response**.


<a name="loiob5d43f624696473b93b812cdc36277ad"/>

<!-- loiob5d43f624696473b93b812cdc36277ad -->

## Recipient List Asynchronous

Recipient list-based integration scenarios and content-based routing integration scenarios can be migrated using the pattern Recipient List Asynchronous.

For example, if your ICO is designed with a recipient list where the message is sent to the default receiver in case the receiver is not determined, the following pattern applies.![](images/RL_ASYNC_0003_5163d0f.png)

If your ICO is designed with 1 router and a receiver for each router branch sending message to default receiver in case of receiver not determined, the following pattern applies. ![](images/CBR_ASYNC_0003_b742101.png)

Similarly, based on other receipient list integration scenarios and content-based routing integration scenarios, the migration tooling applies the Recipient List Asynchronous pattern and dynamically adds the flow steps.

