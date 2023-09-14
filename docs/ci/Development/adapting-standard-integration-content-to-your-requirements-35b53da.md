<!-- loio35b53da5afbe4844a942123d7146434f -->

# Adapting Standard Integration Content to Your Requirements

When you use standard \(predefined\) integration content published on SAP Business Accelerator Hub, there are two different ways how to adapt such content to meet the requirements of your concrete business scenario.

-   Modifying/editing the standard integration flow

-   Configuring externalized integration flow parameters




<a name="loio35b53da5afbe4844a942123d7146434f__section_ngh_tgd_h4b"/>

## Modifying/Editing the Standard Integration Flow

Using this option, you modify the integration flow in *Edit* mode and change its design, for example, by adding new integration flow steps or channels. Modifying an integration flow this way allows you also to change parameter values predefined in the integration flow model.

However, be aware of the fact that when using this option you can run into conflicts when SAP provides an update of the associated integration package. Note that as soon as you've modified a predefined integration flow, you don’t get any further updates to it when SAP provides an update of the related integration package. Furthermore, if you copy an **updated** standard integration package from SAP Business Accelerator Hub to the *Design* workspace of your tenant, you overwrite all changes that you have made to that package before this action.

If you, nevertheless, like to modify standard integration content, it's recommended that you decouple your modifications from the standard content.

More information: [Keep Modifications Separate from Prepackaged Integration Content](keep-modifications-separate-from-prepackaged-integration-content-1f4c046.md)

> ### Note:  
> You can only modify content of a standard integration package if its mode is set to *Editable*.
> 
> There are dedicated standard integration packages that don't allow a user to modify its content \(*Configure-only* mode\). In such a case, you can only configure externalized parameters of the contained integration content \(as described under *Configuring Externalized Integration Flow Parameters*\).



<a name="loio35b53da5afbe4844a942123d7146434f__section_iqd_5gd_h4b"/>

## Configuring Externalized Integration Flow Parameters

When you use a predefined integration flow, it’s likely that certain parameters are defined as *externalized parameters*. When having copied an integration package from SAP Business Accelerator Hub to the *Design* workspace of your tenant, you have the option to configure the values of externalized integration flow parameters. Choosing this option allows you to adapt the integration flow without the need to modify the integration flow model in *Edit* mode.

Typically, the integration developer who provides the standard integration flow has externalized parameters such like, for example, address parameters of adapters. Such parameters typically can't be foreseen by the provider of the standard integration package. The reason is that the values of such parameters depend on the concrete environment and system landscape where the integration flow is finally to be deployed. To enable the integration flow to run in a dedicated environment, such parameters anyway need to be adapted by the consumer of the standard integration package.

When you have configured externalized parameters of integration flow parameters, you can still receive updates of the associated standard integration package.

More information: [Configure Externalized Parameters of an Integration Flow](configure-externalized-parameters-of-an-integration-flow-462a478.md)

