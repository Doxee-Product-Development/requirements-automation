---
id: "3cb8f16f-d88f-491c-990b-9e91e397e641"
title: "Audit log"
slug: "security-configuration-guide-6-6-audit-log"
category: "Concepts"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Security configuration"
  - "Concepts"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-04T13:54:13.264Z"
modified_at: "2025-12-05T12:57:29.681Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-audit-log"
synced_at: "2026-01-28T21:04:59.855Z"
checksum: "5cbeb67a1417072e"
---

Audit logging allows Doxee services to log information about login events to the service and also about specific operations performed by users. Audit logging is currently supported by the Content Repository, the Process Engine, and the Task Manager.

## Authentication Logging
Authentication logging logs information about the following events:

- Login success

- Login failure

- Impersonation success

- Impersonation failure

These log events are standardised across all Doxee services. Status codes for authentication events can be found below.

## Operation Logging
Operation logging logs information about specific service operations invoked by users. Which operations support logging, and what information is logged, depends on the application. Every operation associated with an authenticated user can always include the user name in the log.

## Limitations
Not all requests actually reach the service application. For example, malformed requests may already be intercepted before authentication takes place. In this case, the user will receive an error response, even if the intended operation would require the user to authenticate first (however, no internal information is disclosed, as the operation is rejected purely because it is incompatible with the API), and nothing will be written to the audit log. To get a complete list of all requests (including malformed requests) and their response codes, please consult Tomcat's access log.

## Configuration
The audit log is configured in the applications’ `&lt;security&gt;` configuration node. If no `&lt;audit&gt;` configuration is provided, the audit log is disabled.

The `&lt;audit&gt;` element contains a sub element that configures the actual logger. Currently, the Log4j logger, configured with a `&lt;log4j&gt;` element, is the only supported logger:

`&lt;log4j xmlns="http://www.infinica.com/audit"&gt;
  &lt;appenders&gt; &lt;!--1--&gt;
    &lt;Console name="stdout" target="SYSTEM_OUT" ignoreExceptions="false"&gt;
      &lt;PatternLayout&gt;
        &lt;Pattern&gt;AUDIT: %d{ISO8601} [%p] %m%n&lt;/Pattern&gt;
      &lt;/PatternLayout&gt;
    &lt;/Console&gt;
  &lt;/appenders&gt;

  &lt;patterns&gt; &lt;!--2--&gt;
    &lt;loginSuccess&gt;[[{appName}]] {status} Login [{user}]&lt;/loginSuccess&gt;
    &lt;loginError&gt;[[{appName}]] {status}{:?:  {message}} [{user}]&lt;/loginError&gt;
    &lt;impersonationSuccess&gt;[[{appName}]] {status} Impersonation [{user} -&gt; {impersonatedUser}]&lt;/impersonationSuccess&gt;
    &lt;impersonationError&gt;[[{appName}]] {status}{:?:  {message}} [{user} -&gt; {impersonatedUser}]&lt;/impersonationError&gt;
    &lt;operation&gt;[[{appName}]] {status} {operation}{:?:  &amp;lt;{resource}&amp;gt;}{:?:  {message}} [{user}]{:?:  ({attributes})}&lt;/operation&gt;
    &lt;attribute&gt;{key} = {value}&lt;/attribute&gt;
    &lt;attributeGlue&gt;; &lt;/attributeGlue&gt;
  &lt;/patterns&gt;

  &lt;levels&gt; &lt;!--3--&gt;
    &lt;success&gt;info&lt;/success&gt;
    &lt;clientError&gt;warn&lt;/clientError&gt;
    &lt;serverError&gt;error&lt;/serverError&gt;
  &lt;/levels&gt;
&lt;/log4j&gt;``&lt;appenders&gt;` (1) configures one or more Log4j appenders that will be used as the log target. Please refer to the Log4j documentation for details. If no appender is configured, the audit log is written to the service's default Log4j log instead.

`&lt;patterns&gt;` (2) defines the patterns for log messages of these types:

- loginSuccess

- loginError

- impersonationSuccess

- impersonationError

- operation

Curly braces in these strings denote pattern fields which are replaced by the actual log event values. The backslash character can be used as an escape character. If a curly brace sequence starts with the characters `:?:` followed by a whitespace character, the rest of the curly brace sequence denotes another pattern, usually including one or more additional curly brace sequences denoting sub patterns, that is only output if at least one of its sub patterns results in a non-empty string. The first whitespace after `:?:` is not part of the sub pattern, so if the sub pattern should start with a white space, two white space characters must be used.

The available pattern fields are listed below.

The operation pattern can include the `attributes` field, which may contain a list of attributes, each of which are represented as a key/value pair. `&lt;attribute&gt;` defines the pattern for each of these pairs. If more than one attribute is listed, each pair of attributes is separated by the `&lt;attributeGlue&gt;`.

The values shown in the above snippet are the default patterns.

`&lt;levels&gt;` (3) configures the log levels for the different status classes of audit events. Supported log levels are `trace`,  `debug`, `info`, `warn`, `error`, and `fatal`. The values shown in the above snippet are the default values.

### Pattern Fields
The following fields can be used in Log4J audit log patterns:

Field

Description

`appName`

The name of the application. Useful if multiple applications write to the same audit log.

`status`

Status code.

`message`

Status message. May be empty.

`user`

User name.

`impersonatedUser`

Impersonated user name (for impersonation events).

`resource`

The target resource (for operation events).

`operation`

The operation name (for operation events).

`attributes`

Additional attributes (for operation events).

`key`

(In `&lt;attributes&gt;`) Attribute key.

`value`

(In `&lt;attributes&gt;`) Attribute value.

## Status Codes
All audit log events are associated with a status code. Status codes describe the result of the logged event and use a format similar to that of HTTP status codes. Each code is a three-digit number, with the first digit determining the overall status class:

- 2xx: Success

- 4xx: Client error

- 5xx: Server error

### Authentication Status Codes
For authentication messages, the following well-known status codes are defined independently of the application:

- 200: Trusted without authentication

- 201: Successfully authenticated

- 202: Trusted based on previously cached success

- 401: Invalid credentials

- 402: Missing credentials

- 403: Expired credentials

- 404: Account not found

- 405: Account expired

- 406: Account locked

- 500: Internal Server Error

- 501: Invalid configuration

- 502: User store access error

### Operation Status Codes
Because operation logging depends on the service application, different services use different status codes for their operations. However, they do still adhere to the standard classifications for success, client error, and server error events.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}