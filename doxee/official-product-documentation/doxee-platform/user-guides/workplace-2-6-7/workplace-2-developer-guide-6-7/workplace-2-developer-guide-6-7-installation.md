---
id: "26797150-bed5-4048-9593-fc005ae71850"
title: "Install Workplace 2"
slug: "workplace-2-developer-guide-6-7-installation"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Workplace 2"
  - "Administration guide"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2026-01-07T13:29:03.907Z"
modified_at: "2026-01-07T14:30:56.482Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/workplace-2-developer-guide-6-7-installation"
synced_at: "2026-01-28T20:59:49.155Z"
checksum: "f692eb2f2328e8d9"
---

Navigate to other release versions of Doxee Workplace 2

[6.6](https://docs.doxee.com/docs/en/workplace-6-6)

[6.7](https://docs.doxee.com/docs/en/workplace-6-7)

Workplace 2 is a web-based application which requires no installation for end users. However, it must be installed and configured by an administrator on the server side before end users can interact with it.

This article gives a detailed step-by-step description of the installation and update process. A detailed explanation of the configuration options can be found here: [Configure Workplace 2](/doxee-platform/docs/configure-workplace-2-1).

## Prerequisites
The following software and resources are required for installing Workplace 2:

- **OpenJDK**

- **Apache Tomcat**

- **Relational database** for storing Business Cases

For details on the required software versions, please refer to the [Software and hardware requirements](/doxee-platform/docs/software-and-hardware-requirements).

## Download the software
- Navigate to the official download server [download.infinica.com](https://download.infinica.com/navigate/).

- Authenticate with your credentials.

- Navigate to the subfolder of the component you want to download and download the ZIP file of the version you want to install.

Verify that the downloaded ZIP file contains the following items:

- Folder `conf`

Folder `Catalina`

Folder `&lt;hostname&gt;`

File `rewrite.config`: Contains the configuration to enable proper URL handling.

> Purpose of this file

Because the Workplace 2 frontend is a single-page application, all requests must be forwarded to the application instead of letting Apache Tomcat handle different paths itself.

- Folder `infinica`

Folder `modules`

File `modules.json`: Contains the UI, input and output configurations for the standard Human Task types. It can be used as an example for creating custom Human Task modules with additional types.

- *(optional)* File `taskTypes.xml`: This file can be used to register the standard Human Task types from `modules.json` as a static Human Task type registry in the Task Manager. It’s not required by Workplace 2 itself and can also be generated dynamically through the Workplace 2 REST API, based on the Human Task types provided in `modules.json`.

- *(optional)* File `users.xml`: Contains an example XML user store referenced in the default `workplace.xml` file.

> Purpose of this file

This file is required when using the default configurations as-is. It’s not required if the configuration is changed to a different authentication mechanism and/or user store.

- File `workplace.xml`: Configuration file containing the default application configurations.

- File `workplace.war`

## Installation steps
- Stop Apache Tomcat.

- Copy the installation files to the following locations:

Copy `workplace.war` to `$TOMCAT/webapps`.

- Copy the `infinica` directory to `$TOMCAT`. Alternatively, if a `$TOMCAT/infinica` directory already exists, copy the contents of the directory there.

- Copy the file `rewrite.config` to `$TOMCAT/conf/Catalina/&lt;hostname&gt;`.

- Edit the configuration file `workplace.xml`. The configuration options are described here: [Configure Workplace 2](/doxee-platform/docs/configure-workplace-2-1).

- Modify the file `server.xml` in the folder `$TOMCAT/conf`:

Under `&lt;Server&gt;/&lt;Service&gt;/&lt;Engine&gt;/&lt;Host&gt;`, add `&lt;Valve className="org.apache.catalina.valves.rewrite.RewriteValve"/&gt;`.

- Start Apache Tomcat.

- Verify that Workplace 2 can be accessed.

### FAQ
#### How can I change the name and location of the configuration file?
The name and location of the configuration file can be changed by providing the Java option `infinica.configurationPath`, which must be a path to an XML file in the proper format. The default configuration file is `workplace.xml` and is included in the standard Workplace 2 installation files.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}