---
id: "79148941-0d0f-4489-acb0-0bb20a0761e6"
title: "Configuration"
slug: "6-6-business-designer-developer-guide-configuration-3-1"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Business Designer"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-03T13:36:34.35Z"
modified_at: "2026-01-07T13:52:30.786Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-business-designer-developer-guide-configuration-3-1"
synced_at: "2026-01-28T20:49:55.101Z"
checksum: "3f7a04ddba86673d"
---

Navigate to other release versions of Doxee Platform Business Designer

[6.6](https://docs.doxee.com/docs/en/business-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/business-designer-6-7)

This chapter contains description of Business Designer configuration.

## Configuration Files
Create a new folder "infinica" in the $TOMCAT folder if it doesn’t yet exist. It will contain the configuration data for Business Designer.

- business-designer.properties

This file will contain the needed settings for Business Designer.

The configuration data is not separated into sections - there are just key/value pairs defined in the configuration file. Single rows can be commented out using the sharp symbol "#" at the beginning of the row.

- useraccess.xml

Contains the configuration for the user store. Business Designer needs to be connected to a user store for it to work properly. Usually there is one user store and one useraccess.xml for all Doxee applications. For detailed information see [User Access Configuration](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1-1#user-access-configuration).

> Important

Please note that a Tomcat restart is needed after the change of settings for this change to apply.

- business-designer-log4j2.xml

In this file logging setting for Business Designer can be adjusted. Here is sample XML configuration file - it uses **Log4j2 **format.

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;Configuration status="WARN" monitorInterval="30"&gt;
&lt;Appenders&gt;
&lt;RollingFile name="BDLog" fileName="logs/infinica-business-designer.log" filePattern="logs/$${date:yyyy-MM}/business-designer-%d{MM-dd-yyyy}-
%i.log.gz"&gt;
&lt;PatternLayout&gt;
&lt;Pattern&gt;%d %p %c{1.} [%t] %m%n&lt;/Pattern&gt;
&lt;/PatternLayout&gt;
&lt;Policies&gt;
&lt;TimeBasedTriggeringPolicy  /&gt;
&lt;SizeBasedTriggeringPolicy  size="25  MB"/&gt;
&lt;/Policies&gt;
&lt;DefaultRolloverStrategy max="20"/&gt;
&lt;/RollingFile&gt;
&lt;/Appenders&gt;
&lt;Loggers&gt;
&lt;Logger name="com.infinica.web.tdwng" level="debug" additivity="false"&gt;
&lt;AppenderRef ref="BDLog"/&gt;
&lt;/Logger&gt;
&lt;Root level="info"&gt;
&lt;AppenderRef ref="BDLog"/&gt;
&lt;/Root&gt;
&lt;/Loggers&gt;
&lt;/Configuration&gt;`> Note

Changes to logging configuration are picked up automatically (without server restart). You can see the setting of *monitorInterval *attribute - defines how often the config file will be checked for changes in seconds.

There is only one type of log file defined.

- infinica-business-designer.log - regular application log

## business-designer.properties
The entries could be split into several conceptual sections but this is not enforced. In the main section we could gather the essential configuration entries.

Example snippets of file "business-designer.properties" are as follows:

`# configurable application browser title application.title = DOXEE Business Designer
icr.location = http://localhost:8080/infinica-content-repository icr.externalPaths = PROJECT_RELATIVE
userAccessManager.location = infinica/useraccess.xml #infinicaAuthentication.location=infinica/authentication.xml  font.folder.location = @localConfigurationPath/fonts fop.config.xml.location = infinica/fop_config.xml
composer.location = https://localhost:8443/workplace/live-composer.hbs
composer-next.location https://integration16.infinica.com/infinica-composer/document
# master templates configuration #master.templates.locations = /master-templates
# flat / hierarchical master.templates.strategy = flat master.templates.templateNameAsPrefix = true master.templates.customPrefix = master.templates.customSuffix = master.templates.alwaysShowSummary = true
# example of client extensions configuration (Optional) extensions.sharepoint.available  =  true extensions.sharepoint.baseURL = https://sharepoint.infinica.com/api extensions.sharepoint.createAPI = /document extensions.sharepoint.beforeChangeAPI = /metadatachangeinitiator extensions.sharepoint.afterChangeAPI = /metadatachange extensions.sharepoint.retrieveAPI = /metadata
extensions.sharepoint.extraHeaders = AuthKey:123456,Content-Type:application/json;charset=UTF-8 extensions.sharepoint.documentTypeField = document-type extensions.sharepoint.documentTypeValues = WorkInstruction,Chunk
extensions.sharepoint.tenantId  =  Dev01
# email preview (Optional) process.email_preview.available = true
process.email_preview.engine.uri = http://localhost:8080/infinica-process-engine/rest process.email_preview.process.uri = processes/email-preview/simpleEmailHTMLPreview.ipd #process.email_preview.user.name = infa
#process.email_preview.user.password = password process.email_preview.output.format = html
#extensions extensions.link.referenceUrlPattern =
https://infinica.com?oid=[BD_TEMPLATE_ROOT_ID]&amp;documentType=[BD_DOCUMENT_TYPE]&amp;path=[BD_DOCUMENT
_PATH]&amp;fileName=[BD_TEMPLATE_FILE_NAME] extensions.condition.toggleLayout.available = true extensions.imagePaste.available = true extensions.imagePaste.maxSizeMB = 2 extensions.templateComparison.available = true
# Max Allowed Size for XML Data Sample Files (default is 1048576 bytes ~ 1MB) extensions.elements.dataSample.maxAllowedSize = 1048576
# spellcheck
#spellcheck.dictionaries.directory = file:///c:/local-icr/dict #spellcheck.dictionaries.languages = en_GB, British; it_IT, Italian;de_DE, German
# Help and Video Tutorials configs help.video.vimeoApi = https://api.vimeo.com
help.video.vimeoAuthorizationHeader = Bearer 67abe386c1140301c45c4ea2dcaeb9ac help.video.available = true`- application.title: *Optional. *Indicates the application name visible in the browser as a tab or window title. Defaults to "DOXEE Business Designer".

- icr.location: *Required. *URL specifies where the Doxee Content Repository app is running (server/port). By default, it is assumed that the Doxee Content Repository application runs on the same server as Business Designer.

- icr.externalPaths: *Optional. *It has 3 possible values `PROJECT_RELATIVE`, `FILE_RELATIVE`and `ABSOLUTE` defaulting to `PROJECT_RELATIVE`. Chosen strategy will influence how paths to external resources are generated.

`PROJECT_RELATIVE` - when including resource from project directory, path will contain ~project~ placeholder which will be correctly resolved against project directory. This makes transferring templates and its resources much easier.

- `FILE_RELATIVE` - generated paths are relative to the template.

- `ABSOLUTE` - This one is discouraged to use as it makes transferring templates to different environments possibly harder.

- userAccessManager.location: *Required. *Location of useraccess.xml. Default value is infinica/useracces.xml.

- infinicaAuthentication.location: *Optional. *Location of the Authentication Configuration file (required for OAuth/Alfa security).

- font.folder.location: *Optional. *Defines the path to a folder where font files in ttf format are stored. This is used mainly by FOP Renderer.

- fop.config.xml.location: *Optional. *Location of "fop_config.xml" file. Default value is infinica/fop_config.xml.

- fo.to.html.xsl.location: *Optional. *Location of "fo2html.xsl" Fo2Html XSL stylesheet file. Default value is infinica/fo2html.xsl.

- template.serializer.emptyblockcontent: *Optional. *String value for the template serializer indicating the content for empty blocks. Defaults to non-breaking space character. Any whitespace character needs to be escaped with \. Example contains ASCII 160 (non- breaking space)

- composer.location: *Optional. *URL specifies where the Composer app is running (server/port) so that it is possible to preview templates in Composer. By default, it is assumed that the Composer application runs on the same server as Business Designer. If it is not specified then it defaults to the same server where Business Designer is deployed on with "/composer/live-composer.hbs" context. Composer has to be accessed securely. If Composer preview is not required and will be always hidden via Business Designer roles then this setting may be omitted.

- master.templates.locations: *Optional. *Comma-separated list of ICR paths - relative location to the root of Content Repository of a folder or folders containing master templates. Master templates are templates for templates.

- master.templates.strategy: *Optional. *Can be flat or hierarchical. Hierarchical means that Business Designer will try to copy template resources in the same folder structure as they originally were relative to the master template. Flat means there will be no attempt to recreate the folder structure.

- master.templates.templateNameAsPrefix: *Optional. *Default "true". True means that copied resources filenames will be prefixed with template name.

- master.templates.customPrefix: = *Optional. *Default is no prefix.

- master.templates.customSuffix: = *Optional. *Default is no suffix.

- master.templates.alwaysShowSummary: *Optional. *Default "true".

- custom.component.templates.locations: *Optional. *Comma-separated list of ICR paths - relative location to the root of Content Repository of a folder or folders containing templates or template part packages which define template parts which will be potentially shown as Custom Components in the Palette of Business Designer.

Next section is related to HTML Email preview feature. To enable Email preview feature

Process Engine needs to be installed and properly set up, and the email-generating process file needs to be available.

- process.email_preview.available: Determines if the Email preview is available in the Business Designer at all. By default it is false.

`process.email_preview.available = true
process.email_preview.engine.uri = https://sampleurl.com/infinica-process-engine/rest process.email_preview.process.uri = processes/email-preview/simpleEmailHTMLPreview.ipd # name + password might be empty, then current user will be used process.email_preview.user.name = infa
process.email_preview.user.password = password process.email_preview.output.format = html`
- process.email_preview.engine.uri: URL to the running Process Engine.

- process.email_preview.process.uri = Relative path to the .ipd Ininica process file that is configured to process a template into HTML email.

- process.email_preview.user.name: Optional user name for Process Engine. By default, the name of current user is used.

- process.email_preview.user.password: Optional password for Process Engine. By default, the password of current user is used.

- process.email_preview.output.format: Output format. By default, "html" is used.

Besides predefined set of output formats, you can define custom document previews by calling external Process Engine. Preview process requires precise input and output parameters to be able to create document.

> Note

This is further described in *Template Designer *documentation (Preview Processes chapter)

`#process preview process.preview.html.label=Html 
process.preview.html.available=true
process.preview.html.engine.uri=https://sampleurl/infinica-process-engine/rest  
process.preview.html.process.uri=processes/email-preview/simpleEmailHTMLPreview.ipd  
process.preview.html.renderer=xsl
process.preview.html.format=html process.preview.html.order=1

process.preview.pdf.label=Pdf 
process.preview.pdf.available=true
process.preview.pdf.engine.uri=https://sampleurl/infinica-process-engine/rest 
process.preview.pdf.process.uri=processes/renderFo.ipd 
process.preview.pdf.renderer=fop
process.preview.pdf.format=pdf 
process.preview.pdf.user.name=test 
process.preview.pdf.user.password=password`> Note

Configuration for custom process preview must start with *process.preview. *In this case 2 different preview processes were created. Wording *pdf *and *html *is up to the user.

- label: *Required. *Name of the configuration as it will be presented to the user.

- available: *Optional. true*/*false *value (defaulting to *true*), affecting availability in the UI.

- engine.uri: *Required. *URL to Process Engine instance.

- process.uri: *Required. *Path to the rendering process within the engine.

- renderer: *Required. *Renderer used in the process. This is passed as *target.renderer *parameter to the preview process. Common values are:

- fop

- xfc

- xep

- format: *Required. *Output format passed to the process as *target.format*. Common values are *pdf*, *docx*, *rtf*, *odt*, *ps*, *html*, *assert*. In case you want to produce *fo *output, specify format as *fo*, too.

- fo: *Optional. true*/*false *value (default is *false*). When set to *true*, XSL result from the transformation step will be returned instead of document. Might be useful for debug purposes.

- user.name: *Optional *user name for Process Engine call. By default, the name of current user is used.

- user.password: *Optional *password for Process Engine call. By default, the password of current user is used.

- order: *Optional *number determining order of menu items in the UI. Items are ordered randomly, unless this is specified.

Snippet below shows configuration for external preview/links. This way, one can start Workplace process from Business Designer or generally open predefined link in a new tab.

`external.preview.wp.label=Workplace 
external.preview.wp.available=true
external.preview.wp.url=https://test.infinica.com/workplace/rest/humantask/start-  
process?process=workplace-default-flow2.ipd
external.preview.wp.order=1 
external.preview.sf.label=Salesforce 
external.preview.sf.available=true
external.preview.sf.url=https://test.infinica.com/workplace/rest/humantask/start- 
process?process=demo/salesforce.ipd&amp;parameters={"templatePath": ["{templatePath}"]} 
external.preview.sf.order=2`> Note

Configuration for external preview is similar to **process preview **- it must start with *external.preview. *In this case 2 different external links were created. Wording *wp *and *sf *is up to the user.

- label: *Required. *Name of the configuration as it will be presented to the user.

- available: *Optional. true*/*false *value (defaulting to *true*), affecting availability in the UI.

- url: *Required*. This link will be opened in a new tab after clicking.

- order: *Optional *number determining order of menu items in the UI. If not specified, order is not deterministic.

> Note

These placeholders can be used in the link definition

{templatePath} - path to the opened template in the repository

- {lang} - current language

`extensions.sharepoint.available = true 
extensions.sharepoint.baseURL = https://example-sharepoint-link.com 
extensions.sharepoint.createAPI = /api/document 
extensions.sharepoint.retrieveAPI = /api/metadata
extensions.sharepoint.extraHeaders = AuthKey:123456,Content-Type:application/json;charset=UTF-8 
extensions.sharepoint.beforeChangeAPI = /metadatachangeinitiator 
extensions.sharepoint.afterChangeAPI = /metadatachange
extensions.sharepoint.documentTypeField = document-type 
extensions.sharepoint.documentTypeValues = type1,type2`- These entries are important for extending normal Metadata feature of Business Designer with Sharepoint. By default, it is hidden when not present in the configuration file.

- extensions.sharepoint.extraHeaders: A comma-separated list of key:value pairs used to be set into request headers.

`extensions.link.referenceUrlPattern = 
https://infinica.com?oid=[BD_TEMPLATE_ROOT_ID]&amp;documentType=[BD_DOCUMENT_TYPE]`
- This is an optional configuration. It enables creating links between resources in repository. The user is able to select the resource when creating *Link *element in editor and its root element id and document type are used to replace the pattern placeholders. In this case the [BD_TEMPLATE_ROOT_ID] is replaced with the value of the root id and [BD_DOCUMENT_TYPE] is replaced with the value of document type. New placeholders cannot be added without development effort from Doxee. There are also other optional placeholders - [BD_DOCUMENT_PATH] is replaced with the path to the file and [BD_TEMPLATE_FILE_NAME] is replaced with the file name. Path and name are then shown in the Link dialog if they are configured and available. Since also XPath can be used the entry may look like this:

`extensions.link.referenceUrlPattern   =   {concat('https://infinica.sharepoint/sites/',
$user-id, '/SomePages/SOME-Viewer.aspx', '?oid=[BD_TEMPLATE_ROOT_ID]', '&amp;documentType=[BD_DOCUMENT_TYPE]',
'&amp;path=[BD_DOCUMENT_PATH]', '&amp;fileName=[BD_TEMPLATE_FILE_NAME]')}`> Note

Resolved URL may at the end look like this: "https://infinica.sharepoint/sites/some-user-id/SomePages/SOME-Viewer.aspx?oid=TemplateRoot- xXyY&amp;documentType=SomeInstruction&amp;path=/some_folder/some_file.itx&amp;

fileName=some_file.itx"

`extensions.condition.toggleLayout.available=true`
- This is an optional configuration. It enables displaying of simplified condition toggle element in editor.

`extensions.imagePaste.available = true 
extensions.imagePaste.maxSizeMB = 4`
- By default pasting images to editor is enabled. Maximum size of image is 4MB.

`extensions.templateComparison.available = true`
- Optional configuration. Enables triggering visual comparison of 2 templates from UI. It is enabled by default.

`extensions.autoSave.intervalInSeconds  =  30`
- Optional configuration. Templates can be auto saved, if this is enabled by the user. Saving will be triggered after 30 seconds of inactivity (in case there are any changes in the template). Default value is 30 seconds.

`extensions.elements.dataSample.maxAllowedSize = 1048576`
- Optional configuration. Test Data XML files should have some reasonable size and should not exceed certain acceptable values. This option allows to set the upper limit to maximum allowed file size in bytes. Default value is 1048576 bytes (~1MB). If the value is too large then Business Designer can become unresponsive.

`#Help and Video Tutorials configuration 
help.video.available = true 
help.video.vimeoApi = https://api.vimeo.com/
help.video.vimeoAuthorizationHeader  =  Bearer  67abe386c1140301c45c4ea2dcaeb9ac`This configuration is needed in order to be able to see all the Business Designer video tutorials.

`spellcheck.dictionaries.directory  =  file:///c:/local-icr/dict 
spellcheck.dictionaries.languages = en_GB, British; de_DE, German`> Warning

Don’t forget to add your dictionary files in the defined folders ***/dict***

These 2 options are used for the spellcheck configuration. Business Designer can use [Hunspell dictionaries](http://hunspell.github.io/) for spellchecking. If this is configured, then text in template is checked as user types. Suggestions for typos are provided based on these dictionaries.

- spellcheck.dictionaries.directory: Directory with Hunspell dictionaries. For each language, there must be 2 files. Dictionary file (having .dic suffix) and affixes file (with.aff suffix).

- spellcheck.dictionaries.languages: Comma separated dictionary definition. Semicolon is used for defining more than one language.

> Note

Defining *en_GB, British; de_DE, German *as dictionaries languages will define 2 available dictionaries which can be used in BD. User can choose from *British *or *German *dictionary in the application (This part of configuration is used as label in UI). 4 files must exist on the server in *c:/local-icr/dict *directory - en_GB.dic, en_GB.aff, de_DE.dic and de_DE.aff. Hunspell dictionaries need to be downloaded and used to enable spellchecking feature. BD is not shipped with any dictionaries for spellcheck because of licensing limitations. Here is a list of available dictionaries [https://github.com/wooorm/dictionaries#list-of-dictionaries](https://github.com/wooorm/dictionaries#list-of-dictionaries) informing that each language might have different license options.

There is possibility to define default values for attributes which are set after element is created in the editor. At the moment, it is supported only on *reference *element. Example shows that default value for *src-type *attribute in *reference *element is selective.

`element.configuration.reference.src-type.default = selective`In order to get the **AI features **up and running, following settings must be properly configured :

`# AI Support (commented config items are optional with default values)

# OPEN AI
openai.enabled = true openai.api.token = [OPENAI_API_TOKEN] # openai.api = /v1/chat/completions
# openai.image.api = /v1/images/generations # openai.image.model = dall-e-3
# openai.image.number = 1
# openai.image.quality = standard # openai.image.size = 1024x1024
# openai.image.style = natural # openai.max-tokens = 500
# openai.model = gpt-3.5-turbo # openai.temperature = 0.7

# MISTRAL AI
mistral.enabled  =  true mistral.api.token = [MISTRAL_API_TOKEN] # mistral.api = /v1/chat/completions
# mistral.max-tokens = 250
# mistral.model = mistral-small-latest # mistral.temperature = 0.7

# DEEPL AI
deepl.enabled = true deepl.api.token = [DEEPL_API_TOKEN]
# deepl.api.languages = /v2/languages # deepl.api.translate = /v2/translate
# deepl.base-url = https://api.deepl.com

# GOOGLE GEMINI AI
gemini.enabled = true
gemini.api.token  =  [GOOGLE_GEMINI_API_TOKEN]
# gemini.api = /v1
# gemini.base-url = https://generativelanguage.googleapis.com # gemini.model = gemini-1.5-flash-latest

# AZURE OPEN AI
# general mandatory settings 
azure.openai.enabled = true
# both types (chat and image generation) can share token and base-url 
azure.openai.api.token = [AZURE_OPENAI_CHAT_API_TOKEN] 
azure.openai.base-url = [AZURE_OPENAI_CHAT_BASE_URL] 
azure.openai.image.api.token = [AZURE_OPENAI_IMAGE_API_TOKEN] 
azure.openai.image.base-url = [AZURE_OPENAI_IMAGE_BASE_URL]
# specific CHAT API settings
# https://learn.microsoft.com/en-us/azure/ai-services/openai/chatgpt-quickstart 
azure.openai.api = /chat/completions
azure.openai.api.version = 2024-02-15-preview 
azure.openai.deployment-name = gpt-35-turbo
# these are optional
# azure.openai.max-tokens = 250 
# azure.openai.temperature = 0.8
# specific IMAGE GENERATION settings (support for Dall-E-3 model only)
# https://learn.microsoft.com/en-us/azure/ai-services/openai/dall-e-quickstart 
azure.openai.image.api = /images/generations
azure.openai.image.api.version = 2024-02-01 
azure.openai.image.deployment-name = dall-e-3 
# these are optional
# azure.openai.image.quality = standard 
# azure.openai.image.size = 1024x1024
# azure.openai.image.style = natural`### OPEN AI
- openai.enabled: optional true / false value. Default value is "false". If value is set to "true", correct openai.api.token is required too.

- openai.api.token: represents the valid OpenAI token. Don’t hesitate to ask for one directly via our support support@infinica.com.

- openai.api: in order to get the AI chat features working, completions api is by default set to "/v1/chat/completions".

- openai.max-tokens: the maximum number of tokens that can be generated in the chat completion. Higher number means more tokens allowed within request / response generation. You can think of tokens as pieces of words, where 1,000 tokens is about 750 words. The more tokens you spent, the more you pay. Default is unlimited.

- openai.model: define the AI model to communicate with. You can use for example gpt- 3.5-turbo or gpt-4. Default model is gpt-3.5-turbo.

> Note

There is significant cost difference per 1,000 tokens between those models.

- openai.image.api: the OpenAI Image Generation API URI

- openai.image.model: the model to use for image generation.

- openai.image.number: the number of images to generate. Must be between 1 and 10. 

For model dall-e-3, only 1 is supported.

- openai.image.quality: the quality of the image that will be generated. *hd *creates images with finer details and greater consistency across the image. This param is only supported for dall-e-3.

- openai.image.size: the size of the generated images. Must be one of 256x256, 512x512, or 1024x1024 for dall-e-2. Must be one of 1024x1024, 1792x1024, or 1024x1792 for dall-e-3 models.

- openai.image.style: the style of the generated images. Must be one of *vivid *or *natural*. Vivid causes the model to lean towards generating hyper-real and dramatic images. Natural causes the model to produce more natural, less hyper-real looking images. This param is only supported for dall e-3.

- openai.temperature: the sampling temperature, between 0 and 1. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic. If set to 0, the model will use log probability to automatically increase the temperature until certain thresholds are hit.

- openai.temperature: what sampling temperature to use, between 0 and 2. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic.

## MISTRAL AI
- mistral.enabled: optional true / false value. Default value is "false". If value is set to "true", correct mistral.api.token is required too.

- mistral.api.token: represents the valid Mistral AI API token. Don’t hesitate to ask for one directly via our support support@infinica.com.

- mistral.api: the Mistral AI Conversation API URI

- mistral.max-tokens: the maximum number of tokens that can be generated in the chat completion. Higher number means more tokens allowed within request / response generation. You can think of tokens as pieces of words, where 1,000 tokens is about 750 words. The more tokens you spent, the more you pay. Default is unlimited.

- mistral.model: ID of the model to use. Please see the [Model Overview](https://docs.mistral.ai/models) for model descriptions.

- mistral.temperature: what sampling temperature to use, between 0.0 and 1.0. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic.

## DEEPL
- deepl.enabled: optional true / false value. Default value is "false". If value is set to "true", correct deepl.api.token is required too.

- deepl.api.languages: the DeepL API URI for fetching a list of supported languages

- deepl.api.token: represents the valid DeepL API token. Don’t hesitate to ask for one directly via our support support@infinica.com.

- deepl.api.translate: the DeepL API URI for translation services

- deepl.base-url: it’s a default base DeepL API URL which is used in conjunction with API URIs

## GOOGLE GEMINI AI
- gemini.enabled: optional true / false value. Default value is "false". If value is set to "true", correct gemini.api.token is required too.

- gemini.api.token: represents valid GOOGLE Gemini API token. Don’t hesitate to ask for one directly via our support support@infinica.com.

- gemini.api: the GOOGLE Gemini AI Conversation API URI

- gemini.base-url: it’s a default base GOOGLE Gemini API URL which is used in conjunction with chat URI

- gemini.model: ID of the model to use. Please see [Gemini Models](https://ai.google.dev/gemini-api/docs/models/gemini) for model descriptions.

## AZURE OPEN AI
- azure.openai.enabled: optional true / false value. Default value is "false". If value is set to "true", all mandatory values should be set too.

- azure.openai.api.token: represents valid Azure OpenAI API token for conversation API. Don’t hesitate to ask for one directly via our support support@infinica.com.

- azure.openai.base-url: represents valid base URL of the Azure OpenAI Chat API service, *example: *[*https://doxee-openai.openai.azure.com*](https://doxee-openai.openai.azure.com/)

- azure.openai.image.api.token: represents valid Azure OpenAI API token for Image Generation API. It can be the same token as used for Chat API, but also can be completely independent. Don’t hesitate to ask for one directly via our support support@infinica.com.

- azure.openai.image.base-url: represents valid base URL of the Azure OpenAI Image Generation API service, *example: *[*https://doxee-openai-image.openai.azure.com*](https://doxee-openai-image.openai.azure.com/). It can also be the same as for Chat API.

- azure.openai.api = valid Azure OpenAI chat conversation API URI, *example: /chat/completions*

- azure.openai.api.version = valid version of the chat API, *example: 2024-02-15-preview*

- azure.openai.deployment-name = represents the name under which the AI model is deployed into Azure OpenAI service, can be the same as the name of the AI model, but this is not required, *example: my-gpt35-turbo*

- azure.openai.image.api = valid Azure OpenAI image generation API URI for Dall-E-3 model only, *example /images/generations*

- azure.openai.image.api.version = valid version of the image generation API, *example: 2024-02-01*

- azure.openai.image.deployment-name = represents the name under which the AI model for image generation (dall-e-3 supported only) is deployed into Azure OpenAI service, can be the same as the name of the AI model, but this is not required, *example: my-dalle3*

- azure.openai.image.quality = *same meaning as for OpenAI*

- azure.openai.image.size = *same meaning as for OpenAI*

- azure.openai.image.style = *same meaning as for OpenAI*

- azure.openai.max-tokens = *same meaning as for OpenAI*

- azure.openai.temperature = *same meaning as for OpenAI*

## business-designer-roles.properties
Two kinds of entries are possible in this configuration file. First predefined roles and rights may be assigned to a custom role. Second the predefined roles and rights and also custom roles can be assigned to the specific users or groups.

First three entries are definitions of custom roles by mapping a set of predefined keywords representing rights, for example RIGHT_E_BLOCK. Custom role may be defined also by mapping of any combination of other custom roles, predefined roles and basic rights into it. Custom role name must always start with upper-case prefix "ROLE_" and can contain any combination of upper or lower case English characters. Names of predefined roles and rights are always upper-case.

`# custom roles
ROLE_CUSTOM_A = RIGHT_E_BLOCK, RIGHT_E_TEXT, RIGHT_E_TABLE
ROLE_CUSTOM_B = RIGHT_E_CONDITION, RIGHT_E_CONDITION_BRANCH, RIGHT_E_REPEAT 
ROLE_CUSTOM_C = ROLE_BUSINESS_USER, RIGHT_E_CONDITION, RIGHT_E_CONDITION_BRANCH

# assigning roles to users/groups 
user:infa = ROLE_ADMINISTRATOR 
user:infb = ROLE_BUSINESS_USER 
user:test.* = ROLE_BUSINESS_USER 
user:infc = ROLE_POWER_USER 
user:infd = ROLE_READER 
group:powerUser.* = ROLE_POWER_USER 
user:infe = ROLE_CUSTOM_A
user:inff = ROLE_CUSTOM_A, RIGHT_E_CONDITION, RIGHT_E_CONDITION_BRANCH 
#user:.* = ROLE_POWER_USER`Further entries represent a mapping of any combination of custom roles, predefined roles and basic rights to users or groups existing in the connected user store. For example entry:

grants the user with username "infa" all existing rights in Business Designer. Wildcards can be also used so that entry:

`user:infa  =  ROLE_ADMINISTRATOR`would grant almost all rights existing in Business Designer (with single exception of right RIGHT_S_ADMIN_CONTENT) to all users. This way it is possible to practically disable the whole concept of rights and roles in Business Designer if that is a business requirement.

`user:.*  =  ROLE_POWER_USER`Example assignment of a role to all the groups starting with string "powerUser":

`group:powerUser.* = ROLE_POWER_USER`It is preferable to assign roles to groups (not users) to make use of the group membership and due to the ease of maintenance. Users can be added to the group in the runtime using third-party tools or Administrator. Assignment to group works the same way as assignment to users. Any users belonging to the specific group inherit the role granted to that group. Changes of the role mapping are applied after the Tomcat restart.

> Note

To successfully login to Business Designer, user needs to have a role or right assigned. Otherwise, access is denied.

Following table lists all available keywords representing rights and contains information which predefined hardcoded role contains which rights:

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_E_BLOCK

enables element in palette and editor

X

X

X

RIGHT_E_LIST

enables element in palette and editor

X

X

X

RIGHT_E_CONTAINER

enables element in palette and editor

X

X

X

RIGHT_E_COMMENT

enables element in palette and editor

X

X

X

RIGHT_E_EXTERNAL_DOCUMENT

enables element in palette and editor

X

X

X

RIGHT_E_IMAGE

enables element in palette and editor

X

X

X

RIGHT_E_LINK

enables element in palette and editor

X

X

X

RIGHT_E_TEXT

enables element in palette and editor

X

X

X

RIGHT_E_TEMPLATE_PART_REFERE NCE

enables element in palette and editor

X

X

X

RIGHT_E_TEMPLATE_PARTS

enables adding, removing and adjusting properties of “Template Part” element

X

X

RIGHT_E_TEMPLATE_PART

enables adjusting properties of “Template Parts”

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_E_INSERTIONPOINT

enables element in palette and editor

X

X

RIGHT_E_BARCODE_ASPOSE

enables element in palette and editor

X

X

RIGHT_E_COMPOSER_ELEMENT

enables element in palette and editor

X

X

RIGHT_E_CONDITION

enables element in palette and editor

X

X

RIGHT_E_CONDITION_BRANCH

enables element in palette and editor

X

X

RIGHT_E_DYNAMIC_VALUE

enables element in palette and editor

X

X

RIGHT_E_DYNAMIC_BLOCK

enables element in palette and editor

X

X

RIGHT_E_REFRESHABLE

enables element in editor

X

X

RIGHT_E_REPEAT

enables element in palette and editor

X

X

RIGHT_E_VARIABLE

enables element in palette and editor

X

X

RIGHT_E_PAGE_NUMBER

enables element in palette and editor

X

X

RIGHT_E_PAGE_SEQUENCES

enables element in palette and editor

X

X

RIGHT_E_PAGE_SEQUENCE

enables element in palette and editor

X

X

X

RIGHT_E_PAGE_CONTENT

enables element in palette and editor

X

X

RIGHT_E_TABLE

enables element in palette and editor

X

X

X

RIGHT_E_TEXT_FIELD

enables element in palette and editor

X

X

X

RIGHT_E_TEXT_AREA

enables element in palette and editor

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_E_BUTTON

enables element in palette and editor

X

X

X

RIGHT_E_RADIO

enables element in palette and editor

X

X

X

RIGHT_E_CHECKBOX

enables element in palette and editor

X

X

X

RIGHT_E_COMBOBOX

enables element in palette and editor

X

X

X

RIGHT_E_LISTBOX

enables element in palette and editor

X

X

X

RIGHT_E_LEADER

enables element in palette and editor

X

X

X

RIGHT_E_STYLE_GROUP

enables style/group editing in editor

X

X

RIGHT_E_STYLE_SET

enables style/set editing in editor

X

X

RIGHT_E_DECIMAL_FORMAT

enables decimal format element editing in

/decimal- formats view

X

X

RIGHT_E_METADATA

allows editing of metadata. Based on this right also rights for

&lt;entry&gt;,

&lt;docinfo&gt; and

&lt;docinfo-field&gt; elements are resolved

X

X

RIGHT_E_REFERENCE

allows adding of external references

X

X

RIGHT_E_PAGE_MASTER

allows editing of page masters

X

X

RIGHT_E_OUTPUT_CONFIG

allows editing of output config

X

X

X

RIGHT_E_NUMBERING_SCHEME

allows editing of numbering schemes

X

X

X

RIGHT_E_NUMBERING_REFERENCE

allows editing of numbering reference

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_E_NAMESPACE

allows editing of namespace

X

X

X

RIGHT_E_BOOKMARK

allows editing of bookmark

X

X

X

RIGHT_E_TABLE_OF_CONTENTS

allows editing of table of contents

X

X

X

RIGHT_E_WRAPPER

allows editing of wrapper element

X

X

RIGHT_S_ADMIN_CONTENT

overrides content-security rights set on a document and gives user right to all content changes

X

RIGHT_S_FILEPICKER_HIDDEN_FOL DERS

allows listing of hidden folders (.infinica folders) in file picker

X

RIGHT_S_MASTER_TEMPLATES_M ODIFY_ACTION_STATE

Show copy/rebase options when creating template from master template

X

RIGHT_V_PAGE_MASTERS

allows usage of page masters section

X

X

RIGHT_V_STYLES

allows usage of styles section

X

X

X

RIGHT_V_DECIMAL_FORMATS

allows usage of decimal-formats section

X

X

X

RIGHT_V_TEST_DATA

allows usage of test-data section

X

X

RIGHT_V_META_DATA

allows usage of meta-data section

X

X

RIGHT_V_GLOBAL_VARIABLES

allows usage of variables section

X

X

RIGHT_V_EXTERNAL_RESOURCES_ MANAGEMENT

allows usage of external resources management section

X

X

X

RIGHT_V_NUMBERING

allows usage of numbering section

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_CONTEXT_MENU_EDIT_F REE_TEXTS

allows editing of FREE-TEXTS

elements

X

X

RIGHT_O_PREVIEW_PDF

allows generating pdf preview

X

X

X

RIGHT_O_PREVIEW_DOCX

allows generating docx preview

X

X

X

RIGHT_O_PREVIEW_HTML

allows generating html preview

X

X

RIGHT_O_PREVIEW_FO

allows generating fo preview

X

X

RIGHT_O_PREVIEW_XSLT_FO

allows generating xslt- fo preview

X

X

RIGHT_O_PREVIEW_FOP

allows generating fop preview

X

X

RIGHT_O_PREVIEW_ITX

allows generating itx preview

X

X

RIGHT_O_PREVIEW_COMPOSER

allows generating Composer preview

X

X

X

RIGHT_O_PREVIEW_COMPOSER_N EXT

allows generating Composer Next preview

X

X

X

RIGHT_O_PREVIEW_EMAIL

allows generating email preview

X

X

RIGHT_O_PREVIEW_FOP_INTERME DIATE

allows generating fop intermediate preview

X

X

RIGHT_O_PREVIEW_ZIP_INTERME DIATE

allows generating zip intermediate preview

X

X

RIGHT_O_PREVIEW_PROCESSES

allows generating preview from all defined dedicated processes

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PREVIEW_PROCESSES_[ NAME]

allows generating preview from dedicated process. [NAME] must be replaced by the name of the process preview entry you want to display in upper case (for example "HTML_XY" for "process.preview

.html_xy.label")

RIGHT_O_PREVIEW_EXTERNAL_LIN KS

allows additional preview using all defined external links

X

X

RIGHT_O_PREVIEW_EXTERNAL_LIN KS_[NAME]

allows additional preview using using dedicated external link. [NAME] must be replaced by the name of the external link preview entry you want to display in upper case (for example "WP_XY" for "external.previe w.wp_xy.label")

RIGHT_O_USE_AI_CHAT_ASSISTAN T

sets the visibility of section "AI chat"

X

X

X

RIGHT_O_USE_OUTPUT_CONFIG

sets the visibility of section "Output Config"

X

X

X

RIGHT_O_USE_COMPARISON

allows usage of comparison feature

X

X

X

RIGHT_O_CREATE_TEMPLATE_PAR T_PACKAGE

allows creating template part package from dashboard

X

X

X

RIGHT_O_CREATE_PAGE_MASTER_ PACKAGE

allows creating page master package from dashboard

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_CREATE_STYLE_PACKAGE

allows creating style package from dashboard

X

X

X

RIGHT_O_CREATE_GLOBAL_VARIA BLES_PACKAGE

allows creating variable package from dashboard

X

X

X

RIGHT_O_PALETTE_USE_BLOCK

sets the visibility of the palette element "Block"

X

X

X

RIGHT_O_PALETTE_USE_TEXT

sets the visibility of the palette element "Text"

X

X

X

RIGHT_O_PALETTE_USE_IMAGE

sets the visibility of the palette element "Image"

X

X

X

RIGHT_O_PALETTE_USE_TABLE

sets the visibility of the palette element "Table"

X

X

X

RIGHT_O_PALETTE_USE_LIST

sets the visibility of the palette element "List"

X

X

X

RIGHT_O_PALETTE_USE_COMMEN T

sets the visibility of the palette element "Comment"

X

X

X

RIGHT_O_PALETTE_USE_CONTAIN ER

sets the visibility of the palette element "Container"

X

X

X

RIGHT_O_PALETTE_USE_TEXT_FIEL D

sets the visibility of the palette element "Text field"

X

X

X

RIGHT_O_PALETTE_USE_TEXT_ARE A

sets the visibility of the palette element "Textarea"

X

X

X

RIGHT_O_PALETTE_USE_BUTTON

sets the visibility of the palette element "Button"

X

X

X

RIGHT_O_PALETTE_USE_RADIO

sets the visibility of the palette element "Radio button"

X

X

X

RIGHT_O_PALETTE_USE_CHECKBO X

sets the visibility of the palette element "Checkbox"

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PALETTE_USE_COMBOB OX

sets the visibility of the palette element "Combobox"

X

X

X

RIGHT_O_PALETTE_USE_COMPOSE R_ELEMENT

sets the visibility of the palette element "Composer element"

X

X

RIGHT_O_PALETTE_USE_LISTBOX

sets the visibility of the palette element "Listbox"

X

X

X

RIGHT_O_PALETTE_USE_LEADER

sets the visibility of the palette element "Leader"

X

X

X

RIGHT_O_PALETTE_USE_DYNAMIC

_VALUE

sets the visibility of the palette element "Dynamic Value"

X

X

RIGHT_O_PALETTE_USE_DYNAMIC

_BLOCK

sets the visibility of the palette element "Dynamic Block"

X

X

RIGHT_O_PALETTE_USE_REFRESHA BLE

sets the visibility of the palette element "Refreshable"

X

X

RIGHT_O_PALETTE_USE_REPEAT

sets the visibility of the palette element "Repeat"

X

X

RIGHT_O_PALETTE_USE_VARIABLE

sets the visibility of the palette element "Variable"

X

X

RIGHT_O_PALETTE_USE_BARCODE

_ASPOSE

sets the visibility of the palette element "Barcode"

X

X

RIGHT_O_PALETTE_USE_CONDITIO N

sets the visibility of the palette element "Condition"

X

X

RIGHT_O_PALETTE_USE_CONDITIO N_BRANCH

sets the visibility of the palette element "Condition Branch"

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PALETTE_USE_CONDITIO N_TOGGLE

sets the visibility of the palette element "De-

/Activate"

X

X

RIGHT_O_PALETTE_USE_LINK

sets the visibility of the palette element "Link"

X

X

X

RIGHT_O_PALETTE_USE_PAGE_NU MBER

sets the visibility of the palette element "Page Number"

X

X

RIGHT_O_PALETTE_USE_PAGE_SEQ UENCE

sets the visibility of the palette element "Page Sequence"

X

X

X

RIGHT_O_PALETTE_USE_EXTERNAL

_DOCUMENT

sets the visibility of the palette element "External Document"

X

X

X

RIGHT_O_PALETTE_USE_TEMPLATE

_PART_LOCAL

sets the visibility of the **local **Template Part Reference in the palette

X

X

RIGHT_O_PALETTE_USE_TEMPLATE

_PART_EXTERNAL

sets the visibility of the **external **Template Part Reference in the palette

X

X

RIGHT_O_PALETTE_USE_INSERTIO NPOINT

sets the visibility of the palette element "Insertionpoint"

X

X

RIGHT_O_PALETTE_USE_NUMBERI NG_REFERENCE

sets the visibility of the palette element "Numbering Reference"

X

X

X

RIGHT_O_PALETTE_USE_TABLE_OF

_CONTENTS

sets the visibility of the palette element "Table of Contents"

X

X

X

RIGHT_O_PALETTE_USE_CUSTOM_ ALL

sets the visibility of all custom components in the palette

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PALETTE_USE_CUSTOM_ [NAME]

sets the visibility of specific custom components in the palette. [NAME] must be replaced by the name of the custom component you want to display

X

X

RIGHT_O_PALETTE_USE_WRAPPER

sets the visibility of the palette element "Wrapper"

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_ADVANCED

sets the visibility of all Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_ASSERTION

sets the visibility of Assertion dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_BARCODE

sets the visibility of Barcode dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_BOOKMARK

sets the visibility of Bookmark properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_BORDER

sets the visibility of Border dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_DECIMAL_FORMAT

sets the visibility of Decimal Format dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_DISTANCES

sets the visibility of Distances dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_DYNAMIC_VALUE

sets the visibility of Dynamic Value dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_FONTS

sets the visibility of Fonts dedicated properties tab

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_FORM_FIELD

sets the visibility of Form Field dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_IMAGE

sets the visibility of Image dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_LEADER

sets the visibility of Leader dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_LINK

sets the visibility of Link dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_LIST

sets the visibility of List dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_NUMBERING_SCHE ME

sets the visibility of AdvNumbering Scheme dedicated anced properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_PAGE_NUMBER

sets the visibility of Page Number dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_PAGE_SEQUENCE

sets the visibility of Page Sequence dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_SCRIPT

sets the visibility of Script dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_TABLE

sets the visibility of Table dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_TABLE_BODY

sets the visibility of Table Body dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_TABLE_CELL

sets the visibility of Table Cell dedicated properties tab

X

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_TABLE_COLUMN

sets the visibility of Table Column dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_TABLE_FOOTER

sets the visibility of Table Footer dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_TABLE_HEADER

sets the visibility of Table Header dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_TA B_PROPERTIES_TABLE_ROW

sets the visibility of Table Row dedicated properties tab

X

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_ACCESSIBILITY

sets the visibility of Accessibility section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_AREA_ALIGNMENT

sets the visibility of Area Alignment section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_AREA_DIMENSION

sets the visibility of Area Dimensions section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_BARCODE

sets the visibility of Barcode section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_BARCODE_PRE_V3_0

sets the visibility of Barcode pre V3 section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_BLOCK_AND_LINE

sets the visibility of Block and Line section of Advanced properties

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PROPERTY_SECTION_AD VANCED_BORDER_PADDING_AND

_BACKGROUND

sets the visibility of Border Padding and Background section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_BULLETS_AND_NUMBERI NG

sets the visibility of Bullets and Numbering section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_CHARACTER

sets the visibility of Character section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_CHART

sets the visibility of Chart section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_COLORS

sets the visibility of Colors section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_COMPOSER

sets the visibility of Composer section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_CONVERSION

sets the visibility of Conversion section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_DATAINPUT

sets the visibility of Data Input section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_DECIMAL_FORMAT

sets the visibility of Decimal Format section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_DEPENDENCY

sets the visibility of Dependency section of Advanced properties

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PROPERTY_SECTION_AD VANCED_DYNAMIC_EFFECTS

sets the visibility of Dynamic Effects section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_FLOAT

sets the visibility of Float section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_FONTS

sets the visibility of Fonts section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_FORM_FIELD

sets the visibility of Form Field section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_HYPHENATION

sets the visibility of Hyphenation section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_KEEPS_AND_BREAKS

sets the visibility of Keeps and Breaks section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_LAYOUT

sets the visibility of Layout section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_LEADER_AND_RULE

sets the visibility of Leader and Rule section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_MARGIN

sets the visibility of Margin section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_MARKERS

sets the visibility of Markers section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_MISCELLANEOUS

sets the visibility of Miscelaneous section of Advanced properties

X

X

**Role**

**Description**

**ROLE_R EADER**

**ROLE_B USINES S_USER**

**ROLE_P OWER_ USER**

**ROLE_A DMINI STRAT OR**

RIGHT_O_PROPERTY_SECTION_AD VANCED_NUMBERING

sets the visibility of Numbering section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_OUTPUT

sets the visibility of Output section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_PAGE_MASTER

sets the visibility of Page Master section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_POSITIONING

sets the visibility of Positioning section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_PRINTING

sets the visibility of Printing section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_TABLE

sets the visibility of Table section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_TRACE

sets the visibility of Trace section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_WRITING_MODE

sets the visibility of Writing Mode section of Advanced properties

X

X

RIGHT_O_PROPERTY_SECTION_AD VANCED_XSL

sets the visibility of XSL section of Advanced properties

X

X

## User Access
Business Designer needs to have set up an integration with a user store to work properly. All possible configurations of useraccess.xml are described in appendix [User Access Configuration](/doxee-platform/docs/6-6-business-designer-developer-guide-user-access-and-security-configuration-1-1#user-access-configuration)

> Note

Inactive users cannot log into Business Designer and users do not inherit roles (like ROLE_ADMINISTRATOR) or rights (like RIGHT_E_BLOCK) from inactive groups.

## FOP Config
This serves as configuration for creating PDF preview. This file is created during startup (unless it exists). Example "fop_config.xml" is as follows:

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;!-- NOTE: This is the version of the configuration --&gt;
&lt;fop version="1.0"&gt;
&lt;!-- Source resolution in dpi (dots/pixels per inch) for determining the size of pixels in SVG and bitmap images, default: 72dpi --&gt;
&lt;source-resolution&gt;72&lt;/source-resolution&gt;
&lt;!-- Target resolution in dpi (dots/pixels per inch) for specifying the target resolution for generated bitmaps, default: 72dpi --&gt;
&lt;target-resolution&gt;72&lt;/target-resolution&gt;
&lt;!-- Default (A4) page-height and page-width, in case value is specified as auto --&gt;
&lt;default-page-settings height="297.0mm" width="210.0mm"/&gt;
&lt;!-- Information for specific renderers --&gt;
&lt;!-- Uses renderer mime type for renderers --&gt;
&lt;renderers&gt;
&lt;renderer mime="application/pdf"&gt;
&lt;filterList&gt;
&lt;!-- provides compression using zlib flate (default is on) --&gt;
&lt;value&gt;flate&lt;/value&gt;
&lt;/filterList&gt;
&lt;fonts&gt;
&lt;directory&gt;file:///C:/infinica/fonts&lt;/directory&gt;
&lt;directory&gt;C:/infinica/fonts&lt;/directory&gt;
&lt;directory&gt;file:///c:/local-icr/fonts&lt;/directory&gt;
&lt;/fonts&gt;
&lt;/renderer&gt;
&lt;renderer mime="application/postscript"&gt;
&lt;!-- optimize-resources&gt;true&lt;/optimize-resources --&gt;
&lt;fonts&gt;
&lt;directory&gt;file:///C:/infinica/fonts&lt;/directory&gt;
&lt;/fonts&gt;
&lt;/renderer&gt;
&lt;renderer mime="application/vnd.hp-PCL"&gt;
&lt;/renderer&gt;
&lt;renderer mime="image/svg+xml"&gt;
&lt;format type="paginated"/&gt;
&lt;link value="true"/&gt;
&lt;strokeText value="false"/&gt;
&lt;/renderer&gt;
&lt;renderer mime="application/awt"&gt;
&lt;/renderer&gt;
&lt;renderer mime="image/png"&gt;
&lt;!--transparent-page-background&gt;true&lt;/transparent-page-background--&gt;
&lt;/renderer&gt;
&lt;renderer mime="image/tiff"&gt;
&lt;!--transparent-page-background&gt;true&lt;/transparent-page-background--&gt;
&lt;!--compression&gt;CCITT T.6&lt;/compression--&gt;
&lt;/renderer&gt;
&lt;renderer mime="text/xml"&gt;
&lt;/renderer&gt;
&lt;renderer mime="text/plain"&gt;
&lt;pageSize columns="80"/&gt;
&lt;/renderer&gt;
&lt;/renderers&gt;
&lt;/fop&gt;`## Rewrite Config
File "rewrite.config" is essential for normal function of Business Designer and has to be located in the folder "$TOMCAT\conf\Catalina\localhost\". Business Designer client side is based on multiple views and each view including extra parameters is represented in the form of URL. However, these URLs are not pointing to real server resources, and the Tomcat server would normally in this case return error status code. Therefore, it is needed to activate URL Rewrite Mode which requires two following steps:

As a first step in the file "$TOMCAT\conf\server.xml" add following entry into &lt;Host name="localhost"&gt; section:

`&lt;Valve className="org.apache.catalina.valves.rewrite.RewriteValve"/&gt;`Snippet from the end of the file "server.xml" after the edit might look like this:

`...
&lt;Host name="localhost"  appBase="webapps" unpackWARs="true" autoDeploy="true"&gt;
&lt;Valve className="org.apache.catalina.valves.AccessLogValve" directory="logs" prefix="localhost_access_log"  suffix=".txt"
pattern="%h %l %u %t &amp;quot;%r&amp;quot; %s %b" /&gt;
&lt;Valve className="org.apache.catalina.valves.rewrite.RewriteValve" /&gt;
&lt;/Host&gt;
&lt;/Engine&gt;
&lt;/Service&gt;
&lt;/Server&gt;`Then as a second step add file "rewrite.config" into folder "$TOMCAT\conf\Catalina\localhost\". Example file "rewrite.config" is as follows:

`# rewrite.config for /infinica-business-designer # default login page to return 401
RewriteRule ^\/infinica-business-designer\/login.html(.*)$ - [R=401]
# enable reload when template is already opened # and also enable direct link to template open, # and reload after logout
RewriteRule ^\/infinica-business-designer\/(bd-login|dashboard|template\/.*)$ /infinica- business-designer/index.html [L]
# rewrite.config for /infinica-composer # enable reload after login
RewriteRule ^\/infinica-composer\/(c-login|document)$ /infinica-composer/index.html [L]`> Note

Please note that `infinica-business-designer` is the **application context **under which the Business Designer is deployed in Tomcat. In case application is deployed under different context than /infinica-business- designer, you need to modify the template `rewrite-generic.config` (part of distribution package) and put modified file to regular `rewrite.config` location.

To ensure that the Composer preview works as expected and to avoid potential problems later, please add the following entry at the very end of the file "$TOMCAT\conf\catalina.properties":

`org.apache.tomcat.util.buf.UDecoder.ALLOW_ENCODED_SLASH=true`## Integration with 3rd parties, cookies policy
Business Designer by default allows to be embedded in iframe (Easy integration with Salesforce). This behavior is enforced by [SameSite](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite) cookies policy. To change SameSite value to other than None (least restrictive one), you would need to modify context.xml file in META-INF folder.

`&lt;Context&gt;
&lt;CookieProcessor  sameSiteCookies="None"  /&gt;
&lt;/Context&gt;`> Note

context.xml is located in war file (usually infinica-business-designer.war). CookieProcessor is component provided by Tomcat.

Cookies are created with *Secure *flag, meaning **https **is required for a successful login. In case, when Business Designer is not deployed on secure connection, *Secure *flag can be disabled with system property passed to Tomcat.

`-Dserver.cookies.secure=false`> Note

This is obviously not recommended for production environment.

## Content security policy
[Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) enables administrators additional restrictions on loading resources and executing scripts in browser. It is a standard tool against cross-site scripting. By default, no CSP is set for Business Designer. Example prohibits loading of scripts from different site than application is running on and that application can be embedded into an iframe from salesforce.com domain. Breaking this policy will result in browser refusing to render or blocking the page.

`security.contentSecurityPolicy = script-src 'self' 'unsafe-eval' ; frame-ancestors 'self' 
https://*.lightning.force.com:* https://*.salesforce.com:*`## Dependency Analyzer
Dependency Analyser as a feature of Business Designer supports the user by analyzing and reporting references between Infincia templates (*.itx) - mainly it helps to determine where a certain Template Part is used. It potentially works only in "project directories" that contain all the files for analysis and it is heavily dependent on the setup of Doxee Content Repository

for indexing and on the setup of used external database. For more information please see "Infinica Dependency Analysis: User Guide" and Doxee Content Repository documentation.

`#dependency analyzer
analyzer.location = infinica/dependency-analyzer.xml`This is an optional configuration but necessary for Dependency Analyzer to work. It specifies path to "dependency-analyzer.xml" configuration file - example of this file as follows:

`&lt;indexer xmlns="http://www.infinica.com/indexer"&gt;
&lt;storage&gt;
&lt;sql xmlns="http://www.infinica.com/storage"
url="jdbc:postgresql://192.168.1.1:5432/dependency-analyzer-db" user="postgres"
password="postgres" jdbcDriver="org.postgresql.Driver"&gt;
&lt;properties&gt;
&lt;prop name="hibernate.hbm2ddl.auto" value="update" /&gt;
&lt;prop  name="hibernate.dialect"  value="org.hibernate.dialect.PostgreSQLDialect"
/&gt;
&lt;/properties&gt;
&lt;/sql&gt;
&lt;/storage&gt;
&lt;filters&gt;
&lt;filter exclude="false" pattern=".*itx" /&gt;
&lt;filter exclude="true" pattern=".*idx" /&gt;
&lt;/filters&gt;
&lt;/indexer&gt;`> Note

When PostgreSQL is used as an external database it may happen that there is an error like "PSQLException: ERROR: out of shared memory" in the logs and Dependency Analyzer provides no results. Potential solution is to double the parameter "max_pred_locks_per_transaction" in PostgreSQL configuration.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}