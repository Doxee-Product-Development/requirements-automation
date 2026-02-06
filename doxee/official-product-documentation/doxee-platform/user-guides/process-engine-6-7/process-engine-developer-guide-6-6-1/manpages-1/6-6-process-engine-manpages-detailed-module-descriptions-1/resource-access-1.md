---
id: "2195b587-c10b-49fd-b8c8-b6b6614c0d67"
title: "Resource Access"
slug: "resource-access-1"
category: "Detailed Module Descriptions"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Detailed Module Descriptions"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:11.075Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/resource-access-1"
synced_at: "2026-01-28T20:55:18.572Z"
checksum: "a4230ae4093fb99a"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Provides access to files and directories in the local file system, Infinica Content Repository, or remote servers.

Activities:	

[Property Reader](/doxee-platform/docs/6-6-process-engine-manpages-activities-property-reader-1), [URL Checkin](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-checkin-1), [URL Checkout](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-checkout-1), [URL Enable Versioning](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-enabling-versioning-1), [URL Revert](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-revert-1), [URL Uncheckout](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-uncheckout-1), [URL Version History](/doxee-platform/docs/6-6-process-engine-manpages-activities-url-version-history-1)

The resource access activities use Doxee's Resource Access Layer (RAL) to access files and folders. RAL supports all authentication mechanisms supported by Infinica and can currently access the following types of file systems:

- Local file system (including mounted/mapped network folders)

- Infinica Content Repository (via extended WebDAV)

- Generic WebDAV servers

Not all file systems support the same features. For example, most advanced features like file properties and versioning are not supported by the local file system, and for WebDAV based servers (including Infinica Content Repository) versioning support depends on the server's capabilities and configuration.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}