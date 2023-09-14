<!-- loio1656c9181a394fb2803c1a82e1fc573d -->

# Setting Up Inbound Authentication of an IdP User for API Clients

Using this option, the API client is authenticated based on user credentials associated with a user registered at an identity provider \(IdP\).



In order to protect the API against CSRF \(cross-site request forgery\) attacks, modifying operations \(for example, POST, DELETE\) should be used in conjunction with session-based authentication and client-side CSRF handling.

It is a prerequisite that the client has HTTP cookies enabled, so that the session cookie set by the server is sent back by the client. If the client does not support HTTP cookies, the `Cookie` header can also be set manually. Before being able to execute modifying operations, the client needs to obtain a valid CSRF token from the server. This token has to be requested with a GET request by setting the Using SAP BTP cockpit, perform the following steps`X-CSRF-Token` HTTP header with value `Fetch`. The server will then pass a CSRF token in the HTTP response header `X-CSRF-Token`. The token is only valid for the current HTTP session \(identified by the session cookie\) and needs to be passed in a special HTTP header \(`X-CSRF-Token`\) in subsequent requests.

> ### Note:  
> If you use a custom IDP, refer to [Using Custom IDP with SAP Cloud Integration](using-custom-idp-with-sap-cloud-integration-c59610d.md)

Example fetch request:

> ### Sample Code:  
> ```
> Using SAP BTP cockpit, perform the followingGET /api/v1/ HTTP/1.1 
> Host: <tmn host>.hci.int.sap.hana.ondemand.com 
> Authorization: Basic xxxxxxxxxxxx 
> Accept: */* 
> X-CSRF-Token: Fetch
> ```

**Example fetch response**\(headers only\):

> ### Sample Code:  
> ```
> HTTP/1.1 200 OK
> Cache-Control: private
> Expires: Thu, 01 Jan 1970 00:00:00 UTC
> Set-Cookie: JSESSIONID=3E4F4FD64EE7244E0A137292E4C758CA5B938883A5EE059472ECAB545D26E2DA; Path=/api; Secure; HttpOnly
> Set-Cookie: JTENANTSESSIONID_w1fc74894=a%2BgZSQv3aqD01H1ph6cgQTkj%2B%2FwWBH6iUvhLmed3%2Bcg%3D; Domain=.hana.ondemand.com; Path=/; Secure; HttpOnly
> X-CSRF-Token: 662592DAB9491668BB9844B7C3284BE7
> DataServiceVersion: 1.0
> Date: Tue, 06 Dec 2016 11:58:52 GMT
> Content-Type: application/atomsvc+xml;charset=utf-8
> Content-Length: 2730
> Server: SAP
> ```

**Example POST request** \(headers only\):

> ### Sample Code:  
> ```
> POST /api/v1/IntegrationRuntimeArtifacts HTTP/1.1
> Host: <tmn host>.hci.int.sap.hana.ondemand.com
> Cookie: JSESSIONID=3E4F4FD64EE7244E0A137292E4C758CA5B938883A5EE059472ECAB545D26E2DA; BIGipServer<tmn host>.hci.int.sap.hana.ondemand.com=!twyaWldd1ZciS6dmvioOKDhuBSBfkNy79zlunmPYQM3r8BNSXFbphoAmzVY8He+GC0MT5LscJQMAbRE=; JTENANTSESSIONID_w1fc74894=a%2BgZSQv3aqD01H1ph6cgQTkj%2B%2FwWBH6iUvhLmed3%2Bcg%3D
> Accept: application/atom+xml
> X-CSRF-Token: 662592DAB9491668BB9844B7C3284BE7
> Content-Length: 9184
> Expect: 100-continue
> Content-Type: multipart/form-data; boundary=------------------------2fb3a93483eb87fd
> 
> ```

**Example POST response**:

> ### Sample Code:  
> ```
> HTTP/1.1 202 Accepted
> DataServiceVersion: 2.0
> Date: Tue, 06 Dec 2016 11:59:22 GMT
> Content-Type: application/atom+xml;charset=utf-8
> Content-Length: 0
> Server: SAP
> 
> ```

