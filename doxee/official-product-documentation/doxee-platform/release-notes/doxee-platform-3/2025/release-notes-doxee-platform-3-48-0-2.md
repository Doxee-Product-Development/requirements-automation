---
id: "3206329a-e653-47f9-b358-6510192248fc"
title: "Doxee Platform 3.48.0.2 - October 19, 2025"
slug: "release-notes-doxee-platform-3-48-0-2"
category: "2025"
category_path:
  - "Release notes"
  - "DP3"
  - "2025"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-01T12:08:35.584Z"
modified_at: "2025-10-20T10:04:19.387Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-doxee-platform-3-48-0-2"
synced_at: "2026-01-28T20:39:34.187Z"
checksum: "10481c1eac4adbe8"
---

This section contains the full changelog of **Doxee Platform&reg;**** release 3.48.0.2**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 3.48.0.2
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- No epics were released

- [3.48.0.2 problems](https://infinica.atlassian.net/secure/IssueNavigator.jspa?reset=true&amp;jqlQuery=fixVersion+%3D+3.48.0.2+AND+%28issuetype+In+%28%22SLS%22%2C+%22Problem%22%29+or+%28issuetype+in+%28%22Epic%22%29+and+%22T%26R+Change+Type%22+in%28+%22Problem%22%2C%22SLS%22%29%29+and+%28labels+%21%3D+%22rn%3Ainternal%22+or+labels+%3D+NULL%29+AND+status+NOT+IN+%28%22Rejected%22%29%29+ORDER+BY+issuekey+DESC)

### Batch Production
- **Fixed **an issue that caused resumed jobs to fail very quickly.

- **Fixed** an issue due to which the new status “Production without Outcome” was not working properly. The status logic now behaves as expected:

If a step has failed, then the status is “Production interrupted” as before.

- If the production is completed without delivery but with other terminal components, for example stores, then the status is “Delivery not required” as before.

- If the production is completed without delivery and without other terminal components, for example stores, then the status is “Production without Outcome”.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}