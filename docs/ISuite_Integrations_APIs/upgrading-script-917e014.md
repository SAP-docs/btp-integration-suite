<!-- loio917e014b47094620b2616c125e1a86f3 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Upgrading Script

Learn how to upgrade your script to the latest version to utilize advanced features and help prepare your integrations for future enhancements and upgrades.



## Why Script 2.0

Upgrading the script including Groovy and Java to the latest version will yield following benefits:

-   Future-ready scripts: Receive automatic fixes for incompatible libraries and classes. This helps prepare your scripts for a seamless migration during runtime and software upgrades. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md) and [Use recommended libraries and classes](scripts-fa29f02.md#loiofa29f02c19e744528b50fd721959f337__proxy-usecase)

-   Advance Features: With the runtime 4.0.29, stay compliant with the product standards and use modern language elements such as switch expressions and other capabilities. See release notes



### Prerequisite

You have already added a script step in your integration flow. See [Define a Local Script Step](define-a-local-script-step-03b32eb.md)



### Context

Once you [execute](design-guidelines-view-d62dfe0.md) the design guidelines for your integration flow and the Analysis includes script non-compliance, you can choose to navigate the script editor to [fix those incompatibilities](fix-script-incompatibilities-7397c42.md). You must upgrade your scripts to help maintain compatibility with future upgrades and receive resolution for violations.

> ### Note:  
> The [Resource ODATA APIs](https://api.sap.com/api/IntegrationContent/resource/put_IntegrationDesigntimeArtifacts_Id___Id___Version___Version_____links_Resources_Name___Name___ResourceType___Type___) only support version v1.



### Procedure

You can upgrade your script step to the latest version 2.0, which utilizes runtime 4.0.29.

1.  Open your script in its editor.
2.  Choose *Upgrade* to update the script step to version 2.0. All the script steps that utilize this script will also be updated to version 2.0.

    > ### Note:  
    > To check the current version of the script step, choose the script flow step from your integration flow, and choose <span class="SAP-icons-V5"></span> icon.

3.  In the confirmation dialog box, choose *Upgrade*.

    A copy of your older version of script is retained in Scripts folder if you wish to revert to the older version and the updated version doesn't meet your requirements. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md) and [Scripts](scripts-fa29f02.md)

    You can now receive automatic fixes for incompatibilities like unused import statements, unsupported libraries, and proxy-based classes.

    > ### Recommendation:  
    > [Simulate](simulation-of-an-integration-flow-2e2210b.md) your integration flow with the updated script step to validate it is producing expected outcome.




<a name="loio917e014b47094620b2616c125e1a86f3__down_grade"/>

## Downgrading a Script



### Prerequisite

You have upgraded the script step to version 2.0.



### Context

If the updated version of the step does not yet fit your use case, you can downgrade the script step and revert to the older version. To resolve the issue, follow the below procedure and create a [ticket](https://help.sap.com/docs/link-disclaimer?site=http%3A%2F%2Fsupport.sap.com) using the component LOD-HCI-PI-WT-IFL. However, you must adapt your business processes to use the upgraded script that helps prepare your integrations for future upgrades.



### Procedure



1.  Open your script in its editor.
2.  Choose *Downgrade* to revert your script step to the initial version 1.1.
3.  In the confirmation dialog box, choose *Downgrade*.

    The updates made to the version 2.0 of the script will be discarded. All the script steps utilizing this script will also be downgraded to version 1.1.




