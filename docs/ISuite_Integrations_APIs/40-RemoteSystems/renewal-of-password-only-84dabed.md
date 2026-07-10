<!-- loio84dabedd27d148c69b600427b105c7cd -->

# Renewal of Password Only

In this use case, the password of the user \(through which the sender system is supposed to call the tenant\) is replaced by a new password.

To exchange the password of a user without any downtime, the cloud infrastructure provider has to create an intermediate user as described for the use case *Renewal of User and Password* \(without deleting the old user\).

Security artifact renewal has to be performed in the following sequence:

1.  Cloud infrastructure provider: Informs the sender administrator that he wants to change the password of a certain user used for HTTPS communication with the tenant and that he has created an **intermediate user** \(`user1`\) and password.
2.  Sender administrator: Exchanges the old user/password \(`user0`\) with the intermediate user/password \(`user1`\) in the HTTPS sender client \(back-end system\).
3.  Sender administrator: Informs the cloud infrastructure provider that the sender client now uses the intermediate user \(`user1`\).
4.  Cloud infrastructure provider: Informs the sender administrator that the password of the original user \(`user0`\) has been changed.
5.  Sender administrator: Exchanges the user/password of the intermediate user \(`user1`\) with the original user \(`user0`\) \(and with the new password\).
6.  Sender administrator: Informs the cloud infrastructure provider that user and password has been changed.

