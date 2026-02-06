---
id: "2342d76f-08fa-44a4-8204-1992554a4dd1"
title: "Configuration"
slug: "composer-developer-guide-6-7-configuration"
category: "Administration guide"
category_path:
  - "Product guides"
  - "Composer"
  - "Administration guide"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-11-13T12:50:52.129Z"
modified_at: "2026-01-07T13:57:06.625Z"
authors:
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/composer-developer-guide-6-7-configuration"
synced_at: "2026-01-28T20:50:31.577Z"
checksum: "e4de0a3f085ca900"
---

Navigate to other release versions of Doxee Platform Composer

[6.6](https://docs.doxee.com/docs/en/composer-6-6)

[6.7](https://docs.doxee.com/docs/en/composer-6-7)

This chapter contains a description of the Composer configuration.

## Configuration Files
Create a new folder "infinica" in the $TOMCAT folder if it doesn't yet exist. It will contain the configuration data for Composer.

- composer-next.properties

This file will contain the needed settings for Composer.

The configuration data is not separated into sections - there are just key/value pairs defined in the configuration file. Single rows can be commented out using the sharp symbol "#" at the beginning of the row.

- useraccess.xml

Contains the configuration for the user store. Composer needs to be connected to a user store for it to work properly. Usually there is one user store and one useraccess.xml for all Doxee applications. For detailed information, see [User access](/doxee-platform/docs/composer-developer-guide-6-6-user-access-1).

> Important

Please note that a Tomcat restart is needed after the change of settings for this change to apply.

> Note

As all other Doxee application also Composer is able to use a "fake" XML-based user store for testing purposes. This is NOT recommended.

- composer-next-log4j2.xml

In this file, the logging settings for Composer can be adjusted. Here is one sample XML configuration file - it uses the **Log4j2** format.

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;Configuration status="WARN" monitorInterval="30"&gt;
    &lt;Appenders&gt;
        &lt;RollingFile name="ComposerLog" fileName="logs/composer-next.log"
                     filePattern="logs/$${date:yyyy-MM}/composer-next-%d{MM-dd-yyyy}-%i.log.gz"&gt;
            &lt;PatternLayout&gt;
                &lt;Pattern&gt;%d %p %c{1.} [%t] %m%n&lt;/Pattern&gt;
            &lt;/PatternLayout&gt;
            &lt;Policies&gt;
                &lt;TimeBasedTriggeringPolicy /&gt;
                &lt;SizeBasedTriggeringPolicy size="25 MB"/&gt;
            &lt;/Policies&gt;
            &lt;DefaultRolloverStrategy max="20"/&gt;
        &lt;/RollingFile&gt;
        &lt;RollingFile name="ComposerTraceLog" fileName="logs/composer-next-trace.log"
                     filePattern="logs/$${date:yyyy-MM}/composer-next-trace-%d{MM-dd-yyyy}-%i.log.gz"&gt;
            &lt;PatternLayout&gt;
                &lt;Pattern&gt;%d %p %c{1.} [%t] %m%n&lt;/Pattern&gt;
            &lt;/PatternLayout&gt;
            &lt;Policies&gt;
                &lt;TimeBasedTriggeringPolicy /&gt;
                &lt;SizeBasedTriggeringPolicy size="10 MB"/&gt;
            &lt;/Policies&gt;
            &lt;DefaultRolloverStrategy max="20"/&gt;
        &lt;/RollingFile&gt;
    &lt;/Appenders&gt;
    &lt;Loggers&gt;
        &lt;Logger name="com.infinica.web" level="debug" additivity="false"&gt;
            &lt;AppenderRef ref="ComposerLog"/&gt;
        &lt;/Logger&gt;
        &lt;!-- debug level will log execution times in composer --&gt;
        &lt;AsyncLogger name="com.infinica.performance" level="debug" additivity="false"&gt;
            &lt;AppenderRef ref="ComposerTraceLog"/&gt;
        &lt;/AsyncLogger&gt;
        &lt;Root level="info"&gt;
            &lt;AppenderRef ref="ComposerLog"/&gt;
        &lt;/Root&gt;
    &lt;/Loggers&gt;
&lt;/Configuration&gt;`> Note

Changes to logging configuration are picked up automatically (without server restart). You can see the setting of monitorInterval attribute - defines how often the config file will be checked for changes in seconds.

There is only one type of log file defined.

- composer-next.log - regular application log

## composer-next.properties
The entries could be split into several conceptual sections but this is not enforced. In the main section we could gather the essential configuration entries.

Example snippets of file "composer-next.properties" are as follows:

`# configurable application browser title
application.title = DOXEE Composer
fo.to.html.xsl.location = infinica/fo2html.xsl
font.folder.location = C:/infinica/fonts
fop.config.xml.location = infinica/fop_config.xml
icr.location = http://localhost:8080/infinica-content-repository/
userAccessManager.location = infinica/useraccess.xml
# spellcheck
spellcheck.dictionaries.directory = file://C:/infinica/dict
spellcheck.dictionaries.languages = en_GB, British; it_IT, Italian;de_DE, German
# process preview
process.preview.pdf.label = PDF
process.preview.pdf.available = true
process.preview.pdf.engine.uri = http://localhost:8080/infinica-process-engine/rest
process.preview.pdf.process.uri = processes/render2pdf.ipd
process.preview.pdf.renderer = fop
process.preview.pdf.format = pdf
process.preview.pdf.order = 1
process.preview.html.label = HTML
process.preview.html.available = true
process.preview.html.engine.uri = http://localhost:8080/infinica-process-engine/rest
process.preview.html.process.uri = processes/render2html.ipd
process.preview.html.renderer = xsl
process.preview.html.format = html
process.preview.html.order = 2
process.preview.word.label = MS Word
process.preview.word.available = true
process.preview.word.engine.uri = http://localhost:8080/infinica-process-engine/rest
process.preview.word.process.uri = processes/render2docx.ipd
process.preview.word.renderer = xsl
process.preview.word.format = docx
process.preview.word.order = 3`- application.title: *Optional.* Indicates the application name visible in the browser as a tab or window title. Defaults to "DOXEE Composer".

- icr.location: *Required.* URL specifies where the Doxee Content Repository app is running (server/port). Alternatively also like: "file:///C:/local-icr" (not recommended).

- userAccessManager.location: *Optional.* Location of useraccess.xml. Default value is infinica/useraccess.xml.

- infinicaAuthentication.location: *Optional.* Location of the Authentication Configuration file (required for OAuth/Alfa security).

- font.folder.location: *Optional.* Defines the path to a folder where font files in ttf format are stored. This is used mainly by FOP Renderer.

- fop.config.xml.location: *Optional.* Location of "fop_config.xml" file. Default value is infinica/fop_config.xml.

- template.serializer.emptyblockcontent: *Optional.* String value for the template serializer indicating the content for empty blocks. Defaults to non-breaking space character. Any whitespace character needs to be escaped with \. Example contains ASCII 160 (non-breaking space)

Next section is related to embedded mode.

`composer.embeddedMode = false`- composer.embeddedMode: Embedded mode is suitable in use cases when Composer is integrated in an iframe or generally into some other application and some functions are taken over by this integrating application. It adjusts mostly the header to be more suitable for integrated use-cases.

`preview.pdf.enabled = true`- preview.pdf.enabled: Defines whether the built-in PDF preview should be enabled/visible. Property is optional and default value is true.

`page-breaks.enabled = true`- page-breaks.enabled: Defines whether the Page Breaks Feature should be enabled. Property is optional and default value is true.

`spellcheck.dictionaries.directory = file:///c:/local-icr/dict
spellcheck.dictionaries.languages = en_GB, British; de_DE, German`> Warning

Don't forget to add your dictionary files in the defined folders ***/dict***

These 2 options are used for the spellcheck configuration. Composer can use [Hunspell dictionaries](http://hunspell.github.io/) for spellchecking. If this is configured, then the text in the template is checked as the user types. Suggestions for typos are provided based on these dictionaries.

- spellcheck.dictionaries.directory: Directory with Hunspell dictionaries. For each language, there must be 2 files: One dictionary file (having .dic suffix) and one affixes file (with .aff suffix).

- spellcheck.dictionaries.languages: Comma separated dictionary definition. Semicolon is used for defining more than one language.

> Note

Defining *en_GB, British; de_DE, German* as dictionaries languages will define 2 available dictionaries which can be used in Composer. The user can then choose between the *British* or *German* dictionary in the application (This part of the configuration is used as a label in the UI). 4 files must exist on the server in *c:/local-icr/dict* directory - en_GB.dic, en_GB.aff, de_DE.dic and de_DE.aff.

In order to get the **AI features** up and running, following settings must be properly configured:

`# AI Support (commented config items are optional with default values)

# OPEN AI
openai.enabled = true
openai.api.token = [OPENAI_API_TOKEN]
# openai.api = /v1/chat/completions
# openai.image.api = /v1/images/generations
# openai.image.model = dall-e-3
# openai.image.number = 1
# openai.image.quality = standard
# openai.image.size = 1024x1024
# openai.image.style = natural
# openai.max-tokens = 500
# openai.model = gpt-3.5-turbo
# openai.temperature = 0.7

# MISTRAL AI
mistral.enabled = true
mistral.api.token = [MISTRAL_API_TOKEN]
# mistral.api = /v1/chat/completions
# mistral.max-tokens = 250
# mistral.model = mistral-small-latest
# mistral.temperature = 0.7

# DEEPL AI
deepl.enabled = true
deepl.api.token = [DEEPL_API_TOKEN]
# deepl.api.languages = /v2/languages
# deepl.api.translate = /v2/translate
# deepl.base-url = https://api.deepl.com

# GOOGLE GEMINI AI
gemini.enabled = true
gemini.api.token = [GOOGLE_GEMINI_API_TOKEN]
# gemini.api = /v1
# gemini.base-url = https://generativelanguage.googleapis.com
# gemini.model = gemini-1.5-flash-latest

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

- openai.api.token: represents the valid OpenAI token. Don't hesitate to ask for one directly via our support [support-infinica@doxee.com](mailto:support-infinica@doxee.com).

- openai.api: in order to get the AI chat features working, completions api is by default set to "/v1/chat/completions".

- openai.max-tokens: the maximum number of tokens that can be generated in the chat completion. Higher number means more tokens allowed within request / response generation. You can think of tokens as pieces of words, where 1,000 tokens is about 750 words. The more tokens you spent, the more you pay. Default is unlimited.

- openai.model: define the AI model to communicate with. You can use for example gpt-3.5-turbo or gpt-4. Default model is gpt-3.5-turbo.

> Note

There is significant cost difference per 1,000 tokens between those models.

- openai.image.api: the OpenAI Image Generation API URI

- openai.image.model: the model to use for image generation.

- openai.image.number: the number of images to generate. Must be between 1 and 10. For model dall-e-3, only 1 is supported.

- openai.image.quality: the quality of the image that will be generated. *hd* creates images with finer details and greater consistency across the image. This param is only supported for dall-e-3.

- openai.image.size: the size of the generated images. Must be one of 256x256, 512x512, or 1024x1024 for dall-e-2. Must be one of 1024x1024, 1792x1024, or 1024x1792 for dall-e-3 models.

- openai.image.style: the style of the generated images. Must be one of *vivid* or *natural*. Vivid causes the model to lean towards generating hyper-real and dramatic images. Natural causes the model to produce more natural, less hyper-real looking images. This param is only supported for dall-e-3.

- openai.temperature: the sampling temperature, between 0 and 1. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic. If set to 0, the model will use log probability to automatically increase the temperature until certain thresholds are hit.

### MISTRAL AI
- mistral.enabled: optional true / false value. Default value is "false". If value is set to "true", correct mistral.api.token is required too.

- mistral.api.token: represents the valid Mistral AI API token. Don't hesitate to ask for one directly via our support [support-infinica@doxee.com](mailto:support-infinica@doxee.com).

- mistral.api: the Mistral AI Conversation API URI

- mistral.max-tokens: the maximum number of tokens that can be generated in the chat completion. Higher number means more tokens allowed within request / response generation. You can think of tokens as pieces of words, where 1,000 tokens is about 750 words. The more tokens you spent, the more you pay. Default is unlimited.

- mistral.model: ID of the model to use. Please see the [Model Overview](https://docs.mistral.ai/models) for model descriptions.

- mistral.temperature: what sampling temperature to use, between 0.0 and 1.0. Higher values like 0.8 will make the output more random, while lower values like 0.2 will make it more focused and deterministic.

### DEEPL
- deepl.enabled: optional true / false value. Default value is "false". If value is set to "true", correct deepl.api.token is required too.

- deepl.api.languages: the DeepL API URI for fetching a list of supported languages

- deepl.api.token: represents the valid DeepL API token. Don't hesitate to ask for one directly via our support [support-infinica@doxee.com](mailto:support-infinica@doxee.com).

- deepl.api.translate: the DeepL API URI for translation services

- deepl.base-url: it's a default base DeepL API URL which is used in conjunction with API URIs

### GOOGLE GEMINI AI
- gemini.enabled: optional true / false value. Default value is "false". If value is set to "true", correct gemini.api.token is required too.

- gemini.api.token: represents the valid GOOGLE Gemini API token. Don't hesitate to ask for one directly via our support [support-infinica@doxee.com](mailto:support-infinica@doxee.com).

- gemini.api: the GOOGLE Gemini AI Conversation API URI

- gemini.base-url: it's a default base GOOGLE Gemini API URL which is used in conjunction with chat URI

- gemini.model: ID of the model to use. Please see [Gemini Models](https://ai.google.dev/gemini-api/docs/models/gemini) for model descriptions.

### AZURE OPEN AI
- azure.openai.enabled: optional true / false value. Default value is "false". If value is set to "true", all mandatory values should be set too.

- azure.openai.api.token: represents valid Azure OpenAI API token for conversation API. Don't hesitate to ask for one directly via our support [support-infinica@doxee.com](mailto:support-infinica@doxee.com).

- azure.openai.base-url: represents valid base URL of the Azure OpenAI Chat API service, *example: *[*https://doxee-openai.openai.azure.com*](https://doxee-openai.openai.azure.com__)

- azure.openai.image.api.token: represents valid Azure OpenAI API token for Image Generation API. It can be the same token as used for Chat API, but also can be completely independent. Don't hesitate to ask for one directly via our support [support-infinica@doxee.com](mailto:support-infinica@doxee.com).

- azure.openai.image.base-url: represents valid base URL of the Azure OpenAI Image Generation API service, *example: *[*https://doxee-openai-image.openai.azure.com*](https://doxee-openai-image.openai.azure.com__). It can also be the same as for Chat API.

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

`templateHandlerCache.timeoutInSeconds = 60`To speed up rendering of a document in Composer and operations like adding/updating of building blocks, parsed templates are cached internally in Composer. Default value is 0, meaning no caching is applied.

> Note

Changes applied to the template in Business Designer might not be visible immediately in Composer, if cache is active.

Next section is related to Insertion Points and Building Blocks.

`insertion-points.available-building-block.direct-selection = true`- insertion-points.available-building-block.direct-selection: it decides whether the *available building block* is selected and scrolled onto in the event of building block selection in the editor, or the *applied building block* is selected, which is a default behaviour. This property is optional and defaults to false.

## User Access
Composer needs to have set up an integration with a user store to work properly. All possible configurations of useraccess.xml are described in [User access](/doxee-platform/docs/composer-developer-guide-6-6-user-access-1).

> Tip

Inactive users cannot log into Composer.

## FOP Config
This serves as configuration for creating PDF preview. This file is created during startup (unless it exists).

Example "fop_config.xml" is as follows:

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
File "rewrite.config" is essential for normal function of Composer and has to be located in the folder "$TOMCAT\conf\Catalina\localhost\". Composer client side is based on multiple views and each view including extra parameters is represented in the form of URL. However, these URLs are not pointing to real server resources, and the Tomcat server would normally in this case return error status code. Therefore, the URL Rewrite Mode needs to be activated which requires the two following steps:

As a first step in the file "$TOMCAT\conf\server.xml" add following entry into &lt;Host name="localhost"&gt; section:

`&lt;Valve className="org.apache.catalina.valves.rewrite.RewriteValve"/&gt;`Snippet from the end of the file "server.xml" after the edit might look like this:

`...
            &lt;Host name="localhost" appBase="webapps" unpackWARs="true" autoDeploy="true"&gt;
                &lt;Valve className="org.apache.catalina.valves.AccessLogValve" directory="logs"
                prefix="localhost_access_log" suffix=".txt"
                pattern="%h %l %u %t &amp;quot;%r&amp;quot; %s %b" /&gt;
                &lt;Valve className="org.apache.catalina.valves.rewrite.RewriteValve" /&gt;
            &lt;/Host&gt;
        &lt;/Engine&gt;
    &lt;/Service&gt;
&lt;/Server&gt;`Then as a second step add file "rewrite.config" into folder "$TOMCAT\conf\Catalina\localhost\". Example file "rewrite.config" is as follows:

`# rewrite.config for /infinica-composer
# enable reload
# - after login
RewriteRule ^\/infinica-composer\/(c-login|document)$ /infinica-composer/index.html [L]`For unproblematic function of Composer preview feature and to avoid potential problems later please add the following entry into the file "$TOMCAT\conf\[catalina.properties](http://catalina.properties)" at the very end of the file:

`org.apache.tomcat.util.buf.UDecoder.ALLOW_ENCODED_SLASH=true`## Integration with 3rd parties, cookies policy
Composer by default allows to be embedded in iframe (for an easy integration with Salesforce, among other things). This behavior is enforced by [SameSite](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite) cookies policy. To change SameSite value to other than `None` (least restrictive one), you would need to modify context.xml file in META-INF folder.

`&lt;Context&gt;
   &lt;CookieProcessor sameSiteCookies="None" /&gt;
&lt;/Context&gt;`> Note

context.xml is located in war file (usually infinica-composer.war). CookieProcessor is component provided by Tomcat.

Cookies are created with *Secure* flag, meaning **https** is required for a successful login. In case, when Composer is not deployed on secure connection, *Secure* flag can be disabled with system property passed to Tomcat.

`-Dserver.cookies.secure=false`> Note

This is obviously not recommended for production environment.

## Content security policy
[Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) enables administrators additional restrictions on loading resources and executing scripts in browser. It is a standard tool against cross-site scripting. By default, no CSP is set for Composer. Example prohibits loading of scripts from different site than application is running on and that application can be embedded into an iframe from salesforce.com domain. Breaking this policy will result in browser refusing to render or blocking the page.

`security.contentSecurityPolicy =  script-src 'self' 'unsafe-eval' ; frame-ancestors 'self' https://*.lightning.force.com:* https://*.salesforce.com:*`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}