---
id: "994318d2-4700-4572-bc64-54566e492200"
title: "Resource Access"
slug: "resource-access"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T09:54:14.294Z"
modified_at: "2025-08-22T17:32:48.029Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/resource-access"
synced_at: "2026-01-28T21:01:46.554Z"
checksum: "30ebaafb6c28f148"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides access to files and directories in the local file system, Infinica Content Repository, or remote servers.

Activities:	

[Property Reader](/doxee-platform/docs/property-reader), [URL Checkin](/doxee-platform/docs/url-checkin), [URL Checkout](/doxee-platform/docs/url-checkout), [URL Enable Versioning](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-enabling-versioning), [URL Revert](/doxee-platform/docs/url-revert), [URL Uncheckout](/doxee-platform/docs/url-uncheckout), [URL Version History](/doxee-platform/docs/url-version-history)

The resource access activities use Doxee's Resource Access Layer (RAL) to access files and folders. RAL supports all authentication mechanisms supported by Infinica and can currently access the following types of file systems:

- Local file system (including mounted/mapped network folders)

- Infinica Content Repository (via extended WebDAV)

- Generic WebDAV servers

Not all file systems support the same features. For example, most advanced features like file properties and versioning are not supported by the local file system, and for WebDAV based servers (including Infinica Content Repository) versioning support depends on the server's capabilities and configuration.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}