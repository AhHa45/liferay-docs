---
header-id: bean-security
---

# Bean Security

[TOC levels=1-4]

Specify bean properties the plugin is permitted to acquire. 

*Example:*

    security-manager-get-bean-property=\
        com.liferay.portal.kernel.xml.SAXReaderUtil,\
        com.liferay.portal.util.PortalUtil

Specify bean properties the plugin is permitted to set. 

*Example:*

    security-manager-set-bean-property=\
        com.liferay.portal.kernel.dao.orm.PortalCustomSQLUtil
