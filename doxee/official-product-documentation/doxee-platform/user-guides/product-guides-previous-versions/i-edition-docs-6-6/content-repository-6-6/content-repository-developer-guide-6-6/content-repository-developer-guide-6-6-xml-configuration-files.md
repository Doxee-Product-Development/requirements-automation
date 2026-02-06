---
id: "a69916df-6238-421f-9078-d5b4d93eb893"
title: "XML configuration files"
slug: "content-repository-developer-guide-6-6-xml-configuration-files"
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
created_at: "2025-12-04T10:19:31.196Z"
modified_at: "2025-12-04T13:16:22.315Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-developer-guide-6-6-xml-configuration-files"
synced_at: "2026-01-28T21:00:54.110Z"
checksum: "55eaf8c47518cbf6"
---

Most configurations for Doxee applications are stored in XML files. This section contains useful information about these files.

## Relative URLs
XML configurations often contain URLs to other resources and services. Sometimes, these URLs are allowed to be relative, i.e. they do not begin with a protocol (e.g. 'http://')` [2: Technically, this means the parameter is a URI, not a URL].` Unless explicitly described differently, relative URLs are treated as being relative to the configuration file in which they are defined.

Specifically, this means that a configuration file `demo_config.xml` can refer to an external file `file_a.txt` in the same directory simply via that file’s name `file_a.txt`, and to a file `file_b.txt` in a sub directory `sub` via the relative URL `sub/file_b.txt.`

## XInclude
The XInclude standard [3: [https://www.w3.org/TR/xinclude/](https://www.w3.org/TR/xinclude/)] allows XML content to be spread over more than a single file. In particular, this allows XML configurations to store some sections in separate files, and to share these files with other configurations.

Typical candidates are the user access and security configurations, which can be stored once and then referenced by the configurations of Process Engine, Doxee Content Repository etc.

To include an external file in an XML configuration, the following XML code can be used:

`&lt;xi:include href="external_file.xml" parse="xml" xmlns:xi="http://www.w3.org/2001/XInclude"/&gt;`If the external file is not an XML file, it can be included as plain text content by setting `parse` to `text`.

> Note

Relative URLs in included external XML files will not work as described in the previous chapter if the external file has a different path than the file it is included by. This is because the XInclude mechanism treats the contents of the included file as part of the main file, so when the relative URL is resolved, no information about the included file is available. Relative URLs in external XMLs are therefore treated as relative to the main XML file.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}