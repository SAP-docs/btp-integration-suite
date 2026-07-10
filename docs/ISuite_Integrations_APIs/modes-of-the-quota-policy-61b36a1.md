<!-- loio61b36a1be81e4b62acd0512a33dc7b12 -->

# Modes of the Quota Policy

Quota type is an attribute of the Quota policy that you define while configuring the policy.

Supported modes of the Quota policy:

-   *Calendar*:

    In calendar mode, quota reset aligns with the clock based on the specified duration and unit.

    For hourly quotas, resets happen at the top of the hour \(e.g., 9:00 am, 10:00 am, etc.\), regardless of when the first call was made.

    For monthly quotas, resets always occur on the first day of each month, not a month from the initial request.

    Consider the following examples:

    -   **Minutes/Hours**: If you set a 60-minute quota starting at 8:15 AM, the first quota period will end at the next top of the hour, which is 9:00 AM. Subsequent resets will occur every hour on the hour: 10:00 AM, 11:00 AM, and so on.

    -   **Months**: : If a quota begins on June 26th with a duration of "1 month", it will reset at the beginning of the next calendar month, which is midnight on July 1st. The next resets will be on August 1st, September 1st, and so on..


    **Reset Timing Summary**: The following table shows when the next reset would occur based on the chosen time unit, assuming the current time is 11:55:25 on Monday, November 21, 2022.


    <table>
    <tr>
    <th valign="top">

    Time Unit
    
    </th>
    <th valign="top">

    Next Reset Time \(UTC\)
    
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
    
-   *Dynamic*: In dynamic mode, the quota period starts when an application makes its first request.

    Each application has its own independent quota window, based on its start time. This allows flexible, personalized quota durations like 1 week or 1 month per application.

-   *Fixed*: In fixed mode, the quota starts at a specified time and resets strictly after the configured duration, not aligned to the clock.

    A "month" is treated as a fixed 28-day period, not a calendar month. For example, a 1-month quota starting on June 26 at 8:30 am will reset on July 24 at 8:30 am.

    Examples:

    -   **Minutes/Hours**: If the count starts at 8:30 AM with a duration of 60 minutes, it will reset exactly at 9:30 AM \(8:30 AM + 60 minutes\). This differs from Calendar mode, which would reset at 9:00 AM.

    -   **Months**: If counting begins at 8:30 AM on June 26th with a 1-month duration, the counter will reset 28 days later, on July 24th. This is different from Calendar mode, which would have reset on July 1st



**Related Information**  


[Add Quota Policy to API Endpoint](add-quota-policy-to-api-endpoint-8d1b56b.md "Adding quota policy to an API artifact for traffic management.")

