<!-- loioa1c26c88f52c40bfa32fd7f6ec20d361 -->

# Renewal of User and Password

In this use case, the user \(through which the tenant calls the receiver system\) is replaced by a new user \(and password\) in the receiver system.

> ### Note:  

Security artifact renewal has to be performed in the following sequence:

1.  Receiver administrator: Creates a new user \(`user1`\) and assigns authorization roles to the user.

    After this step has been performed, two users are configured on the receiver system for a certain HTTPS communication: the old user \(`user0`\) and the new one \(`user1`\).

2.  Receiver administrator: Informs the tenant administrator that he wants to exchange the old user \(`user0`\) with a new user \(`user1`\).

    The new user also should have a new password.

3.  Tenant administrator: Opens the related *User Credentials* artifact \(specified for `user0` and the communication path with the receiver system\) and exchanges the old user/password with the new user/password.
4.  Tenant administrator: Restarts the corresponding integration flow\(s\).
5.  Tenant administrator: Informs the receiver administrator that user/password has been exchanged.
6.  Receiver administrator: Removes the old user.

In case a **SuccessFactors** receiver channel is used, note the following, slightly adapted sequence of steps:

1.  Success Factors administrator \(receiver administrator\): Creates a new user/password and assigns the adequate authorizations to the user for the new company ID.
2.  Success Factors administrator: Informs the tenant administrator that a new user/password for new company ID has been created and that the old user/password/company ID will be no longer valid from a certain point in time.
3.  Tenant administrator: Changes the user/password/company ID for the existing credentials \(User Credentials artifact\).
4.  Success Factors administrator: Removes old user/password/company ID from Success Factors system after the specified point in time has been reached.

**Related Information**  


[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

