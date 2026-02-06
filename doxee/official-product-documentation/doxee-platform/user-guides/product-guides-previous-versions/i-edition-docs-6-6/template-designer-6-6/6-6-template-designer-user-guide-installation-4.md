---
id: "e62f4b3c-52da-4243-891f-8580c799bed7"
title: "Installation"
slug: "6-6-template-designer-user-guide-installation-4"
category: "Template Designer"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Template Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-14T13:25:38.641Z"
modified_at: "2025-11-18T10:26:30.578Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-template-designer-user-guide-installation-4"
synced_at: "2026-01-28T21:03:58.115Z"
checksum: "d433aecfed757e17"
---

Navigate to other release versions of Doxee Platform Template Designer

[6.6](https://docs.doxee.com/docs/en/template-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/template-designer-6-7)

To install Doxee Template Designer, start the installer executable and follow the installation steps. After successful installation, the application can be started using the InfinicaTemplateDesigner executable in the installation directory or the start menu entry.

## Configuration
Once installation is complete, there are several configuration files that can be adapted to the users´ needs.

### InfinicaTemplateDesigner.ini
The InfinicaTemplateDesigner.ini file is located in the Template Designer installation directory. The parameters configured in this file are handed to the Java Virtual Machine (Java VM). For this reason it is important that supplements are always specified at the end (after -vmargs).

- **VM **Path that points to the Java VM ( javaw.exe)

- **Xms **Initial size of the Java heap memory

- **Xmx **Maximum size of the Java heap memory

### config.ini
The config.ini configuration file is located in the subdirectory /configuration/ of the installation directory.

- **osgi.instance.area **Workspace directory

- **osgi.configuration.area **Configuration storage area

For both settings, the default value contains a reference to @user.home, which means that workspace and configuration will be stored separately for each user. Using a path without @user.home means that all users have a common workplace and configuration.

- **osgi.nl **Set language (de = German, en = English)

- **infinicaServerPort **Sets the port where Template Designer listens for commands to open more templates. This facilitates opening multiple templates in the same instance of Template Designer by double-clicking them in Windows Explorer.

### Infinica.log (configuration via log4j.xml)
The log4j.xml configuration file is located in the subdirectory

/plugins/com.infinica.plugins.core_6.x/ of the installation directory. This file defines where and how much of the log file infinica.log is written.

- **File **Directory and name of the log file (infinica.log)

- **Priority **Amount of information that is written to the log file.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}