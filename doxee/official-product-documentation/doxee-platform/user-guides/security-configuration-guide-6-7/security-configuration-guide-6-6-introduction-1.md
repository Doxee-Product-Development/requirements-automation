---
id: "9ed47fe5-bb21-460a-846d-1834f5bce6b4"
title: "Introduction"
slug: "security-configuration-guide-6-6-introduction-1"
category: "Security configuration"
category_path:
  - "Product guides"
  - "Security configuration"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:18.192Z"
modified_at: "2026-01-07T13:47:44.468Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-introduction-1"
synced_at: "2026-01-28T20:40:08.275Z"
checksum: "3fb571e3713388eb"
---

Doxee's services share common concepts for security management. While not all application configurations have been unified (differences will be noted in the individual applications' administration guides), most of the concepts described here will apply to most Doxee services, including Process Engine, Content Repository, and Task Manager.

The first section of this guide (Concepts) describes the general security concepts implemented by Doxee, and how to configure them. The second section (Authentication mechanisms and user stores) describes individual mechanisms and user stores, and their  specific configuration, in their individual chapters. It is recommended that administrators read the full first section along with any chapters from the second section that are relevant for their environment.

> Tip

When configuring multiple services on the same server/in the same container, it can be useful to share authentication and user store configurations with all services. This can be accomplished by keeping the `&lt;authentication&gt;` and `&lt;userAccessConfiguration&gt;` elements in separate XML files and referencing them from the correct location in each service's configuration using the XInclude mechanism:

`&lt;xi:include href="authentication.xml" parse="xml" xmlns:xi="http://www.w3.org/2001/XInclude"/&gt;
...
&lt;xi:include href="useraccess.xml" parse="xml" xmlns:xi="http://www.w3.org/2001/XInclude"/&gt;`For brevity, XInclude examples in the remainder of this documentation will leave out the namespace definition. It is recommended to configure the namespace globally in all XML files that use it, by adding the `xmlns:xi` attribute to the root element.

## Concepts
This section describes concepts and configurations common to all Doxee setups regardless of the chosen authentication and user store types. The concepts described here are the prerequisites for the detailed descriptions of specific authentication mechanisms and user store types described in the next section, Authentication mechanisms and user stores.

## Authentication mechanisms and user stores
This section provides in-depth information and configuration descriptions for all standard authentication mechanisms and user stores supported by Doxee. Knowledge of the concepts and general configuration structure described in the previous section (Concepts) is required.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}