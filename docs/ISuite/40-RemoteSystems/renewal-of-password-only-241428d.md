<!-- loio241428ddf1434a44bc38b35c25c16149 -->

# Renewal of Password Only

In this use case, the password of the user through which the tenant calls the receiver system is replaced in the receiver system.

> ### Note:  

To exchange the password of a user without any downtime, the receiver administrator has to create an intermediate user as described for the use case *Renewal of User and Password* \(without deleting the old user\).

1.  Receiver administrator: Creates a new **intermediate user** \(`user1`\) and assigns authorization roles to the user.

    After this step has been performed, two users are configured on the receiver system for a certain HTTPS communication: the old user \(`user0`\) and the new one \(`user1`\).

2.  Receiver administrator: Informs the tenant administrator that he wants to change the password of a certain user used for a certain HTTPS communication and that he has created an intermediate user \(`user1`\) with a certain password.
3.  Tenant administrator: Opens the related *User Credentials* artifact \(specified for `user0` and the communication path with the receiver system\) and exchanges the old user0/password with the new user1/password.
4.  Tenant administrator: Informs the receiver administrator that the client now uses the intermediate user \(`user1`\).
5.  Receiver administrator: Changes the password of the original user \(`user0`\).
6.  Receiver administrator: Informs the tenant administrator that the password of the original user \(`user0`\) has been changed.
7.  Tenant administrator: Opens the related *User Credentials* artifact \(now containing the credentials of `user1`\) and exchanges the credentials \(user/password\) of the intermediate user \(`user1`\) with the credentials \(user name and new password\) of the original user \(`user0`\).
8.  Tenant administrator: Informs the receiver administrator that user password has been changed.
9.  Receiver administrator: Removes the intermediate user.

> ### Note:  
> In case the receiver administrator does not accept this complicated procedure, a simplified procedure might be adopted that way that the tenant administrator just changes the password as soon as he notices that the connection to the receiver system fails due to a wrong password.

> ### Note:  
> The same procedure is applicable in case a SuccessFactors receiver channel is used.

**Related Information**  


[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

