<!-- loioae14ad7916c04ecbaba3d26e2404410a -->

# Define a Timer Start Event

You can configure an integration flow to automatically start and run on a particular schedule.



## Context

If you want to configure a process to automatically start and run on a particular schedule, you can use this procedure to set the date and time on which the process must run once or repetitively. The day and time combinations allow you to configure the schedule the process requires. For example, you can set the trigger once on a specific date or repetitively on that date. You can periodically trigger the timer every day, specific days in a week, or specific days in a month.

> ### Caution:  
> Don’t model a Timer start event and a start message event \(sender channel\) in the same integration flow. Such a design would result in different possible errors. The timer only triggers the business logic \(integration flow\) and has no other role. To decouple the timer start event from the actual integration flow, refer to the SAP Note [2905759](https://launchpad.support.sap.com/#/notes/2905759).

> ### Remember:  
> -   When you deploy or undeploy an integration flow with *Scheduler*, the system automatically releases all the scheduler locks.
> 
> -   When you deploy small integration flows with *Timer* \(for example, an integration flow with timer, content modifier and mail adapter\), due to fast processing times, multiple schedules are triggered. When you deploy small integration flows with *Timer* \(for example, an integration flow with timer, content modifier and mail adapter\), due to fast processing times, multiple schedules are triggered.
> 
> -   If the *Timer* is configured to trigger message processing at periodic intervals and the processing isn’t completed before the next scheduled interval, then the *Timer* skips the following interval.
> 
> -   If you configure the *Timer* to trigger message processing on a specific time and date, and once this message processing is completed, the integration flow is in error state. You can see the status in the *Manage Integration Content* view in *Monitor* tab. The error occurs because the configured time and date are in the past, and the integration flow can’t process any further messages.
> 
> -   If there are multiple runtime nodes, the Timer-triggered messages have their *Status* as *Discarded* where there’s no actual execution on the particular runtime node. See [Message Status](../Operations/message-status-733a57b.md) to know more about the status of the message.



<a name="loioae14ad7916c04ecbaba3d26e2404410a__steps_c11_ltl_cv"/>

## Procedure

1.  In the palette, choose *Events* \> *Timer*.

2.  In the *Name* field, provide a name for the timer.

3.  Choose *Scheduler*.

4.  Select options or provide values in fields based on description in table.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Run Once*

    Select if you want the message processing to be triggered immediately after you deploy the integration flow.
    
    </td>
    <td valign="top">
    
    Not Applicable
    
    </td>
    <td valign="top">
    
    When you use timer with *Run Once* option enabled, the message is triggered immediately after deploying the integration flow. If you want to trigger the message with an integration flow that you’ve already deployed, you have to undeploy the integration flow and deploy it again. If you restart the integration flow bundle, message isn't triggered.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="5">
    
    *Schedule on Day*

    Select if you want the message processing to be triggered on a specific date and time.

    The fields *On Date* and *Time Zone* are mandatory. Choose between *On Time* and *Every* based on your use case.
    
    </td>
    <td valign="top">
    
    On Date
    
    </td>
    <td valign="top">
    
    Select the date on which you want the message processing to be triggered
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    On Time
    
    </td>
    <td valign="top">
    
    Select the time at which you want the message processing to be triggered
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Every
    
    </td>
    <td valign="top">
    
    Select this option if you want to trigger message processing repeatedly in a specific time interval.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Time Zone
    
    </td>
    <td valign="top">
    
    The time zone that you want to be used as reference for the configured date and time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Throw exception on schedule expiry* 
    
    </td>
    <td valign="top">
    
    The option is enabled by default. If a non-recurring schedule expires, then this option throws validation exception that sets the integration flow status to error in the *Manage Integration Content* tile of the *Monitoring* section.

    In case of multiple timer steps – if at least one timer step is expired, the runtime status of the integration artifact goes into "Error" status. If you like to keep the integration artifact in "Started" status, the recommendation is to disable this option.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="4">
    
    *Schedule to Recur*

    Select if you want to repeatedly trigger message processing according to a specific schedule.

    The fields *Schedule to Recur* and *Time Zone* are mandatory. Choose between *On Time* and *Every* based on your use case.
    
    </td>
    <td valign="top">
    
    Schedule to Recur
    
    </td>
    <td valign="top">
    
    From the list of recurrence pattern, choose *Daily*, *Weekly*, or *Monthly*.

    Accordingly, if you choose

    -   *Weekly*, choose the days of the week

    -   *Monthly*, choose the day of the month from the list.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    On Time
    
    </td>
    <td valign="top">
    
    Select the time at which you want the message processing to be triggered
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Every
    
    </td>
    <td valign="top">
    
    Select this option if you want to trigger message processing repeatedly in a specific time interval.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Time Zone
    
    </td>
    <td valign="top">
    
    The time zone that you want to be used as reference for the configured date and time.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    *Advanced* 
    
    </td>
    <td valign="top">
    
    Seconds

    Minutes

    Hours

    Days

    Months

    Years
    
    </td>
    <td valign="top">
    
    Create a schedule by choosing the different units of time measurement available in seconds, minutes, hours, days, months, and years. The resulting time schedule will be a combined configuration from the multiple options that you choose. The default schedule recurs at every 5th minute starting at the 0th second.

    With the *Advanced* scheduler option, you can configure complex and granular schedules using combination of various units of time measurement. For example, last day of the month, last weekday of the week, specific days in a month or year, every few minutes, between certain hours, and so on. For sample usecases, read the [blog](https://blogs.sap.com/2023/03/06/sap-integration-suite-advanced-scheduler-configuration/).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Time Zone
    
    </td>
    <td valign="top">
    
    The time zone that you want to be used as reference for the configured date and time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Throw exception on schedule expiry* 
    
    </td>
    <td valign="top">
    
    The option is enabled by default. If a non-recurring schedule expires, then this option throws validation exception that sets the integration flow status to error in the *Manage Integration Content* tile of the *Monitoring* section.

    In case of multiple timer steps – if at least one timer step is expired, the runtime status of the integration artifact goes into "Error" status. If you like to keep the integration artifact in "Started" status, the recommendation is to disable this option.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The Timer step supports daylight saving time, the advancing of the clock and returning to the standard time happens by default. When you select a time zone that supports daylight saving, during the daylight saving duration, there’s a difference in time at which the event triggering happens. This difference in time depends on the duration for which the clock is advanced for the selected time zone.
    > 
    > If you want the events to happen at a specific time, with no relation to the specific time of the day during daylight saving, select a time zone that doesn't support daylight saving.
    > 
    > > ### Example:  
    > > Coordinated Universal Time \(UTC\) is a time standard that isn’t adjusted for daylight saving.

5.  Save the changes.


