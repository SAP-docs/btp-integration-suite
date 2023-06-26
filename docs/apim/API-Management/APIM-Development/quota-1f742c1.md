<!-- loio1f742c1e1a5c4a21bd83994071ddaea0 -->

# Quota

The Quota policy defines the number of request messages an application can submit to an API over a given period of time.

The period of time can be an hour, a day, or a month and so on. You can apply this policy on the context of request messages.

The Quota policy helps API Providers to restrict the number of calls made to an API. For example, you can restrict access to your applications by defining the number of API calls made as 20 per day or 20,000 over a period of one week.

API Management maintains a counter that keeps track of the number of calls made to the API. Once the counter reaches the Quota limit, all successive calls made to the API are rejected. API Management returns an error message to an API-call made after the Quota limit is exceeded. The Quota policy provides the capability to reset the counters automatically after the stipulated period of time, unless it is explicitly reset by using the Reset Quota policy.

**Related Information**  


[Types of Quota](types-of-quota-3e32f19.md "")

[Static and Dynamic Settings](static-and-dynamic-settings-f21c01f.md "A Quota can be static or dynamic.")

[Designing Quota Policy](designing-quota-policy-2539fb2.md "")

