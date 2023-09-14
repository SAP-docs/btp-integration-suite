<!-- loio7752ba94975148d7aa0149afafbde8dd -->

# Other Security-Related Information

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



<a name="loio7752ba94975148d7aa0149afafbde8dd__section_cqt_v1x_vgb"/>

## User Interface Security

Cloud Integration provides user interfaces for designing and deploying message flows, and monitoring them at runtime.

A Web tool \(Web UI\) is available to accomplish these tasks. The Web UI is implemented using JavaScript and HTML \(UI5\).

This user interface is built to prevent vulnerabilities such as cross-site scripting \(XSS\) and cross-site request forgery \(XSRF\). The built-in security capabilities of these technologies are used together with secure design and coding principles.



<a name="loio7752ba94975148d7aa0149afafbde8dd__section_zlc_y1x_vgb"/>

## Security Measures for Remote API

You can access certain functions of Cloud Integration through application programming interfaces \(APIs\).

The OData API is protected by basic authentication.

In order to protect the API against CSRF \(cross-site request forgery\) attacks, modifying operations \(for example, POST, DELETE\) should be used in conjunction with session-based authentication and client-side CSRF handling.



<a name="loio7752ba94975148d7aa0149afafbde8dd__section_iyw_svk_qqb"/>

## Auditing and Logging Information

More information: [Auditing and Logging Information](../SecurityCF/auditing-and-logging-information-d1c7bfe.md)

