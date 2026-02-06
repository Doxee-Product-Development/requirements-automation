---
id: "3c7360a6-8cdb-4abb-9376-72ef91552cde"
title: "Installation"
slug: "composer-developer-guide-6-6-installation"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Composer"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-20T12:24:02.475Z"
modified_at: "2025-09-01T13:00:29.3Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/composer-developer-guide-6-6-installation"
synced_at: "2026-01-28T21:00:47.556Z"
checksum: "8dbf53791ecff287"
---

Navigate to other release versions of Doxee Platform Composer

[6.6](https://docs.doxee.com/docs/en/composer-6-6)

[6.7](https://docs.doxee.com/docs/en/composer-6-7)

As a web front-end application Composer allows the users to comfortably access and documents usually stored in Infinica Content Repository. Therefore, it usually depends on the other Doxee applications so special care has to be taken while installation and setup.

## System Requirements
These applications have to be successfully installed and working before installing Doxee Composer:

- OpenJdk 17

- Apache Tomcat 8.5 or 9 (recommended)

- Infinica Content Repository

- Process Engine (optional)

- Business Designer (optional)

> Note

It is strictly speaking possible to run Composer without Doxee Content Repository although it is NOT recommended. A simple folder on the local disk can be configured as a Content Repository. Many features might be NOT available in this setup.

## Installation of the web applications
The listed System requirements, OpenJdk and Apache Tomcat, have to be installed following the normal installation process. After the installation of Apache Tomcat the following actions have to be performed additionally:

- Apache Tomcat maximum heap size should be set to at least 2GB.

`-Xmx2048m`
- Java Classpath in the Java tab of Tomcat properties should contain also the following:

`$TOMCAT\infinica\lib\authentication-layer-endorsed.jar;$TOMCAT\infinica\lib\infinica-protocol-`
- Java options in the Java tab of Tomcat properties should contain also the following:

`-Dhttp.maxConnections=20

-Dfile.encoding=UTF-8

-Dorg.apache.tomcat.util.buf.UDecoder.ALLOW_ENCODED_SLASH=true

-Dorg.apache.catalina.connector.CoyoteAdapter.ALLOW_BACKSLASH=true`
## Installation of the Composer
The following files have to be copied into the respective folders and Tomcat needs to be restarted. The home folder of Tomcat is called $TOMCAT in the following text (usually it is something like "C:\Program Files\Apache Software Foundation\Tomcat 9.0\" on Windows systems):

Into $TOMCAT/infinica

- composer-next.properties (The configuration file composer-next.properties contains the main settings for the usage of Composer.)

Into $TOMCAT/webapps

- infinica-composer.war (This is the main file.)

- infinica-content-repository.war (Required as it stores and handles all the files for Composer.)

- infinica-process-engine.war (Optional, only required for preview processes.)

> Note

There is no need to have separate infinica-composer.war (for Composer) in case Workplace is available or already set up because Composer is already part of Workplace (part of infinica-workplace.war). For more information on the use of Composer with and inside of Workplace please refer to the Workplace documentation. 

After the main file "infinica-composer.war" unpacks there should be just 2 folders inside the folder "infinica-composer" and no files on the first level (META-INF, WEB-INF).

> Note

Doxee Content Repository needs to have its own configuration files properly placed and set up according to its own documentation. Also, please note that files 'authentication-layer-endorsed.jar' and 'infinica-protocol-handler.jar' need to exist in '$TOMCAT\infinica\lib\' folder.

## Composer embedded in iframe
Composer can run embedded in iframe but embedding page or application has to follow certain rules so that all features can still work as expected. To be able to copy and paste in iframe mode it is recommended to allow it explicitly like in following example:

`&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
    &lt;meta charset="UTF-8"&gt;
    &lt;title&gt;Composer in iframe&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;p&gt;Composer embedded in iframe.&lt;/p&gt;
&lt;iframe id="ifrm" src="https://someserver.infinica.com/infinica-business-designer/" width="1280" height="720" allow="clipboard-read; clipboard-write"&gt;&lt;/iframe&gt;
&lt;/body&gt;
&lt;/html&gt;`> Note

The embedding page or application is not part of Composer or Doxee suite in general so it has to be set up and configured separately.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}