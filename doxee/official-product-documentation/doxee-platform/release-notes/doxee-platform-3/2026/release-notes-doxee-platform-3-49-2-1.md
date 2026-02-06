---
id: "b9f6a382-a41c-4249-a107-f150765dcf1a"
title: "Doxee Platform 3.49.2.1 - January 23, 2026"
slug: "release-notes-doxee-platform-3-49-2-1"
category: "2026"
category_path:
  - "Release notes"
  - "DP3"
  - "2026"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-26T09:15:57.014Z"
modified_at: "2026-01-26T10:34:25.446Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-doxee-platform-3-49-2-1"
synced_at: "2026-01-28T20:39:29.895Z"
checksum: "dbbb32383104a7a6"
---

This section contains the full changelog of **Doxee Platform&reg; release 3.49.2.1**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 3.49.2.1
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- No epics were released

- [3.49.2.1 problems](https://infinica.atlassian.net/secure/IssueNavigator.jspa?reset=true&amp;jqlQuery=fixVersion+%3D+3.49.2.1+AND+%28issuetype+In+%28%22SLS%22%2C+%22Problem%22%29+or+%28issuetype+in+%28%22Epic%22%29+and+%22T%26R+Change+Type%22+in%28+%22Problem%22%2C%22SLS%22%29%29+and+%28labels+%21%3D+%22rn%3Ainternal%22+or+labels+%3D+NULL%29+AND+status+NOT+IN+%28%22Rejected%22%29%29+ORDER+BY+issuekey+DESC)

### Cloud Analytics
- **Fixed** `doxee_platform_id` having different maximum character lengths across different Cloud Analytics tables. `doxee_platform_id` now supports 255 characters in both dp-message-publisher and ca-aws-infrastructure.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}