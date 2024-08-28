<!-- loioba86ff5d974c4c37be714fa81b863a28 -->

# Exception Raised During the Transport


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Exception raised during the transport

</td>
<td valign="top">

**Solution 1:**

Please make sure that these settings are maintained in the following way at the **Content Agent Service destination**, at the **Source Subaccount** side:

-   Value of the *Name* field is **ContentAssemblyService**.

    This value is hard-coded, please use only this name for the destination.

-   Value of the URL can be found in the *URL* field of your **Content Agent** instance's service key.

    Example of URL: **\*content-agent-assembly\***

-   Value of the Token Service URL can be found in the *URL* field, under *UAA* section of your **Content Agent** instance's service key.

    Please verify that the **/oauth/token** is appended to that URL.

    Example of Token Service URL is shown below:

    **\*authetication.<region\>.hana.ondemand.com/oauth/token**


Please update the above-mentioned details in the destination and re-run the test.

</td>
</tr>
<tr>
<td valign="top">

Attempt 2: If the transport is still failing

</td>
<td valign="top">

**Solution 2:**

**Transport Management destination**, at the **Source Subaccount** side:

-   Value of the *Name* field is **TransportManagementService**.

    This value is hard-coded, please use only this name for the destination.

-   Value of the URL can be found in the *URL* field of your **Cloud Transport Management** instance's service key.

    Example of URL: **\*backend.ts\***

-   Value of the Token Service URL can be found in the *URL* field, under *UAA* section of your **Cloud Transport Management** instance's service key.

    Please verify that the **/oauth/token** is appended to that URL.

    Example of Token Service URL is shown below:

    **\*authetication.<region\>.hana.ondemand.com/oauth/token**

-   Make sure that the value of **sourceSystemId** equals with the **name of source node under the Transport Nodes** within Cloud Transport Management.

Please update the above-mentioned details in the destination and re-run the test.

</td>
</tr>
<tr>
<td valign="top">

Attempt 3: If the transport is still failing

</td>
<td valign="top">

**Solution 3:**

Please make sure that these settings are maintained in the following way at the **API Management destination**, at the **Destination Subaccount** side:

-   Value of the *Name* field is **APIManagement**.

    This value is hard-coded, please use only this name for the destination.

-   Value of the URL can be found in the *URL* field of your **API Management** instance's service key.

    Example of URL: **\*apiportal\***

-   Value of the Token Service URL can be found in the *tokenUrl* field, under *UAA* section of your **API Management** instance's service key.

    Example of Token Service URL is shown below:

    **\*tmssourceparsec.authetication.<region\>.hana.ondemand.com/oauth/token**

-   The role **APIPortal.Administrator** has assigned to the instance's service key's. If not sure, please create a new instance and provide the following JSON payload at second step **Configure instance parameters**:

    \{**role: APIPortal.Administrator**\}

    Please create a new service key and use the newly generated values in the **API Management destination** at the **Destination Subaccount** side.


Please update the above-mentioned details in the destination and re-run the test.

</td>
</tr>
<tr>
<td valign="top">

Attempt 4: If the transport is still failing

</td>
<td valign="top">

**Solution 4:**

Please make sure that the following settings are maintained in the following way at the **Cloud Transport Management application** at the **Source Subaccount** side.

There are two nodes under the **Transport Nodes** section:

-   A **Destination** Node

    The value of the **Destination** field is the same as the name of the destination that is configured in the **Deploy Service destination** at the **Source Subaccount** side.

    Example: TMSDeploy

-   A **Source** Node

Please update the above-mentioned details in the destination and re-run the test.

</td>
</tr>
<tr>
<td valign="top">

Attempt 5: If the transport is still failing

</td>
<td valign="top">

**Solution 5:**

Please create a support ticket on the **OPU-API-OD-DT** component with all the details about your current issue.

</td>
</tr>
</table>

