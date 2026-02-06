---
id: "9c0b2139-ba04-4324-8947-627d836ea912"
title: "Doxee Platform 3.49.1.1 - January 7, 2026"
slug: "release-notes-doxee-platform-3-49-1-1"
category: "2026"
category_path:
  - "Release notes"
  - "DP3"
  - "2026"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2026-01-08T13:54:13.059Z"
modified_at: "2026-01-08T15:14:38.757Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-doxee-platform-3-49-1-1"
synced_at: "2026-01-28T20:39:30.806Z"
checksum: "40867f8d139fc3ab"
---

This section contains the full changelog of **Doxee Platform&reg;**** release 3.49.1.1**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 3.49.1.1
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- No epics were released

- [3.49.1.1 problems](https://infinica.atlassian.net/secure/IssueNavigator.jspa?reset=true&amp;jqlQuery=fixVersion+%3D+3.49.1.1+AND+%28issuetype+In+%28%22SLS%22%2C+%22Problem%22%29+or+%28issuetype+in+%28%22Epic%22%29+and+%22T%26R+Change+Type%22+in%28+%22Problem%22%2C%22SLS%22%29%29+and+%28labels+%21%3D+%22rn%3Ainternal%22+or+labels+%3D+NULL%29+AND+status+NOT+IN+%28%22Rejected%22%29%29+ORDER+BY+issuekey+DESC)

### Batch Production
- **Fixed **an issue with the Send Emails Batch Workflows task. This issue occurred with scheduled emails with attachments using email template bundles. The task would populate the field `ATTACHMENTS` with the absolute path to the attached file, causing the dispatcher to fail because it expected the files to be located in the work directory `bp3-outbound`.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}