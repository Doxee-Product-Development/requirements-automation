---
id: "ce27c794-3d9c-4959-952d-4af73194adec"
title: "Introduction"
slug: "content-repository-developer-guide-6-6-introduction"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Content Repository"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-04T10:18:12.52Z"
modified_at: "2025-12-04T12:41:08.436Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-developer-guide-6-6-introduction"
synced_at: "2026-01-28T21:00:51.275Z"
checksum: "450a253159b099b6"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

This document is targeted at administrators and describes how to install and configure Doxee Content Repository. Content Repository is a WebDAV based remote file system providing advanced features like ACL-based permission management and file versioning.

Content Repository is based on [Apache Jackrabbit](http://jackrabbit.apache.org/), which is the reference implementation of the JCR standard. Some configuration files are specific to Jackrabbit, while others set up the extended Doxee features. Where necessary, this documentation will refer to the official Jackrabbit documentation for details.

For information on how to use the Content Repository, please refer to its user guide.

## System Requirements
The following software and resources are required for installing ICR:

- OpenJdk

- Apache Tomcat

- Local file system storage for the repository’s cache and index

An overview of the supported software versions can be found in the general document *Software Requirements*.

The following optional dependencies may be necessary:

- Relational database for storing the repository’s content. Most JDBC enabled databases are supported. For details, please see the [corresponding section](https://wiki.apache.org/jackrabbit/PersistenceManagerFAQ) in the Jackrabbit documentation.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}