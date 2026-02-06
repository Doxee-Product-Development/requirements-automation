---
id: "484db2f5-5bf4-41f1-a5ca-fa54e49f62bd"
title: "SOAP Caller"
slug: "6-6-process-engine-manpages-activities-soap-caller-1"
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
created_at: "2026-01-07T13:42:17.14Z"
modified_at: "2026-01-07T14:06:53.719Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-activities-soap-caller-1"
synced_at: "2026-01-28T20:56:21.696Z"
checksum: "527a2e21b04d4dd6"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

(soapCaller, Module: [SOAP](/doxee-platform/docs/6-6-process-engine-manpages-detailed-module-descriptions-soap-1))

Calls a SOAP service. Currently SOAP(1.1/1.2) over HTTP is supported 

**Input Parameters:**

- operationInfo (text/xml) (0-1)

Operation info as XML. If this is specified, the parameters endpointUrl, service, portType, and operation are taken from this XML.

- endpointUrl (x-infinica/url) (0-1)

Address of the target service endpoint as a URL.

- wsdlUrl (x-infinica/url) (0-1)

URL where the WSDL which should be used is located. If this location is identical with the endpointUrl, it can be omitted.

- service (text/plain) (0-1)

Service definition to call.

- portType (text/plain) (0-1) 

Port definition to call. 

- operation (text/plain) (0-1) 

Operation to call.

- operationParams (x-infinica/xml-node) (0-unbounded)

 Parameters of the operation.

- headers (x-infinica/xml-node) (0-unbounded) 

XML nodes for the SOAP header.

- wsse (x-xsd/boolean) (0-1)

If true, the standard way to add credentials to the outgoing message via the Authentication Layer will be bypassed and username/password credentials will instead be passed via a WSSE header.

Default:

false

- timeout (x-xsd/integer) (0-1)

Timeout for the SOAP calls, in milliseconds.

- send (x-xsd/boolean) (0-1)

Whether to send the request. If this is false, the SOAP request is created and returned, but not send to the target server.

Default:

true

- *

Parameters for the request. Each parameter will result in an XML element within the operation element. The parameter name will be used as the element name, and the parameter value as the element content.

**Output Parameters:**

- operationInfo (text/xml)

Operation info as XML. This can be used for a future call to the same operation to skip parsing the WSDL again.

- request (x-infinica/stream) (0-1)

SOAP request as an XML stream. Only created if an endpoint URL was available.

- output (x-infinica/stream) (0-1) 

Response of the service call.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}