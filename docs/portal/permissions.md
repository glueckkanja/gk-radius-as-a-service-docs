# Permissions

The permissions menu allows you to configure the permissions for the access to the RADIUSaaS admin portal.

RADIUSaaS leverages Azure AD as identity provider for the logon-authentication to the admin portal. It does not store or manage own administrator identities. The authentication is delegated to the corresponding Azure AD tenant of the provided UPN.

Therefore administrators enjoy the comfort of working with their own Azure AD accounts and do not have to setup additional accounts.

![](../.gitbook/assets/image%20%2857%29.png)

Please enter **Azure AD UPNs** in the provided fields and **separate them with comma and space**. 

Example:

```text
john.doe@contoso.com, peter.pan@contoso.com, jane.doe@other-aad-tenant.com
```

The wildcard "\*" is also supported, and may be used to allow all users from a certain domain.

Example:

```text
*@contoso.com
```

### Administrators

Azure AD UPNs entered in this field have the permission to access the RADIUSaaS admin portal. Permissions include:

* See dashboard and logging
* See and change users
* See and change settings including permissions

### Users

Reserved for upcoming features and **currently not used**.

### Guests

Reserved for upcoming features and **currently not used**.

