<!-- loioee8ba5b4c9354fbb8c07c24199f7540f -->

# Delay Software Update

Configure your tenants to receive monthly updates delayed by a week.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).





### What is Delay Software Update

You can now configure your tenants so that you receive the monthly updates and increments from SAP delayed by a week. The delay in update affects only the Cloud Integration runtime. The Cloud Integration design time gets updated without any delay.

> ### Remember:  
> -   The delay is applicable only for the monthly increments. If there are patch updates during the 1-week delay period, they're always applied on your tenants without any delay. For example, if there's a pending delayed monthly update for your tenant and meanwhile SAP pushes a patch update, then the delayed update is skipped and patch update gets applied without delay. This approach means that your tenant receives the monthly update and the patch update without any delay, as a part of the patch.
> 
> -   In the tenant where delay is enabled, new design time increments might not be available for consumption owing to dependency on the runtime. In certain cases, the new design time increments might be consumable but deploying them can lead to runtime errors. In either case, we recommend you to consume the new design time increments only after the runtime update.



### Why Delay Software Update

Using this feature, you can configure your production tenants for delayed updates and keep the test tenants untouched. This way, you get a week's time to test the new increments on your test tenants. You can use this week's time to identify any risks caused by the new increments on your custom-built integration flows. If such regressions happen during your testing, mitigate the same to SAP via the incident management system.

> ### Note:  
> Make sure that you mention "Regression" in your incident when you report regressions so that the incident can be handled appropriately.



### Prerequisites for the feature

The self-service capability to enable and disable delay software update is available under the *Settings* view for the tenant administrator with the **PI\_Administrator** role collection.



### Enable/Disable the feature

1.  Go to *Settings* \> *Integration*.

2.  Move to the *Software Updates* tab and choose *Edit*.

3.  Enable or disable the *Delay Software Updates* feature and choose *Save*.


> ### Remember:  
> -   If you enable the feature, all subsequent monthly updates are delayed by a week.
> 
> -   If you enable the feature before an update is triggered by SAP, the delay is effective from the immediate upcoming update.
> 
>     -   If you come back to the same screen after an update is triggered by SAP, you see a date on which the delayed update is scheduled for.
> 
> 
> -   If you enable the feature after an update is triggered by SAP, the delay is effective only from the next update cycle. The currently triggered update from SAP happens without any delay.
> 
> -   If you disable the feature after an update is triggered by SAP, the delay is still applicable for the currently triggered update. The delay isn't applicable only from the next update cycle and subsequent cycles.



### View the Runtime Version

After you receive communications about a monthly update, you can compare the current software build number of the Cloud Integration design time and runtime components in multiple tenants with the following steps. This way, you can see that your test tenant is updated to latest runtime while the production tenant \(or more than one tenants\) are on lower runtime versions.

1.  In the SAP Integration Suite home page, on the top-right corner, choose your profile button.

2.  Choose *About*.

    The software build numbers of SAP Integration Suite and the activated capabilities come up.


> ### Remember:  
> -   If you haven't enabled the delay, Cloud Integration and Cloud Integration runtime are on the same build number.
> 
>     > ### Note:  
>     > Even if you don't activate delay, it is possible for the Cloud Integration design time to be on higher versions, if there are patches applied after regular monthly updates.
> 
> -   If you have enabled the delay and
> 
>     -   SAP hasn't triggered an update – Cloud Integration and Cloud Integration runtime are on the same build number.
> 
>     -   SAP has triggered an update – Cloud Integration and Cloud Integration runtime are on the same build number. Additionally, you see a date on which the runtime component would be updated.
> 
>     -   SAP has applied an update – the capability Cloud Integration is on a higher build number than Cloud Integration runtime. Additionally, you see a date on which the runtime component would be updated.

