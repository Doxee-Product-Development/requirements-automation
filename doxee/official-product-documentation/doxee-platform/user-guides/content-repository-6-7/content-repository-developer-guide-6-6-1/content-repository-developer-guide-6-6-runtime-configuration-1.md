---
id: "a3ccf2da-719f-434d-83b5-b00659011c4b"
title: "Runtime configuration"
slug: "content-repository-developer-guide-6-6-runtime-configuration-1"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Content Repository"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:44:21.843Z"
modified_at: "2026-01-07T14:03:18.629Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-developer-guide-6-6-runtime-configuration-1"
synced_at: "2026-01-28T20:50:35.793Z"
checksum: "f1fe0446a85e77c1"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

This chapter describes those repository configuration settings which are only used once the repository has been initialised successfully and is accessed by clients.

## Reloading the Configuration
After the runtime configuration is changed, the repository must be instructed to reload the configuration for the changes to take effect. This can be done either by restarting the repository server application or by performing a special `reinit` command in the form of a `PUT` request on the `/.system` directory.

## Runtime Configuration Options
The runtime behaviour of the repository can be configured using a number of parameters in the form of key/value pairs. These parameters can be set in two locations:

- in the repository, in `/.system/.properties`

- in the file system, in `$TOMCAT/repository.properties`

If the same parameter is set in both of these files, the setting from the repository internal configuration file always takes precedence.

> Note

If `$TOMCAT/repository.properties` is changed, the web application *must* be restarted for the changes to take effect. The `reinit` command described in [Reloading the configuration](/doxee-platform/docs/content-repository-developer-guide-6-6-runtime-configuration-1#reloading-the-configuration) is not effective in this case.

The repository internal configuration file `/.system/.properties` is a properties file with the following structure:

`module1.property1 = value1
module2.property2 = value2
...`The available properties are described in the following sections.

### Automatic Versioning
Automatic versioning can be enabled with the following parameter:

`auto-versioning.enabled = true
auto-versioning.exclusions = /.system`If automatic versioning is enabled, every newly created file written to the repository is automatically versioned.

> Note

This does not perform automatic checkout and checkins. It simply enables versioning for new files.

By default, the directory `/.system` is excluded from this feature, i.e. even with auto versioning enabled, no files will be versioned automatically in that directory. This setting can be changed with the `exclusions` parameter. Multiple directories can be specified by separating them with the colon character `:`).

### Home Directory
The following lines show the standard settings of the home directory feature:

`home-dir.location-pattern = /home/{username} //&lt;1&gt;
home-dir.auto-generate = true //&lt;2&gt;
home-dir.path-expression = ^((?:[^~]+\/)?\/?\~)([^\/\~]*)?(\/.*)?.*$ //&lt;3&gt;``location-pattern` [1] defines the path to a user's home directory in the repository. The parameter `{username}` is automatically replaced with the login name of the user.

If `auto-generate` [2] is `true`, the home directory will be created automatically if it does not already exist when it is accessed.

`path-expression` [3] sets a regular expression for detecting if a path in a repository URL contains a reference to a user's home directory, and how to extract the name of that user.

The default setting shown above recognises URLs of the following structure:

`http://localhost/~/fileInHomeDir.txt //&lt;4&gt;
http://localhost/some/other/path/~/fileInHomeDir.txt //&lt;5&gt;
http://localhost/~user2/fileInHomeDir.txt //&lt;6&gt;`The home directory reference is marked by the tilde character `~`). In the first two examples (4, 5), no user name is specified, so the name of the current user is used. The third [6] example explicitly refers to the home directory of `user2`.

The second line [5] also shows that the home directory reference can occur at any point in a path. Path segments before the reference are ignored, and the resulting path corresponds to the part of the URL after the home directory reference, relative to the selected home directory.

### Property Extractors
Property extractors are used to automatically transfer data from a file's content to some of its properties when the file is written. The Content Repository defines a property extractor for ITX files, which can be configured with the following properties:

`property.extractor.itx.fileName = ^.*\.itx$ //&lt;1&gt;
property.extractor.itx.mimeType = //&lt;2&gt;
property.extractor.itx.maxSize = //&lt;3&gt;`The settings shown here are the default values.

`fileName` [1] sets a regular expression which matches the names of all files that should be handled by the extractor. The default setting handles all files with the extension `.itx`.

`mimeType` [2] sets a regular expression which matches the MIME types of all files that should be handled by the extractor. By default, no restriction on MIME types is configured.

`maxSize` [3] can be set to the maximum size (in bytes) of files that should be handled. Any files larger than this setting will be ignored by the handler. The default settings defines no size limit.

### Import Approval
In order to require approval for all imports, the following property must be set:

`import.requireApproval = true`When import approval is activated, all received imports are kept in state `pending approval`. After successful approval, execution of the import is resumed.

