---
id: "5d4965bd-9836-4d65-a6ab-ae002e970fed"
title: "Features"
slug: "content-repository-6-6-features-1"
category: "Content Repository"
category_path:
  - "Product guides"
  - "Content Repository"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:44:21.247Z"
modified_at: "2026-01-07T14:01:41.512Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-6-6-features-1"
synced_at: "2026-01-28T20:50:33.306Z"
checksum: "127c9c0520234fd8"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

## Versioning
The repository supports versioning of files according to the checkout-in-place feature of the Delta-V extension for WebDAV. A normal file can be turned into a versioned one using the VERSION-CONTROL method. Versioned files have a version history attached. They can only be modified after checking them out using the CHECKOUT method first. After successful editing, a new version is created upon checking it in with the CHECKIN method. In case the file should be returned to the checked in state again without creating a new version, discarding possible changes to the file, the checkout can be reversed with the UNCHECKOUT method.

Contrary to basic WebDAV versioning, in Doxee Content Repository checked out files are automatically locked by the user who did the checkout. This prevents other users from writing the file before it was checked in by the editing user. Users reading a file checked out by someone else, are redirected to the last checked in version. This means that current modifications of a user only become public once they are checked in. Depending on the users privileges it may be possible to explicitly read the currently checked out version of a different user. 

### Automatic Versioning
Usually a newly created file is not versioned and only upon explicitly enabling versioning for the file, a version history is attached. The repository can also be configured to version each new file automatically.

### Date-based version access
The content repository allows accessing a certain version of a resource by appending a date to the URL. The date must have the format defined in RFC 3339 (e.g. 2015-06-12T15:16:29.594+02:00). Note that the parameter is encoded in the actual URL, because it contains reserved characters. The version which is accessed is the newest which already existed at the provided point in time.

`http://server/file.txt?versionDate=2015-06-12T15%3A16%3A29.594%2B02%3A00`### Base-path query parameters
In the example given above, the parameter is passed to the content repository in the query string (the part of the URL after the question mark). This is a standard way of passing parameters via HTTP and is well established. However, in certain situations passing parameters in the query string has undesired side effects. The query string is stripped away when a relative path is resolved against a base URL. Consider the following URL:

`http://server/template.itx?versionDate=2015-06-12T15%3A16%3A29.594%2B02%3A00`This returns the newest version of the template that existed at the given date. This template may contain references to other resources, very often by relative paths. The path "logo.png" would be resolved to this URL:

`http://server/logo.png`Note that the query string is gone in the resolved URL. The result is a template from a given date, that contains the latest version of the image, instead of the corresponding version.

This effect can be side-stepped by moving parameters to the "base path" like this:

`http://server/=versionDate=2015-06-12T15%3A16%3A29.594%2B02%3A00=/template.itx`The content repository interprets any path segments starting and ending with an equals sign (=) as query parameters. For the client, the parameter is a normal part of the path, so that resolving the reference "logo.png" will now result in this URL:

`http://server/=versionDate=2015-06-12T15%3A16%3A29.594%2B02%3A00=/logo.png`The parameter is still present in the resolved URL, and the document that is created from the template of a given date will contain the image from the same date.

### Filter-based version access
A different way to access a certain version of a resource is filtering by properties. For the sake of this documentation, suppose you create a new property "custom:language", where "custom" is a namespace prefix for "[http://my.custom.namespace](http://my.custom.namespace)". Then we consider an example where several versions of a file called "file.txt" are created like this:

- version 1.0, custom:language=de, creation date: 2015-01-01T12:00:00.000+00:00

- version 1.1, custom:language=en, creation date: 2015-02-01T12:00:00.000+00:00

- version 1.2, custom:language=fr, creation date: 2015-03-01T12:00:00.000+00:00

- version 1.3, custom:language=de, creation date: 2015-04-01T12:00:00.000+00:00

- version 1.4, custom:language=en, creation date: 2015-05-01T12:00:00.000+00:00

- version 1.5, custom:language=hu, creation date: 2015-06-01T12:00:00.000+00:00

- version 1.6, custom:language=fr, creation date: 2015-07-01T12:00:00.000+00:00

- version 1.7, custom:language=hu, creation date: 2015-08-01T12:00:00.000+00:00

You can filter by the property "custom:language" by passing a parameter in the query like this: versionFilter=custom:language=en

With proper encoding, this is the URL for filter-based version access:

`http://server/=versionFilter=custom%3Alanguage%3Den=/file.txt`This query will return the content of version 1.4, which is the newest version that satisfies the query.

It is possible to combine date-based and filter-based version access:

`http://server/=versionFilter=custom%3Alanguage%3Den=/=versionDate=2015-03-12T00%3A00%3A00.000%2B00%3A00=/file.txt`This will return the content of version 1.1, which was the newest version with custom:language=en on 2015-03-12.

