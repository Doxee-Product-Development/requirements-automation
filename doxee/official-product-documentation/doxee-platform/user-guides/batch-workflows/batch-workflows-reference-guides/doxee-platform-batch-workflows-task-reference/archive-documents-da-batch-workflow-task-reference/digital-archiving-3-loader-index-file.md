---
id: "88406ea5-02e0-43fa-b6a5-fc59f3f69019"
title: "Digital Archiving 3 Loader Index File"
slug: "digital-archiving-3-loader-index-file"
category: "Archive Documents (DA) Batch Workflow Task Reference"
category_path:
  - "Product guides"
  - "Batch Workflows"
  - "Batch Workflows Reference Guides"
  - "Doxee Platform Batch Workflows Task Reference"
  - "Archive Documents (DA) Batch Workflow Task Reference"
status: "published"
content_type: "block"
version: 5
public_version: 5
created_at: "2025-12-08T08:06:40.134Z"
modified_at: "2026-01-19T14:19:05.637Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/digital-archiving-3-loader-index-file"
synced_at: "2026-01-28T20:49:10.312Z"
checksum: "7550c7c8e98e2d3c"
---

## Introduction
There are different modes to invoke the DA3 Loader:

- **Upload mode**

Upload document without attachments

- Upload document with attachments

- **Update mode**

Update metadata

- Update file

- Update attachments

The input package contains the following files, depending on the selected mode:

**DA3 Mode**

**Index file**

**Document files**

**Assets package**

**Upload document without attachments**

X

X

**Upload document without attachments**

X

X

X

**Update metadata**

X

**Update file**

X

X

**Update attachments**

X

X

> Important

The index file is mandatory in all cases.

## Index structure
### Upload mode
#### Sections
The DA3 index file includes the following sections:

**Section**

**Description**

**Mandatory**

**Count**

**//documents**

Root element for the upload mode

X

1

**//documents/document**

Section that identifies a single document

X

1...n

**//documents/document/indexes**

Section that contains custom indexes

X

1

**//documents/document/indexes/index**

Section that identifies a custom index

X

1...n

**//documents/document/purl**

Section that identifies the parameters for public documents

1

**//documents/attachment**

Section that identifies assets packages

1

#### Fields
The DA3 index file includes the following fields:

**Field**

**Description**

**Mandatory**

**Length**

**//documents/@lotId**

Segment identifier

1...40

**//documents/@scope**

Production environment

1...40

**//documents/@useCase**

Production application

1...40

**//documents/document/@id**

Document identifier

> Important

It must be unique within the segment.

**//documents/document/@shipmentId**

Shipment identifier

1...40

**//documents/document/@classCode**

Document class

X

**//documents/document/@title**

Document title

X

1...255

**//documents/document/@file**

Document filename

X

1.255

**//documents/document/@attachment**

Assets package indicator

true / false

**//documents/document/@attachedToId**

Assets package reference

**//documents/document/@hash**

Assets package hash (only for assets)

**//documents/document**

**/@pvpAdditionalData**

Pvideo player properties

**//documents/attachment/@id**

Assets package identifier

**//documents/document/@file**

Assets package file

**//documents/document/@hash**

Assets package hash

**//documents/document**

**/@pvpAdditionalData**

Pvideo player properties

**//documents/document/indexes/index**

**/@code**

Index identifier

X

**//documents/document/indexes/index**

**/@value**

Index value

> Note

If the index is of date type, the requested format is "YYYY-MM-DD".

X

**//documents/document/purl/@type**

pURL access:

- (direct)

- (indirect)

> Deprecated field

This field is deprecated.

> Document Composition

It is mandatory to fill this field in the Document Composition application; however, the system will ignore the input.

**//documents/document/purl/@hostName**

pURL host

> Deprecated field

This field is deprecated.

> Document Composition

It is mandatory to fill this field in the Document Composition application; however, the system will ignore the input.

**//documents/document/purl/@docGuid**

pURL identifier (only for direct)

