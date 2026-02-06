---
id: "b94f65c5-bae1-4b28-86f8-9c45a693dc25"
title: "Characteristics"
slug: "content-repository-6-6-characteristics-1"
category: "Content Repository"
category_path:
  - "Product guides"
  - "Content Repository"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2026-01-07T13:44:21.301Z"
modified_at: "2026-01-07T14:01:41.512Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/content-repository-6-6-characteristics-1"
synced_at: "2026-01-28T20:50:33.631Z"
checksum: "0386611a0097c2a7"
---

Navigate to other release versions of Doxee Platform Content Repository

[6.6](https://docs.doxee.com/docs/en/content-repository-6-6)

[6.7](https://docs.doxee.com/docs/en/content-repository-6-7)

## Access Control
The access on files or directories and their sub-resources can be controlled by setting access control lists (ACLs). Through these lists, privileges on certain resources can be granted or denied for individual users or whole user groups. In addition to the standard privileges defined by WebDAV, Doxee defines additional ones. All the privileges available in the repository are listed in the appendix [Privileges](/doxee-platform/docs/content-repository-6-6-privileges-1). An ACL for a resource can be set using the ACL method. The access control list as defined in the WebDAV standard must be included in the request in XML form. Please note that this method does not add entries to the list but replaces the entire list for the resource identified by the URL. This means that for adding an entry to an existing list, the current list must be retrieved, the entry added to the XML and the modified list sent to the repository. ACLs can be retrieved by fetching the ACL property from the resource.

## Home Directory
The repository assigns a home directory to each individual user. This directory can be created automatically upon first access. Users can utilize their home directory for storing private files. Access by different users can be limited with ACLs. Using the default settings, the home directories are found at the path */home* and are named after the login names of their users.

The following URL can be used to access a file in a users own home directory:

`http://localhost/~/fileInHomeDir.txt`The tilde symbol (~) in the URL marks the home directory. Any path segments before this symbol are ignored, meaning that the following URL points to the same resource as the one above:

`http://localhost/some/other/path/~/fileInHomeDir.txt`It is also possible to access the home directory of a different user, by putting the login name after the tilde symbol:

`http://localhost/~username/fileInHomeDir.txt`## Digest Property
When writing a file, a digest value depending on the content and properties of file is generated. It can be used to determine if two files are identical. The digest is stored in the property *{http://www.infinica.com/jcr/namespace}digest*.

## Property Extractors
Property extractors automatically set certain file properties to a value derived from the file content when it is modified. In the current version the repository defines a property extractor for ITX files, which sets the following properties:

Property

Description

auhor

The author of the template.

company

The company of the author.

title

The title of the template.

version

The version number of the template.

dataInputNames

A list of the names of the data inputs.

testDataUrl_dataInputName

The URLs of the template test-data. For each data input a separate property is set. The name of the data input is used as suffix.

In addition to the listed properties, any property manually set in the meta data view of Template Designer is set as an accordingly named file property. All properties lie within the Infinica namespace.

## Base Path Queries
In standard HTTP and WebDAV URLs query parameters can be append to a URL like this:

`http://server/path?query`The content repository allows to alternatively write these queries as part of the URL path, e.g.:

`http://server/basePathQuery/path`The advantage is that URLs with this form can be used as base URL for resolving relative paths, such that the query parameters of the original URL also apply to the resolved URL. This allows keeping query parameters for access via transitive paths.

### Format
A traditional URL with a single query parameter can be transformed into a base path query URL like this:

`http://server/path?flag -&gt; http://server/=flag=/path`When using a parameter value the transformation looks like this:

`http://server/path?flag=value -&gt; http://server/=flag=value=/path`Multiple parameters correspond to multiple path segments in a base path query:

`http://server/path?key=value&amp;key2=value2 -&gt; http://server/=key=value=/=key2=value2=/path`## Reloading the Configuration
If the repository configuration is changed, the repository does not automatically react to the changes. The new configuration takes effect either after restarting the repository application or when a client explicitly commands the repository to reload the configuration.

This is done by sending a *PUT* request to the following address:

`http://server/.system/`This special *PUT* method does not make any changes to the `.system` directory but only causes the repository to reload its configuration files and reinitialise its modules.

> Note

Only changes to the *runtime configuration* will take effect this way. If the *bootstrap configuration* is changed, the repository *has* to be restarted for the new settings to take effect. Please refer to the Administration Reference for details.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}