<!-- loiod548233bc966496a95c6d2a1132a5f13 -->

# Delete Data of Unregistered Users

SAP API Management stores the data of users who have logged on to the developer portal but have not registered. This topic describes the service used to delete the data of such users.



<a name="loiod548233bc966496a95c6d2a1132a5f13__prereq_q4s_brt_jdb"/>

## Prerequisites

You are assigned the AuthGroup.API.Admin role.



## Context



## Procedure

Run the following service using the standard REST console:

-   Service URL: https://<Dev-Portal-URL\>/api/1.0/offboarding/\{userId\}
-   Method: POST
-   Request Header: x-csrf-token: fetch
-   Content Type: application/json
-   Response: 201

The user data is deleted.

