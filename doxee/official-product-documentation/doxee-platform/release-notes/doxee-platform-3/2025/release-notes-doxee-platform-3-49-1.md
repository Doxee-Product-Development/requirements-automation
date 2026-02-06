---
id: "bb5be52f-4b3d-4161-8ac0-ccd944f17a9f"
title: "Doxee Platform 3.49.1 - December 1, 2025"
slug: "release-notes-doxee-platform-3-49-1"
category: "2025"
category_path:
  - "Release notes"
  - "DP3"
  - "2025"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-01T09:07:58.883Z"
modified_at: "2025-12-01T16:53:30.645Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-doxee-platform-3-49-1"
synced_at: "2026-01-28T20:39:31.218Z"
checksum: "cbf9e33050d5d765"
---

This section contains the full changelog of **Doxee Platform&reg; release 3.49.1**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 3.49.1
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- [3.49.1 epics](https://infinica.atlassian.net/secure/IssueNavigator.jspa?reset=true&amp;jqlQuery=fixVersion+%3D+3.49.1.0+and+issueType%3D%22Epic%22+and+%22T%26R+Change+Type%22+Not+in+%28%22Development%22%2C%22Problem%22%2C%22SLS%22%29+and+%28labels+%21%3D+%22rn%3Ainternal%22+or+labels+%3D+NULL%29+and+status+NOT+IN+%28%22Rejected%22%29)

- No problems were released

### Output Management
- **Added** the option to [simplify the XML structure](https://code.doxee.com/confluence/display/DX/Accessibility+Structure+Simplification) of accessibility tags in Intermediate Format before the data is sent to FOP. This helps reduce memory usage during the execution. The new flag *Simplify tag structure* is available under the PDF options of the Target.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}