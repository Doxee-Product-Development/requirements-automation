---
id: "777cca88-ff17-4a4e-82ce-c19395ec3614"
title: "List Element"
slug: "composer-6-6-list-element"
category: "Document elements"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Composer"
  - "Document elements"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-25T15:40:35.726Z"
modified_at: "2025-11-13T12:14:55.352Z"
authors:
  - name: "Davide Daccico"
    email: "ddaccico@doxee.com"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/composer-6-6-list-element"
synced_at: "2026-01-28T21:00:40.372Z"
checksum: "f750902e7437d32a"
---

Navigate to other release versions of Doxee Platform Composer

[6.6](https://docs.doxee.com/docs/en/composer-6-6)

[6.7](https://docs.doxee.com/docs/en/composer-6-7)

The Composer provides a rich choice of list types, these are basically divided into numbered and bulleted lists ![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAVCAIAAADTi7lxAAAAVklEQVQ4EWP4QyXAQCVz/gx+g1avXr1mzRoy/Ivutc2bN2/btu3Pnz+3bt3agQNgtQbdIKyKiBGkmUGjYYQZ/OiBPRpGhMMIUwWRIuiBTaQ2TGXD2CAAjHmxqn+ScbgAAAAASUVORK5CYII=). These can be inserted with a simple click on the single list icon in floating toolbar, ctx menu or right panel either in a freely editable region or an existing editable text can be replaced by list. In the latter case, select the corresponding text portion and choose list floating-toolbar button. After this the selected passage is converted to a list item.

> An existing list type can NOT be changed into the other types in the current version of the Composer.

Lists are automatically continued upon creation of a new paragraph. If you want this continuation stopped, press the return key to create new list item and then remove the list by clicking the button. Result is a normal new paragraph.

> If you want an empty line between two list items then this is currently NOT possible. Shift+Enter (soft break) is currently NOT supported.

In the following sections the settings of both list types are explained in detail.

## Properties of lists
> List properties are NOT supported in the current version of the Composer.

> The Composer is able to show all list types and configurations as set up in the original template but not capable to change/configure these.

List can be set up as a numbered or as bulleted lists in the original template. In a numbered list every new paragraph receives a sequential number. Document templates allow designers to define both the start index, as well as the kind of numbering.

The Composer supports following list properties as set up in the template:

- Start Index

sets the starting index, which normally is 1.

- List type

allows choosing the number scheme, currently the following are available:

Decimal (1, 2, 3, etc.)

- Upper Alphabetic (A, B, C, D, E, etc.)

- Lower Alphabetic (a, b, c, d, e, etc.)

- Upper Roman (I, II, III, IV, V, etc.)

- Lower Roman (i, ii, iii, iv, v, etc.) 

Bulleted list options:

- circle ❍

- disc •

- square 

- Not set

Prefix and suffix of the list bullet or number are also supported when configured in the template. It is recommended to use only short one-character prefixes and suffixes to avoid conflicts.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}