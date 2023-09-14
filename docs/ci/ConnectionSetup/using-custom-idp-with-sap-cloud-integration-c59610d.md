<!-- loioc59610d483974fcda631af4a2aae586b -->

# Using Custom IDP with SAP Cloud Integration

SAP Cloud Integration supports the usage of custom identity providers. By default, SAP Cloud Integration uses the global standard *account.sap.com* as the identify provider. However, you can use a tenant-specific Identity Authentication Service or your own SAML based identity provider.

For more information on configuring custom IDP, see [Authentication](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e637f62abb571014857cb0232adc43a7.html).



<a name="loioc59610d483974fcda631af4a2aae586b__section_sy1_cyl_vdb"/>

## Change Account Configuration to Basic Authentication While Using a Tenant-Specific Identity Authentication Service

> ### Note:  
> These instructions are relevant only when you use SAP Cloud Integration in the Neo environment.

Let us consider a scenario where you are using a custom IDP and you are able to log in to SAP Cloud Integration web application. However, when you try to connect to the operations server using **Basic Authentication**, you will be unable to log in using your custom IDP credentials

In SAP Cloud Integration this is due to the usage of the Eclipse UA and the OData API. If you consider using the same credentials for these two use cases, you need to change your account configuration to basic authentication.

You can change this configuration using the SAP BTP cockpit. For more information, see [Basic Authentication](https://help.sap.com/docs/BTP/ea72206b834e4ace9cd834feed6c0e09/a2c696be81c14da189ccaeae9a2d687f.html).

> ### Remember:  
> Only *account.sap.com* and *Identity Authentication Service* can be configured for basic authentication. You are not allowed to use any arbitrary custom IDP for this use case.



<a name="loioc59610d483974fcda631af4a2aae586b__section_kbd_cgg_wrb"/>

## Set up Custom IDP within Cloud Foundry Environments

> ### Note:  
> These instructions are relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.

For more information see: [Setting Up SAP Identity Authentication Service as Custom IdP for Basic Authentication, Cloud Foundry Environment](setting-up-sap-identity-authentication-service-as-custom-idp-for-basic-authentication-clo-0668507.md)

If you open a support ticket on the component **BC-CP-CF-SEC-IAM** to get help from SAP.

