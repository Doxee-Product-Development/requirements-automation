---
id: "307e8b42-fee7-4939-b3c4-241b43739b90"
title: "Doxee Platform 3.48.0.6 - October 22, 2025"
slug: "doxee-platform-34806"
category: "2025"
category_path:
  - "Release notes"
  - "DP3"
  - "2025"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-01T09:10:02.045Z"
modified_at: "2025-12-02T17:21:36.713Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/doxee-platform-34806"
synced_at: "2026-01-28T20:39:32.536Z"
checksum: "11603892565ac818"
---

This section contains the full changelog of **Doxee Platform&reg;**** release 3.48.0.6**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 3.48.0.6
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- No epics were released

- [3.48.0.6 problems](https://infinica.atlassian.net/secure/IssueNavigator.jspa?reset=true&amp;jqlQuery=fixVersion+%3D+3.48.0.6+AND+%28issuetype+In+%28%22SLS%22%2C+%22Problem%22%29+or+%28issuetype+in+%28%22Epic%22%29+and+%22T%26R+Change+Type%22+in%28+%22Problem%22%2C%22SLS%22%29%29+and+%28labels+%21%3D+%22rn%3Ainternal%22+or+labels+%3D+NULL%29+AND+status+NOT+IN+%28%22Rejected%22%29%29+ORDER+BY+issuekey+DESC)

### Pvideo
- **Added **analytics tracking for Pvideos generated through the Babelee interface.

- **Improved **performance by adding request caching.

- **Fixed:** Pvideo GUIDs weren’t being passed on properly to workflow branches containing Send Email and Send SMS tasks. This issue occurred when the workflow also contained a Transform Files (DT) task, which would generate its own GUID and pass it on instead of the correct Pvideo GUID.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}