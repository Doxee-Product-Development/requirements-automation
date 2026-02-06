---
id: "02aecd8a-b9e1-4770-b2ab-d16fdc3481ac"
title: "i-Edition 6.5 SP2 - August 22, 2025"
slug: "release-notes-i-edition-6-5-sp2"
category: "i-Edition"
category_path:
  - "Release notes"
  - "i-Edition"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-08-04T13:39:03.267Z"
modified_at: "2025-11-13T12:26:01.752Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/release-notes-i-edition-6-5-sp2"
synced_at: "2026-01-28T20:40:01.758Z"
checksum: "c0d57ec48eceb478"
---

This section contains the full changelog of **Doxee Platform&reg;**** release 6.5 SP2**. This service pack introduced critical fixes and enhancements to several components of the Doxee Platform&reg;. Please refer to the respective sections for a complete overview of changes.

Before adopting this software version, please read these release notes carefully to find out about new features, improvements, changes, fixes, deprecations, known bugs, limitations, or user impacts which may affect your operations.

## Changelog of 6.5 SP2
> For Doxee internal users

For more details on individual release items, please refer to Jira:

- [6.5 SP2 release items](https://infinica.atlassian.net/issues/?filter=16693)

### Doxee Platform&reg;
> Actions required before installing this version

- Migrating databases with the Migrator and Storage Manager tools **requires manual action**. Due to a bug, Storage Manager may not properly remove generated objects during the clear action. This may lead to failures when trying to reimport migrated storages. To prevent errors during the database migration process, it is necessary to check whether the clear action was completed successfully. If necessary, generated objects must be removed manually.

#### **Server Infrastructure &amp; Runtime**
- **Updated** Apache FOP rendering processor to 2.10.

#### **Access Management &amp; Security**
- **Improved** the LDAP security configuration to allow for more flexibility. It’s now possible to add multiple subconfigurations.

- **Fixed **vulnerabilities by updating various libraries:

activemq to 5.19.0

- bytebuddy to 1.17.5

- commons-configuration to commons-configuration2 2.12.0

- commons-fileupload to 1.6.0

- commons-lang3 to 3.18.0

- fontbox to 3.0.4

- jackrabbit to 2.22.1

- mina-core to 2.2.4

- mockito to 5.17.0

- mysql-connector-j to 9.3

- nimbus-jose-jwt by upgrading nimbus-oauth to 11.27

- pdfbox to 2.0.34

- poi-ooxml to 5.4.1

- tika to 2.9.4

- Removed the library commons-lang and replaced it with calls to infinica-inner-core and commons-lang3.

- **Fixed **SOAP server projects compiling generated code for wrong Java version.

- **Fixed** ActiveMQ vulnerabilities across several web-based components.

#### **Stability &amp; Performance**
- **Fixed** process storages exported with Storage Manager containing empty Process Watchers. The missing data would subsequently trigger exceptions when trying to reimport the storage.

- **Fixed **an issue where clearing the execution cache would sometimes close the resources of actively running processes.

### Business Designer &amp; Composer
#### **UI/UX Enhancements &amp; Usability**
- **Improved** the application UI with rebranding.

### Process Engine
#### Security
- **Updated** the library commons-beanutils to 1.11.0.

#### **Usability Enhancements**
- **Changed** the behavior of iteration targets on start elements in included processes, which lead to an accumulation of outputs.

> Backward compatibility

This fix addresses an undesired change in behavior which occurred from version 6.5 onwards. Iteration targets now again behave as expected in version 6.4.

- **Improved** the handling of warnings from deprecated activities. These warnings are now also written into the diagnostic-log, in addition to the application-log.

- **Improved:** The log level for ProcessTerminateException has been reduced to avoid redundant termination warnings when a process is terminated purposefully.

- **Fixed** nonexistent sub-pipeline variables, for example in a group, inheriting the types of unmapped homonyms from a parent pipeline. This issue would manifest as seemingly unrelated errors, for example corrupted PDFs.

#### **Integration &amp; Module Extensions**
- **Added** the `getMetadata` API endpoint to retrieve helpful process metadata.

### Resource Explorer
#### **UI/UX Enhancements &amp; Usability**
- **Improved** the application UI with rebranding.

### Workplace
> This section refers to changes made to the **Workplace 1** application.

#### Access Management &amp; Security
- **Fixed** duplicate library entries in the Workplace WAR file.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}