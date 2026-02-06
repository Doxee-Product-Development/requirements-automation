---
id: "b6a1f1b0-09b5-4f9d-8b9e-1a174e9524c5"
title: "Third-party software requirements"
slug: "third-party-software-requirements-6-7"
category: "Product guides"
category_path:
  - "Product guides"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-12T09:25:47.934Z"
modified_at: "2026-01-12T09:27:07.529Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/third-party-software-requirements-6-7"
synced_at: "2026-01-28T20:40:05.995Z"
checksum: "1efcc5e54ee3b75f"
---

Doxee Platform&reg; products require third-party tools and software to run and use their applications. This page gives an overview of the third-party dependencies and the required or recommended versions.

## Overview of third-party dependencies
The following table lists the major Doxee applications and their requirements on the environments they are running and they are used in.

Component

Application type

Operating system

Middleware

Browser

**Template Designer**

Desktop application

Microsoft Windows

Java

Microsoft Edge

**Process Designer**

Desktop application

Microsoft Windows

Java

Microsoft Edge

**Resource Explorer**

Desktop application

Microsoft Windows

Java

Microsoft Edge

**Content Repository**

Server application

Microsoft Windows

Linux

Java

Apache Tomcat

SQL database

**Process Engine**

Server application

Microsoft Windows

Linux

Java

(optional) Apache Tomcat

(optional) SQL Database

(optional) NoSQL database

**Task Manager**

Server application

Microsoft Windows

Linux

Java

Apache Tomcat

SQL database

**Administrator**

Server application

Microsoft Windows

Linux

Java

Apache Tomcat

(optional) SQL database

Microsoft Edge

Mozilla Firefox

Google Chrome

Safari

**Business Designer**

Server application

Microsoft Windows

Linux

Java

Apache Tomcat

Microsoft Edge

Mozilla Firefox

Google Chrome

Safari

**Composer**

Server application

Microsoft Windows

Linux

Java

Apache Tomcat

Microsoft Edge

Mozilla Firefox

Google Chrome

Safari

**Workplace**

Server application

Microsoft Windows

Linux

Java

Apache Tomcat

(optional) SQL database

Microsoft Edge

Mozilla Firefox

Google Chrome

Safari

> Note on Doxee Design Tools and Microsoft Edge browser

The browser must be accessible for the application, for example for OAuth authentication purposes. Additionally, a [Microsoft Edge WebView2](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) installation is required in order to embed Microsoft Edge in the application.

## Required software versions
Software

Required version

**Operating system (desktop applications)**

Microsoft® Windows 10 or 11

**Operating system (server applications)**

Microsoft® Windows Server 2019

Red Hat® Enterprise Linux®  8 LTS

SUSE® Linux Enterprise Server 15

**Java**

OpenJDK17

> Note

The Doxee Design Tools installer includes a fitting Java version. Optionally, an existing Java installation may be selected during the installation process instead.

> Warning

Using openJDK from Linux package managers is not recommended.

**Apache® Tomcat**

Apache® Tomcat 10.x

**SQL database**

Enterprise Oracle® 19c

MySQL 8.0

SQL Server 2019 or 2022

> Warning

There is a known issue with the Cumulative Update 16 for SQL Server 2022, which prevents this database version from working properly as a process and task storage. This problem didn't occur in previous releases of SQL Server 2022 and might be fixed in future releases, but currently, we can't guarantee that it is usable with Process Engine and Task Manager when Update 16 is used.

PostgreSQL 14

**NoSQL database**

MongoDB 6.0

**Browser**

> Note

The release date of the browser version should be no older than 12 months.

Microsoft Edge

Mozilla Firefox

Google Chrome

Safari

## Minimum hardware requirements
To run the desktop client application suite **Doxee Design Tools**, consisting of Process Designer, Template Designer and Content Repository, please ensure that your system meets the following minimal hardware requirements:

Hardware

Requirements

Processor

- Intel multi-core processor (with 64-bit support)

- AMD Athlon® 64 processor

Operating system

- Windows 10 (64-bit)

- Windows 11 (64-bit)

RAM

2 GB RAM per client tool

Hard drive

- 4 GB of free disk space

> Note

Of the required disk space, 1 GB is required for the installation, 300 MB for the user workspace, and the rest as a buffer or for multi-user areas.

- SSD recommended

Screen resolution

1600 x 900 pixel monitor resolution (1920 x 1080 recommended)

Internet connection

Required for accessing cloud services (Process Engine, Content Repository), as well as when using other external services (e.g., an external image library for email templates)

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}