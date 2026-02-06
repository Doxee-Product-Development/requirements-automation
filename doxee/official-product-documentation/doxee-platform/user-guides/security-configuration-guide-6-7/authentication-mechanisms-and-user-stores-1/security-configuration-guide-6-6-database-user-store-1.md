---
id: "f1b76bf6-e83c-49e4-9895-934792b5786c"
title: "Database user store"
slug: "security-configuration-guide-6-6-database-user-store-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:19.157Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-database-user-store-1"
synced_at: "2026-01-28T20:40:12.201Z"
checksum: "77ffdc4ef1ec0707"
---

The `database` user store keeps its principals in an SQL database. The database structure is created automatically if it does not yet exist on the server. The User Management application can be used to administrate the users and groups stored in the database.

`&lt;database&gt;
  &lt;connection&gt; &lt;!--1--&gt;
    ...
  &lt;/connection&gt;

  &lt;attribute name="..."&gt;...&lt;/attribute&gt; &lt;!--2--&gt;

  &lt;users&gt; &lt;!--3--&gt;
    &lt;attribute name="..."&gt;...&lt;/attribute&gt;
    ...
    &lt;passwordAttribute&gt;...&lt;/passwordAttribute&gt; &lt;!--4--&gt;
  &lt;/users&gt;

  &lt;groups&gt; &lt;!--5--&gt;
    &lt;attribute name="..."&gt;...&lt;/attribute&gt;
  &lt;/groups&gt;
&lt;/database&gt;`The database connection is configured in the `&lt;connection&gt;` element [1] using Java Hibernate properties. A typical configuration looks like this:

`&lt;connection&gt;
  &lt;hibernate.connection.url&gt;...&lt;/hibernate.connection.url&gt;
  &lt;hibernate.connection.driver_class&gt;...&lt;/hibernate.connection.driver_class&gt;
  &lt;hibernate.connection.username&gt;...&lt;/hibernate.connection.username&gt;
  &lt;hibernate.connection.password&gt;...&lt;/hibernate.connection.password&gt;
  &lt;hibernate.dialect&gt;...&lt;/hibernate.dialect&gt;
&lt;/connection&gt;`Like any user store configuration, attribute mappings for all principals may be configured using `&lt;attribute&gt;` elements [2].

Specific configurations may be defined for users [3] and groups [5]. For both of these, attribute mappings may be defined which are only used for the corresponding principal type. Additionally, the attribute which stores a user's password must be defined [4].

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}