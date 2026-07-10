<!-- loio102257d29973497cb25cb73b2af4c71c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Delete an Eligible Virtual Host

You can delete a virtual host only if it is eligible for deletion. To maintain system integrity and prevent unintended API impact, deletion is restricted for default virtual hosts and virtual hosts associated with deployed APIs.



## Prerequisites

-   The *PI\_Administrator* role collection should be assigned to you.




## Context

A virtual host can be deleted only under the following conditions:

-   The virtual host is not configured as the default virtual host.
-   The virtual host is not associated with any deployed APIs.
-   If the virtual host is referenced only by APIs that are not deployed, deletion is allowed.

Deletion is blocked for:

-   Default virtual hosts
-   Virtual hosts referenced by deployed APIs



## Procedure

1.  Log on to the Integration Suite.

2.  From the left navigation pane, choose *Monitor* \> *Integrations and APIs*.

3.  From the *Runtime* dropdown in the top left corner, choose the*Integration Cell* to reveal the *Virtual Host* tile.

4.  Scroll down to the *Manage Virtual Host* section and select the *Virtual Host* tile.

5.  On the following screen, locate the virtual host that you want to delete.

6.  Under *Actions*, choose the :wastebasket: icon corresponding to the virtual host.

7.  In the confirmation dialog, review the warning message and choose *Delete* to remove the virtual host permanently.

    > ### Note:  
    > Post-Deletion Behavior - If the deleted virtual host was previously referenced by an API, the following behavior applies:
    > 
    > -   During API deployment, a message is displayed indicating:
    >     -   The previously assigned virtual host has been deleted.
    >     -   The default virtual host will be selected for deployment.
    > 
    > -   In API artifact details -
    >     -   The *Virtual Host* field in the overview section appears empty.
    >     -   The API artifact *URL* falls back to the default virtual host and indicates that the previously assigned virtual host was deleted.
    > 
    > -   During API edit -
    >     -   After selecting a new virtual host and saving the API configuration, the warning message is cleared.
    >     -   The updated virtual host configuration is persisted.




## Results

The eligible virtual host is deleted successfully, and affected APIs automatically fall back to the default virtual host until a new virtual host is assigned.

