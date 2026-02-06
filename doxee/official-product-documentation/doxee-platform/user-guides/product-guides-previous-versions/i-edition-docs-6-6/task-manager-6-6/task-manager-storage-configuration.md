---
id: "ac072731-228e-4a76-9553-dbc2543ec737"
title: "Storage configuration"
slug: "task-manager-storage-configuration"
category: "Task Manager"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Task Manager"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-03T11:42:04.55Z"
modified_at: "2025-12-04T13:14:57.921Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/task-manager-storage-configuration"
synced_at: "2026-01-28T21:03:57.782Z"
checksum: "55a3d774ee55ea65"
---

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