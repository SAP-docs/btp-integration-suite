<!-- loio61b36a1be81e4b62acd0512a33dc7b12 -->

# Modes of the Quota Policy

Quota type is an attribute of the Quota policy that you define while configuring the policy.

Supported modes of the Quota policy:

-   *Calendar*:

    In calendar mode, the reset time for the first quota refresh cycle is synchronized with the clock. The quota counter is refreshed according to the duration and time unit specified by the user.

    Consider the following examples:

    -   For instance, if you configure a calendar-based quota to start counting at 8:30 am and set the duration to 60 minutes, the initial quota reset will occur at 9:00 am. Subsequently, in each subsequent cycle, the reset will take place every 60 minutes, from 9:00 am to 10:00 am, 10:00 am to 11:00 am, and so on.

    -   If the duration is specified in months, the counter will reset on the first day of the following month. For example, if the counting begins at 8:30 am on June 26 and the duration is set as 1 month, then the counter will reset on July 1st. Subsequently, the counter will reset on August 1st, September 1st, and so on, with each refresh cycle.


    The start time for the next refresh cycle will be calculated as follows:


    <table>
    <tr>
    <th valign="top">

    Time Unit
    
    </th>
    <th valign="top">

    Example of the start time of the next refresh cycle \(UTC\)
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Second
    
    </td>
    <td valign="top">
    
    11:55:25 \[21/11/2022\]
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Minute
    
    </td>
    <td valign="top">
    
    11:56:00 \[21/11/2022\]
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Hour
    
    </td>
    <td valign="top">
    
    12:00:00 \[21/11/2022\]
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Day
    
    </td>
    <td valign="top">
    
    00:00:00 \[22/11/2022\]
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Week
    
    </td>
    <td valign="top">
    
    00:00:00 \[28/11/2022\] Monday
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Month
    
    </td>
    <td valign="top">
    
    00:00:00 \[01/12/2022\] December
    
    </td>
    </tr>
    </table>
    
-   *Dynamic*: Dynamic Quota enforcement causes the count to start when the first request message is received from an app. Under flexible Quota enforcement, the start time varies; each app has its own start time based on when the first request is received. This enables you to provide quotas that support access periods of 1 week, 1 month, or 6 months, customized for each app.

-   *Fixed*: Even in Fixed mode, the counter starts counting from the specified start time. However, it is not aligned with the clock and resets after the specified duration for which the quota is allotted has been reached. It considers 28 days as equivalent to 1 month.

    Consider the following examples:

    -   If the counting begins at 8:30 am on June 26, and the duration is set as 60 minutes, then the counter will reset at 9:30 am on June 26.

        Similarly, if the counting begins at 8:30 am on June 26 and the duration is set as 1 month, then the counter will reset after 28 days, which is July 24th.



**Related Information**  


[Adding Quota Policy Step to API Endpoint](adding-quota-policy-step-to-api-endpoint-8d1b56b.md "Adding Quota policy step to an API artifact for traffic management.")

