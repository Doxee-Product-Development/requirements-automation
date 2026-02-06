---
id: "1b241ae6-d464-4e83-8d55-4a7f9e5c1402"
title: "Installation"
slug: "content-repository-developer-guide-6-6-installation"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Content Repository"
  - "Administration guide"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-04T10:18:31.278Z"
modified_at: "2025-12-05T16:00:35.285Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-developer-guide-6-6-installation"
synced_at: "2026-01-28T21:00:51.611Z"
checksum: "61fa2a4a0e6ca513"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

This chapter describes how to set up a new Content Repository installation.

## Bootstrap Overview
When the Content Repository web application is started and no local repository home directory exists yet, a new repository is initialised and the home directory is created on the local disk. This process is called bootstrapping.

Bootstrapping happens when the repository application is started for the first time on a new system, but also when you delete the repository home directory before starting the application. This may be necessary during the installation phase if the configuration is faulty and the repository cannot be initialised correctly.

The repository always uses a database to store its structure and content. The tables and other database objects are created as part of the bootstrapping process. By default, this database is a local Derby database which stores all its data in the repository home directory. If the repository is configured to use an external database server, all database objects created by the repository should be deleted as well when the local repository home directory is deleted. Otherwise, the newly initialised repository will still be using the tables and data of the previous repository.

> Important

Once a new repository is initialised, it is recommended that you check the log files in *$TOMCAT/logs* to verify if the bootstrapping process was completed successfully. If the log files show errors during the repository initialisation (e.g. failure to access an external database), you should stop the application, delete the local repository home directory and any database objects created by the repository if you have configured an external database, fix the configuration and start the application again to retry the bootstrapping process.

## Installation Steps
The following steps must be performed to install a new Content Repository:

- Stop Tomcat

- Copy the installation files

Copy `infinica-content-repository.war` to `$TOMCAT/webapps` 

- Copy the `infinica` directory to `$TOMCAT` (or if a directory `$TOMCAT/infinica` already exists, copy the contents of the directory

- Edit the bootstrap configuration files

- Start Tomcat

- Check the log files to see if any errors occurred during the bootstrapping process

If there were errors, stop Tomcat, delete the local repository home directory and any tables and database objects if you have configured an external database, fix the configuration and continue with step 4

- Verify that the repository can be accessed

> Warning

After you have copied the WAR file into Tomcat, *do not* start the server until you have completed configuring the repository. Otherwise, a new repository will be initialised and you will have to delete it as described in step 5b it when you change the configuration.

## Editing the Bootstrap Configuration Files
All [term]#bootstrap configuration# files for the repository application can be found in the `infinica` directory. The two files `repository.properties` and `icr.xml` must be edited to set up the repository. A third file, `repository.xml`, may be edited to change the storage configuration, e.g. when using an external database server.

These configuration files are described in [Bootstrap configuration](/doxee-platform/docs/content-repository-developer-guide-6-6-bootstrap-configuration).

In addition to the bootstrap configuration, which is required to start the server application, the Content Repository has another set of configuration options which are only used once the repository is up and running. These settings are called the runtime configuration and described in a separate chapter.

> Caution

Before setting up a clustered repository, make sure to carefully read [Cluster configuration](/doxee-platform/docs/content-repository-developer-guide-6-6-cluster-configuration) and edit the configuration files accordingly.

## Verifying Repository Access
Once the repository is up and running, it can be accessed using the following URL (assuming Tomcat is running on the same machine on its standard port):

`http://localhost:8080/infinica-content-repository/`Accessing this URL via a web browser should prompt for credentials (or use the current user's credentials if a single sign on authentication mechanism like `Negotiate` is configured) and show the directory listing of the root folder.

Further access can then be tested by navigating the repository in the browser or via Resource Explorer.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}