<!-- loio0e38815915554144ba19e13155d02a6b -->

# Manually Rotate Signing Keys of Access Tokens

You can manually rotate the signing keys for the access tokens of the Edge Local Authentication and Authorization component.



<a name="loio0e38815915554144ba19e13155d02a6b__context_djk_m33_1fc"/>

## Context

The Edge Local Authentication and Authorization component periodically rotates the signing keys used for signing and verifying access tokens. This rotation happens automatically. You can also manually rotate the signing keys for access tokens via *Component Monitor* in the Operations Cockpit. For more information, see [Component Monitor](../component-monitor-49f487e.md).

Follow these steps to manually rotate the signing keys:



## Procedure

1.  In the Operation Cockpit, choose the *Component Monitor* card.

2.  Open the *Actions* menu from the Edge Local Authentication and Authorization component.

3.  Choose *Rotate Signing Key*. The new dialog window displays information about the current and deprecated signing keys.

4.  Choose *Rotate* to deprecate the current key and generate a new one.

5.  In the confirmation dialog window, you can:

    1.  Confirm the *Rotate* action to rotate the signing key for access tokens. A new active signing key is created, and the old one becomes deprecated. The deprecated key can still verify already issued tokens.

        > ### Note:  
        > Performing the *Rotate* action in the next 10 minutes is idempotent. You can rotate the signing key again after this interval.

    2.  Confirm the *Rotate* action with the check-box selected. By purging the key, the new signing key is used immediately for signing and verifying access tokens, without any grace period.


    > ### Note:  
    > Use this option only in exceptional cases. For instance, when a private key is compromised. This operation might cause active requests to fail, as tokens can't be verified anymore.


**Related Information**  


 <?sap-ot O2O class="- topic/link " href="8cb10332523e4a2a85b4204701a26a43.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/0e38815915554144ba19e13155d02a6b.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