## Locking Resources
Resources in the repository can be locked and unlocked in accordance with the WebDAV standard, using the LOCK and UNLOCK methods. Contrary to a generic WebDAV server, the repository does not require the locking user to provide the id of the created lock (lock token) with each subsequent access on the locked resource. The owner of the lock is automatically granted access to the resource. Other users can still access the locked resource by manually providing the lock token.

### Lock Stealing
Depending on the users privileges it may be possible that a resource locked by user A is taken over by user B. In this case the lock is not removed, only the owner is changed to user B. This way it is also possible that user B takes over the work on a version checked out by user A.

## XSL Generation
The content repository can automatically generate XSL files from Infinica templates. This can be used for example to render a template in a process without being required to do the XSL generation in a separate step. For XSL generation the *xsl* parameter is appended when accessing a template:

`http://server/template.itx?xsl` As value for the *xsl* parameter, the name of a target can be provided. The default target is *fo*:

`http://server/template.itx?xsl=fo`For each target, a configuration file must be installed. Please see the

Administration Reference for details.

## ZIP Import/Export
Files or whole Directory trees can be exported directly from the repository into a ZIP archive, including all properties, ACLs and versions. The resulting ZIP file can be imported into a directory in the same or a different repository, restoring all resources exactly as they were before the export. This enables creating backups or migration of arbitrary parts of the repository.

A ZIP export is done by sending a GET request with the query parameter *zip* to the repository:

`GET: http://server/sourceDir/?zip`A ZIP import is done by sending a PUT request with the query parameter *zip* to the repository:

`PUT: http://server/targetDir/?zip`Additional properties of the export and import can be controlled with additional parameters. These parameters can be activated with the value 1 on deactivated with the value 0:

- *acl* (Import/Export): Includes the ACLs of the exported ZIP / imports them from the ZIP to the repository.

- *checkedOut* (Export): Includes the currently checked out files in the exported ZIP.

- *history* (Import/Export): Includes the version history of files into the exported ZIP / imports files from the ZIP including their versioning status and older versions.

- *virtual* (Import/Export): Includes all virtual (automatically generated) resources into the exported ZIP / imports also virtual resources (they are skipped during import otherwise).

- *path* (Export): Exports only the resources specified by the paths instead of the whole directory tree.

- *deploy* (Import/Export): Executes the ZIP import/export in deployment mode (see below). The use of deployment mode requires that deployment parameters are configured in the repository (see Admin Guide).

- *deployId* (Export): In deployment mode, adds the deployId parameter to the generated ZIP file.

- *deployName* (Export): In deployment mode, adds the deployName parameter to the generated ZIP file.

- *deployComment* (Export): In deployment mode, adds the deployComment parameter to the generated ZIP file.

- *deployTarget* (Export): In deployment mode, adds the deployTarget parameter to the generated ZIP file.

### Filter
The request header of a ZIP operation can contain a *filter* parameter for filtering the exported/imported resources based on their properties. The format is derived from the grammar defined in the DASL specification: The value of the parameter must be an XML tree corresponding to the content of the *where* element of a basicsearch query.

### Scheduled Imports
When the module `webdav-import-scheduler` is installed, scheduling of imports is available. When a submitted import specifies the parameter *time*, the import is kept in state `scheduled` until the specified time, at which time the import is executed.

Scheduled imports are persisted in the repository, and are resumed after a restart of the repository. All scheduled imports that should have taken place while the repository was not running will be executed as soon as the repository is running again.

### Deployment
Executing a *ZIP Export* operation in deployment mode does the following things in addition to a normal ZIP export:

- adds a file [deploymentSettings.properties](http://deploymentSettings.properties) to the generated ZIP with the following parameters:

deployId (if specified in the request)

- deployName (if specified in the request)

- deployComment (if specified in the request)

- deployTarget (if specified in the request)

- deploySource (if configured in the deployment settings - see Admin Guide)

- deploySourcePublicKey (if configured in the deployment settings - see Admin Guide)

- adds a file [signature].xml to the generated ZIP that contains a signed (encrypted) hash value of the ZIP content. The server's private deployment key is used for the signature (see Admin Guide).

Executing a *ZIP Import* operation in deployment mode does the following things in addition to a normal ZIP import:

- verifies that the ZIP file is signed, and that the signature matches the public key of the source

- verifies that the specified target is either empty or matches its own deployment ID

- verifies that the specified source is in its list of accepted deployment sources

- refuses the import with an exception if any of the above verifications fails

- does not require write access or the ZIP import privilege in order to execute (runs in admin mode), rather checks for the infinica:deploy privilege

The last item on the list means that it is not necessary to grant write access to users on the production environment, which would allow them to make unchecked changes of any kind. The users can still perform deployments from pre-approved sources.

## Performance Statistics
If performance logging is enabled in the repository configuration, the current performance statistics can be queried via two properties on the folder `/.system`:

Property

Description

`infinica:performance-statistics`

Provides an XML structure containing the performance statistics of all recorded WebDAV method calls.

`infinica:property-performance-statistics`

Provides an XML structure containing the performance statistics of all recorded WebDAV property evaluations.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}