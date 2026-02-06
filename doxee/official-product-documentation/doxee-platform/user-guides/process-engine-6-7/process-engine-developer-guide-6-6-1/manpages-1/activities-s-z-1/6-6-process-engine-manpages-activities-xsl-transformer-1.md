---
id: "ac0e17c0-d145-4af0-a6b4-8730776d2a35"
title: "XSL Transformer"
slug: "6-6-process-engine-manpages-activities-xsl-transformer-1"
category: "Activities (S to Z)"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Activities (S to Z)"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:17.385Z"
modified_at: "2026-01-07T14:06:57.169Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-xsl-transformer-1"
synced_at: "2026-01-28T20:56:31.672Z"
checksum: "890a52d0694083ec"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(xslTransformer, Module: [Core](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-core-1))

Transforms XML input using an XSL stylesheet.

Multiple XSLTs and multiple XMLs are supported in the following way:

- If there are multiple XSLTs and one (or no) XML, the XML input is transformed with each of the XSLTs, producing the same number of result XMLs are there are XSLTs.

- If there are multiple XMLs and one XSLT, each XML is transformed with the XSLT, producing the same number of result XMLs are there are input XMLs.

- If there are multiple XSLTs and multiple XMLs, they should be equal in number. The first XML is transformed with the first XSLT, the second XML with the second XSLT, and so on.

Note that all other parameters (base Uri, cache, transformer factory, load-on-demand, named XSL parameters) are the same for all transformations. Also, messages and errors from the transformations are returned as lists, and if only some transformations produce messages/errors, it is not possible to deduce exactly which transformation produced which output. If you need that level of control, you must run each transformation in its own activity.

**Input Parameters:**

- xslt (x-infinica/stream) (1-unbounded)

XSL stylesheets. If multiple stylesheets are provided, each of them is executed.

- xml (x-infinica/stream) (0-unbounded)

Input XMLs. Optional. If this is not specified, which makes sense for XSLTs that generate static output or that rely on named inputs, an empty XML is generated at runtime. If multiple XMLs are provided, each of them is transformed.

- baseUri (x-infinica/url) (0-1)

Base URI for transformation. If this is not specified, the base URI is taken from the XSLT stream.

- cacheXsl (text/plain)

Optional switch to use an XSL transformer cache. Allowed values:

true - Use cache.

- false - Do not use cache.

- clear - Clear the entire cache and use it.

Default:

- false

- cacheUserKey (text/plain) (0-1)

Specifies the user key for cache access. If it is not specified, the user key will be calculated automatically based on the URL and the current credentials registry.

- cachePartition (text/plain) (0-1)

Specifies a custom cache partition.

- transformerFactory (text/plain)

Optional transformer factory class name.

Default:

com.infinica.transformer.InfinicaTransformerFactory

- outputBaseUrlParameter (text/plain) (0-1)

Optional name of a template parameter which takes a directory URL for additional output files created by the template.

- loadOnDemandCallbackClassname (text/plain) (0-1)

Optional class name for load-on-demand callback. The class must have a no-args constructor and implement the ILoadOnDemandCallback interface. All other parameters that start with loadOnDemandCallback will be passed to the instantiated class (finding setters via reflection).

- *

All additional inputs will be passed to the XSL transformation as named parameters.

**Output Parameters:**

- output (x-infinica/stream)

Transformed XML. Note that it is not guaranteed that a result is returned, in case that errors happened during the transformation. See the errors output parameter below.

- errors (text/plain)

Errors and warnings that happened during the XSL transformation. The errors will be collected and returned as a single string. No exception will be thrown. If exception handling is desired, the process should check whether errors are returned.

- messages (text/plain)

Output from xsl:message elements. This is always a single string.

- If the transformation writes additional result files (see the outputBaseUrlParameter input parameter), each created file results in an additional output parameter. The parameter name is the file name (dots are replaced by underscores), and the value is a stream of the file content.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}