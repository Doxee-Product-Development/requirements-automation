---
id: "288b20bd-7b5e-464e-a6d2-3ff42e61bbfa"
title: "User Access"
slug: "6-6-process-engine-manpages-detailed-module-descriptions-user-access"
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
created_at: "2025-08-13T10:03:33.465Z"
modified_at: "2025-08-22T17:32:48.029Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-detailed-module-descriptions-user-access"
synced_at: "2026-01-28T21:01:49.695Z"
checksum: "fca2d34ce7b820c4"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Support for accessing user data.

Activity:	

[Read Principal](/doxee-platform/docs/read-principal)

This module provides access to the attributes of the current user, and other users in the user store.

Which data is available depends on the configured user store. In particular, some ticket based authentication systems work without an actual user store and can therefore only provide information about the currently authenticated user. Consequently, user queries are only available if an actual user store is available, and the accessing user has the necessary permissions.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}