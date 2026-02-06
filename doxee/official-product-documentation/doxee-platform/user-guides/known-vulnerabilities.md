---
id: "25d16f8e-094d-43bf-8725-f0c191dd9b59"
title: "Known vulnerabilities"
slug: "known-vulnerabilities"
category: "Product guides"
category_path:
  - "Product guides"
status: "published"
content_type: "block"
version: 3
public_version: 3
created_at: "2025-08-13T13:16:10.499Z"
modified_at: "2025-08-25T13:08:17.612Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/known-vulnerabilities"
synced_at: "2026-01-28T20:40:07.455Z"
checksum: "2e3aca8df478d5dc"
---

Doxee Platform&reg; relies on third-party libraries to deliver core functionality. These dependencies can introduce security risks when a library becomes outdated. Whenever such a vulnerability is identified, a fix is implemented as soon as possible. However, this may not be possible in individual cases, for example due to legacy system requirements.

Below is a curated list of known vulnerabilities in libraries used by Doxee Platform&reg; or its individual components, including severity ratings, affected versions, and mitigation steps (if applicable).

> Internal documentation

This is an internal document. By default, its visibility is restricted for external users. It may be shared on an as-needed basis.

## Known vulnerabilities in 6.5 SP2
The following third-party libraries are used by one or more Doxee Platform&reg; components and have been identified as vulnerable.

Library

Vulnerable versions

Fix available

Vulnerability ID

Severity

Affected components

Description

commons-lang

2.6

No

GHSA-j288-q9x7-2f5v

Medium

Composer 1

Workplace 1

The module PE-json-lang has a dependency on commons-lang through json-lib. json-lib is a deprecated library.

## Duplicate libraries in 6.5 SP2
The following third-party libraries are present in one or more entries across various Doxee Platform&reg; components, typically due to legacy system requirements. Only the vulnerable library versions are given in this table.

Library

Vulnerable versions

Fix available

Vulnerability ID

Severity

Affected components

Description

fontbox

3.0.3

Yes

NA

NA

Composer 1

Composer NG

NA

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}