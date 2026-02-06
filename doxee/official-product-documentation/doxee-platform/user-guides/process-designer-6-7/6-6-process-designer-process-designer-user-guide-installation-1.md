---
id: "61c819d2-dab7-419b-ad04-dc8a840e0ab3"
title: "Installation"
slug: "6-6-process-designer-process-designer-user-guide-installation-1"
category: "Process Designer"
category_path:
  - "Product guides"
  - "Process Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:43:42.635Z"
modified_at: "2026-01-07T14:03:47.367Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-designer-process-designer-user-guide-installation-1"
synced_at: "2026-01-28T20:54:32.512Z"
checksum: "f7c26f82856f7417"
---

Navigate to other release versions of Doxee Platform Process Designer

[6.6](https://docs.doxee.com/docs/en/process-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/process-designer-6-7)

To install Process Designer, start the installer executable and follow the installation steps.

After the installation was successful, the application can be started using the

InfinicaProcessDesigner executable in the installation directory or the start menu entry.

## Configuration
Once the installation is complete, there are several configuration files that can be adapted to the users needs.

### InfinicaProcessDesigner.ini
The InfinicaProcessDesigner.ini file is located in the Process Designer installation directory. The parameters configured in this file are handed to the Java Virtual Machine (Java VM). For this reason it is important that supplements are always specified at the end (after -vmargs).

- **Dosgi.configuration.area** Directory for the individual user configurations

- **VM** Directory that points to the Java VM (javaw.exe)

- **Xms** Initial size of the Java heap memory

- **Xmx** Maximum size of the Java heap memory

### config.ini
The config.ini configuration file is located in the subdirectory /configuration/ of the installation directory.

- **osgi.instance.area** Workspace directory

- **osgi.nl** Set language (de = German, en = English)

### Infinica.log (configuration via log4j2.xml)
The log4j2.xml configuration file is located in the subdirectory

/plugins/com.infinica.plugins.core_6.x/ of the installation directory. This file defines which log messages are written where. It is a standard Apache Log4j 2 configuration.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}