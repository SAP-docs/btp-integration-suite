<!-- loio6adb0caf41be4e069e8b7b8298a97032 -->

# Ensure Upgrade Readiness

This design guideline helps you create and maintain integration artifacts that are clean, consistent, and prepared for future runtime version upgrades.

> ### Note:  
> As a tenant administrator, you cannot disable these guidelines for your tenants.

As an integration developer, design your integration artifacts to be clean, consistent, and free from unsafe or outdated patterns. This ensures the integration artifacts in your tenant remain stable, easy to maintain, and ready to adopt major runtime version upgrades without disruptions and performance impacts. Regularly reviewing and aligning your integration content with best practices reduces hidden dependencies and simplifies future updates. See [Basic Concepts of Integration Design](basic-concepts-of-integration-design-ca0f6f7.md)

The Cloud Integration capability of SAP Integration Suite currently provides the checks and fixes to keep the script step in your integration flows ready for such upgrades.

**Related Information**  


[Groovy Script](groovy-script-fa29f02.md "A Groovy script step can be used in an integration flow for script operations on the message content.")

[Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md "Fix the incompatibilities in the scripts that are automatically identified by the script editor.")

[Design Guidelines](IntegrationSettings/design-guidelines-4d1c84f.md "As the integration lead for your organization, help your integration developers design enterprise-grade integration flows.")

