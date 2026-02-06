---
id: "c43ad74b-c8a2-455a-a1a3-807855aab8fe"
title: "XML user store"
slug: "security-configuration-guide-6-6-xml-user-store-1"
category: "Authentication mechanisms and user stores"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Authentication mechanisms and user stores"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:19.088Z"
modified_at: "2026-01-07T13:49:26.008Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-xml-user-store-1"
synced_at: "2026-01-28T20:40:11.813Z"
checksum: "23b630b461d27cf7"
---

The `xml` user store is a very simple file based user store, primarily intended for test and demo setups. Principals are defined in an XML file and read from there during application startup. Principal data cannot be changed without restarting the application.

`&lt;xml&gt;
  &lt;source&gt;users.xml&lt;/source&gt; &lt;!--1--&gt;
&lt;/xml&gt;`The only configuration option is the `&lt;source&gt;` element [1] which defines the relative URL to the XML file containing the principals. The principals file looks like this:

`&lt;principals xmlns="http://www.infinica.com/"&gt;
  &lt;user &lt;!--1--&gt;
      id="user1" &lt;!--2--&gt;
      loginName="user1" &lt;!--3--&gt;
      displayName="..." &lt;!--4--&gt;
      password="..." &lt;!--5--&gt;
      attr1="..." &lt;!--6--&gt;
      attr2="...&gt;
    &lt;group&gt;group1&lt;/group&gt; &lt;!--7--&gt;
    ...
  &lt;/user&gt;
  ...

  &lt;group &lt;!--8--&gt;
      id="group1"&gt;
    &lt;group&gt;group2&lt;/group&gt;
    ...
  &lt;/group&gt;

  &lt;group id="group2" /&gt; &lt;--9--&gt;
  ...
&lt;/principals&gt;`Any number of `&lt;user&gt;` [1] and `&lt;group&gt;` [8] elements may be specified to define the principals.

Each principal can have attributes. Standard attributes include the ID [2], a login name [3], a display name [4] and (only relevant for users) a password [5]. Arbitrary custom attributes may be specified as well [6].

Each user and group can be assigned as a member of another group by including a `&lt;group&gt;` element containing the ID of the parent group [8].

In the above example, the user `user` [1] is a member of the group `group1` [8], which in turn is a member of the group `group2` [9].

If a principal does not define a login name, its ID doubles as its login name. If a principal does not define a display name, its login name is used as the display name.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}