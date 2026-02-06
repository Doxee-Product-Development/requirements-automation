---
id: "e1aa1820-243c-446a-96fe-c893c665bf3a"
title: "Configuration"
slug: "6-6-process-designer-design-tools-installation-guide-configuration"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Designer"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-08T07:47:54.378Z"
modified_at: "2025-08-20T19:18:11.105Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-designer-design-tools-installation-guide-configuration"
synced_at: "2026-01-28T21:01:11.114Z"
checksum: "d5359252a420d530"
---

Navigate to other release versions of Doxee Platform Process Designer

[6.6](https://docs.doxee.com/docs/en/process-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/process-designer-6-7)

The installation program stores the selected options in several configuration files. It is possible to change these settings after the installation by opening the configuration files with a text editor.

All paths in this chapter are relative to the *installation directory* as described in chapter [Select Components](/doxee-platform/docs/6-6-process-designer-design-tools-installation-guide-installation#select-components).

## Configure *Template Designer* and *Process Designer*
Both Designers are Eclipse-based RCP (Rich Client Platform) applications and as such they have a program-ini and a config-ini file. The file paths are as follows:

- Template Designer\InfinicaTemplateDesigner.ini (program-ini for TD)

- Template Designer\configuration\config.ini (config-ini for TD)

- Process Designer\InfinicaProcessDesigner.ini (program-ini for PD)

- Process Designer\configuration\config.ini (config-ini for PD)

### Changing the program-ini
In the program-ini you can fine-tune the Java start parameters:

- You can change the path to the Java runtime in the line after -vm.

- You can specify parameters for the Java runtime in the line after -vmargs.

### Changing the config-ini
In the config-ini you may want to adapt the following entries:

- **osgi.instance.area** Workspace directory

- **osgi.nl** Set language (en = English, de = German)

## Configure *Resource Explorer*
The settings for *Resource Explorer* can be edited in the file Resource

Explorer\InfinicaResourceExplorer.l4j.ini. The file contains startup parameters for the Java virtual machine:

- **-Dlang** Set language (en = English, de = German)

- **-Dre.settings** path to the settings.xml where RE stores information about Content Repository URLs, credentials, column layout, …

- Further VM parameters like memory settings

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}