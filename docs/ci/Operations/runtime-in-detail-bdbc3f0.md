<!-- loiobdbc3f0224864ad5b163355ec537f6c6 -->

# Runtime in Detail

For different customers, separate resources \(in terms of: memory, CPU, file system\) of the cloud-based integration platform are allocated – although all customers share the same hardware. This concept is also referred to as tenant isolation.

At runtime, data is processed on a tenant allocated for a connected customer.

> ### Note:  
> A tenant represents the resources of the cloud-based integration platform allocated for a customer. Typically one tenant is defined for each customer connected to the platform.

It is always made sure that each tenant uses a separate database schema, which guarantees that data of different customers is strictly separated. The architecture guarantees that different tenants are unable to interfere and that physical resources of the cloud platform are partitioned per tenant.

For more information on the architecture, see:

-   [Technical Landscape, Cloud Foundry Environment](../SecurityCF/technical-landscape-cloud-foundry-environment-cc22301.md) \(for the Cloud Foundry environment\)

-   [Technical Landscape, Neo Environment](../SecurityNeo/technical-landscape-neo-environment-7fec71d.md) \(for the Neo environment\)


