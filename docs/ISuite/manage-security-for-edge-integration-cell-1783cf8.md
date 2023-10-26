<!-- loio1783cf87caa2449e96082f0cf754449d -->

# Manage Security for Edge Integration Cell

The manage security section allows you to manage various kinds of security-related artifacts according to the runtime deployment possibilities.

For each available runtime, you can create/add and deploy different security materials, such as.

-   User Credentials

-   Secure Parameters
-   OAuth2 Client Credentials
-   Oauth2 Saml Bearer Assertion
-   Known Hosts

> ### Restriction:  
> You can only deploy a maximum of 500 credentials per runtime \( excepting Known Hosts\).
> 
> The maximum size of a known hosts file is limited to 1 MB.

To manage security-related artifacts, choose the *Security Material* tile in the *Manage Security* section of the monitoring overview.

To access the security-related artifacts of a specific runtime, select a runtime from the drop-down list of the *Runtime* field. The Cloud Integration runtime is the default runtime for the Integration Suite, all other runtimes are Edge Integration Cell runtimes.

According to your selection from the drop-down list, you get two different views:


<table>
<tr>
<th valign="top">

All View

</th>
<th valign="top">

Runtime-specific View

</th>
</tr>
<tr>
<td valign="top">

-   You can see all the security-related artifacts for all runtimes.

-   You can create, edit, upload, and undeploy security artifacts. During creation or updating, you can assign security artifacts to specific runtimes \(including Cloud Integration\), in the corresponding dialog boxes.

    > ### Caution:  
    > If you undeploy a security-related artifact in the *All* view, it's undeployed from all the runtimes, with all related data.


The number displayed in the *Runtime* column indicates the different runtimes the security-related artifact is deployed on. To see the different runtimes, select the number.

</td>
<td valign="top">

-   You can see all security-related artifacts deployed on the selected runtime.

-   You can add a security-related artifact to the specific runtime, or remove it.

-   You can see the deployment status of the security-related artifacts.


> ### Note:  
> If a security-related artifact is deployed on one runtime only, you can't remove it from the runtime using the *Runtime-specific* view. You've to switch to the *All* view, to undeploy the artifact.



</td>
</tr>
</table>

For more information, see [Managing Security Material](https://help.sap.com/docs/integration-suite/sap-integration-suite/managing-security-material?version=CLOUD).

