---
id: "a03ff51f-bdff-45f2-9f1d-e81699b0c2e3"
title: "Apache FOP 2.8, 2.9+"
slug: "third-party-integration-guide-6-6-apache-fop"
category: "Third-party integration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Third-party integration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-04T14:03:28.785Z"
modified_at: "2025-12-04T14:04:25.909Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/third-party-integration-guide-6-6-apache-fop"
synced_at: "2026-01-28T21:04:57.675Z"
checksum: "f83e10075399137f"
---

When utilizing Apache FOP for document rendering, such as through the use of the fopRenderer Process Engine activity, it is important to note that with Apache FOP version 2.8 and higher, there have been changes in the way certain PNG images are embedded. These changes may result in discrepancies compared to earlier versions, and could potentially cause errors when opening the PDF in a viewer.

To revert back to the previous behavior, it is necessary to add the following settings to the root level of the FOP configuration file.

`&lt;image-loading&gt;
	&lt;penalty value="2000" class="org.apache.xmlgraphics.image.loader.impl.PreloaderRawPNG"/&gt;
	&lt;penalty value="2000" class="org.apache.xmlgraphics.image.loader.impl.ImageLoaderRawPNG"/&gt;
&lt;/image-loading&gt;`It is currently unclear whether future versions of Apache FOP will return to the previous default behavior or not.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}