<!-- loioa49c05ff355f4872b152e1883c1b0a25 -->

# Service to View User Details on API business hub enterprise

API Management allows user to view their personal data stored in the API business hub enterprise.

**Service to view personal data on API business hub enterprise:**

-   URL: https://<Dev-Portal-URL\>/api/1.0/user

-   Method: GET
-   Response: Fetches your personal details stored in API business hub enterprise.

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


