---
id: "04e3d2df-74b8-4f9e-bb60-0d2285dc3a53"
title: "Client credentials"
slug: "security-configuration-guide-6-6-client-credentials-1"
category: "Concepts"
category_path:
  - "Product guides"
  - "Security configuration"
  - "Concepts"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:45:18.547Z"
modified_at: "2026-01-07T13:48:07.06Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/security-configuration-guide-6-6-client-credentials-1"
synced_at: "2026-01-28T20:40:09.645Z"
checksum: "62a6fed1044360eb"
---

When an application (e.g. a service) has to access another service without user interaction and that service requires authentication, the matching *credentials* have to be configured in the application.

This is mainly important for Process Engine, which uses configured credentials specifically to access the Task Manager but also when accessing any other external service (e.g. the Content Repository, or a custom service). Workplace also uses configured credentials for technical access to the Task Manager.

The XML elements used to configure credentials depend on the chosen authentication mechanisms and are described in detail in the second section of this documentation (Authentication mechanisms and user stores).

When an application requires only one set of credentials for a specific purpose (e.g. Process Engine and Workplace for technical task access), the corresponding section in its configuration expects one single credentials XML element.

For specifying credentials for accessing any number of arbitrary external services, a *credentials registry* is used, which specifies the credentials XML elements for each of these services. Currently, the Process Engine is the only application to use configurable credentials registries. Their configuration is therefore described in the Process Engine Administration Guide.

Credentials of any type usually also require a *credentials configuration*. This configuration can be defined as part of the credentials themselves, or provided separately in a *credentials configuration registry*. If no configuration is provided, the application may be able to create a matching configuration based on its own authentication configuration. Alternatively, if preemptive authentication is disabled, the authentication error response from the server may provide the necessary information.

When describing credentials elements later in this document (Authentication mechanisms and user stores), the credentials configurations are usually described as part of the credentials. These same elements may be omitted in the credentials elements and instead provided in the credentials configuration registry.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}