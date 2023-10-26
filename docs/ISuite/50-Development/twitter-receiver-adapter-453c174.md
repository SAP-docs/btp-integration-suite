<!-- loio453c174be6ca4098a8c99dc4c1262d25 -->

# Twitter Receiver Adapter

You use the Twitter receiver adapter to extract information from the Twitter platform based on certain criteria such as keywords, user data, for example. As one example, you can use this feature to send, search for and receive Twitter feeds.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

The connection works that way that the tenant logs on to Twitter based on an OAuth authentication mechnism and searches for information based on criteria as configured in the adapter at design time. OAuth allows the tenant to access someone else’s resources \(of a specific Twitter user\) on behalf of the tenant. As illustrated in the figure, the tenant \(through the Twitter receiver adapter\) calls the Twitter API to access resources of a specific Twitter user. Currently, the Twitter adapter can only be used as receiver adapter. For more information on the Twitter API, go to: [https://dev.twitter.com/](https://dev.twitter.com/).

![](images/Twitter_Adapter_OAuth_Mechanism_d23ff1f.png)

Once you have created a receiver channel and selected the Twitter Receiver Adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Endpoint* 

</td>
<td valign="top">

To access Twitter content, you can choose among the following general options.

-   *Send Tweet*

    Allows you to send content to a specific user timeline.

-   *Search*

    Allows you to do a search on Twitter content by specifying keywords.

-   *Send Direct Message*

    Allows you to send messages to Twitter \(write access, direct message\).




</td>
</tr>
<tr>
<td valign="top">

*User*

\(only if you select *Send Direct Message* endpoint\)

</td>
<td valign="top">

Specifies the Twitter user from which account the information is to be extracted.

</td>
</tr>
<tr>
<td valign="top">

*Page Size* 

</td>
<td valign="top">

Specifies the maximum number of results \(tweets\) per page.

</td>
</tr>
<tr>
<td valign="top">

*Number of Pages* 

</td>
<td valign="top">

Specifies the number of pages which you want the tenant to consume.

</td>
</tr>
<tr>
<td valign="top">

*Max. Characters Retrieved from Tweet*

\(only if you select *Search* endpoint\)

</td>
<td valign="top">

Select the maximum numbers of characters that are fetched from a tweet.

> ### Note:  
> -   If you select 140 and tweet contains more than 140 characters, then the tweet is truncated and the tweet URL is appended.
> 
> -   If you select 280 and the tweet contains more than 140 characters, then for regular tweets and for retweets the adapter fetches the entire tweet.



</td>
</tr>
<tr>
<td valign="top">

*Keywords*

\(only if you select *Search* endpoint\)

</td>
<td valign="top">

Specifies the keywords used to filter the results.

Use commas to separate different keywords or a valid Twitter Search API query \(-\(For more information, go to [https://dev.twitter.com/rest/public/search](https://dev.twitter.com/rest/public/search)\).

</td>
</tr>
<tr>
<td valign="top">

*Language*

\(only if you select *Search* endpoint\)

</td>
<td valign="top">

Specify the search language.

</td>
</tr>
<tr>
<td valign="top">

*Consumer Key* 

</td>
<td valign="top">

An alias by which the consumer \(tenant\) that requests Twitter resources is identified

</td>
</tr>
<tr>
<td valign="top">

*Consumer Secret* 

</td>
<td valign="top">

An alias by which the shared secret is identified \(that is used to to define the token of the consumer \(tenant\)\)

</td>
</tr>
<tr>
<td valign="top">

*Access Token* 

</td>
<td valign="top">

An alias by which the access token for the Twitter user is identified

In order to make authorized calls to the TwitterAPI, your application must first obtain an OAuth access token on behalf of a Twitter user

</td>
</tr>
<tr>
<td valign="top">

*Access Token Secret* 

</td>
<td valign="top">

An alias by which shared secret is identified that is used to define the token of the Twitter user

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

The type of proxy you want to use for establishing connection with OData V2 service.

-   *Internet*

-   *Manual*: If you select this option, you can manually specify *Proxy Host* and *Proxy Port* \(using the corresponding entry fields\).




</td>
</tr>
</table>

The authorization is based on shared secret technology. This method relies on the fact that all parties of a communication share a piece of data that is known only to the parties involved. Using OAuth in the context of this adapter, the Consumer \(that calls the API of the receiver platform on behalf of a specific user of this platform\) identifies itself using its **Consumer Key** and **Consumer Secret**, while the context to the user itself is defined by an **Access Token** and an **Access Token Secret**. These artifacts are to be generated for the receiver platform app \(consumer\) and should be configured that way that they will never expire. This adapter only supports consumer key/secret and access token key/secret artifacts that do not expire.

To finish the configuration of a scenario using this adapter, the generated consumer key/secret and access token key/secret artifacts are to be deployed as Secure Parameter artifact on the related tenant. To do this, use the Integration Operations feature, position the cursor on the tenant and chosen *Deploy Artifact*. As artifact type, choose *Secure Parameter*.