### Update mode
#### Sections
The DA3 index file includes the following sections:

**Section**

**Description**

**Mandatory**

**Count**

**//documents_update**

Root element for the update mode

X

1

**//documents_update/document_update**

Section that identifies a single search query for metadata update

X

1...n

**//documents_update/document_update/indexes_update**

Section that contains the search parameters and fields to be updated

X

(to update metadata and pURL parameters)

1

**//documents_update/document_update/indexes_update/index_param**

Section that identifies a custom index to search the document

X

(to update metadata and pURL parameters)

**//documents_update/document_update/indexes_update/index_update**

Section that identifies a custom index to be updated

X

(to update the metadata)

**//documents_update/document_update/indexes_update/purl_provider_update**

Section that identifies a system index related to the pURL metadata to be updated

X

(to update pURL parameters)

**//documents_update/document_update/file_update**

Section that contains the search parameters and the file to be updated

X

(to update a file)

**//documents_update/document_update/file_update/index_param**

Section that identifies a custom index to search the document

X

(to update a file)

**//documents_update/document_update/file_update/file_update**

Section that identifies a file to be updated

X

(to update the file)

**//documents_update/document_update/attachment_update**

Section that contains the search parameters and attachment to be updated

X

(to update attachments)

**//documents_update/document_update/attachment_update/index_param**

Section that identifies a custom index to search the document

X

(to update attachments)

1...n

**//documents_update/document_update/attachment_update/attachment_update**

Section that identifies an attachment to be updated

X

(to update attachments)

1...n

#### Fields
The DA3 index file includes the following fields:

**Field**

**Description**

**Mandatory**

**//documents_update/document_update/@id**

Document identifier

**//documents_update/document_update/@lotd**

Segment identifier

**//documents_update/document_update/@classCode**

Document class

X

**//documents_update/document_update/@shipmentId**

Shipment identifier

**//documents_update/document_update**

**/indexes_update|file_update|attachment_update/index_param/@code**

Index identifier

**//documents_update/document_update**

**/indexes_update|file_update|attachment_update/index_param/@value**

Index value to search for

**//documents_update/document_update**

**/indexes_update|file_update|attachment_update/index_param/@operator**

The available operators are:

- =

- ! =

- &gt; (to be encoded as *&amp;gt;*)

- &lt; (to be encoded as *&amp;lt;*)

- &gt;= (to be encoded as *&amp;gt;=*)

- &lt;= (to be encoded as *&amp;lt;=*)

> Note

If no operator is specified, the default operator "=" is used.

The operators &lt;, &lt;=, &gt;, &gt;= are only applicable to number, date and time data types.

**//documents_update/document_update/indexes_update**

**/index_update/@code**

Index identifier

X

**//documents_update/document_update/indexes_update/index_update/@value**

Index value to update with

X

**//documents_update/document_update/indexes_update/purl_provider_update/@code**

pURL parameter

The available options are:

**ATTACHMENT_KEY DEVICE_TARGET_TYPE DOC_GUID HOST_NAME NUM_VIEWS_ALLOWED TTL**

**TYPE**

**//documents_update/document_update/indexes_update/purl_provider_update/@value**

pURL parameter to update

**//documents_update/document_update/file_update/file_update/@file**

Relative path to the file to update

**//documents_update/document_update/attachment_update/attachment_update/@file**

Relative path to the attachment to update

**//documents_update/document_update/attachment_update/attachment_update/@id**

Assets package identifier

**//documents_update/document_update/attachment_update/attachment_update/@hash**

Assets package hash

**//documents_update/document_update/attachment_update/attachment_update/@pvpAdditionalData**

Pvideo player properties related to the new assets package

> Important

The index file with the **documents_update **root tag may contain only one type of update queries.

> Note

For the file update and attachment update modes, it is possible to update only a single document using a single **document_update **query. If more than one documents are found by the search criteria, an error is returned.

> **Compatibility Considerations**

