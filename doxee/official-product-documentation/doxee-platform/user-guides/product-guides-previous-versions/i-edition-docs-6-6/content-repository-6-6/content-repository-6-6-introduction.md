---
id: "a213f1c7-914b-4e81-81ca-cf40a1d45a34"
title: "Introduction"
slug: "content-repository-6-6-introduction"
category: "Content Repository"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Content Repository"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-04T10:12:02.876Z"
modified_at: "2025-12-04T10:38:11.963Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-6-6-introduction"
synced_at: "2026-01-28T21:00:48.890Z"
checksum: "57854f891ed3c664"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

Doxee Content Repository is a network-based filesystem, which allows multiple persons to use the same files with Doxee products from different devices. The main focus lies on Doxee files (e.g. templates, XML files etc.), but any kind of file can be stored in the repository. The repository is accessed via WebDAV. The WebDAV protocol is an extension of the HTTP standard, which means that files can be accessed by any application with HTTP support. It is possible for example, to view images or XML files, stored in the repository, directly in a web browser. Doxee Content Repository is based on Apache Jackrabbit, which handles the storage of files. The repository offers various functionality defined by the WebDAV standard and its extensions such as versioning, locking of resources and access control. In addition there are some features specific to Doxee such as ZIP import/export, XSL generation, home directories, automated versioning and lock stealing.

The next chapter provides a short introduction into [WebDAV](/doxee-platform/docs/content-repository-6-6-webdav) and its key concepts. A basic knowledge of this topic is required to understand how communication with the repository and accessing resources works. 

Chapter [Features](/doxee-platform/docs/content-repository-6-6-features) lists and describes all available features, which are either not part of the WebDAV specification or have some specific functionality in Doxee Content Repository.

Chapter [Characteristics](/doxee-platform/docs/content-repository-6-6-characteristics) explains important details about how the repository works.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}