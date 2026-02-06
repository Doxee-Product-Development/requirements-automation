---
id: "6c058b6c-8ba2-4e8f-955b-1eea02157c1c"
title: "REST Caller"
slug: "6-6-process-engine-manpages-activities-rest-caller"
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
created_at: "2025-08-13T13:30:19.988Z"
modified_at: "2025-08-22T17:31:15.418Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-rest-caller"
synced_at: "2026-01-28T21:02:44.029Z"
checksum: "415774e6d4fbc508"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(restCaller, Module: [REST](/doxee-platform/docs/rest))

Sends a request to a REST API and processes the response.

If any proxy parameters are provided, the proxy settings are taken from these parameters, otherwise the proxy settings configured via system properties are used (if any).

**Input Parameters:**

- url (x-infinica/url)

The URL to which the request should be sent.

- method (text/plain)

The HTTP method for the request. If no method is provided, a GET request will be sent.

Default:

GET

- headers (text/xml) (0-1)

Optional XML containing headers for the request. Below is an example for how the XML looks. The nodes header and value can occur arbitrary times. The "name" attribute of "header" node specifies the header name. The content of the "value" node specifies the header value.

`&lt;headers&gt; &lt;header name="..."&gt; &lt;value&gt;... &lt;/value&gt; ... &lt;/header&gt; ... &lt;/ headers&gt;`- content (x-infinica/stream, application/octet-stream, text/xml, text/plain) (0-1) 

Optional content which will be set as the body of the request.

- contentType (text/plain) (0-1)

Optional type for the content of the request.

- failOnHttpErrors (x-xsd/boolean)

Whether the activity should throw an exception if the REST request results in an HTTP error.

Default:

 true

- * (text/plain) (0-unbounded)

Any variable starting with the prefix "header_" will be used as a header for the request. The part of the variable name coming after the prefix is used as header name, the variable values are used as header values. Headers specified in individual mappings will overwrite headers with the same name defined in the "headers" xml.

- proxyHost (text/plain) (0-1) 

Proxy host name or IP.

- proxyPort (x-xsd/integer) (0-1) 

Proxy port.

- proxyUser (text/plain) (0-1)

Proxy user name (for Basic authentication).

- proxyPassword (x-infinica/secret-text) (0-1) 

Proxy password (for Basic authentication).

- keyStore (x-infinica/stream) (0-1)

A keystore containing a certificate and key in PKCS12 format for authenticating the client through mTLS.

- keyStorePassword (text/plain) (0-1)

A password required for the keystore provided through the keyStore parameter. Not necessary if no keystore has been provided.

**Output Parameters:**

- statusCode (x-xsd/integer)

HTTP status code of the response.

- statusPhrase (text/plain)

Text phrase belonging to the HTTP status code of the response.

- headers (text/xml)

An XML containing the headers of the HTTP response. The XML has the same structure as for the "header" parameter in the inputs.

- content (x-infinica/stream) (0-1)

Body of the response as stream.

- contentType (text/plain) (0-1)

Type for the content of the response if any.

- contentEncoding (text/plain) (0-1)

Encoding for the content of the response if any.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}