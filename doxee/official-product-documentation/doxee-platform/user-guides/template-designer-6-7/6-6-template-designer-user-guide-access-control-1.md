---
id: "dfa132d3-510d-4e45-9ddb-1c1610d7588d"
title: "Access Control"
slug: "6-6-template-designer-user-guide-access-control-1"
category: "Template Designer"
category_path:
  - "Product guides"
  - "Template Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:38:39.547Z"
modified_at: "2026-01-07T14:16:25.689Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-template-designer-user-guide-access-control-1"
synced_at: "2026-01-28T20:58:39.421Z"
checksum: "c224c12efcdc1e29"
---

Navigate to other release versions of Doxee Platform Template Designer

[6.6](https://docs.doxee.com/docs/en/template-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/template-designer-6-7)

Access rights can be set for each element. There are two properties that define access rights:

- *editable-template *for *Business Designer *defaults to *true*

- *editable-document *(previously *editable*) for *Composer *defaults to *false*

> Note:

These properties have no effect on the behaviour of *Template Designer *itself, only on *Business Designer *and *Composer*.

In addition to the values *true *and *false*, access rights can be assigned by ID to principals such as users, groups, or roles.

Access rights on an element are added to the access rights that are inherited from the parent element (with one exception described below).

There are three modes of access right assignment:

- *grant*: Users that match any of the principals of a *grant *section are allowed to edit the element.

- *deny*: Users that match any of the principals of a *deny *section cannot edit the element. *deny *takes precedence over *grant*, so a user matching both groups still cannot edit.

- *only*: Only users that match any of the principals of an *only *section may edit the element, all others are denied write access, effectively breaking the inheritance from the parent element.

It does not make sense to combine *grant *and *only *sections in one setting. For both of them, there are legitimate use cases to combine them with *deny*.

## Examples
Here are some valid access control values:

- *grant:group:A,group:B*: Users from groups A and B can edit the element. For all other users, access rights are inherited from the parent element.

- *deny:user:X*: User X cannot edit the element. For all other users, access rights are inherited from the parent element.

- *grant:group:A,group:B deny:user:X*: Users from groups A and B can edit the element. User X cannot edit the element, even if user X is a member of group A or B. For all other users, access rights are inherited from the parent element.

- *only:group:A,group:B*: Users from groups A and B can edit the element. All other users cannot edit the element, regardless of access rights on the parent element.

- *only:group:A,group:B deny:user:X*: Users from groups A and B can edit the element. User X cannot edit the element, even if user X is a member of group A or B. All other users cannot edit the element, regardless of access rights on the parent element.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}