An approver needs the privilege `{http://www.infinica.com/jcr/namespace}approveImport` on the target of the import, and cannot be the submitter of the import.

### Security Context of Delayed Imports
In general, a delayed import (one that waited for approval or was scheduled for a later time) runs in the context of the user who submitted it. An important exception are deployments (see below), which will always be executed in administrator mode.

Also, the import will be executed in administrator mode if the following property is set:

`import.delayedAsAdmin = true`### Deployment
In order to enable deployment mode for ZIP import and export, the following property must be set:

`webdav-import-export.deployment.enabled = true`All further settings regarding deployment also start with the prefix `webdav-import-export.deployment.`. The supported settings are:

- *acceptUnsignedZips* (true or false, default: false): setting this to true skips the signature check on ZIP import. It is strongly discouraged to do this on production systems.

- [*source.id*](http://source.id): a name that identifies this server

- *source.publicKey*: the public key of this server (base-64 encoded)

- *source.privateKey*: the private key of this server (base-64 encoded)

- *targets*: a comma-separated list of target server IDs for deployment from this server; This has merely informational purpose for the Resource Explorer.

- *allowedSourceIds*: a comma-separated list of source server IDs from which deployments will be accepted onto this server; An empty list means that all deployments are accepted (not recommended on production systems). Deployments will only be accepted if the source ID in the ZIP file matches an entry from the list.

- *sourceKey.'sourceId'*: the public key of the server specified by 'sourceId' (base-64 encoded), which will be used to verify the signature of ZIP files from that server; If no public key is specified for a given server (not recommended on production systems), the public key that is in the ZIP file is trusted.

### XSL Generation
The Content Repository can automatically generate XSL files from Infinica templates. A client that calls this features specifies the desired target. The repository must have a configuration file for each target that may be used. These configuration files are stored in `/.system`.

The following targets are supported:

Target

Configuration file

fo

xsl-fo-settings.xml

idx

xsl-idx-settings.xml

The configuration files can be created by exporting the XSL-FO settings from Template Designer's preferences dialogue. The exported file must be modified before it can be used as a configuration file for the repository.

A settings file exported by Template Designer looks like this:

`&lt;?xml version="1.0" encoding="UTF-8" standalone="yes"?&gt;
&lt;xsl_settings&gt;
  &lt;FO&gt;
    ...FO settings...  &lt;!--1--&gt;
  &lt;/FO&gt;
  &lt;IDX&gt;
    ...IDX settings... &lt;!--2--&gt;
  &lt;/IDX&gt;
&lt;/xsl_settings&gt;`For `xsl-fo-settings.xml`, the `&lt;FO&gt;` element must be extracted to a separate XML file, keeping the root element `&lt;xsl-settings&gt;` but only including the contents of the `&lt;FO&gt;` element [1] as its children.

`&lt;?xml version="1.0" encoding="UTF-8" standalone="yes"?&gt;
&lt;xsl_settings&gt;
  ...FO settings...  &lt;!--1--&gt;
&lt;/xsl_settings&gt;``xsl-idx-settings.xml` can be created in a similar fashion:

`&lt;?xml version="1.0" encoding="UTF-8" standalone="yes"?&gt;
&lt;xsl_settings&gt;
  ...IDX settings...  &lt;!--2--&gt;
&lt;/xsl_settings&gt;`If the XSL files generated by the repository will be used by external XSL transformers and not just by Doxee applications, the following additional settings must be included in these `&lt;xsl_settings&gt;` elements:

`&lt;infinicaResourcesPrefix&gt;http://server/.system/infinica/&lt;/infinicaResourcesPrefix&gt; &lt;!--1--&gt;
&lt;metaData type="com.infinica.output.MetaDataOptions"&gt;DONT_USE_FUNCTION&lt;/metaData&gt;``&lt;infinicaResourcesPrefix&gt;` [1] must point to a directory containing the standard Infinica resource files, which can be copied from the directory `infinica_resources` provided as part of the Doxee Content Repository distribution.

### Dependency Analysis
The following settings can be configured for the dependency indexer:

`dependencyAnalysis.indexerStarterDelay = 30000 &lt;1&gt;
dependencyAnalysis.indexerLockRefresherDelay = 60000 &lt;2&gt; 
dependencyAnalysis.indexerLockTimeout = 300000 &lt;3&gt;``indexerStartDelay` [1] defines the delay after repository startup before the indexer start.

`indexerLockRefresherDelay` [2] sets the interval after which the current indexer node in a clustered setup refreshes its lock on the indexer. In a cluster setup, only one node can run the indexer at any moment. If the current indexer fails to refresh the lock within the configured lock timeout [3], the cluster will assume that the indexer node has been lost and another node will take over as the new indexer node. The lock refresher delay must therefore always be significantly shorter than the lock timeout.

All values are specified in milliseconds.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}