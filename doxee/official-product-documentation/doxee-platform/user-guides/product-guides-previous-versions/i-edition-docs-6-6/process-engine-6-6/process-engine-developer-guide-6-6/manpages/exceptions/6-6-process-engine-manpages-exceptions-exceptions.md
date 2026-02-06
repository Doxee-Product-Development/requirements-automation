---
id: "8062b23d-604f-4dc3-bdce-0fa39fa90a0a"
title: "Exceptions"
slug: "6-6-process-engine-manpages-exceptions-exceptions"
category: "Exceptions"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
  - "Manpages"
  - "Exceptions"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-19T08:05:09.419Z"
modified_at: "2025-08-22T17:37:14.184Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-manpages-exceptions-exceptions"
synced_at: "2026-01-28T21:03:52.290Z"
checksum: "3a71699c26440ec8"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

#### **argument**
Class:java.lang.IllegalArgumentException 

#### **authentication**
Health: broken 

#### **infinica.break**
Parent: infinica Health: broken 

#### **infinica.process**
Parent:infinica

Class:com.infinica.engine.access.exceptions.InfinicaEngineAccessException 

#### **infinica.process.authentication**
Parents: infinica.process, authentication

Class:com.infinica.engine.access.exceptions.InfinicaEngineAuthenticationException 

#### **infinica.process.authorization**
Parent:infinica.process

Class:com.infinica.engine.access.exceptions.InfinicaEngineAuthorizationException 

#### **internal**
Parent:internal

Class:java.lang.Throwable 

#### **internal.array_index_out_of_bounds**
Parent:internal

Class:java.lang.ArrayIndexOutOfBoundsException 

####  **internal.malformed_url**
Parent:internal

Class:java.net.MalformedURLException 

#### **internal.null_pointer**
Parent:internal

Class:java.lang.NullPointerException

#### **internal.unsupported_charset**
Parent:internal

Class:java.nio.charset.UnsupportedCharsetException 

#### **internal.uri_syntax**
Parent:internal

Class:java.net.URISyntaxException

#### **net.unknown_host**
Class:java.net.UnknownHostException 

####  **printer**
Class:javax.print.PrintException

#### **regexp.syntax**
Class:java.util.regex.PatternSyntaxException 

#### **resource_access**
Parent:	resource_access

Class:com.infinica.access.resources.exceptions.ResourceAccessException

#### **resource_access.argument**
Parent:	resource_access

Class:com.infinica.access.resources.exceptions.ResourceArgumentException 

#### **resource_access.io**
Parent:	resource_access

Class:	java.io.IOException 

#### **resource_access.io**
Parent:	resource_access

Class:com.infinica.access.resources.exceptions.ResourceIOException 

#### **resource_access.io.authentication**
Parents: resource_access.io, authentication

Class:	com.infinica.access.resources.exceptions.ResourceAuthenticationException 

#### **resource_access.io.bad_request**
Parent:	resource_access.io

Class:com.infinica.access.resources.exceptions.ResourceBadRequestException 

#### **resource_access.io.conflict**
Parent:	resource_access.io

Class:	com.infinica.access.resources.exceptions.ResourceConflictException 

#### **resource_access.io.conflict.checked_in**
Parent:	resource_access.io.conflict

Class:com.infinica.access.resources.exceptions.ResourceCheckedinException 

#### **resource_access.io.conflict.checked_out**
Parent:	resource_access.io.conflict

Class:com.infinica.access.resources.exceptions.ResourceNotCheckedinException 

#### **resource_access.io.forbidden**
Parent:	resource_access.io

Class:com.infinica.access.resources.exceptions.ResourceForbiddenException

####  **resource_access.io.interrupted**
Parent:	resource_access.io

Class:com.infinica.access.resources.exceptions.ResourceInterruptedException 

#### **resource_access.io.locked**
Parent:	resource_access.io

Class:com.infinica.access.resources.exceptions.ResourceLockedException 

#### **resource_access.io.method_not_allowed**
Parent:	resource_access.io

Class:com.infinica.access.resources.exceptions.ResourceMethodNotAllowedException

#### **resource_access.io.not_connected**
Parent:	resource_access.io

Class:com.infinica.access.resources.exceptions.NotConnectedException 

#### **resource_access.io.not_found**
Parent:	resource_access.io

Class:	java.io.FileNotFoundException 

#### **resource_access.io.not_found**
Parent:	resource_access.io

Class:	com.infinica.access.resources.exceptions.ResourceNotFoundException

#### **resource_access.io.timeout**
Parent:	resource_access.io

Class:com.infinica.access.resources.exceptions.ResourceTimeoutException 

#### **resource_access.property_access**
Parent:	resource_access

Class:com.infinica.access.resources.exceptions.PropertyAccessException

#### **resource_access.property_access.unknown_property**
Parent:	resource_access.property_access

Class:com.infinica.access.resources.exceptions.UnknownPropertyException 

#### **resource_access.property_access.unknown_property_type**
Parent:	resource_access.property_access

Class:com.infinica.access.resources.exceptions.UnknownPropertyTypeException 

#### **sql**
Class:	java.sql.SQLException 

#### **task.authentication**
Class:com.infinica.tasks.exceptions.TaskUnauthenticatedException 

#### **xml**
Parent:	xml

Class:	org.w3c.dom.DOMException 

#### **xml.parse**
Parent:	xml

Class:	org.xml.sax.SAXException 

#### **xml.transform**
Parent:	xml

Class:javax.xml.transform.TransformerException 

#### **xml.transform.configuration**
Parent:	xml.transform

Class:javax.xml.transform.TransformerConfigurationException

#### **xml.transform.message**
Parent:	xml.transform

Class:net.sf.saxon.instruct.TerminationException

#### **xpath**
Class:	javax.xml.xpath.XPathExpressionException

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}