The DA3 Loader must ignore [XML Namespaces](https://www.w3schools.com/xml/xml_namespaces.asp) in the index file for backward compatibility.

## Examples
### Uploading documents
**Example: Index file to upload documents**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;documents lotId="0000000001093658" scope="TEST" useCase="BATCH"&gt;
&lt;document id="1" classCode="Invoices" title="Invoice XXYYZZ" file="Invoice_XXYYZZ.pdf" attachment="false" shipmentId=" 5477d0d14a97a71b4b1badbabbf4c6f922c"&gt;
&lt;indexes&gt;
&lt;index code="INVOICE_NUMBER" value="AS0001" /&gt;
&lt;index code="CUSTOMER_CODE" value="SA0001" /&gt;
&lt;index code="ISSUE_DATE" value="2017-12-11" /&gt;
&lt;/indexes&gt;
&lt;/document&gt;
&lt;/documents&gt;`### **Uploading documents with attachments**
There are two ways to load documents with an assets package (i.e. attachments):

- the assets package is identified by the **&lt;document&gt; **element

- the assets package is identified by the **&lt;attachment&gt; **element

**Example 1: Index File to upload documents with an assets package (using the document element)**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;documents
    lotId="0000000000534068"
    scope="TEST"
    useCase="BATCH"&gt;
  &lt;document id="1" classCode="Video" title="assets.zip" file="assets_93400/assets.zip" attachment="true" hash="e7fb5c98882b7635b31c25750736b6cc516d01481f5663277d066bb4363a3a96" shipmentId="0000000000534068" /&gt;
  &lt;document id="2" classCode="Video" title="pvideo_c45009e9df5740dfa4a62415be7bb56e" file="pvideo_c45009e9df5740dfa4a62415be7bb56e.html" attachment="false" attachedToId="1" shipmentId="0000000000534068"&gt;
    &lt;indexes&gt;
      &lt;index code="firstName" value="John" /&gt;
      &lt;index code="lastName" value="Doe" /&gt;
      &lt;index code="activationDate" value="2016-12-16" /&gt;
    &lt;/indexes&gt;
    &lt;pURL type="0" hostName="https://media-cert.doxee.com" docGuid="c45009e9df5740dfa4a62415be7bb56e" /&gt;
  &lt;/document&gt;
&lt;/documents&gt;`**Example 2: Index File to upload documents with an assets package (using the attachment element)**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;documents lotId="0000100067985123" scope="PRODUCTION" useCase="BATCH" &gt;
    &lt;attachment id="1" file="asset_549185/attachments.zip" hash="67761c00cccee3cdf1caff32a603708e88f9d36726f4fba7451bfed4817cfe3c" pvpAdditionalData="eyBwdnBWZXJzaW9uIDogIjIuMTMuMy4wIiwgdHRzVmVyc2lvbiA6ICIyLjEzLjMuMCIsIHB2cENkbkhvc3RuYW1lIDogImh0dHBzOi8vcHZpZGVvLXBsYXllci5kb3hlZS5jb20vIiwgdHRzQ2RuSG9zdG5hbWUgOiAiaHR0cHM6Ly9wdmlkZW8tcGxheWVyLmRveGVlLmNvbS8iLAlwdnBCYXNlUGF0aCA6ICJyZWxlYXNlLyIsIHR0c0Jhc2VQYXRoIDogInJlbGVhc2UvIiwgcHZwQnVpbGRJZCA6ICIiLCB0dHNCdWlsZElkIDogIiIgfQ==" /&gt;
    &lt;document id="2" classCode="GENERIC_CLASS" title="pVideo" file="Video_ffb54504a8b64ac58e0902ab64eefdbc.html" attachment="false" attachedToId="1" shipmentId="ffb54504a8b64ac58e0902ab64eefdbc" &gt;
        &lt;indexes&gt;
            &lt;index code="firstName" value="XXX"/&gt;
        &lt;/indexes&gt;
        &lt;pURL type="0" hostName="https://test11.dev.doxee.com" docGuid="asb54504a8b64ac58e0902ab64ee1006" deviceTargetType="0" /&gt;
    &lt;/document&gt;
    &lt;document id="3" classCode="GENERIC_CLASS" title="pVideo" file="Video_9762aabf11a345afbbd1c174226723ce.html" attachment="false" attachedToId="1" shipmentId="9762aabf11a345afbbd1c174226723ce" &gt;
        &lt;indexes&gt;
            &lt;index code="firstName" value="YYY"/&gt;
        &lt;/indexes&gt;
        &lt;pURL type="0" hostName="https://test11.dev.doxee.com" docGuid="as62aabf11a345afbbd1c1742262007" deviceTargetType="0" /&gt;
    &lt;/document&gt;
    &lt;document id="4" classCode="GENERIC_CLASS" title="pVideo" file="Video_6be11cb103594d839acb5e08d11ac1d9.html" attachment="false" attachedToId="1" shipmentId="6be11cb103594d839acb5e08d11ac1d9" &gt;
        &lt;indexes&gt;
            &lt;index code="firstName" value="ZZZ"/&gt;
        &lt;/indexes&gt;
        &lt;pURL type="0" hostName="https://test11.dev.doxee.com" docGuid="ase11cb103594d839acb5e08d130008" deviceTargetType="0" /&gt;
    &lt;/document&gt;
&lt;/documents&gt;`### **Updating metadata**
**Example: Index file to update metadata**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;documents_update&gt;
    &lt;document_update id="1" classCode="document_class" lotId="0001" shipmentId=""&gt;
        &lt;indexes_update&gt;
            &lt;index_param code="CUSTOMER_CODE" value="AB0001" operator="="/&gt;
            &lt;index_param code="ISSUE_DATE" value="2019-10-30" operator="&amp;gt;"/&gt;         
            &lt;index_update code="EMAIL" value="change@me.com"/&gt;
        &lt;/indexes_update&gt;
    &lt;/document_update&gt;
&lt;/documents_update&gt;`### **Updating pURL metadata**
**Example: Index file to update pURL metadata**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;documents_update&gt;
    &lt;document_update id="1" classCode="document_class" lotId="0001" shipmentId=""&gt;
        &lt;indexes_update&gt;
            &lt;index_param code="SEGMENT" value="AAA" /&gt;
            &lt;index_param code="INVOICE_NUM" value="0123456" /&gt;
            &lt;index_param code="ISSUE_DATE" value="2017-10-30"/&gt;
            &lt;purl_provider_update code="TYPE" value="1"/&gt;
            &lt;purl_provider_update code="DEVICE_TARGET_TYPE" value="0"/&gt;
            &lt;purl_provider_update code="HOST_NAME" value="https://platform.doxee.com"/&gt;
            &lt;purl_provider_update code="DOC_GUID" value="03oejfrt657q2pfb389olmn34yu7i891"/&gt; 
        &lt;/indexes_update&gt;
    &lt;/document_update&gt;
&lt;/documents_update&gt;`### Updating the file
**Example: Index file to update the file**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;documents_update&gt;
    &lt;document_update id="1" class="Invoices"&gt;
        &lt;file_update&gt;
            &lt;index_param code="DOXEE_ID" value="BP-JOB-SEGMENT-1"/&gt;
            &lt;file_update file="document.pdf"/&gt;
        &lt;/file_update&gt;
    &lt;/document_update&gt;
&lt;/documents_update&gt;`### **Updating the assets package**
**Example: Index file to update the assets package**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;documents_update&gt;
    &lt;document_update id="1" class="Invoices"&gt;
        &lt;attachment_update&gt;
            &lt;index_param code="DOXEE_ID" value="BP-JOB-SEGMENT-1"/&gt;
            &lt;attachment_update id="ATTACHMENT_ID" file="attachment.zip" hash="HASH" pvpAdditionalData="DATA"/&gt;
        &lt;/attachment_update&gt;
    &lt;/document_update&gt;
&lt;/documents_update&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}