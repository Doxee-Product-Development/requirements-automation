---
id: "8d3738b3-23ea-4d30-a852-246040df9f12"
title: "application/json"
slug: "6-6-process-engine-manpages-xpathfunctions-applicationjson-1"
category: "Types"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Types"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:07.222Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-xpathfunctions-applicationjson-1"
synced_at: "2026-01-28T20:57:20.374Z"
checksum: "d964b470978ef517"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(Module: [JSON Support](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-json-support-1))

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