---
id: "94f16549-0102-4ee5-9d83-dd8c953208ba"
title: "Cluster configuration"
slug: "content-repository-developer-guide-6-6-cluster-configuration"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Content Repository"
  - "Administration guide"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-04T10:20:05.971Z"
modified_at: "2025-12-05T15:59:46.962Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-developer-guide-6-6-cluster-configuration"
synced_at: "2026-01-28T21:00:56.775Z"
checksum: "bed4a36d8e7576fc"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

The Doxee Content Repository can be configured as a cluster. In this scenario, multiple instance of the repository web application run on different servers, providing access to the same repository content. Most of the content is kept in centralised storage, but some data is stored locally with the individual nodes and synchronised automatically. A repository cluster must be carefully configured to avoid conflicts between the cluster nodes and potential data loss.

The cluster functionality is entirely based on core functionality provided by Apache Jackrabbit. Specific configuration details depend on the database type used as the content storage, among other things. For detailed information about cluster specific configuration issues, please refer to the official Apache Jackrabbit documentation, especially the [cluster configuration](https://wiki.apache.org/jackrabbit/Clustering) overview.

## Requirements
The following requirements must be met by all content repository instances configured to be a part of a cluster setup:

- Each cluster node must have its own `repository.properties` and `repository.xml` configuration files and its own storage directory (specified in the properties file)

- The virtual file system as well as the workspace and versioning persistence storages must be the same for all cluster nodes. Typically, a database will be used for this and referenced by all cluster nodes.

- The file systems for workspaces and the versioning storage must be local on all cluster nodes.

- All cluster nodes must use a common journal, typically stored in a database.

- Each cluster node must have its own, unique ID.

- No DataStore should be used, or if one is required, it must be shared by all nodes.

## Configuring a Cluster Node
Based on the default `repository.xml` provided with the Content Repository installation files, a cluster node can be configured with a few additional steps compared to the usual configuration modifications. The sections referenced below can be easily found in the default configuration by looking for XML comments containing the text 'FOR CLUSTER SETUPS'.

Typically, a cluster will be set up by first configuring only one cluster node and starting it. If initial testing shows that the repository has been initialised correctly, further cluster nodes can be added.

### Replace the default virtual filesystem with a shared file system
Remove the `&lt;FileSystem&gt;` element using the `LocalFileSystem` class defined near the top of the configuration file (_not_ the ones in the `&lt;Workspace&gt;` and `&lt;Versioning&gt;` sections) and enable the commented out `&lt;FileSystem&gt;` element with the `DbFileSystem` class immediately below it:

`&lt;FileSystem class="org.apache.jackrabbit.core.fs.db.DbFileSystem"&gt;
  &lt;param name="driver" value="DRIVER"/&gt;
  &lt;param name="schema" value="SCHEMA"/&gt;
  &lt;param name="url" value="URL"/&gt;
  &lt;param name="user" value="USER" /&gt;
  &lt;param name="password" value="PASSWORD" /&gt;				
  &lt;param name="schemaObjectPrefix" value="globalfs_"/&gt;
&lt;/FileSystem&gt;`Fill in the database driver, schema (i.e. database type), URL, user and password according to your database setup. For certain database types, the `DbFileSystem` class may be replaced by more specific implementations (please refer to the Apache Jackrabbit documentation for details).

### Disable the DataStore
Remove the `&lt;DataStore&gt;` element to make sure that larger binary files are stored correctly in the cluster.

### Configure global persistence managers
By default, persistence managers defined in the `&lt;Workspace&gt;` and `&lt;Versioning&gt;` configurations use a local Derby database for storage. These must be replaced with a global persistence storage, typically the external database already used for the virtual file system above. This is equivalent to the regular configuration of a database persistence storage for non-clustered setups, as described in [Bootstrap configuration](/doxee-platform/docs/content-repository-developer-guide-6-6-bootstrap-configuration).

### Cluster-specific settings
Every cluster node must have a unique ID. Also, every node must access the cluster's journal.

The journal is where a clustered repository tracks the changes made on individual nodes so that the other nodes can be synchronised correctly. Typically, the journal is stored in the same database as the virtual file system and the persistence storages.

The necessary configuration can be added by uncommenting the `&lt;Cluster&gt;`  element at the bottom of the default configuration file:

`&lt;Cluster id="NODE ID" syncDelay="2000"&gt;
  &lt;Journal class="org.apache.jackrabbit.core.journal.DatabaseJournal"&gt;
    &lt;param name="revision" value="${rep.home}/revision.log" /&gt;
    &lt;param name="driver" value="DRIVER"/&gt;
    &lt;param name="databaseType" value="DATABASE TYPE"/&gt;
    &lt;param name="url" value="URL"/&gt;
    &lt;param name="user" value="USER" /&gt;
    &lt;param name="password" value="PASSWORD" /&gt;				
  &lt;/Journal&gt;
&lt;/Cluster&gt;	`The node ID and database settings must be filled in correctly. `databaseType` corresponds to the `schema` parameter in the virtual filesystem configuration.

## Starting a Clustered Repository
To avoid unnecessary complications in the case of configuration problems, the first node of a clustered repository should be started and verified before configuring and starting additional nodes. Once the cluster configuration has been modified as described above, the first repository node can be started in the regular fashion like an unclustered repository.

After the repository has started, the log files should be inspected. If they are free of errors, access to the repository can easily be tested with a web browser by navigating to the root URL of the repository, e.g.:

`http://localhost:8080/infinica-content-repository/`This should prompt for the user's credentials (if authentication has been configured) and display the contents of the root folder. For further testing, Resource Explorer can be used to copy a few test files into the repository and verifying that they can be read again.

If any errors are found while testing, the following steps should be taken:

- Stop the server.

- Fix the configuration.

- Delete the local repository directory (as specified in `repository.xml`).

- Delete all database objects created by the repository (if the repository does not share its database with any other applications, simply delete and re-create the database).

- Optionally delete all log files.

- Start the server and restart testing.

## Adding Cluster Nodes
Once the Repository is up and running correctly, further cluster nodes can be added.

To add another node to a repository cluster, copy the web application to another server (make sure it is not running at this point). Then copy the configuration files `icr.xml`, `repository.properties` and `repository.xml`) from an already configured cluster node to the new server.

> Tip

Typically, the configuration files will be nearly identical between multiple nodes of the same cluster. The one option that must always be different for each node is the cluster node ID defined in `repository.xml`. Depending on the filesystem layout of the individual server, the paths to the local repository directory in `repository.properties` may vary as well.

Now the new cluster node can be started and tested by accessing its server URL. Immediately upon starting, the new cluster node should already show the same content as the cluster nodes started earlier. Any changes on any nodes in the cluster (e.g. adding, modifying or deleting files and folders) should automatically be synchronised and show up on the other nodes.

## Further Configuration
Once a cluster of two or more nodes has been set up, a load balancer may be set up to provide one single repository URL for end users. The load balancer may redirect clients accessing this URL to any of the configured repository nodes.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}