<!-- loio86319603293b432b8c65880c609aa9d2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Migration Steps for 2.0 Compatibility

Migrate an active agreement that uses AS2 Sender adapter to make it compatible with the 2.0 version of the generic integration flow.

The 2.0 version of the generic integration flow is not compatible with all existing active agreements. The AS2 adapter now consists of two configuration modes -*Profile* and *Channel* mode and the latest integration flow configuration works only with the *Profile* mode of the AS2 adapter.

Let us say, you have an active agreement that uses the AS2 Sender adapter and is not compatible with this version but you would like to make it work with this version. If that is the requirement, you need to make few configuration changes. Follow the steps mentioned below:

1.  Login to your application.

2.  Navigate to *Design* \> *B2B Scenarios*.
3.  Choose the *Agreements* tab.
4.  Search and open the active Agreement that you want to migrate.
5.  Choose *Deactivate* and select *OK* in the resulting dialog. This will deactivate the agreement.
6.  Close your agreement and navigate to the *Trading Partners* tab.
7.  Select and open the trading partner that you have used in the agreement that you deactivated.
8.  Navigate to the *Systems* tab and open the system that you have used in the agreement.
9.  Navigate to the *Communications* tab and select Edit :pencil2: button next to the AS2 Sender entry. This will add the *Security Configuration Mode* to the communication channel.
10. Choose *Save*.
11. Close the partner profile and navigate back to the *Agreements* tab.
12. Open the deactivated agreement and choose *Activate*. This updated agreement is now compatible with the 2.0 generic integration flow version.

