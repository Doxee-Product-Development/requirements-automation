---
id: "3907b4a4-e0f8-49e9-89e5-b15774caf6be"
title: "Storage Configuration"
slug: "6-6-process-engine-administration-reference-storage-configuration-1"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:42:06.477Z"
modified_at: "2026-01-07T14:06:10.919Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-storage-configuration-1"
synced_at: "2026-01-28T20:55:09.134Z"
checksum: "4b6b3460af91b842"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Across different Doxee applications, data storages are configured in a standard way:

`&lt;storage&gt;
  &lt;mainConfig ...&gt;
    &lt;subConfig ... /&gt;
    &lt;subConfig ... /&gt;
  &lt;/mainConfig&gt;

  &lt;mainConfig ...&gt;
    ...
  &lt;/mainConfig&gt;

  ...
&lt;/storage&gt;`*Main configurations* configure main storage types, e.g. a filesystem or a database storage. *Sub configurations* configure individual storages, e.g. a process storage in a filesystem, or a task storage in a database.

The available main storage types are described in the remained of this chapter. Sub storages depend on the Doxee application being configured, and are described in that application’s configuration chapter.

> Note

If an application requires a storage that is not configured, but for which a matching main storage has been configured, a default configuration for that storage is created automatically. For example, if a Process Engine defines a *filesystem* main storage but no process storage, a file process storage is automatically created for the configured filesystem storage.

If multiple main storage configurations are present, default storages are created for the first matching main storage. For example, if a *filesystem* and an *SQL* storage are configured (in that order), a file process storage would automatically created in the filesystem, but an SQL task storage (if required) would be created, as there currently is no filesystem implementation of a task storage.

## Filesystem Storage
Filesystem storages store their data in a directory on the filesystem.

`&lt;filesystem xmlns="http://www.infinica.com/storage"
    base="storage"&gt; ①
  &lt;!-- Sub configurations --&gt;
&lt;/filesystem&gt;``base `[1] configures the storage directory. Relative URLs will be considered relatove to the configuration file containing the storage configuration.

Sub storages will typically provide optional configuration options to store their own data in individual sub directories.

## SQL Storage
SQL storages store their data in a traditional SQL database.

`&lt;sql xmlns="http://www.infinica.com/storage"
    url="..." ①
    user="..." ②
    password="..." ③
    jdbcDriver="..."&gt; ④
  &lt;properties&gt; ⑤
    &lt;prop name="..." value="..." /&gt;
  &lt;/properties&gt;
  &lt;!-- Sub configurations --&gt;
&lt;/sql&gt;``url`[1] is a required attribute and defines the JDBC URL of the database. `user`[2], `password`[3] and `jdbcDriver`[4] are optional attributes to further configure the database connection.

An optional list of `properties`[5] can be specified, providing low level Hibernate connection parameters.

Sub storages typically also allow individual properties to be set on their configuration section.

## MongoDB Storage
MongoDB storages store their data in a MongoDB NoSQL database.

`&lt;mongo xmlns="http://www.infinica.com/storage"
    databaseName="..." ①
    dataStoreProvider="..." ②
    host="..." ③
    port="..." ④
  &lt;properties&gt; ⑤
    &lt;prop name="..." value="..." /&gt;
  &lt;/properties&gt;
  &lt;!-- Sub configurations --&gt;
&lt;/mongo&gt;``databaseName `[1], `dataStoreProvider `[2], `host `[3] and `port`[4] configure the database connection. An optional list of `properties `[5] can be specified, providing low level Hibernate connection parameters.

Sub storages typically also allow individual properties to be set on their configuration section.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}