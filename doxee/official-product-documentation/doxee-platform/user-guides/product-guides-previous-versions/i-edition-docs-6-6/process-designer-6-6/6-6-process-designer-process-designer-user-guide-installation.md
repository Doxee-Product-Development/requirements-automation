---
id: "c2e8e8a6-3285-4e7f-9731-24e3145ace14"
title: "Installation"
slug: "6-6-process-designer-process-designer-user-guide-installation"
category: "Process Designer"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-08T07:07:52.118Z"
modified_at: "2025-08-20T19:15:51.866Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-designer-process-designer-user-guide-installation"
synced_at: "2026-01-28T21:00:57.892Z"
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