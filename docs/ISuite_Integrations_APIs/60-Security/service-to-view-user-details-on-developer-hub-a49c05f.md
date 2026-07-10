<!-- loioa49c05ff355f4872b152e1883c1b0a25 -->

# Service to View User Details on Developer Hub

API Management allows user to view their personal data stored in the Developer Hub.

**Service to view personal data on Developer Hub:**

-   URL: https://<Dev-Portal-URL\>/api/1.0/user

-   Method: GET
-   Response: Fetches your personal details stored in Developer Hub.

    > ### Sample Code:  
    > Sample response
    > 
    > ```
    > {
    > "Name": "<user ID>",
    > "FirstName": "<First name>",
    > "LastName": "<Last name>",
    > "LoggedOut": false,
    > "Email": "<e-mail id>"
    > }
    > ```


