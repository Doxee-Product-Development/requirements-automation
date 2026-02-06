---
id: "59914067-1c4a-4125-9843-a17840f064f1"
title: "Project Directory"
slug: "6-6-process-engine-user-guide-project-directory"
category: "Process Engine"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-06T17:05:13.815Z"
modified_at: "2025-08-19T16:57:40.894Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-user-guide-project-directory"
synced_at: "2026-01-28T21:01:21.119Z"
checksum: "fd281aa6a1bb1a07"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

Starting with version 6.0, the Doxee platform uses the concept of a *Project Directory*.

## Defining a Project Directory
Any directory, both on the file system (local or network) or in the Content Repository, can be a Project Directory by having a sub-directory .`infinica `with a project settings file `project.xml` in it. A sample of a Project Directory structure with a valid project settings file is installed with Template Designer. For Doxee to recognize a directory as Project Directory, it is enough for the file to exist. It can even be empty. You may get a few warnings in the logs, though, if it is not a valid project settings file.

> Note

Creating a Project Directory on the root level is not supported.

## Using a Project Directory
The main purpose of a Project Directory is to be used as reference point. All file references (to images, templates, processes, XMLs, …) can be made relative to the project directory by starting with `~project~`/.

This has some advantages:

- The references are not truly relative, so the same reference path works from anywhere within a Project Directory tree structure, no matter how deeply it is nested. References can be copied from one file to another, and referencing files can be moved, while all references will still work. It is no longer a concern whether relative paths used in a template part package will work from within the calling template.

- The references are not absolute either. The Project Directory can be moved to another location and all references relative to it will not be affected.

## Performance Considerations
Doxee finds the Project Directory for a given URL by moving up the parent URLs until it finds a directory with an existing file `.infinica/project.xml.`

On the file system, this is done on the client side. The lookup is usually not noticable, since the file system itself is fast enough for this kind of operation, and there is the caching of the operating system on top of that.

In the Content Repository, the lookup happens on the server. A virtual property `projectDirectory` is made available for each resource, which triggers the lookup on the server and returns the path of the Project Directory, which is always some ancestor of the given resource.

In any case, it is recommended to mark your project by a file `.infinica/project.xml`, even if you do not intend to use any of the project features. It will keep Doxee programs (Template Designer, Process Engine, Content Repository) from searching for a project directory repeatedly.

## Project Directory Settings
As of version 6.0, the settings in the file `project.xml` (`name `and `description `so far) are there purely for documentation purposes. They have no effect on the behaviour of any Doxee components.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}