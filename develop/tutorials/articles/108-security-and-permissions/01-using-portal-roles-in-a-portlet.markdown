---
header-id: using-portal-roles-in-a-portlet
---

# Using Portal Roles in a Portlet

[TOC levels=1-4]

"A role, a role, my portal for a role!" Don't worry, using portal roles in your
portlets isn't too difficult. Roles in Liferay Portal are the primary means for
granting or restricting access to content. When a role is assigned to a user,
the user is granted the permissions that have been defined for the role. Read
on to learn how to use portal roles in your application!

## JSR 286 Portlet Security

The JSR 286 portlet specification defines a means to specify roles used by
portlets in their `docroot/WEB-INF/portlet.xml` descriptors. The role names
themselves, however, are not standardized. When these portlets run in Liferay,
you'll recognize familiar role names. For example, consider the Guestbook
project:
[Guestbook Project](https://github.com/liferay/liferay-docs/tree/6.2.x/develop/tutorials/code/01-mvc/learning-sdk/portlets/guestbook-portlet).
The Guestbook project is the sample project that you create by
following the steps of Liferay's
[MVC Learning Path](/docs/6-2/tutorials/-/knowledge_base/t/writing-a-liferay-mvc-application).
The Guestbook project contains two portlets: The Guestbook portlet and the
Guestbook Admin portlet. Notice that Guestbook project's `portlet.xml` file
references the *administrator*, *guest*, *power-user*, and *user* roles: 

```xml
<?xml version="1.0"?>
<portlet-app xmlns="http://java.sun.com/xml/ns/portlet/portlet-app_2_0.xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/portlet/portlet-app_2_0.xsd http://java.sun.com/xml/ns/portlet/portlet-app_2_0.xsd" version="2.0">

<portlet>
    <portlet-name>guestbook</portlet-name>
    <display-name>Guestbook</display-name>
    <portlet-class>
        com.liferay.docs.guestbook.portlet.GuestbookPortlet
    </portlet-class>
    <init-param>
        <name>view-template</name>
        <value>/html/guestbook/view.jsp</value>
    </init-param>
    <expiration-cache>0</expiration-cache>
    <supports>
        <mime-type>text/html</mime-type>
        <portlet-mode>view</portlet-mode>
    </supports>
    <portlet-info>
        <title>Guestbook</title>
        <short-title>Guestbook</short-title>
        <keywords></keywords>
    </portlet-info>
    <security-role-ref>
        <role-name>administrator</role-name>
    </security-role-ref>
    <security-role-ref>
        <role-name>guest</role-name>
    </security-role-ref>
    <security-role-ref>
        <role-name>power-user</role-name>
    </security-role-ref>
    <security-role-ref>
        <role-name>user</role-name>
    </security-role-ref>
</portlet>
<portlet>
    <portlet-name>guestbook-admin</portlet-name>
    <display-name>Guestbook Admin</display-name>
    <portlet-class>
        com.liferay.docs.guestbook.portlet.GuestbookAdminPortlet
    </portlet-class>
    <init-param>
        <name>view-template</name>
        <value>/html/guestbookadmin/view.jsp</value>
    </init-param>
    <expiration-cache>0</expiration-cache>
    <supports>
        <mime-type>text/html</mime-type>
        <portlet-mode>view</portlet-mode>
    </supports>
    <portlet-info>
        <title>Guestbook Admin</title>
        <short-title>Guestbook Admin</short-title>
        <keywords></keywords>
    </portlet-info>
    <security-role-ref>
        <role-name>administrator</role-name>
    </security-role-ref>
    <security-role-ref>
        <role-name>guest</role-name>
    </security-role-ref>
    <security-role-ref>
        <role-name>power-user</role-name>
    </security-role-ref>
    <security-role-ref>
        <role-name>user</role-name>
    </security-role-ref>
</portlet>
```

Your `portlet.xml` roles must be mapped to specific roles in the portal.
These mappings allow the portal to resolve conflicts between roles with the same
name that are from different portlets (e.g. portlets from different developers). 

| **Note:** Each role named in a portlet's `<security-role-ref>` element is given
| permission to add the portlet to a page.

## Mapping Portlet Roles to Portal Roles

To map the roles to Liferay Portal, you'll have to use the
`docroot/WEB-INF/liferay-portlet.xml` Liferay-specific configuration file. For
an example, see the mapping defined in the Guestbook project's
`liferay-portlet.xml` file. Many Liferay projects use identical role mappings.

```xml
<role-mapper>
    <role-name>administrator</role-name>
    <role-link>Administrator</role-link>
</role-mapper>
<role-mapper>
    <role-name>guest</role-name>
    <role-link>Guest</role-link>
</role-mapper>
<role-mapper>
    <role-name>power-user</role-name>
    <role-link>Power User</role-link>
</role-mapper>
<role-mapper>
    <role-name>user</role-name>
    <role-link>User</role-link>
</role-mapper>
```

If a portlet definition references the role `power-user`, that portlet is mapped
to the Liferay role called *Power User* that's already in Liferay's database. 

As stated above, there is no standardization with portal role names. If you
deploy a portlet with role names different from the above default Liferay names,
you must add the names to the `system.roles` property in your
`portal-ext.properties` file: 

```properties
system.roles=my-role,your-role,our-role
```

This prevents roles from being created accidentally. 

Once roles are mapped to the portal, you can use methods as defined in the
portlet specification: 

- `getRemoteUser()`
- `isUserInRole()`
- `getUserPrincipal()`

For example, you can use the following code to check if the current user has
the `power-user` role:

```java
if (renderRequest.isUserInRole("power-user")) {
    // ...
}
```

By default, Liferay doesn't use the `isUserInRole()` method in any built-in
portlets. Liferay uses its own permission system directly to achieve more
fine-grained security. If you don't intend on deploying your portlets to other
portal servers, we recommend using Liferay's permission system, because it
offers a much more robust way of tailoring your application's permissions. 

## Related Topics

[Customizing Liferay Portal](/docs/6-2/tutorials/-/knowledge_base/t/customizing-liferay-portal)

[Plugin Security and PACL](/docs/6-2/tutorials/-/knowledge_base/t/plugin-security-and-pacl)

[Developing Plugins with Liferay IDE](/docs/6-2/tutorials/-/knowledge_base/t/liferay-ide)

[User Interfaces with AlloyUI](/docs/6-2/tutorials/-/knowledge_base/t/alloyui)

[Liferay UI Taglibs](/docs/6-2/tutorials/-/knowledge_base/t/liferay-ui-taglibs)
