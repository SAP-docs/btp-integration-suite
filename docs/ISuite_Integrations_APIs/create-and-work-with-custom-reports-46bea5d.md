<!-- loio46bea5dc8e0444859b06177b02ed41ff -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create and Work with Custom Reports

Create your own custom reports in the analytics dashboard.



## Context

> ### Note:  
> Availability of the MCP Server feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

You can create customized charts for API metrics that are critical to your business. Using the Custom view feature, you can group all these API metrics and view them in a single window.

> ### Note:  
> Changing the *Artifact Type* between *API* and *MCP Server* in the analytics dashboard will not affect custom reports. Only changes to the runtime configuration will impact how data is reflected in custom reports.



## Procedure

1.  In the analytics dashboard, choose *Add Custom View*.

2.  In the *Add Custom View* dialog, enter a name for your new custom report and choose *OK*.

3.  In the *Create Chart* window, enter a title and a description for the chart that you want to create.

4.  Under *Dimensions*, choose the API or MCP server metric that you want to measure from the drop-down menu.

    -   If you select an API dimension \(example: API Name\), the chart becomes an API-specific chart.
    -   If you select an MCP dimension \(example: MCP Server Name\), the chart becomes an MCP server-specific chart.

5.  **\(Optional\)** Add additional dimensions:

    -   Choose :heavy_plus_sign: \(Add dimension\) again.

    -   The drop-down now shows only dimensions from the same set as your first selection.
    -   Repeat as needed.

6.  Under *Measures*, choose how you want to measure the selected API or MCP server metric.

    For example, you want to create a chart to plot the number of API calls received through a device type. In this case, you can name the chart as Number of calls per device, and choose Device type under Dimensions, and choose Calls under Metrics.

    **Adding multiple dimensions and measures**

    You can add multiple measures with various dimensions for a single chart. For example, you can plot the total number of calls and errors occurring on a particular device type. To do so, you can select device type under Dimension and add two entries under Measures, one for tracking the number of calls and the other for tracking the number of errors.

    To view the chart for a particular measure, select the measure from *Selected Measures* drop-down menu available at the top of the chart. In addition, the dimension and measures, and its details appear as a table below the chart.

    You can also add multiple dimensions. For example, if you want to plot the number of calls from a particular device type and from an operating system, then you can add two entries under Dimensions, one for the device type and the other for the Operating System type.

    To drill down on a particular dimension, click the corresponding bar on the plotted chart. If you apply a filter to a chart to drill down to the details, you can navigate back to any previous parameter by using the breadcrumb option.

    **Applying Filters**

    If you want to analyze using a particular value of measure or dimension in the plotted chart, choose the **Filter** icon at the top of the chart and set the required values in the Filter popup. You can enter values for measures manually using the Equals to and Not Equals to options. For static dimensions \(default\), you can choose multiple values from the drop-down list.

    **Dependent Filters: MCP Target Type and Target Value**

    When both MCP Target Type and MCP Target Value are added as dimensions to an MCP server chart, their filters operate in a parent-child \(dependent\) relationship:

    -   **Filter by MCP Target Type**

        The MCP Target Type filter displays the following fixed values:


        <table>
        <tr>
        <th valign="top">

        MCP Target Type
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        API
        
        </td>
        <td valign="top">
        
        The MCP Server connects to an API as its backend target.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        RFC
        
        </td>
        <td valign="top">
        
        The MCP server connects to a Remote Function Call \(RFC\) as its backend target.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        HTTP Endpoint
        
        </td>
        <td valign="top">
        
        The MCP Server connects to an HTTP endpoint URL as its backend target.
        
        </td>
        </tr>
        </table>
        
    -   **Filter by MCP Target Value**

        After selecting an MCP Target Type, the MCP Target Value drop-down is dynamically populated:


        <table>
        <tr>
        <th valign="top">

        If MCP Target Type is...
        
        </th>
        <th valign="top">

        Then MCP Target Value shows...
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        API
        
        </td>
        <td valign="top">
        
        List of available API names configured as targets.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        RFC
        
        </td>
        <td valign="top">
        
        List of available RFC names configured as targets.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        HTTP Endpoint
        
        </td>
        <td valign="top">
        
        List of available HTTP endpoint URLs configured as targets.
        
        </td>
        </tr>
        </table>
        

7.  Choose *OK* and then save the chart by choosing *Save*.

    The newly created custom view appears as a new report page next to the default report pages. To view all your custom charts and reports, choose the created custom view report page. You can create up to thirty custom views.

    To edit the name of a custom view, select the required custom view and click on the :pencil2: icon displayed next to the custom view name.

8.  To add new charts to your custom view, choose the required custom view and click *Create*.

9.  In the *Create Chart* window, enter a name and a description for the chart in the *Title* and *Description* fields, and under *Dimensions and Measures*, choose the API metric that you want to track and measure.

    At the top of your custom report page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the bubble-like endpoints on the date-range selector.

    At the top of the date-range selector, select **Month**, **Week**,**Day**, **Hour**, or **Minutes** to see data by month, week, day, or hour.

    The **Month** option displays six touch points, one for each of the last six months inclusive the current month.

    The **Week** option displays one touch point for every week of a month.

    The **Day** option displays one touch point for each day.

    The **Hour** option displays 24 touch points, one for each hour of the day.

    The **Minutes** option displays 48 touch points, one for every 30 minutes of the day.

10. At the top-right corner of the date-range selector, you find options to hide the date-range selector, view a grid representation of all your custom charts, and refresh the reports.

    Click <span class="SAP-icons-V5"></span> to hide or unhide the date-range selector.

    Click <span class="SAP-icons-V5"></span> to view a grid representation of all the charts that are a part of your custom view. Hovering over each chart gives you options to either remove the chart from your custom view or add the chart to your custom view.

    Click <span class="SAP-icons-V5"></span> to refresh the reports with latest data from API calls.

    Click to :wastebasket: delete a custom view.

    Deleting a custom view deletes all its associated charts and data.

11. Each custom chart that you add to your custom view provides an action bar with options to edit and delete the chart.

    Click :pencil2: to edit the chart.

    Click :wastebasket: to delete the chart.

    > ### Note:  
    > In any of the custom charts, if you choose `Line Chart` or `Stacked Bar Chart` chart types, the custom chart displays a time-wise trend of the report. For example, if you have a custom chart created for displaying the number of calls per API, then selecting the `Line Chart` type displays the number of calls based on the time period \(Month, Week, or Day\) you have selected.


**Related Information**  


[Analyze APIs and MCP Servers](analyze-apis-and-mcp-servers-da4af34.md "SAP Integration Suite provides comprehensive analytics capabilities to understand consumption and performance patterns across APIs and MCP servers.")

