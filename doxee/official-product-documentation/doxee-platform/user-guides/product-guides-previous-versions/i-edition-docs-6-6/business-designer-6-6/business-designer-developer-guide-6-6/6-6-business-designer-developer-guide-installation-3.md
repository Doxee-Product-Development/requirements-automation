---
id: "936813ac-7def-48d1-9a75-50d0f091dd00"
title: "Installation"
slug: "6-6-business-designer-developer-guide-installation-3"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Business Designer"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-13T11:21:58.411Z"
modified_at: "2026-01-07T13:52:34.606Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-business-designer-developer-guide-installation-3"
synced_at: "2026-01-28T21:00:28.910Z"
checksum: "cf4ef8603c3829cd"
---

Navigate to other release versions of Doxee Platform Business Designer

[6.6](https://docs.doxee.com/docs/en/business-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/business-designer-6-7)

As a web front-end application Business Designer allows the users to comfortably access and edit templates usually stored in Doxee Content Repository. Therefore, it usually depends on the other Doxee applications so special care has to be taken while installation and setup.

## System Requirements
These applications have to be successfully installed and working before installing Doxee Business Designer:

- OpenJdk 17

- Apache Tomcat 8.5 or 9 (recommended)

- Doxee Content Repository

- Doxee Process Engine (optional)

- Doxee Composer (optional)

## Installation of the web applications
The listed System requirements, OpenJdk and Apache Tomcat, have to be installed following the normal installation process. After the installation of Apache Tomcat the following actions have to be performed additionally:

- Apache Tomcat maximum heap size should be set to at least 2GB.

`-Xmx2048m`
- Java Classpath in the Java tab of Tomcat properties should contain also the following:

`$TOMCAT\infinica\lib\authentication-layer-endorsed.jar;$TOMCAT\infinica\lib\infinica-protocol-   handler.jar`
- Java options in the Java tab of Tomcat properties should contain also the following:

`-Dhttp.maxConnections=20
-Dfile.encoding=UTF-8`
## Installation of the Business Designer
The following files have to be copied into the respective folders and Tomcat needs to be restarted. The home folder of Tomcat is called $TOMCAT in the following text (usually it is something like "C:\Program Files\Apache Software Foundation\Tomcat 9.0\" on Windows systems):

`Into $TOMCAT/infinica`- business-designer.properties (The configuration file business-designer.properties contains the main settings for the usage of Business Designer.)

`Into $TOMCAT/webapps`
- infinica-business-designer.war (This is the main file.)

- infinica-content-repository.war (Required as it stores and handles all the files for Business Designer.)

- infinica-process-engine.war (Optional, only required for HTML Email preview.)

- composer.war (Optional, only required for Composer preview.)

There is no need to have separate composer.war (for Composer) in case

> Note

Workplace is available or already set up because Composer is already part of Workplace (part of workplace.war).

After the main file "infinica-business-designer.war" unpacks there should be just three folders inside the folder "infinica-business-designer" and no files on the first level (docs, META-INF, WEB-INF).

> Note

Doxee Content Repository needs to have its own configuration files properly placed and set up according to its own documentation. Also, please note that files 'authentication-layer-endorsed.jar' and 'infinica- protocol-handler.jar' need to exist in '$TOMCAT\infinica\lib\' folder.

## Business Designer embedded in iframe
Business Designer can run embedded in iframe but embedding page or application has to follow certain rules so that all features can still work as expected. To be able to copy and paste in iframe mode it is recommended to allow it explicitly like in following example:

`&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
&lt;meta charset="UTF-8"&gt;
&lt;title&gt;BD in iframe&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;p&gt;BD embedded in iframe.&lt;/p&gt;
&lt;iframe id="ifrm" src="https://someserver.infinica.com/infinica-business-designer/" width="1280" height="720" allow="clipboard-read; clipboard-write"&gt;&lt;/iframe&gt;
&lt;/body&gt;
&lt;/html&gt;`> Note

The embedding page or application is not part of Business Designer or Doxee suite in general so it has to be set up and configured separately.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}