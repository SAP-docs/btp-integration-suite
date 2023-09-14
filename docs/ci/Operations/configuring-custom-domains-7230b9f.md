<!-- loio7230b9ff41914cc0969223e6a020104b -->

# Configuring Custom Domains

Allows you to customize the default tenant URL or domain as per your needs and access the tenant using your own the domain.

There are use cases where you do not wish to expose the default domain provided by SAP Cloud Integration. In such a scenario, you can construct custom domain names and TLS settings for specific Cloud Integration instance.

Use the procedure here to create and add custom domains.

> ### Note:  
> When a custom domain is used, the domain name and the server certificate of the domain are owned by the customer.

1.  To use a custom domain for your application, you must fulfill a number of preliminary steps. For more information, see [Prerequisites](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/cde25474fcc1424db48ad86eb2ba9502.html).

2.  [Create an SSL Host](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/77cf0e6cd32e496c9cc8eeac4bedde94.html#loio70f4d19d3dbd434aa9aa165d53e2896c) - the host holds the mapping between your chosen custom domain and the application on SAP BTP as well as the SSL configuration for secure communication through this custom domain.

3.  [Upload a Certificate](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/77cf0e6cd32e496c9cc8eeac4bedde94.html#loio55120d899d314e23ab8e33b4b388cea6) - it will be used as a server certificate on the SSL host.

4.  [Bind the Certificate to the SSL Host](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/77cf0e6cd32e496c9cc8eeac4bedde94.html#loio1d4248f3582a40cdb6f4a2439a55fb65).

5.  [Add the Custom Domain](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/77cf0e6cd32e496c9cc8eeac4bedde94.html#loiobf395cf25683491eabefadb4383ed7ff) - this maps the custom domain to the Cloud Integration URL.

    > ### Note:  
    > The format of the default application URL is `https://<application_name><provider_subaccount>-<consumer_subaccount>.<domain>`.

    You can find the required components for the above URL in the SAP BTP Cockpit:


    <table>
    <tr>
    <th valign="top">

    URL Elements


    
    </th>
    <th valign="top">

    Where to find it?


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `<application_name>` 


    
    </td>
    <td valign="top">
    
    In *Application* \> *Subscriptions* find the subscribed application details.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `<provider_subaccount>` 


    
    </td>
    <td valign="top">
    
    In *Application* \> *Subscriptions* and then choose the relevant *Application*. In the *Subscribed Application - <account ID\> Overview* page, find the *Provider Subaccount* details. For example, Provider Subaccount: myacct **\(wc077ad\)**.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `<consumer_subaccount>` 


    
    </td>
    <td valign="top">
    
    Under the *Subaccount Information* section, use the subaccount *Name*.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > After creating an custom domain, you can use both the default URL as well as the custom domain to access the application.

6.  [Configure DNS](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/77cf0e6cd32e496c9cc8eeac4bedde94.html#loio004406e1c9a8441fb05a25f5f87d45b7)- you can create a CNAME mapping.

7.  [Configure Single Sign-On](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/77cf0e6cd32e496c9cc8eeac4bedde94.html#loio6b671d39f46c41d1bbd89b7e698fe384) - if you have a custom trust configuration in your subaccount, you need to enable single logout.


The configuration of custom domains has different setups related to the subscriptions of your subaccount. For more information about custom domains for applications that are part of a subscription, see [Custom Domains for Multitenant Applications](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/b2b5dcc4fd9842388bb047d2922be48c.html).



<a name="loio7230b9ff41914cc0969223e6a020104b__section_hbv_lhn_t2b"/>

## Enabling TLS Protocol Versions

Configure and enable TLS protocol of your choice for inbound communication to SAP Cloud Integration. For more information, see [How to replace SSL with TLS](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/29569757974e4ebd9806eaf099d517a0.html).

> ### Note:  
> Use `--supported-protocols` parameter to enable the specified TLS protocol.

