---
id: "348ba64a-1499-4c2e-8ff4-f06594a639b5"
title: "Doxee Platform 3.48.0.4 - October 6, 2025"
slug: "release-notes-doxee-platform-3-48-0-4"
category: "2025"
category_path:
  - "Release notes"
  - "DP3"
  - "2025"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-10-01T12:17:42.308Z"
modified_at: "2025-10-07T09:55:03.647Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-doxee-platform-3-48-0-4"
synced_at: "2026-01-28T20:39:33.356Z"
checksum: "615a84979b2e2e2d"
---

This section contains the full changelog of **Doxee Platform&reg;**** release 3.48.0.4**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 3.48.0.4
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- No epics were released

- [3.48.0.4 problems](https://infinica.atlassian.net/secure/IssueNavigator.jspa?reset=true&amp;jqlQuery=fixVersion+%3D+3.48.0.4+AND+%28issuetype+In+%28%22SLS%22%2C+%22Problem%22%29+or+%28issuetype+in+%28%22Epic%22%29+and+%22T%26R+Change+Type%22+in%28+%22Problem%22%2C%22SLS%22%29%29+and+%28labels+%21%3D+%22rn%3Ainternal%22+or+labels+%3D+NULL%29+AND+status+NOT+IN+%28%22Rejected%22%29%29+ORDER+BY+issuekey+DESC)

### Digital Archiving
- **Fixed** an issue which occurred when creating or editing an index in the Digital Archiving Store configuration. Previously, the drop-down menu for selecting the index type would display fewer options than were actually available. The available slots are now correctly determined based on the [index type limits](/doxee-platform/docs/digital-archive-developer-guide-manage-indexes#adding-a-new-index). Indexes which are used multiple times across different document categories are now counted only once towards the limit.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}