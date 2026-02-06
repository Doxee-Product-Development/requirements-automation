---
id: "119ae1e5-eca6-4e00-a2c0-9932dbe94d46"
title: "Doxee Platform 3.48.0.1 - September 24, 2025"
slug: "release-notes-doxee-platform-3-48-0-1"
category: "2025"
category_path:
  - "Release notes"
  - "DP3"
  - "2025"
status: "published"
content_type: "block"
version: 4
public_version: 4
created_at: "2025-09-25T07:41:42.678Z"
modified_at: "2025-10-07T09:55:28.855Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-doxee-platform-3-48-0-1"
synced_at: "2026-01-28T20:39:34.614Z"
checksum: "78800a0acbd9354a"
---

This section contains the full changelog of **Doxee Platform&reg;**** release 3.48.0.1**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 3.48.0.1
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- No epics were released

- [3.48.0.1 problems](https://infinica.atlassian.net/issues/?jql=fixVersion%20%3D%203.48.0.1%20AND%20%28issuetype%20In%20%28%22SLS%22%2C%20%22Problem%22%29%20or%20%28issuetype%20in%20%28%22Epic%22%29%20and%20%22T%26R%20Change%20Type%22%20in%28%20%22Problem%22%2C%22SLS%22%29%29%20and%20%28labels%20%21%3D%20%22rn%3Ainternal%22%20or%20labels%20%3D%20NULL%29%20AND%20status%20NOT%20IN%20%28%22Rejected%22%29%29%20ORDER%20BY%20issuekey%20DESC%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20)

### On-Demand Production
- **Fixed** a regression bug introduced with release 3.48. Due to this issue, On-Demand jobs related to workflows released before 3.48 weren’t working. A rollback was necessary to resolve the problem.

### Pvideo
- **Fixed** an issue that caused the Publish Documents (Pvideo) Batch and On-Demand tasks to ignore attachments coming from the input file. This issue was caused by missing properties for attachments in the input mapping class. Fixing the mapping restored the correct behavior.

### Pweb
- **Fixed** an issue that caused the Publish Documents (Pweb) Batch and On-Demand tasks to ignore attachments coming from the input file. This issue was caused by missing properties for attachments in the input mapping class. Fixing the mapping restored the correct behavior.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}