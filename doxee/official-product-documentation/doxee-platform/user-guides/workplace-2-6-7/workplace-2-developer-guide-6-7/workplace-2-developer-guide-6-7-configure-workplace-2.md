---
id: "be474596-ded8-4c42-a08e-d341614536ae"
title: "Configure Workplace 2"
slug: "workplace-2-developer-guide-6-7-configure-workplace-2"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Workplace 2"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:29:03.964Z"
modified_at: "2026-01-07T14:29:45.125Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/workplace-2-developer-guide-6-7-configure-workplace-2"
synced_at: "2026-01-28T20:59:49.491Z"
checksum: "ad15d0945903684a"
---

Navigate to other release versions of Doxee Workplace 2

[6.6](https://docs.doxee.com/docs/en/workplace-6-6)

[6.7](https://docs.doxee.com/docs/en/workplace-6-7)

Workplace 2 is a highly customizable application. This article explores the various configuration options, ranging from integration with Task Manager and Process Engine to custom Human Task types and user access and security.

## Configuration options
Workplace 2 requires a configuration file in XML format. By default, it will use the file `$TOMCAT/workplace.xml`. This is the default configuration file included in the standard Workplace 2 distribution. It contains the following configuration:

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;workplace xmlns="http://www.infinica.com/workplace" xmlns:xi="http://www.w3.org/2001/XInclude"&gt;
    &lt;storage&gt;
        &lt;sql jdbcDriver="org.sqlite.JDBC"
             url="jdbc:sqlite:memory:test"
             user="dbuser"
             password="dbpassword"/&gt;
    &lt;/storage&gt;
    &lt;taskManager url="http://localhost:8080/infinica-task-manager/rest" &gt;
        &lt;technicalCredentials&gt;
            &lt;passwordCredentials xmlns="http://www.infinica.com/credentials" name="admin" password="admin" /&gt;
        &lt;/technicalCredentials&gt;
    &lt;/taskManager&gt;
    &lt;processEngine url="http://localhost:8080/infinica-process-engine/rest" watch="true"&gt;
        &lt;technicalCredentials&gt;
            &lt;passwordCredentials xmlns="http://www.infinica.com/credentials" name="admin" password="admin" /&gt;
        &lt;/technicalCredentials&gt;
    &lt;/processEngine&gt;
    &lt;taskDefinitions&gt;
        &lt;moduleDirectory&gt;modules/&lt;/moduleDirectory&gt;
    &lt;/taskDefinitions&gt;
    &lt;userAccessConfiguration xmlns="http://www.infinica.com/useraccess"&gt;
		&lt;userStore&gt;
				&lt;xml&gt;
					&lt;source&gt;users.xml&lt;/source&gt;
				&lt;/xml&gt;
		&lt;/userStore&gt;
    &lt;/userAccessConfiguration&gt;
  	&lt;security&gt;
		&lt;authentication xmlns="http://www.infinica.com/auth"&gt;
				&lt;basic realm="Infinica" /&gt;
		&lt;/authentication&gt;
		&lt;audit xmlns="http://www.infinica.com/audit"&gt;
				&lt;log4j /&gt;
		&lt;/audit&gt;
        &lt;roles&gt;
            &lt;role name="admin" loginName="admins" /&gt;
        &lt;/roles&gt;
	&lt;/security&gt;
    &lt;documentation url="https://docs.doxee.com/docs/workplace-6-6"/&gt;
&lt;/workplace&gt;`The individual XML nodes and their required values are explained below:

Field

Description

`storage`

Workplace 2 requires a storage for storing Business Case data. Currently, only SQL databases are supported as storage. It supports the same database systems as the rest of Doxee Platform&reg;.

`taskManager`

Determines how to access Task Manager. Must contain the attribute `url` with a valid address to the REST or SOAP API of a Task Manager.

`taskManager/technicalCredentials`

Enables technical calls to Task Manager. Must contain valid credentials to authenticate against the Task Manager API.

*(optional)* `taskManager/userCredentials`

By default, when the Task Manager API is called from the context of a user request, the credentials of the user are forwarded to Task Manager for authentication. In case this is not the desired behavior, an optional node `userCredentials` can be added on the same level as `technicalCredentials`, containing static credentials which should always be used for access to Task Manager.

`processEngine`

Determines how to access Process Engine. Must contain the attribute `url` with a valid address to the REST or SOAP API of a Process Engine.

`processEngine/technicalCredentials`

Enables technical calls to Process Engine. Must contain valid credentials to authenticate against the Process Engine API.

*(optional)* `processEngine/userCredentials`

By default, when the Process Engine API is called from the context of a user request, the credentials of the user are forwarded to Process Engine for authentication. In case this is not the desired behavior, a node `userCredentials` can be added on the same level as `technicalCredentials`, containing static credentials which should always be used for access to Process Engine.

*(optional)* `taskDefinitions`

Workplace 2 offers the possibility to register additional Human Task definitions to extend the existing standard definitions. These definitions are collected in module files, which need to be put into the module directory. The directory `module` can be configured as the value of the node `moduleDirectory`.

`userAccessConfiguration`

Specifies the user store which should be used for managing access to Workplace 2. The format of this configuration is in line with the rest of the platform and is explained in detail in the Security Configuration Guide.

`security`

`security/authentication`

Specifies the mechanism for authenticating users. The format of this configuration is in line with the rest of the platform and is explained in detail in the Security Configuration Guide.

*(optional)* `security/audit`

Optional configuration of the audit log. The format of this configuration is in line with the rest of the platform and is explained in detail in the Security Configuration Guide.

`security/roles`

Contains a list of `role` and `roleDefinition` nodes.

`security/roles/role`

Assigns a standard or custom role to the `loginName` of a principal. The attribute `name` specifies the name of the role and `loginName` identifies the principal, which can be a user or group. The following standard roles are available:

- `businessUser`

- `supervisor`

- `manager`

- `admin`

*(optional) *`security/roles/roleDefinition`

Can be used to define a custom role with a custom set of privileges. It has an attribute name and a list of privilege nodes, with the name of the privilege as the value. The following privileges are available:

- `authenticated`: ?

- `admin`: ?

- `createBusinessCaseDefinition`: Can create Business Cases.

- `readBusinessCaseDefinition`: ?

- `writeBusinessCaseDefinition`: ?

- `deleteBusinessCaseDefinition`: Can delete Business Cases.

- `startBusinessCase`: Can start Business Cases.

- `terminateBusinessCaseInstance`: Can terminate Business Case Instances.

- `deleteBusinessCaseInstance`: Can delete Business Case Instances.

- `readBusinessCaseInstance`: ?

- `readBusinessCaseInstance`: ?

- `createFolder`: Can create folders.

- `readFolder`: ?

- `writeFolder`: ?

- `deleteFolder`: Can delete folders.

`documentation`

The attribute `url` specifies the URL for opening Workplace 2 documentation in another browser tab. A default link is provided.

- `storage`: Workplace 2 requires a storage for storing Business Case data. Currently, only SQL databases are supported as storage. It supports the same database systems as the rest of Doxee Platform&reg;.

- `taskManager`: Determines how to access Task Manager. Must contain the attribute `url` with a valid address to the REST or SOAP API of a Task Manager.

`technicalCredentials`: Enables technical calls to Task Manager. Must contain valid credentials to authenticate against the Task Manager API.

- *(optional)* `userCredentials`: By default, when the Task Manager API is called from the context of a user request, the credentials of the user are forwarded to Task Manager for authentication. In case this is not the desired behavior, a node `userCredentials` can be added on the same level as `technicalCredentials`, containing static credentials which should always be used for access to Task Manager. 

- `processEngine`: Determines how to access Process Engine. Must contain the attribute `url` with a valid address to the REST or SOAP API of a Process Engine.

`technicalCredentials`: Enables technical calls to Process Engine. Must contain valid credentials to authenticate against the Process Engine API.

- *(optional)* `userCredentials`: By default, when the Process Engine API is called from the context of a user request, the credentials of the user are forwarded to Process Engine for authentication. In case this is not the desired behavior, a node `userCredentials` can be added on the same level as `technicalCredentials`, containing static credentials which should always be used for access to Process Engine.

- *(optional)* `taskDefinitions`: Workplace 2 offers the possibility to register additional Human Task definitions to extend the existing standard definitions. These definitions are collected in module files, which need to be put into the module directory. The directory `module` can be configured as the value of the node `moduleDirectory`.

- `userAccessConfiguration`: Specifies the user store which should be used for managing access to Workplace 2. The format of this configuration is in line with the rest of the platform and is explained in detail in the Security Configuration Guide.

- `security`

`authentication`: Specifies the mechanism for authenticating users. The format of this configuration is in line with the rest of the platform and is explained in detail in the Security Configuration Guide.

- *(optional)* `audit`: Optional configuration of the audit log. The format of this configuration is in line with the rest of the platform and is explained in detail in the Security Configuration Guide.

- `roles`: Contains a list of `role` and `roleDefinition` nodes.

`role`: Assigns a standard or custom role to the `loginName` of a principal. The attribute `name` specifies the name of the role and `loginName` identifies the principal, which can be a user or group. The following standard roles are available:

`businessUser`

- `supervisor`

- `manager`

- `admin`

- *(optional) *`roleDefinition`: Can be used to define a custom role with a custom set of privileges. It has an attribute name and a list of privilege nodes, with the name of the privilege as the value. The following privileges are available:

`authenticated`: ?

- `admin`: ?

- `createBusinessCaseDefinition`: Can create Business Cases.

- `readBusinessCaseDefinition`: ?

- `writeBusinessCaseDefinition`: ?

- `deleteBusinessCaseDefinition`: Can delete Business Cases.

- `startBusinessCase`: Can start Business Cases.

- `terminateBusinessCaseInstance`: Can terminate Business Case Instances.

- `deleteBusinessCaseInstance`: Can delete Business Case Instances.

- `readBusinessCaseInstance`: ?

- `readBusinessCaseInstance`: ?

- `createFolder`: Can create folders.

- `readFolder`: ?

- `writeFolder`: ?

- `deleteFolder`: Can delete folders.

- `documentation`: The attribute `url` specifies the URL for opening Workplace 2 documentation in another browser tab. A default link is provided.

An interactive step within a Business Case. Depending on the type of Human Task, the user may be prompted to provide input in order to advance or complete the Business Case.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}