<!-- loio079c68f35a634f55bf3ee88462aa2f07 -->

# Setting Up Your Account

Create a subaccount in your assigned global account using the SAP BTP cockpit.



<a name="loio079c68f35a634f55bf3ee88462aa2f07__context_gm5_zsh_vlb"/>

## Context

After you've received your logon data by email, follow the steps here to create subaccounts in your global account:

> ### Note:  
> If you’ve subscribed to Process Integration, API Management, and/or Open Connector services in your existing subaccount, then please subscribe to the Integration Suite service in a new subaccount.



## Procedure

1.  In the overview page, choose *Subaccounts* from the left pane and choose *New Subaccount*.

2.  Specify a display name.

3.  *Optional*: Specify a description.

4.  Leave the *Neo Environment* checkbox deselected and choose the desired infrastructure provider and region for your subaccount.

    > ### Note:  
    > Integration Suite service runs only on the SAP BTP, Cloud Foundry environment.

5.  Enter a *Subdomain* for your subaccount. This subdomain becomes part of the URL for accessing applications that you subscribe to from this subaccount.

    > ### Note:  
    > The subdomain must be unique across all subaccounts in the same region, and can contain only:
    > 
    > -   letters
    > -   digits
    > -   hyphens \(although hyphens aren’t allowed at the beginning or at the end of the subdomain\)
    > 
    > Uppercase and lowercase letters can be used, however that alone doesn’t qualify as a means to differentiate between subdomains \(for example, SUBDOMAIN and subdomain are considered to be the same\).

6.  *Optional*: If your subaccount is to be used for production purposes, select the *Use for production* option.

    > ### Note:  
    > -   By flagging your subaccount with this option, you can help SAP Support to take appropriate action when handling incidents that are related to mission-critical accounts in production systems.
    > 
    > -   Don’t select this option if your subaccount isn’t intended for production purposes, such as development, testing, or demos. You can change your selection at any time by editing the subaccount properties.

7.  Save your changes.




<a name="loio079c68f35a634f55bf3ee88462aa2f07__result_b3q_sfw_4lb"/>

## Results

A new tile appears in the global account page with the subaccount details. The subaccount is also listed in the *System Landscape* page.

