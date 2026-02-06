---
id: "95827c48-388d-4e3c-a96f-1fa6cb7b9a0e"
title: "i-Edition 6.5 SP3 - November 20, 2025"
slug: "release-notes-i-edition-6-5-sp3"
category: "i-Edition"
category_path:
  - "Release notes"
  - "i-Edition"
status: "published"
content_type: "block"
version: 3
public_version: 3
created_at: "2025-10-07T10:09:11.012Z"
modified_at: "2025-11-20T15:05:29.928Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-i-edition-6-5-sp3"
synced_at: "2026-01-28T20:40:01.215Z"
checksum: "ae9ef79bc3ea893b"
---

This section contains the full changelog of **Doxee Platform&reg;**** release 6.5 SP3**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 6.5 SP3
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- [6.5 SP3 release items](https://infinica.atlassian.net/issues/?filter=16948)

### Business Designer
#### Images
- **Fixed** Base64-encoded images not being rendered correctly.

### Process Designer
#### Stability &amp; Performance
- **Fixed** an issue that caused redirect callback server errors when setting up a new OpenID Process Engine.

### Process Engine
#### **Security**
- **Fixed **vulnerabilities by updating various libraries:

org.eclipse.jetty:jetty-http to 10.0.26

- io.netty:netty-codec to 4.1.126.Final

- io.undertow:undertow-core to 2.3.19.Final

#### Stability &amp; Performance
- **Fixed** prober services starting before the beginning of the warmup phase. The expected behavior is for prober services to start during the warmup phase.

- **Fixed:** The tag `processEngineId` is now again present in responses from Process Engine processes.

- **Fixed** processes getting stuck in ready status after waking up from a wait state while local resources were being registered.

### Template Designer
#### Security
- **Fixed **vulnerabilities by updating various libraries:

org.verapdf:core to 1.26.5

- commons-io to 2.14.0

- undertow-core to 2.3.20.Final

- jdom2 to 2.0.6.1

#### Images &amp; Dynamic Content
- **Fixed** word overflow issues in dynamically inserted HTML tables with CSS style sheets.

- **Fixed** errors when including a PDF file as an image or external document element.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}