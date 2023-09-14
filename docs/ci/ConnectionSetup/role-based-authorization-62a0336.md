<!-- loio62a03365f0c64fdda7417b6da7e5a4a7 -->

# Role-Based Authorization

This option allows you to define permissions for users in the connected identity provider \(by default, SAP Identity Service\) and to perform an authorization check based on these settings.

For HTTPS requests sent to Cloud Integration, it is checked if the role **ESBMessaging.send** is assigned to the user.

The permissions of the sending client are checked according to roles assigned to the user in the associated identity provider

User management \(which includes the assignment of permissions to users\) is performed by the tenant administrator using SAP BTP cockpit.

