<!-- loio027e47a644174cc0acb6f961d291babf -->

# Authenticate Your REST API Requests

Learn how to authenticate the API requests that you make from your applications.



<a name="loio027e47a644174cc0acb6f961d291babf__prereq_khp_2gs_ldc"/>

## Prerequisites

-   You have configured a message client. See [Configure A Message Client](../configure-a-message-client-867c517.md)

-   You have created a queue. See [Create A Queue](create-a-queue-95357fa.md).




## Procedure

1.  In the SAP BTP cockpit, choose *Services* \> *Instances and Subscriptions*.

2.  For your service instance of the message client, choose the service binding.

3.  Look out for the section *"type": "saprestmgw"* where you can find the OAuth2 client credentials.

    A sample of the section that you look out for:

    > ### Sample Code:  
    > ```
    > "broker": {
    >  "type": "saprestmgw"
    >  },
    >  "oa2": {
    >  "clientid": "*******************",
    >  "clientsecret": "*******************",
    >  "granttype": "client_credentials",
    >  "tokenendpoint": "https://tokenendpoint-url/oauth/token"
    >  },
    >  "protocol": [
    >  "httprest"
    >  ],
    >  "uri": "https://base-url"
    > ```


You must first fetch an access token from the token endpoint.

4.  Append `?grant_type=client_credentials&response_type=token` to the *tokenendpoint* copied from the service binding. To receive a token, make a POST request using a REST client tool.

5.  Use basic authentication and provide the values of *clientid* and *clientsecret* as the username and password.

    You receive a response for the POST request.

6.  Copy the *access\_token* value from the response.

7.  When accessing the available REST APIs, use the authentication type *Bearer Token* and provide the copied *access\_token* value.


