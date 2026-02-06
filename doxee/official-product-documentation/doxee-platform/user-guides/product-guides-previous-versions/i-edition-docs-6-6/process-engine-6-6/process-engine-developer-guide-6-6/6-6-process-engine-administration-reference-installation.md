---
id: "135e1732-3985-4bec-b2ff-be19fb822a88"
title: "Installation"
slug: "6-6-process-engine-administration-reference-installation"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Engine"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-04T10:14:45.869Z"
modified_at: "2025-08-20T18:39:34.111Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-process-engine-administration-reference-installation"
synced_at: "2026-01-28T21:01:33.279Z"
checksum: "9c63af371e328490"
---

Navigate to other release versions of Doxee Platform Process Engine

[6.6](https://docs.doxee.com/docs/en/process-engine-6-6)

[6.7](https://docs.doxee.com/docs/en/process-engine-6-7)

This chapter describes how to install and configure a new process engine instance.

## Distribution Structure
Process Engine is provided as a set of files called a distribution. The distribution is the source for new process engine installations and also includes the documentation and examples.

The main directory of a process engine distributions contains the following folders:

**bundler**

A tool for creating process engine bundles which are used to install new instances of the process engine. Also contains the core files of the actual process engine and all modules which are part of the standard process engine distribution.

**client**

Java libraries for calling the process engine from custom Java classes.

**doc**

Documentation, including this document and all other documents that are part of the standard documentation set.

## Creating an Installation Bundle
To install Process Engine, you have to create an installation bundle using the bundler tool. This tool can be found in the bundler directory of the distribution.

Calling the bundler without parameters lists the available options:

`&gt; java -jar bundler.jar
2025-07-17T12:34:29,235 (main) [WARN] com.infinica.utils.StringUtils:80 - The default character
set on this system is windows-1252 2025-07-17T12:34:29,279 (main) [WARN] com.infinica.utils.StringUtils:81 - Consider setting it to
UTF-8 by using the file.encoding property. usage: bundler [options] [target]
 -a,--addSrc &lt;directory&gt;   additional module sources
 -b,--bundle               bundle process engine
 -c,--config &lt;arg&gt;         alternative config file
 -h,--help                 print this message
 -k,--skip                 skip additional files
 -l,--list                 list modules
 -m,--man                  generate man pages
 -o,--overwrite            overwrite destination
 -p,--skipman              skip man pages
 -s,--src &lt;arg&gt;            source directory
 -t,--target &lt;arg&gt;         target`### Listing Modules
When the bundler tool creates a bundle, it takes a set of process engine modules and combines them into a single bundle. Depending on the modules used, the resulting bundle can be a directory containing a runnable standalone version of the process engine or a web application archive that can be deployed in Apache Tomcat.

To see the list of available modules, the bundler tool can be called with the --list parameter:

`&gt; java -jar bundler.jar --list Found 3 core modules:

[cmd]  Command Line Main Module
     The command line version of the Infinica Process Engine. Can be used to run a single process or can be started as a standalone server. [service]  Service Main Module      Runs the Process Engine as a system service.
[war]  Web Application Main Module
     A web application version of the Infinica Process Engine. Can be used to deploy the process engine in an application container like Apache Tomcat. Found 22 extension modules:
[base]  Base      Common activities and XPath functions required for many processes.
[core]  Core
[database-logging]  Database Logging      Provides a logger for writing logging output to an SQL database.
[email]  E-Mail      Provides an activity for sending emails via an SMTP server.
[fo-concatenation]  FO Concatenation
[fop]  FOP
[itext]  iText
     Provides activities for using and modifying PDFs via itext. Some of the activities in this module have an input and output parameter pdf-reader. If a process uses multiple such activities with the same PDFs, the first one can map the output pdf-reader to the pipeline and the subsequent ones use the reader as input instead of the pdfs. The functionality is the same when doing this but it can improve performance because there is no need to create a new reader for each activity.
[json]  JSON Support
[lpr]  LPR
[message-logging]  Message Logging      Provides a logger for writing logging output to a message queue.
[pdf-forms]  PDF Forms
[pdf-renderer]  PDF Renderer
[pdfbox]  PDFBox      PDF utility activities based on the PDFBox library.
[postscript-handler]  PostScript Handler
[process-engine-webservice]  Process Engine Web Service Support
[resource-access]  Resource Access
[rest]  REST
[splitter]  Splitter
[storage-jpa]  JPA Storage
[template-conversion]  Template Conversion
[users]  User Access
[webservices]  Web Services`There are two different types of modules:

**Core modules**

A core module contains the process engine itself. Each bundle must include exactly one core module. Depending on the selected core module, the resulting bundle will be a command line based process engine or a web application.

**Extension modules**

This type of module can provide activities, XPath functions and loggers which can then be used by processes.

Core modules contain no activities and XPath functions whatsoever. Therefore, to be usable, a process engine bundle should at least include the `base` and `core` modules, along with any other modules that may be required by the processes you intend to run. For example, to render PDF documents with Apache FOP, the `fop` module should be included.

> Note

The `fop` module is also required to generate man pages via the Process Engine command line utility.

### Creating a Bundle
To create a bundle, the bundler tool has to be called with the `--bundle` option. Specifying this option also requires setting a target with the `--target` option. The target can be set as an (absolute or relative) URL or as a file system path.

What the target points to depends on the chosen core module:

`cmd`

This module produces a process engine that can be run from the command line or installed as a system service. The target points to a directory where the required process engine files will be generated.

`war`

This module generates a web application archive (WAR) with the specified file name. The WAR file can then be deployed in a Tomcat installation.

Finally, when calling the bundler tool with the `--bundle` option, you have to specify the modules that should be included in the generated bundle. The list of modules must include exactly one core module and may (and should) include any number of extension modules. Modules are specified via their ID as shown in brackets before the full name of each module in the module list created by the tool (see above). Multiple modules are separated by spaces.

> Note

Because they include the basic activities and XPath functions used by most processes, and also do not include any additional libraries, the `core` and `base` modules should be included in every process engine bundle.

#### Creating a Command Line Bundle
To generate a command line installation of the process engine, a bundler call like this may be used:

`&gt; java -jar bundler.jar -t C:/doxee/process-engine/ -b cmd core base fop`This will generate a complete process installation in the directory `C:/doxee/processengine/`. The installation includes the standard `core` and `base` modules and also the fop module for rendering PDFs. Such a process engine can be used to render Doxee templates.

To verify that the process engine was bundled succesfully, it can be started with the `--version` option:

`C:\doxee\process-engine&gt; java -jar infinica-process-engine.jar --version
INFINICA Process Engine 6.6.2.0`#### Creating a Web Application Bundle
To generate a web application installation of the process engine, a bundler call like this may be used:

`&gt; java -jar bundler.jar -t C:/temp/process-engine/infinica-process-engine.war -b war core base
fop`This will generate a complete process installation WAR named `infinica-processengine.war` in the directory `C:/doxee/process-engine/`. The installation includes the standard `core` and `base` modules and also the `fop` module for rendering PDFs. Such a process engine can be used to render Doxee templates.

In addition to the WAR file, two additional directories will be copied to the target directory.

To install the generated process engine bundle in an Apache Tomcat installation, perform the following steps. Tomcat’s base directory (typically the directory where Tomcat was installed) is referred to as `%TOMCAT%.`

- Stop Tomcat (if it is running)

- Copy the `infinica` directory to `%TOMCAT%.`

- Modify Tomcat’s system class path to include the directory

`%TOMCAT%/infinica/lib` (see below)

- Copy the `infinica-process-engine.war` file itself to `%TOMCAT%/webapps.`

- Start Tomcat

##### Setting Tomcat’s System Class Path
Some of Doxee’s libraries are used by low level Java classes and therefore must be loaded by the system class loader. This includes the *protocol handler* which is used to resolve URLs beginning with the *infinica:* protocol. This handler must be seen by Java’s URL class and therefore cannot be loaded by the web application’s class loader. To have these libraries loaded by the system class loader, all libraries from the directory

`%TOMCAT%/infinica/lib` have to be added to Tomcat’s system class path.

When starting Tomcat from the command line (or as a Linux service), the easiest way to extend the system class path is to create (or extend, if it already exists) the setenv file in

`%TOMCAT%/bin/:`

`setenv.sh` (on Linux systems):

`CLASSPATH=$CLASSPATH:"$CATALINA_BASE/infinica/lib/*"``setenv.bat` (on Windows systems):

`SET CLASSPATH=%CLASSPATH%;"$CATALINA_BASE\infinica\lib\*"`For Windows services, the `CLASSPATH` variable must be set in the service options, which can be configured by starting the `tomcatw.exe` utility.

##### Testing the Installation
To verify that the process engine was installed succesfully, you can access its overview page with a web browser. Assuming Tomcat is running on port 8080 on `localhost`, the overview page can be found at this URL:

`http://localhost:8080/infinica-process-engine/`Please note that this URL depends on the name of the generated WAR file. If you use a different name for your WAR file, you will also have to adapt the URL accordingly.

#### Creating a Windows Service Bundle
The process engine can run as a Microsoft Windows system service. Using the service base module will create a `service` bundle:

`&gt; java -jar bundler.jar -t C:/infinica/process-engine/ -b service core base fop`The bundle in the specified directory will contain two files `install.bat` and `uninstall.bat` that can be used to install and uninstall the service, respectively. The service will not be registered to start automatically, but this setting can be changed in the `Services` system tool found in the Windows Control Panel.

> Note

Administrative privileges may be required to run these scripts.

> Important

The installer script registers the service in the system. The process engine is still started from the directory where the installer script was started, so this directory must not be deleted as long as the service is installed.

The file `infinica-process-enginew.exe` may be run to configure the Java VM parameters of the process engine service.

#### Creating Man Pages
When creating a Process Engine bundle, the bundler will also automatically create a PDF document containing the man pages for all installed modules. It is also possible to use the bundler to create the man pages PDF only, without producing a Process Engine bundle:

`&gt; java -jar bundler.jar --man -t C:/doxee/process-engine/manpages.pdf`#### Additional Options
Some additional options can be used to control the behaviour of the bundling process:

`--overwrite`

Can be used to overwrite existing target files. Without this option, the bundler will refuse to create a new bundle if the target already exists.

`--skip`

In addition to the dynamically generated process engine JARs or WARs themselves, the bundler creates some additional files in the target location, as described above. These include default config files and, if necessary, endorsed libraries. These files do not change depending on the list of modules and are therefore considered *static files* (they may, however, change between one version of Process Engine and the next).To skip creating static files in the target location, you may specify the `--skip` option.For example, when generating the web application version of the process engine(using the war core module), this will create only the WAR file specified by the target URL. This can even be used to create the WAR file directly in Tomcat’s `webapps` directory.

`--skipman`

When creating a Process Engine bundle, the bundlers also automatically creates a man pages PDF describing all the installed modules. Use this option to skip creation of this PDF.

`--src`

When creating a new installation bundle, the bundler tool uses an *installation data *directory to read all required files from. By default, this is the data sub directory in the bundler tool’s directory.

Using the `--src` option, you can specify a different location for the installation data files, e.g. if you have created your own distribution including custom modules in a separate directory (please see to the Extension Reference for details).

## Bundler Script Files
To repeatedly generate identically configured bundles of the process engine, even with different engine versions (e.g. after an update), bundle script files can be used. One script file can be used to create one or more process engine bundles.

### The Script File
A bundler script is an XML file specifying the modules and options to be used to create a number of process engine bundles. The script file does not currently support every option available on the command line.

A script file looks like this `[1: An XSD schema for script files is included in the distribution under bundler/xsd/bundler_script.xsd]:`

`&lt;bundler xmlns="http://www.infinica.com/process-engine"&gt;
&lt;bundle target="infinica-process-engine"&gt;
&lt;module&gt;cmd&lt;/module&gt;
&lt;module&gt;core&lt;/module&gt;
&lt;module&gt;base&lt;/module&gt;
&lt;module&gt;fop&lt;/module&gt;
&lt;/bundle&gt;
&lt;/bundler&gt;`The root element, `bundler`, may optionally contain a `src` attribute which points to the directory containing the process engine’s installation data, similar to the `--src` option on the command line (see above).

Inside the root element, any number of `bundle` sections may be specified. Each bundle section creates one installation bundle of the process engine. If multiple bundles are specified, all configured bundles will be created when the script is run.

The bundle element must contain a `target` attribute specifying the target location of the bundle, like the `--target` option on the command line does. Inside the bundle, any number of `module` elements may be listed, each specifying a module that should be included in the bundle. As with regular command line calls, exactly one core module and any number of extension modules may be used per bundle.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}