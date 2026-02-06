---
id: "7bea2b04-ae59-4ebe-a68d-70a600cebf74"
title: "application/json"
slug: "6-6-process-engine-manpages-xpathfunctions-applicationjson"
category: "Types"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Types"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T16:03:24.392Z"
modified_at: "2025-08-22T17:34:19.966Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-applicationjson"
synced_at: "2026-01-28T21:03:39.675Z"
checksum: "601e23737a1ba69c"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(Module: [JSON Support](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-json-support))

JSON documents. Conversions to and from XML are supported.

**Parameters:**

- **allowTrailingComma**

boolean value specifying whether JSON strings which contain trailing commas are allowed tobe parsed. Only relevant when converting from text/plain to application/json type. If this is false, converting a string with a trailing comma will throw an exception. Default is `false`.

- **includeElementNames**

boolean value specifying whether the names of XML elements should be preserved whenconverting an XML into JSON. Default is `true`.

- **withNamespaces**

boolean value specifying whether XML namespaces should be preserved when converting betweenXML and JSON. Relevant when converting from text/xml to application/json or the other way around, if the JSON has been previously created from an XML. Default is `true`.

- **valuesAsAttributes**

boolean value specifying whether JSON value fields should be transformed to XML attributeswhen converting from JSON to XML. If this is `true`, the type information from the JSON will be lost and the value is treated as a string. When set to `false`, the JSON field will be transformed into an XML element with the field value as content and the field type as an attribute. This element will have a separate namespace (http://www.infinica.com/json) so it can be identified in case of being transformed back into JSON. Default is `true`.

- **useConversionNamespace**

boolean value specifying whether the XML namespace `http://www.infinica.com/json` should be applied to value elements (when values are converted to elements rather than attributes, see `valuesAsAttributes` above). When converting from application/json to text/xml and back, setting this namespace ensures lossless conversion. In case you only need conversion in one direction, you may want to switch this feature off for simpler XMLs. Default is `true`.

- **defaultRootName**

The name which should be given to the XML root element when converting from JSON to XML, in case there is none. Defaults to `root`

- **defaultArrayItemName**

The name which should be given to XML elements created from the objects in a JSON array when converting from JSON to XML. Defaults to `item`

**Conversions:**

application/json → text/plain 

text/plain → application/json 

application/json → text/xml

 text/xml → application/json 

x-infinica/stream → text/plain → application/json 

application/json → text/plain → x-infinica/stream 

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}