# Permissions

The permissions menu allows you to configure the permissions for the access to the RADIUSaaS admin portal.

![](../.gitbook/assets/image%20%2857%29.png)

Please enter **Azure AD UPNs** here and **separate them with comma and space**. 

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

