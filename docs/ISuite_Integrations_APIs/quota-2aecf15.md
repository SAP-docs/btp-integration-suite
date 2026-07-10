<!-- loio2aecf15b996f4e26ae395268d22f16df -->

# Quota

The Quota policy defines the number of requests an application can submit to an API endpoint over a given period of time.

Quota policy limits the total number of requests allowed over a defined time period to manage overall usage, whereas Surge Protection policy regulates the rate of incoming requests in real time to prevent sudden traffic spikes from overwhelming the system.

The period of time can be an hour, a day, or a month and so on. You can apply this policy on the context of requests.

The Quota policy helps to restrict the number of calls made to an API. For example, you can restrict access to your applications by defining the number of API calls made as 20 per day or 20,000 over a period of 1 week.

See the following video for visual instructions on how to add and configure the Quota policy:

> ### Note:  
> When the Quota limit specified in the policy is reached, the subsequent calls to the API artifact are rejected with the response code 429 \( request limit exceeded\). The rejection period lasts until the end of the quota window. Let's illustrate this with the following example:
> 
> The quota window opens at 00:00 \(12 AM\) and ends at 00:05 \(12:05 AM\). Let us assume that the quota allotted is 3 requests in the specified period of 5 minutes. At 00:03, if the quota limit is reached, the subsequent requests post 00:03 are rejected until the window is reset at 00:05.

**Related Information**  


[Surge Protection](surge-protection-3d14745.md "The surge protection policy is designed to protect against traffic surges by controlling the rate at which requests are processed by an API during runtime. This policy acts as a safeguard, reducing the likelihood of downtime and performance issues.")

[IP Filter](ip-filter-3a8b424.md "The IP filter policy allows or denies calls from specific IP addresses or address ranges.")

