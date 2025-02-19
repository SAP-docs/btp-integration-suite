<!-- loio3b7a5a1258ea469b963dc047c3f443a0 -->

# Optimize Groovy Scripts

Enhance your Groovy scripts using Generative AI.



<a name="loio3b7a5a1258ea469b963dc047c3f443a0__prereq_rql_t3q_kdc"/>

## Prerequisites

Ensure that Generative AI features are enabled in your SAP Integration Suite tenant. For more information, see [Generative AI](IntegrationSettings/generative-ai-0c93c17.md).



<a name="loio3b7a5a1258ea469b963dc047c3f443a0__context_qdg_nmx_kdc"/>

## Context

*Script Optimization* is a Generative AI feature that helps you improve Groovy scripts in the script editor by focusing on resource usage.



<a name="loio3b7a5a1258ea469b963dc047c3f443a0__steps_rdg_nmx_kdc"/>

## Procedure

1.  Open the script editor in edit mode.

2.  Choose *Optimize* from the upper right menu.

3.  GenAI inspects your script and displays the results in a report titled *AI-Generated Review Report*. If there's potential for improving your script, this report contains the following sections:


-   *Recommended Changes*. These recommendations address individual areas for improvement, each offering a brief explanation, and relevant code snippets.

-   *Improved Script*. This section includes a complete script demonstrating how to apply the above recommendations.


> ### Note:  
> If the AI doesn't detect any issues and there are no further recommendations, the report confirms this with the following message: "The provided Groovy script is well structured and follows best practices for memory and CPU optimization. No further improvements are necessary."

4.  Review the recommendations and improved script that the AI suggested.

5.  Apply the recommended changes to the original script. You can copy the respective snippets from the *Recommended Changes* section and paste them into the correct lines in the script editor. Alternatively, copy the full script from the report and paste it into the editor to completely replace the original script.

6.  Once you're satisfied with your changes, choose *Apply*.

    > ### Remember:  
    > You can use *Optimize* repeatedly, but there's a limit on usage to avoid exceeding token limits

    > ### Caution:  
    > Don't expose sensitive information in your scripts when using *Optimize*. For more information, see SAP Note [3542713](https://me.sap.com/notes/3542713).

    > ### Restriction:  
    > This feature is only available for the Premium service plan of the SAP Integration Suite. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).






### Troubleshooting

If you can't see the *Optimize* button, please check the following criteria:

-   AI features are enabled as described in [Generative AI](IntegrationSettings/generative-ai-0c93c17.md).

-   You're using the script editor in edit mode.

-   You're editing a Groovy script, rather than a JavaScript.




### 

If any of the following error messages pop up when using *Optimize*, perform the corresponding actions:


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Generative AI feature not enabled.

</td>
<td valign="top">

You haven't enabled the AI features as described in [Generative AI](IntegrationSettings/generative-ai-0c93c17.md).

</td>
</tr>
<tr>
<td valign="top">

You have exceeded the rate limit, please try again later.

</td>
<td valign="top">

There is an upper limit to the number of times you can invoke *Optimize* per minute. If this limit is exceeded, please wait for one minute before trying again.

</td>
</tr>
<tr>
<td valign="top">

Authentication failed.

</td>
<td valign="top">

Your user can't be authenticated. Please open an incident on component LOD-HCI-PI-OPS.

</td>
</tr>
<tr>
<td valign="top">

You are not authorized to perform this operation because you do not have the necessary roles.

</td>
<td valign="top">

Please contact your tenant administrator to grant the required role WebToolingWorkspace.Write

</td>
</tr>
<tr>
<td valign="top">

No Groovy script has been provided.

</td>
<td valign="top">

Please check the contents of the code editor.

</td>
</tr>
<tr>
<td valign="top">

The provided Groovy script content is too large.

</td>
<td valign="top">

The Groovy script exceeds the maximum size of 50 KB. Please shorten it.

</td>
</tr>
<tr>
<td valign="top">

The AI request could not be processed because you have reached your fair usage token quota.

</td>
<td valign="top">

You have exhausted the token quota for the current month. Please wait until it regenerates.

</td>
</tr>
<tr>
<td valign="top">

The AI request cannot be processed at the moment, please try again later.

</td>
<td valign="top">

The *Optimize* feature is temporarily unavailable. Please try again later. If the issue persists, please open an incident on component LOD-HCI-PI-RC.

</td>
</tr>
<tr>
<td valign="top">

There was a failure in processing the AI request.

</td>
<td valign="top">

Please open an incident on component LOD-HCI-PI-RC.

</td>
</tr>
</table>

