<!-- loio02ea0c585869489f893359c8bb552a30 -->

# Camel Upgrade

Apache Camel runtime will be updated from version 2.24 to 3.14.7.

To ensure seamless migration to the new runtime, you must validate your [custom integration adapters](../developing-custom-adapters-7392cc4.md) in the new runtime version before the software is updated with it.

> ### Note:  
> This upgrade is significant only if you have deployed custom integration adapters in your tenant.

This is a two-step process. In the first step, you request a test tenant, which is equipped with Camel 3.14 runtime where you validate your custom integration adapters.

In the second step, upload the compatible adapters from your existing production tenant, so that they are made available in your tenant when the software is updated with the new runtime version.

