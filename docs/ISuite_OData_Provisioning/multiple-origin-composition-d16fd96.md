<!-- loiod16fd96f5c144c12a982033801164ff3 -->

# Multiple-Origin Composition

Multiple-Origin Composition \(MOC\) is the ability to collect data from different back-end systems, aggregate them in a single service, and update different back-end systems, while using the same user. You can also execute a `$batch` request with MOC.



## Prerequisites

You have assigned multiple destinations to a service in the OData Provisioning Administration to fetch data from multiple back-end systems effectively.

URL Patterns

-   For a QUERY \(READ feed\) request

    `http://<hostname>/odata/<namespace>/<servicename>;<version>;mo/<entityse`t\>

-   For a `$batch` Request

    `http://<hostname>/odata/<namespace>/<servicename>;<version>;mo/$batch`


> ### Note:  
> Append the URL with `';mo'`, otherwise only the default system data is fetched.



## Error Tolerance

In a MOC scenario, while fetching data from multiple destinations, if one or more of those destinations causes an error, then the entire response returns that error. By default, services registered in OData provisioning are **not** error tolerant. This feature provides you with a way to make a service error tolerant so that it can handle such errors in multiple-origin scenarios.

To access this functionality, choose a registered service to open its details and turn *Error Tolerance*, *ON* or *OFF*.

When you make a service error tolerant, its behavior changes in the following way:

-   An error is returned only if the data retrieval from all back-end systems causes an error. Otherwise, if only some of the back-end systems cause an error, a feed is returned to the client.

-   The data retrieved successfully from some of the back-end systems is added into that feed.

-   The data from the back-end systems that caused an error can be requested again using the OData skiptoken added to that feed.


URL Pattern Examples

-   For a single failed destination, the skiptoken URL would look like this:

    `<link href="<EntitysetName>?$skiptoken=MISSING_DATA_FROM_<number_of_destinations>_<failed_destination_name> rel="next"/>`

-   If there are multiple failed destinations, the destination names are separated with a semicolon \(;\), and each of the destination names is prefixed with the total number of destinations assigned to the service, followed by an underscore\(\_\).

    For example, if three destinations are assigned to a service, out of which two destinations - DEST1 and DEST2 - fail to return any data, then the skiptoken URL in the response would look like this:

    `<link href="ProductCollection?$skiptoken=MISSING_DATA_FROM_3_DEST1;3_DEST2 rel="next"/>`

-   You can fetch data from a one or more failed destinations by appending the skiptoken to your service root URL.

    -   For example, to fetch data from the failed destination DEST2:

        `https://<http://<hostname>/odata/<namespace>/<servicename>;<version>/ProductCollection?$skiptoken=MISSING_DATA_FROM_3_DEST2`

    -   To fetch data from multiple failed destinations DEST1 and DEST2:

        `https://<http://<hostname>/odata/<namespace>/<servicename>;<version>/ProductCollection?$skiptoken=MISSING_DATA_FROM_3_DEST1;3_DEST2` 


-   If any of the destinations still fail to return data, then the response contains a skiptoken for that destination.


