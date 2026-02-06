---
id: "4873ff5a-9863-4716-b904-aeba1b3a6ee9"
title: "Convert Template"
slug: "6-6-process-engine-manpages-activities-convert-template"
category: "Activities (A to R)"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (A to R)"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-13T10:39:36.072Z"
modified_at: "2025-08-22T17:31:46.465Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-convert-template"
synced_at: "2026-01-28T21:01:52.588Z"
checksum: "15ba1a3f66c31899"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(convertTemplate, Module: [Template Conversion](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-template-conversion)) 

Converts a template stream into a stream in the specified format.

**Input Parameters:**

- input (x-infinica/stream) (1-unbounded) 

Template input.

- aesKeyIn (application/octet-stream) (0-1)

Optional decryption key for reading the template(s) (currently only used for XHTML input).

- outputFormat (text/plain) (0-unbounded) 

Target format name or mimetype.

- infinicaResourcesPrefix (text/plain)

Prefix to use for links to external Infinica resources.

Default:

infinica://resources/

- emptyBlockContent (text/plain) (0-1)

Optional text to insert into empty blocks.

- outputConfig (text/plain) (0-1)

Optional name of the output configuration to use.

- onTheFly (x-xsd/boolean)

Optional flag to create xsl code for on-the-fly conversion (with modified xsl:include URLs).

Default:

false

- writeGuids (x-xsd/boolean)

Optional flag to write existing GUID attributes to the output (for ITX and IDX) or to create new GUIDs on the generated IDX for XSLIDX. Ignored for all other formats.

Default: 

true

- accessibilityProcessing (x-xsd/boolean)

Optional flag to process the accessibility attributes. Corresponds to the "Process accessibility attributes" option in Template Designer.

Default:

true

- keepEmptyBuildingBlocks (x-xsd/boolean) (0-1)

If true, Chosen Parts within an Insertion point will be kept even if they provide no content. Defaults to false.

- templateParts (text/plain) (0-unbounded)

If provided, only the listed Template Parts will be written to the output.

- templatePartParameters (text/plain) (0-unbounded)

The listed parameters will be added to the generated template as top-level XSL parameters.

- metaData (text/plain) (0-1)

Controls the behaviour regarding the XSL parameter '_infinica_metadata'. Valid values are: internal, include, dont-use; Defaults to internal.

- language (text/plain) (0-1)

If a language is provided, only the matching branch of each Language Switch element will be written to the output.

- variant (x-infinica/url) (0-1)

Generate XSL code for the specified variant.

- prettyPrint (x-xsd/boolean) (0-1)

If true, the output will be pretty-printed (with line breaks and XML indentations). If false, the resulting XML will be written without any unnecessary whitespace. Defaults to true.

- xslProcessor (text/plain) (0-1)

If provided, the resulting XML will be transformed with an XSL transformation which must be available on the classpath under /com/infinica/model/serializer/xml/{$xslProcessor}/postprocess.xsl.

- aesKeyOut (application/octet-stream) (0-1)

Optional encryption key for writing the template(s) (currently only used for XHTML output).

- indexerConfig (text/xml) (0-1)

Indexer configuration. This configuration takes precedence over any indexer that may be provided by the project. If no configuration is specified, the indexer is acquired from the project directory, if possible.

**Output Parameters:**

- output (x-infinica/stream) (1-unbounded) 

Output stream.

- messages (text/plain) (1-unbounded) 

Messages from template conversion.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}