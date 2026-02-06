---
id: "a691ee93-74f1-4406-8f97-af21b348ab83"
title: "XML Input File Structure for Doxee Platform 3 Native Tasks"
slug: "xml-input-file-structure-for-doxee-platform-3-native-tasks-2"
category: "Batch Workflows Reference Guides"
category_path:
  - "Product guides"
  - "Batch Workflows"
  - "Batch Workflows Reference Guides"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-16T17:22:36.211Z"
modified_at: "2026-01-14T10:23:13.8Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/xml-input-file-structure-for-doxee-platform-3-native-tasks-2"
synced_at: "2026-01-28T20:41:03.666Z"
checksum: "a0507e80a23c2c7a"
---

## Overview
This page provides a representation of the XML input file schema required for the correct execution of a Doxee Platform 3 workflow procedure (including details on all the available features) and for the correct generation of a Cloud Analytics report.

Currently, Doxee Platform 3 allows to cover the following scenarios:

Scenario

Batch Workflow Task

**Pvideo production**

[Publish Documents (Pvideo)](/doxee-platform/docs/publish-documents-pvideo-batch-workflow-task-reference)

**Pweb production**

[Publish Documents (Pweb)](/doxee-platform/docs/publish-documents-pweb-on-demand-workflow-task-reference)

**Email delivery**

[Deliver Emails](/doxee-platform/docs/deliver-emails-batch-workflow-task-reference)

**SMS delivery**

[Deliver SMS](/doxee-platform/docs/deliver-sms-batch-workflow-task-reference)

> Note

For more information on how to configure the required Enrich Analytics (Pvideo/Pweb) tasks in the workflow, see: 

- [Enrich Analytics (Pvideo) Batch Workflow Task Reference](/doxee-platform/docs/enrich-analytics-pvideo-batch-workflow-task-reference-1)

- [Enrich Analytics (Pweb) Batch Workflow Task Reference](/doxee-platform/docs/enrich-analytics-pweb-batch-workflow-task-reference)

The following sample XML structure covers all the above scenarios.&nbsp;In the example, we will assume that the XML file is the output of the Data Transformation task.

**Generic XML structure**

`&lt;!-- pvideo.xml --&gt;
&lt;?xml version="1.0" encoding="UTF-8" ?&gt;
&lt;COMMUNICATIONS&gt;
    &lt;COMMUNICATION&gt;
        &lt;PWEB TITLE="pweb_title" GUID="ba30d0c1afd844d6b0fb4760cf128a30" SID="sdsdsd" SHORTENING="dox.cm" CUSTOM_DOMAIN="video.acme.com" GAID="UA-122232323-1" ANALYTICS="Enabled" ANONYMIZATION="Enabled"&gt;
            &lt;DATA
                NOME_SC="MARIO"
                CIAO_NOME_SC="CIAO_MARIO"
                SALVE_NOME_SC="SALVE_MARIO"
                BUONGIORNO_NOME_SC="BUONGIORNO_MARIO" DATA_SCADENZA_ART_SC="" DATA_SCADENZA_NO_ART_SC=""
                NUMERO_SC="" MARCA_SC="" MODELLO_SC="" MARCA="" MODELLO="" TARGA="" SEQUENZA_01_SC=""
                SEQUENZA_02_SC="" SEQUENZA_03_SC="" SEQUENZA_04_SC="" SEQUENZA_05_SC=""
                SEQUENZA_06_SC="" SEQUENZA_07_SC="" SEQUENZA_08_SC="" SEQUENZA_09_SC=""
                SEQUENZA_10_SC="" NOME_UPPER="MARIO" NOME_LOWER="mario" NOME_SENTENCE="MARIO"
                DATA_SHORT="" DATA_LONG="" GIORNO="" MESE="" ANNO="" CTA_LINK_01="" CTA_LINK_02=""
                CTA_LINK_03="" CTA_LINK_04="" CTA_LINK_05="" IMG_LINK_01="" IMG_LINK_02=""
                IMG_LINK_03="" IMG_LINK_04="" IMG_LINK_05="" SESSO="" ETA="" CF="" PIVA=""
                EMAIL="" CELL="" CANALE_INVIO="" INDIRIZZO="" CAP="" PROVINCIA="" LOCALITA=""
                DATA_NASCITA="" CORSO_PRESCELTO="" SEDE_CORSO="" COGNOME="" FIRST_NAME="MARIO"
                LAST_NAME="ROSSI" RATA="268,30" TOTALE="14086,90" PRESTITO="6753,36" SOMMA="6836,00"
                MESI="83" TAN="6,70" TAEG="6,91" NUMERO_TELEFONO="tel: +390000000000"
                DATA_INIZIO="23/09/2021" DATA_FINE="23/10/2021"
                WHATEVER="other data for the pweb..."
            /&gt;
            &lt;DYNAMIC_DATA
                TEXT1="https://contenthub.doxee.com/render/items/news?fields=title&amp;filter[id][_eq]=1"
                TEXT2="https://contenthub.doxee.com/render/items/news?fields=title&amp;filter[id][_eq]=2"
      
            /&gt;
            &lt;DA
                GUID="value" COMMUNICATION_ID="value"
                CUSTOMER_CODE="value" CUSTOMER_EMAIL="value" CUSTOMER_PHONE_NUMBER="value"
                JOB_ID="value" INPUT_FILE="value"
                CUSTOM_1="value" CUSTOM_2="value" CUSTOM_3="value" CUSTOM_4="value" CUSTOM_5="value"
                CUSTOM_6="value" CUSTOM_7="value" CUSTOM_8="value" CUSTOM_9="value" CUSTOM_10="value"
            /&gt;
            &lt;ANALYTICS CAMPAIGN="campaign" CUSTOMER_CODE="code"&gt;
                &lt;TAG_MANAGERS&gt;
                    &lt;MATOMO_TAG_MANAGER ENABLED="true" CONTAINER_ID="M-12345" ENDPOINT="matomo.doxee.com"/&gt;
                    &lt;GOOGLE_TAG_MANAGER ENABLED="true" CONTAINER_ID="G-12345"/&gt;
                &lt;/TAG_MANAGERS&gt;
                &lt;ENDPOINTS&gt;
                    &lt;HEADLIGHT ENABLED="true" ENDPOINT="https:hl.doxee.com"/&gt;
                    &lt;CLOUD_ANALYTICS ENABLED="true" ENDPOINT="https://ca.doxee.com"/&gt;
                    &lt;MATOMO ENABLED="true" ENDPOINT="matomo.doxee.com" SITE_ID="1" ANONYMIZATION="true"/&gt;
                    &lt;GOOGLE_ANALYTICS_UNIVERSAL ENABLED="true" PROPERTY_ID="UA-123" ANONYMIZATION="true"/&gt;
                    &lt;GOOGLE_ANALYTICS_4 ENABLED="true" PROPERTY_ID="M-123" ANONYMIZATION="true"/&gt;
                    &lt;WEBHOOKS ALIAS="nurtigo" ENABLED="true" ANONYMIZATION="true" ENDPOINT="nurtigo.doxee.com"/&gt;
                    &lt;WEBHOOKS ALIAS="custom" ENABLED="true" ANONYMIZATION="false" ENDPOINT="custom.com"/&gt;
                &lt;/ENDPOINTS&gt;
                &lt;TAGS NAME="campaign" VALUE="pvideo-campaign" CD="0" /&gt;
                &lt;TAGS NAME="lang" VALUE="IT" CD="1" /&gt;
                &lt;METADATA ADDITIONAL_METADATA1="additional_metadata1" ADDITIONAL_METADATA2="additional_metadata2"/&gt;              
            &lt;/ANALYTICS&gt;
        &lt;/PWEB&gt;
        &lt;PVIDEO TITLE="pvideo_title" GUID="044029c973c14198b77a725c11197a0d" SID="sdsdsd" SHORTENING="dox.cm" CUSTOM_DOMAIN="video.acme.com" GAID="UA-122232323-1" ANALYTICS="Enabled" ANONYMIZATION="Enabled"&gt;
            &lt;DATA
                NOME_SC="MARIO"
                CIAO_NOME_SC="CIAO_MARIO"
                SALVE_NOME_SC="SALVE_MARIO"
                BUONGIORNO_NOME_SC="BUONGIORNO_MARIO" DATA_SCADENZA_ART_SC="" DATA_SCADENZA_NO_ART_SC=""
                NUMERO_SC="" MARCA_SC="" MODELLO_SC="" MARCA="" MODELLO="" TARGA="" SEQUENZA_01_SC=""
                SEQUENZA_02_SC="" SEQUENZA_03_SC="" SEQUENZA_04_SC="" SEQUENZA_05_SC=""
                SEQUENZA_06_SC="" SEQUENZA_07_SC="" SEQUENZA_08_SC="" SEQUENZA_09_SC=""
                SEQUENZA_10_SC="" NOME_UPPER="MARIO" NOME_LOWER="mario" NOME_SENTENCE="MARIO"
                DATA_SHORT="" DATA_LONG="" GIORNO="" MESE="" ANNO="" CTA_LINK_01="" CTA_LINK_02=""
                CTA_LINK_03="" CTA_LINK_04="" CTA_LINK_05="" IMG_LINK_01="" IMG_LINK_02=""
                IMG_LINK_03="" IMG_LINK_04="" IMG_LINK_05="" SESSO="" ETA="" CF="" PIVA=""
                EMAIL="" CELL="" CANALE_INVIO="" INDIRIZZO="" CAP="" PROVINCIA="" LOCALITA=""
                DATA_NASCITA="" CORSO_PRESCELTO="" SEDE_CORSO="" COGNOME="" FIRST_NAME="MARIO"
                LAST_NAME="ROSSI" RATA="268,30" TOTALE="14086,90" PRESTITO="6753,36" SOMMA="6836,00"
                MESI="83" TAN="6,70" TAEG="6,91" NUMERO_TELEFONO="tel: +390000000000"
                DATA_INIZIO="23/09/2021" DATA_FINE="23/10/2021"
                WHATEVER="other data for the pvideo ..."
            /&gt;
            &lt;DYNAMIC_DATA
                TEXT1="https://contenthub.doxee.com/render/items/news?fields=title&amp;filter[id][_eq]=1"
                TEXT2="https://contenthub.doxee.com/render/items/news?fields=title&amp;filter[id][_eq]=2"
      
            /&gt;
            &lt;SCENES&gt;
                &lt;SCENE&gt;Scene_1&lt;/SCENE&gt;
                &lt;SCENE&gt;Scene_3&lt;/SCENE&gt;
                &lt;SCENE&gt;Scene_8&lt;/SCENE&gt;
            &lt;/SCENES&gt;
            &lt;TTS&gt;
                &lt;DATA&gt;
                    &lt;SPEECH ID="TTS_MALE01" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Joey" LANGUAGE="en-US" GENDER="Male"&gt;Hi, I'm Joey &lt;break TIME='2s'/&gt;  and I'm using a TTS to talk to you in English &lt;lang xml:LANG='it-IT'&gt; ma ti posso parlare anche in italiano&lt;/lang&gt;.&lt;/SPEECH&gt;
                    &lt;SPEECH ID="TTS_FEMALE01" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Conchita" LANGUAGE="es-ES" GENDER="Female"&gt;Hola Matteo3 soy Conchita y estoy usando un TTS para hablar contigo.&lt;/SPEECH&gt;
                    &lt;SPEECH ID="TTS_MALE03-01" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Joey" LANGUAGE="en-US" GENDER="Male"&gt;Using TTS frame sync you can make the voice start at an exact frame&lt;/SPEECH&gt;
                    &lt;SPEECH ID="TTS_FEMALE03-02" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Conchita" LANGUAGE="es-ES" GENDER="Female"&gt;Sí, eso es sin duda útil para sincronizar TTS a animación&lt;/SPEECH&gt;
                &lt;/DATA&gt;
                &lt;!-- settings node is added by pvideo content uploader --&gt;
                &lt;SETTINGS
                    APP_DN=""
                    AUTHORIZATION=""
                    CACHING=""
                    DATA_HASH=""
                    DOC_ID=""
                    ENV=""
                    ENV_DN=""
                    HASH_ZIP=""
                    PARTNER_ID="" /&gt;
            &lt;/TTS&gt;
            &lt;DA
                GUID="value" COMMUNICATION_ID="value"
                CUSTOMER_CODE="value" CUSTOMER_EMAIL="value" CUSTOMER_PHONE_NUMBER="value"
                CUSTOM_1="value" CUSTOM_2="value" CUSTOM_3="value" CUSTOM_4="value" CUSTOM_5="value"
                CUSTOM_6="value" CUSTOM_7="value" CUSTOM_8="value" CUSTOM_9="value" CUSTOM_10="value"
            /&gt;
            &lt;ANALYTICS CAMPAIGN="CAMPAIGN" /&gt;
        &lt;/PVIDEO&gt;
		&lt;!-- ===== Pvideo Designer ============================ --&gt;
        &lt;PVIDEO COMMUNICATION_NAME="7290f802-0273-492e-aa7f-4aa2e690e876" PROJECT="d34523f7-01ca-42a5-802e-3a1c940578c5" MAPPING="cf03e145-64ba-43fe-a58f-a4be284d1ab9" STORYBARD="35797767-10e0-4b14-8a76-b060cdd55d39"&gt;
           &lt;DATA NOME="MARIO" EMAIL="mario@doxee.com" /&gt;
        &lt;/PVIDEO&gt;  &nbsp; &nbsp; &nbsp; &nbsp; 
        &lt;EMAIL COMMUNICATION_NAME="same as pvideo value"&gt;
            &lt;DOCUMENTS&gt;
                &lt;DOCUMENT
                    GUID="same as pvideo value"
                    PURL="aggiunto post produzione pvideo (dominio custom + guid)"
                    SHORT_PURL="aggiuto post produzione pvideo (chi lo genera?)"
                    DOCUMENT_NAME="aggiunto post produzione pvideo (id generato da DA3 per il documento)"/&gt;
            &lt;/DOCUMENTS&gt;
            &lt;ANALYTICS
                CUSTOMER_CODE="same as pvideo value"
                CAMPAIGN="same as pvideo value"/&gt;          
            &lt;DATA TEMPLATE_PROPERTY_A="MARIO"
                TEMPLATE_PROPERTY_B="14086,90"
                WHATEVER="other data for the email ..." /&gt;
            &lt;DELIVERY SUBJECT="here or on the email template settings ?"&gt;
 	           
				&lt;!-- ===== OLD Recipient tag ============================ --&gt;
            	&lt;TO ADDRESS="recipient address" NAME="recipient name"/&gt;
            	&lt;!-- ====  EOF OLD Recipient tag ========== --&gt;
           
				&lt;!-- ==== NEW Recipient tag ====== --&gt;
            	&lt;TO&gt;
               		&lt;ITEM ADDRESS="fproietti@doxee.com" NAME="Filippo Proietti"/&gt;
               		&lt;ITEM ADDRESS="second_user@doxee.com" NAME="Second User"/&gt;
               		&lt;ITEM ADDRESS="another_user@doxee.com" NAME="Another User"/&gt;
            	&lt;/TO&gt;
            	&lt;!-- ==== EOF NEW Recipient tag ====== --&gt;

                &lt;CC&gt;
                    &lt;ITEM ADDRESS="carbon copy address" NAME="carbon copy recipient name"/&gt;
                    &lt;ITEM ADDRESS="carbon copy address" NAME="carbon copy recipient name"/&gt;
                &lt;/CC&gt;
                &lt;BCC&gt;
                    &lt;ITEM ADDRESS="blind carbon copy address" NAME="blind carbon copy recipient name"/&gt;
                    &lt;ITEM ADDRESS="blind carbon copy address" NAME="blind carbon copy recipient name"/&gt;
                &lt;/BCC&gt;
                &lt;ATTACHMENTS&gt;
                    &lt;ATTACHMENT&gt;test.txt&lt;/ATTACHMENT&gt;
                &lt;/ATTACHMENTS&gt;
            &lt;/DELIVERY&gt;
        &lt;/EMAIL&gt;
        &lt;SMS COMMUNICATION_NAME="same as pvideo value"&gt;
            &lt;DOCUMENTS&gt;
                &lt;DOCUMENT
                    GUID="same as pvideo value"
                    PURL="aggiunto post produzione pvideo (dominio custom + guid)"
                    SHORT_PURL="aggiuto post produzione pvideo o direttamente dal DT"/&gt;
            &lt;/DOCUMENTS&gt;
            &lt;ANALYTICS
                CUSTOMER_CODE="same as pvideo value"
                CAMPAIGN="same as pvideo value"/&gt;          
            &lt;DATA TEMPLATE_PROPERTY_A="MARIO"
                TEMPLATE_PROPERTY_B="14086,90"
                WHATEVER="other data for the sms ..." /&gt;
            &lt;DELIVERY&gt;
                &lt;TO PHONE="+3932812345678" /&gt;
            &lt;/DELIVERY&gt;
        &lt;/SMS&gt;     
    &lt;/COMMUNICATION&gt;
&lt;/COMMUNICATIONS&gt;`## XML file structures by feature
The following sections provide a detailed analysis of the sample XML file structure for each one of the available features, taking into account that these structures can be joined to cover more complex cases.

The following legend explains the labels used in the&nbsp;**Type** and&nbsp;**Flag** columns of the tables below, listing all available tags and attributes:

Label

Description

MANDATORY

The field is **mandatory for task execution**. Without it, the task will fail.

CLOUD_ANALYTICS

The field is **mandatory for report extraction**. Without it, the task will not fail but the report will not be produced correctly.

OPTIONAL

The field is optional for both task execution and report production.

TAG

The field is an XML tag. It must be unique.

ATTRIBUTE

The field is an attribute for a specific tag.

MAP

The tag contains a pair of *key:value*.

LIST

The tag behaves like a list.

ELEM_LIST

The tag is a list element and can be repeated within the list.

ELEM

The tag can be repeated within the XML structure.

## Pvideo production
The tags and attributes described in the following sections are children of the&nbsp;**COMMUNICATIONS/COMMUNICATION**&nbsp;XML element. For better readability, this dependency will not be repeated when describing the fields.

### Pvideo Legacy
The following table describes all tags and attributes of the&nbsp;**PVIDEO** XML section, indicating those required for task execution and those required for the generation of the Cloud Analytics report.

Root Tag

Tags

Attributes

Description

Type

Flags

**PVIDEO**

**-**

**-**

Root tag for the Pvideo section

TAG

MANDATORY

**TITLE**

Title of the Pvideo that will be displayed on the browser tab

ATTRIBUTE

MANDATORY

**SID**

Short URL ID

ATTRIBUTE

OPTIONAL

**GUID**

Unique GUID

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**SHORTENING**

If present, it overrides the Custom Domain for Shortening setting specified in the Pweb template resource.

When present and not blank, this value will be used as domain for the generated shorten pURL.

ATTRIBUTE

OPTIONAL

**CUSTOM_DOMAIN**

If present, it overrides the custom domain specified in the Pvideo template resource.

ATTRIBUTE

OPTIONAL

**GAID**

If present, it overrides the *GAID* specified&nbsp;in the Pvideo template resource.

It can be overridden by the *ANALYTICS* tag configuration (below).

ATTRIBUTE

OPTIONAL

DEPRECATED

**ANALYTICS**

If present, it overrides the Analytics setting specified&nbsp;in the Pvideo template resource.

The possible values are:

- **Enabled**

- **Disabled**

It can be overridden by the *ANALYTICS* tag configuration (below).

ATTRIBUTE

OPTIONAL

DEPRECATED

**ANONYMIZATION**

If present, it overrides the Anonymization setting specified&nbsp;in the Pvideo template resource.

The possible values are:

- **Enabled**

- **Disabled**

It can be overridden by the Analytics tag configuration (below).

ATTRIBUTE

OPTIONAL

DEPRECATED

**SHORT_PURL**

Short pURL of the published Pvideo

This attribute will only be present if URL shortening is enabledon the Pvideo template resource,&nbsp;and will be added after execution of the Publish documents (Pvideo) task.

ATTRIBUTE

OPTIONAL

**PURL**

pURL of the published Pvideo

This attribute will be added after execution&nbsp;of the Publish documents (Pvideo) task.

ATTRIBUTE

OPTIONAL

**DATA**

**-**

Contains the variables to be used in the Pvideo template resource as attributes.

TAG

MAP

MANDATORY

**DYNAMIC_DATA****&nbsp;**

-

Contains the variables to be used in the Pvideo template resource as attributes.

TAG

MAP

OPTIONAL

**SCENES&nbsp;**

**-**

**-**

List of Pvideo scenes

TAG

LIST

MANDATORY

**SCENE&nbsp;**

**-**

Represents a single scene in the Pvideo.

ELEM_LIST

**TTS**

**-**

**-**

Contains TTS information for the Pvideo.

ELEM

OPTIONAL

**DATA**

**-**

**-**

List of TTS elements

ELEM_LIST

MANDATORY

**SPEECH**

**-**

Single element of the TTS list, representing&nbsp;a single sentence to be pronounced

ELEM

MANDATORY

**ID**

TTS ID

ATTRIBUTE

MANDATORY

**TYPE**

TTS type

ATTRIBUTE

MANDATORY

**SAMPLE_RATE**

Sample rate

ATTRIBUTE

MANDATORY

**RATE**

Speech rate

ATTRIBUTE

MANDATORY

**VOLUME**

Audio volume

ATTRIBUTE

MANDATORY

**SENTENCE_BREAK**

Sentence break time

ATTRIBUTE

MANDATORY

**PARAGRAPH_BREAK**

Paragraph break time

ATTRIBUTE

MANDATORY

**NAME**

Speaker name

ATTRIBUTE

MANDATORY

**LANGUAGE**

Speaker language

ATTRIBUTE

MANDATORY

**GENDER**

Speaker gender

ATTRIBUTE

MANDATORY

**TEXT**

Text to be pronounced

ATTRIBUTE

MANDATORY

**SETTINGS**

**-**

Contains the TTS settings.

TAG

OPTIONAL

**APP_DN**

Name of the current workflow

ATTRIBUTE

MANDATORY

**AUTHORIZATION**

Concatenation of dataHash, docID, partnerID

ATTRIBUTE

MANDATORY

**CACHING**

Name of the current campaign

ATTRIBUTE

MANDATORY

**DATA_HASH**

Concatenation of all TTS data entry properties

ATTRIBUTE

MANDATORY

**DOC_ID**

Shipment ID of the current document

ATTRIBUTE

MANDATORY

**ENV**

TEST or PRODUCTION

ATTRIBUTE

MANDATORY

**ENV_DN**

Name of the current tenant

ATTRIBUTE

MANDATORY

**HASH_ZIP**

HA256&nbsp;hash of the template file

ATTRIBUTE

MANDATORY

**PARTNER_ID**

Partner ID&nbsp;for the current account

ATTRIBUTE

MANDATORY

**DA**

**-**

Contains further information for Data Acquisition.

TAG

MANDATORY

CLOUD_ANALYTICS

**GUID**

Unique GUID

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**COMMUNICATION_ID**

Communication ID

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**CUSTOMER_CODE**

Customer code

Leave it empty in case of Monopurl

ATTRIBUTE

MANDATORY

**CUSTOMER_EMAIL**

Customer email

ATTRIBUTE

OPTIONAL

**CUSTOMER_PHONE_NUMBER**

Customer phone number

ATTRIBUTE

OPTIONAL

**JOB_ID**

Job ID

ATTRIBUTE

OPTIONAL

**INPUT_FILE**

Input file name

ATTRIBUTE

OPTIONAL

**CUSTOM_1**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_2**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_3**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_4**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_5**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_6**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_7**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_8**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_9**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_10**

Custom attribute

ATTRIBUTE

OPTIONAL

**ANALYTICS**

**-**

**-**

Contains information on analytics production.

TAG

MANDATORY

CLOUD_ANALYTICS

**CUSTOMER_CODE**

Client customer code

ATTRIBUTE

CLOUD_ANALYTICS

**CAMPAIGN**

Campaign name

ATTRIBUTE

CLOUD_ANALYTICS

**TAG_MANAGERS**

**-**

**-**

Contains information about the tag manager to initialize.

MTM is used for internal analytics data production, to provide data to Doxee's BI tools.

GTM is used for external analytics data production, to send data to the customer's platforms.

TAG

OPTIONAL

**MATOMO_TAG_MANAGER**

**-**

Contains information to configure Matomo Tag Manager (MTM).

TAG

OPTIONAL

**CONTAINER_ID**

ID of the container configuration to use

If not specified, the default one is used.

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the tag manager or not.

If present, it overrides the bundle settings and the communication dimension configuration.

ATTRIBUTE

OPTIONAL

**ENDPOINT**

Endpoint to which to send the events

If not specified, the default one is used.

ATTRIBUTE

OPTIONAL

**GOOGLE_TAG_MANAGER**

**-**

Contains information to configure Google Tag Manager (GTM).

TAG

OPTIONAL

**CONTAINER_ID**

ID of the container configuration to use

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the tag manager or not.

(Default value: false)

ATTRIBUTE

OPTIONAL

**ENDPOINTS**

**-**

**-**

Contains configuration about the endpoints where the Tag Managers will send the analytics events.

TAG

OPTIONAL

**HEADLIGHT**

**-**

Headlight configurations

TAG

OPTIONAL

**ENABLED**

Whether to enable the destination or not.

If present, it overrides the *ANALYTICS&nbsp;*bundle settings and the communication dimension configuration.

ATTRIBUTE

OPTIONAL

**ENDPOINT**

Endpoint to which to send the events

If not specified, the default one is used.

ATTRIBUTE

OPTIONAL

**CLOUD_ANALYTICS**

**-**

Cloud Analytics configurations

TAG

OPTIONAL

**ENABLED**

Whether to enable the destination or not.

If present, it overrides the *ANALYTICS&nbsp;*bundle settings and the communication dimension configuration.

ATTRIBUTE

OPTIONAL

**ENDPOINT**

Endpoint to which to send the events

If not specified, the default one is used.

ATTRIBUTE

OPTIONAL

**MATOMO**

**-**

Matomo configurations

TAG

OPTIONAL

**ENABLED**

Whether to enable the destination or not.

ATTRIBUTE

OPTIONAL

**ENDPOINT**

Endpoint to which to send the events

If not specified, Endpoint to whichmo Tag Manager endpoint is used.

ATTRIBUTE

OPTIONAL

**SITE_ID**

Matomo site into which to record the events

Required when Matomo is enabled.

ATTRIBUTE

MANDATORY

(when enabled)

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.

If present, it overrides the *ANONYMIZATION*&nbsp;bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**WEBHOOKS**

**-**

Custom webhook configurations

It is possible to define more than one tag.

TAG

ELEM

OPTIONAL

**ALIAS**

Name of the target webhook (e.g. Nurtigo)

ATTRIBUTE

MANDATORY

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.

If present, it overrides the *ANONYMIZATION&nbsp;*bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the destination or not

(Default value: false)

ATTRIBUTE

MANDATORY

**ENDPOINT**

URL to which to send the events

ATTRIBUTE

MANDATORY

(when enabled)

**GOOGLE_ANALYTICS_UNIVERSAL**

**-**

Legacy Google Universal Analytics (UA) configurations

The functionality also depends on the presence of the&nbsp;**GOOGLE_TAG_MANAGER** configuration.

TAG

OPTIONAL

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.&nbsp;

If present, it overrides the *ANONYMIZATION&nbsp;*bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the destination or not.

(Default value:&nbsp;false)

If a&nbsp;*GAID&nbsp;*is provided through bundle settings or communication dimension, it will be enabled by default unless explicitly disabled.

ATTRIBUTE

OPTIONAL

**PROPERTY_ID**

Property into which to record the events

If present, it overrides the *GAID&nbsp;*bundle settings.

ATTRIBUTE

MANDATORY

(when enabled)

**GOOGLE_ANALYTICS_4**

**-**

Google Universal 4 (GA4) configurations

The functionality also depends on the presence of the&nbsp;**GOOGLE_TAG_MANAGER** configuration.

TAG

OPTIONAL

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.

If present, it overrides the *ANONYMIZATION&nbsp;*bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the destination or not.&nbsp;

(Default value: false)

ATTRIBUTE

OPTIONAL

**PROPERTY_ID**

Property (*measurement_id*) into which to record the events

ATTRIBUTE

MANDATORY

(when enabled)

**TAGS**

**-**

Additional custom dimensions to be attached to analytics events

More than one tag can be present.

TAG

ELEM

OPTIONAL

**NAME**

Name of the metadata (e.g. campaign, lang, etc)

ATTRIBUTE

MANDATORY

**VALUE**

Value of the metadata

ATTRIBUTE

MANDATORY

**CD**

Index of the custom dimension

Valid values are between 0 and 9. The value should be unique among all tags.

ATTRIBUTE

MANDATORY

**METADATA**

**-**

Additional metadata to attach to analytics events

TAG

OPTIONAL

**&lt;METADATA_NAME&gt;**

All attributes name and value will be made available on the document and can then be configured for the events.

ATTRIBUTE

OPTIONAL

### Pvideo Designer
The following table describes all tags and attributes of the&nbsp;**PVIDEO** (Pvideo Designer) XML section, indicating those required for task's execution.

> Important

(*) The **PROJECT** and **MAPPING** attributes are mandatory only when the Input Override is enabled in the task configuration's UI.

> Important

(*) The **STORYBOARD** attribute is mandatory only when dynamic storyboard is not configured in the mapping schema and Input Override is enabled in the task configuration's UI.

Root Tag

Tags

Attributes

Description

Type

Flags

**PVIDEO**

**-**

**-**

Root tag for the Pvideo section

TAG

MANDATORY

**COMMUNICATION_NAME**

Unique GUID identifying the communication

> Note

Valid from 

Doxee Platform v.3.47.0

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**PROJECT**

UUID of the project to use for production.

> Note

The project's UUID can be retrieved from the Pvideo Designer platform.

ATTRIBUTE

MANDATORY

(*) see note above

**MAPPING**

UUID of the mapping schema to use for production.

> Note

The mapping's UUID can be retrieved from the Pvideo Designer platform.

> Warning

The mapping schema must belong to the specified project.

ATTRIBUTE

MANDATORY

(*) see note above

**STORYBOARD**

UUID of the storyboard to use for production.

> Note

The mapping's UUID can be retrieved from the Pvideo Designer platform.

> Important

Dynamic storyboard configured in the mapping schema will override any configuration provided both from Task configuration or input XML.

ATTRIBUTE

OPTIONAL

(**) see note above

**DATA**

**-**

Contains the variables to be used to personalize the video.

> Note

Personalizations in Pvideo Designer are defined by creating ***data* **variables inside the mapping schema.

Variable names defined in the mapping schema must match the attribute names in the DATA element.

> Warning

Integration with Pvideo Designer is intended for personalized videos only; therefore, the mapping schema must contain at least one ***data*** variable.

TAG

MAP

MANDATORY

## Pweb production
The tags and attributes described in the following sections are children of the&nbsp;**COMMUNICATIONS/COMMUNICATION**&nbsp;XML element. For better readability, this dependency will not be repeated when describing the fields.

The following table describes all tags and attributes of the&nbsp;**PWEB&nbsp;**XML section, indicating those required for task execution and those required for the generation of the Cloud Analytics report.

Root Tag

Tags

Attributes

Description

Type

Flags

**PWEB**

-

-

Root tag for the Pweb section

TAG

MANDATORY

**TITLE**

Title of the Pweb that will be displayed on the browser tab

ATTRIBUTE

MANDATORY

**SID**

Short URL ID

ATTRIBUTE

OPTIONAL

**GUID**

Unique GUID

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**SHORTENING**

If present, it overrides the *Custom Domain for Shortening *setting specified in the Pweb template resource.

When present and not blank, this value will be used as domain for the generated shorten pURL.

ATTRIBUTE

OPTIONAL

**CUSTOM_DOMAIN**

If present, it overrides the custom domain specified&nbsp;in the Pweb template resource.

ATTRIBUTE

OPTIONAL

**GAID**

If present, it overrides the *GAID* specified&nbsp;in the Pweb template resource.

It can be overridden by the *ANALYTICS* tag configuration (below).

ATTRIBUTE

OPTIONAL

DEPRECATED

**ANALYTICS**

If present, it overrides the Analytics setting specified&nbsp;in the Pweb template resource.

The possible values are:

- **Enabled**

- **Disabled**

It can be overridden by the Analytics tag configuration (below).

ATTRIBUTE

OPTIONAL

DEPRECATED

**ANONYMIZATION**

If present, it overrides the Anonymization&nbsp;setting specified&nbsp;in the Pweb template resource.

The possible values are:

- **Enabled**

- **Disabled**

It can be overridden by the Analytics tag configuration (below).

ATTRIBUTE

OPTIONAL

DEPRECATED

**SHORT_PURL**

Short pURL of the published Pweb

This attribute will only be present if URL shortening is enabledon the Pweb template resource,&nbsp;and will be added after execution of the Publish documents (Pweb) task.

ATTRIBUTE

OPTIONAL

**PURL**

pURL of the published Pweb

It will be added after execution of the Publish documents (Pweb) task.

ATTRIBUTE

OPTIONAL

**DATA**

-

Contains the variables to be used in the Pweb template resource as attributes.

TAG

MAP

MANDATORY

**DYNAMIC_DATA**

-

Contains the variables to be used in the Pweb template resource as attributes.

TAG

MAP

OPTIONAL

**DA**

-

Contains further information for Data Acquisition.

TAG

MANDATORY

CLOUD_ANALYTICS

**GUID**

Unique GUID

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**COMMUNICATION_ID**

Communication ID

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**CUSTOMER_CODE**

Customer code

> Important

Leave it empty in case of Monopurl

ATTRIBUTE

MANDATORY

**CUSTOMER_EMAIL**

Customer email

ATTRIBUTE

OPTIONAL

**CUSTOMER_PHONE_NUMBER**

Customer phone number

ATTRIBUTE

OPTIONAL

**JOB_ID**

Job ID

ATTRIBUTE

OPTIONAL

**INPUT_FIL**E

Input file name

ATTRIBUTE

OPTIONAL

**CUSTOM_1**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_2**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_3**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_4**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_5**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_6**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_7**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_8**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_9**

Custom attribute

ATTRIBUTE

OPTIONAL

**CUSTOM_10**

Custom attribute

ATTRIBUTE

OPTIONAL

**ANALYTICS**

**-**

**-**

Contains information on analytics production.

TAG

MANDATORY

CLOUD_ANALYTICS

**CUSTOMER_CODE**

Client customer code

ATTRIBUTE

CLOUD_ANALYTICS

**CAMPAIGN**

Campaign name

ATTRIBUTE

CLOUD_ANALYTICS

**TAG_MANAGERS**

**-**

**-**

Contains information about the tag manager to initialize.

MTM is used for internal analytics data production, to provide data to Doxee's BI tools.

GTM is used for external analytics data production, to send data to the customer's platforms.

TAG

OPTIONAL

**MATOMO_TAG_MANAGER**

**-**

Contains information to configure Matomo Tag Manager (MTM).

TAG

OPTIONAL

**CONTAINER_ID**

ID of the container configuration to use

If not specified, the default one is used.

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the tag manager or not.&nbsp;

If present, it overrides the *ANALYTICS&nbsp;*bundle settings and the communication dimension configuration.

ATTRIBUTE

OPTIONAL

**ENDPOINT**

Endpoint to which to send the events

If not specified, the default one is used.

ATTRIBUTE

OPTIONAL

**GOOGLE_TAG_MANAGER**

**-**

Contains information to configure Google Tag Manager (GTM)

TAG

OPTIONAL

**CONTAINER_ID**

ID of the container configuration to use.

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the tag manager or not.

(Default value: false)

ATTRIBUTE

OPTIONAL

**ENDPOINTS**

**-**

**-**

Contains configuration about the endpoints where the Tag Managers will send the analytics events.

TAG

OPTIONAL

**HEADLIGHT**

**-**

Headlight configurations

TAG

OPTIONAL

**ENABLED**

Whether to enable the destination or not.&nbsp;

If present, it overrides the *ANALYTICS&nbsp;*bundle settings and the communication dimension configuration.

ATTRIBUTE

OPTIONAL

**ENDPOINT**

Endpoint to which to send the events

If not specified, the default one is used.

ATTRIBUTE

OPTIONAL

**MATOMO**

**-**

Matomo configurations

TAG

OPTIONAL

**ENABLED**

Whether to enable the destination or not.&nbsp;

ATTRIBUTE

OPTIONAL

**ENDPOINT**

Endpoint to which to send the events

If not specified, the same Matomo Tag Manager endpoint is used.

ATTRIBUTE

OPTIONAL

**SITE_ID**

Matomo site into which to record the events

This field is required when enabled.

ATTRIBUTE

MANDATORY

(when enabled)

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.&nbsp;

If present, it overrides the *ANONYMIZATION&nbsp;*bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**WEBHOOKS**

**-**

Custom webhook configurations

More than one tag can be present.

TAG

OPTIONAL

**ALIAS**

Name of the target webhook (e.g. Nurtigo)

ATTRIBUTE

MANDATORY

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.&nbsp;

If present, it overrides the *ANONYMIZATION&nbsp;*bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the destination or not.

(Default value: false)

ATTRIBUTE

MANDATORY

**ENDPOINT**

URL to which to send the events

ATTRIBUTE

MANDATORY

(when enabled)

**GOOGLE_ANALYTICS_UNIVERSAL**

**-**

Legacy Google Universal Analytics (UA) configurations

The functionality also depends on the presence of the&nbsp;**GOOGLE_TAG_MANAGER** configuration.

TAG

OPTIONAL

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.&nbsp;

If present, it overrides the *GAID* bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the destination or not.

(Default value: false)

If a&nbsp;*GAID&nbsp;*is provided through bundle settings or communication dimension, it will be enabled by default unless explicitly disabled.

ATTRIBUTE

OPTIONAL

**PROPERTY_ID**

Property into which to record the events

ATTRIBUTE

MANDATORY

(when enabled)

**GOOGLE_ANALYTICS_4**

**-**

Google Universal 4 (GA4) configurations

The functionality also depends on the presence of the&nbsp;**GOOGLE_TAG_MANAGER&nbsp;**configuration.

TAG

OPTIONAL

**ANONYMIZATION**

Whether to enable anonymization for the destination or not.&nbsp;

If present, it overrides the *ANONYMIZATION&nbsp;*bundle settings and the communication dimension configuration.

(Default value: true)

ATTRIBUTE

OPTIONAL

**ENABLED**

Whether to enable the destination or not.

(Default value: false)

ATTRIBUTE

OPTIONAL

**PROPERTY_ID**

Property (*measurement_id*) into which to record the events

ATTRIBUTE

MANDATORY

(when enabled)

**TAGS**

**-**

Additional custom dimensions to be attached to analytics events

More than one tag can be present.

TAG

OPTIONAL

**NAME**

Name of the metadata (e.g. campaign, lang, etc)

ATTRIBUTE

MANDATORY

**VALUE**

Value of the metadata

ATTRIBUTE

MANDATORY

**CD**

Index of the custom dimension

 Valid values are between 0 and 9. The value should be unique among all tags. 

ATTRIBUTE

MANDATORY

**METADATA**

**-**

Additional metadata to attach to analytics events

TAG

OPTIONAL

**&lt;METADATA_NAME&gt;**

All attribute names and values&nbsp;will be made available on the document and can then be configured for the events.

ATTRIBUTE

OPTIONAL

## Email delivery
> Important

The tags and attributes described in the following sections are children of the **COMMUNICATIONS/COMMUNICATION** XML element. For better readability, this dependency will not be repeated when describing the fields.

The following table describes all tags and attributes of the&nbsp;**EMAIL&nbsp;**XML section, indicating those required for task execution and those required for the generation of the Cloud Analytics report.

Root tag

Tags

Attributes

Description

Type

Flags

**EMAIL**

**-**

**-**

Root tag for the Email section

TAG

MANDATORY

**COMMUNICATION_NAME**

Unique GUID identifying the communication

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**DOCUMENTS**

**-**

**-**

List of DOCUMENT tags

TAG

LIST

MANDATORY

**DOCUMENT**

**-**

Represents a single document to be sent.

TAG

ELEM_LIST

MANDATORY

**GUID**

Unique GUID&nbsp;

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**PURL**

pURL of the published Pvideo

ATTRIBUTE

OPTIONAL

**SHORT_PURL**

Short pURL of the published Pvideo

This attribute will only be present if URL shortening is enabled on the Pvideo template resource.

ATTRIBUTE

OPTIONAL

**DOCUMENT_NAME**

Unique GUID&nbsp;

ATTRIBUTE

MANDATORY

**ANALYTICS**

**-**

Contains information on analytics production.

TAG

MANDATORY

**CUSTOMER_CODE**

Client customer code

ATTRIBUTE

OPTIONAL

**CAMPAIGN**

Name of the campaign

ATTRIBUTE

OPTIONAL

**TAGS**

-

Additional custom dimensions to be attached to analytics events

More than one tag can be present.

TAG

OPTIONAL

**NAME**

Name of the metadata (e.g. campaign, lang, etc)

ATTRIBUTE

OPTIONAL

**VALUE**

Value of the metadata

ATTRIBUTE

OPTIONAL

**CD**

Index of the custom dimension

Valid values are between 0 and 9. The&nbsp;value should be unique among all tags.

ATTRIBUTE

OPTIONAL

**DATA**

Contains the variables to be used in the Email template resource as attributes.

TAG

MAP

MANDATORY

**DELIVERY**

**-**

**-**

Contains information on email delivery.

TAG

MANDATORY

**-**

**SUBJECT**

Subject of the email

ATTRIBUTE

CLOUD_ANALYTICS

**TO**

**-**

**-**

Contains information on TO recipients

ELEM_LIST

MANDATORY

**ITEM**

**-**

Item of the TO list

ELEM

TAG

MANDATORY

**ADDRESS**

TO recipient's email address

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**NAME**

TO recipient's name

ATTRIBUTE

OPTIONAL

**CC**

**-**

**-**

Contains information on CC recipients

ELEM_LIST

OPTIONAL

**ITEM**

**-**

Item of the CC list

ELEM

TAG

OPTIONAL

**ADDRESS**

CC recipient's email address

ATTRIBUTE

MANDATORY

**NAME**

CC recipient's name

ATTRIBUTE

OPTIONAL

**BBC**

**-**

**-**

Contains information on BCC recipients

ELEM_LIST

OPTIONAL

**ITEM**

**-**

Item of the BCC list

ELEM

TAG

OPTIONAL

**ADDRESS**

BCC recipient's email address

ATTRIBUTE

MANDATORY

**NAME**

BCC recipient's name

ATTRIBUTE

OPTIONAL

**ATTACHMENTS**

**-**

**-**

List of attached files

ELEM_LIST

OPTIONAL

**ATTACHMENT**

**-**

Item of the attachments list, identifying a specific attachment to be sent

ELEM

TAG

OPTIONAL

**X-HEADERS**

**-**

**-**

List of extra headers

ELEM_LIST

OPTIONAL

**X-HEADER**

**-**

Item of the x-headers list, identifying a specific extra header to be appended to the message

ELEM

TAG

OPTIONAL

**KEY**

Key name (with "X-"), uppercase (without :)

ATTRIBUTE

MANDATORY

**VALUE**

Value of the x-header (without :)

ATTRIBUTE

MANDATORY

> Important

If you specify the same email address in the To, Cc, or Bcc fields the communication will be discarded, due to the current constraints of the SendGrid service provider.

> Valid to Doxee Platform 3 Build 3.29

Up to DP3 build 3.29, the structure of the **TO** tag was the following:

**TO**

-

Contains information on the recipient of the email message.

TAG

MANDATORY

**ADDRESS**

Recipient's email address

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**NAME**

Recipient's name

ATTRIBUTE

OPTIONAL

Currently, both structures are still supported, but in the future the single recipient XML structure will be deprecated.

## SMS delivery
> Important

The tags and attributes described in the following sections are children of the **COMMUNICATIONS/COMMUNICATION** XML element. For better readability, this dependency will not be repeated when describing the fields.

The following table describes all tags and attributes of the&nbsp;**SMS** XML section, indicating those required for task execution and those required for the generation of the Cloud Analytics report.

Root Tag

Tags

Attributes

Description

Type

Flags

**SMS**

-

-

Root tag for the SMS section

TAG

MANDATORY

**COMMUNICATION_NAME**

Unique GUID identifying the communication

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**DOCUMENTS**

-

**-**

List of DOCUMENT tags

TAG

LIST

MANDATORY

**DOCUMENT**

-

Represents a single document to be sent.

TAG

ELEM_LIST

MANDATORY

**GUID**

Unique GUID&nbsp;

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

**PURL**

pURL of the published Pvideo

ATTRIBUTE

OPTIONAL

**SHORT_PURL**

Short pURL of the published Pvideo

This attribute will only be present if URL shortening is enabled on the Pvideo template resource.

ATTRIBUTE

OPTIONAL

**DOCUMENT_NAME**

Unique GUID&nbsp;

ATTRIBUTE

MANDATORY

**ANALYTICS**

-

Contains information on analytics production.

TAG

MANDATORY

**CUSTOMER_CODE**

Client customer code

ATTRIBUTE

OPTIONAL

**CAMPAIGN**

Name of the campaign

ATTRIBUTE

OPTIONAL

**TAGS**

**-**

Additional custom dimensions to be attached to analytics events

More than one tag can be present.

TAG

OPTIONAL

**NAME**

Name of the metadata (e.g. campaign, lang, etc)

ATTRIBUTE

OPTIONAL

**VALUE**

Value of the metadata

ATTRIBUTE

OPTIONAL

**CD**

Index of the custom dimension

Valid values are between 0 and 9. The value should be unique among all tags.

ATTRIBUTE

OPTIONAL

**DATA**

**-**

Contains the variables to be used in the SMS template resource as attributes.

TAG

MAP

MANDATORY

**DELIVERY**

**-**

**-**

Contains information on SMS delivery.

TAG

MANDATORY

**TO**

-

Contains information on the recipient of the SMS message.

TAG

MANDATORY

**PHONE**

Recipient's phone number

ATTRIBUTE

MANDATORY

CLOUD_ANALYTICS

## AppIO delivery
> Important

The tags and attributes described in the following sections are children of the **COMMUNICATIONS/COMMUNICATION** XML element. For better readability, this dependency will not be repeated when describing the fields.

The following table describes all tags and attributes of the&nbsp;**SMS** XML section for the AppIO Delivery, indicating those required for task execution.

Root Tag

Tags

Attributes

Description

Type

Flags

**SMS**

-

-

Root tag for the SMS section

TAG

MANDATORY

**COMMUNICATION_NAME**

Unique GUID identifying the communication

ATTRIBUTE

MANDATORY

**DOCUMENTS**

-

-

List of DOCUMENT tags

TAG

LIST

MANDATORY

**DOCUMENT**

-

Represents a single document to be sent.

TAGELEM_LIST

MANDATORY

**PURL**

pURL of the published Pvideo

ATTRIBUTE

OPTIONAL

**SHORT_PURL**

Short pURL of the published Pvideo

This attribute will only be present if URL shortening is enabled on the Pvideo template resource.

ATTRIBUTE

OPTIONAL

**DATA**

**FISCAL_CODE**

end user fiscal code

ATTRIBUTE

MANDATORY

**APP_IO_SUBJECT**

The subject of the message - note that only some notification channels support the display of a subject. When a subject is not provided, one gets generated from the client attributes. (&gt;= 10 characters&lt;= 120 characters)

ATTRIBUTE

MANDATORY

**APP_IO_DUE_DATE**

A date-time field in ISO-8601 format and UTC timezone.

ATTRIBUTE

OPTIONAL

**APP_IO_REQUIRE_SECURE_CHANNEL**

Boolean, When true messages won't trigger email notifications (only push).

ATTRIBUTE

OPTIONAL

**APP_IO_PAYMENT_AMOUNT**

Amount of payment in euro cent. PagoPA accepts up to 9999999999 euro cents.

(&gt;= 1, &lt;= 9999999999)

ATTRIBUTE

OPTIONAL

**APP_IO_PAYMENT_NOTICE_NUMBER**

The field "Numero Avviso" of pagoPa, needed to identify the payment. Format is `&lt;aux digit(1n)&gt;[&lt;application code&gt; (2n)]&lt;codice IUV (15|17n)&gt;`. See [pagoPa specs](https://docs.pagopa.it/saci/specifiche-attuative-dei-codici-identificativi-di-versamento-riversamento-e-rendicontazione/premessa) for more info on this field and the IUV.

Match pattern:^[0123][0-9]{17}$

ATTRIBUTE

OPTIONAL

**APP_IO_PAYMENT_PAYEE**

Metadata needed to explicit payment's payee.

fiscal_code string&lt;OrganizationFiscalCode&gt;required (Organization fiscal code)

ATTRIBUTE

OPTIONAL

**APP_IO_PAYMENT_INVALID_AFTER_DUE_DATE**

boolean, payment invalid after due date

ATTRIBUTE

OPTIONAL

## SMS/Email delivery schedule
> Important

The tags and attributes described in the following sections are children of the **COMMUNICATIONS **XML element. For better readability, this dependency will not be repeated when describing the fields.

> Important

The mandatory fields under this section are mandatory only for the delivery scheduling use case. If this is not the right use case, please ignore them  

Root Tag

Tags

Attributes

Description

Type

Flags

**SCHEDULE**

-

-

Root tag for the Delivery schedule section

TAG

MANDATORY

**DISPATCH**

-

Tag for Dispatch settings

TAG

MANDATORY

**FROM**

Define schedule windows. Admitted format are

- YYYY-MM-DD (es. 2024-07-29)

- YYYY-MM-DDTHH:mm:SS.sssZ (es.2024-07-29T18:00:00.000Z)

ATTRIBUTE

OPTIONAL

## Example: XML structure of the input file for a Pvideo sent via Email or SMS
The following example represents the structure of an XML input file covering the scenario of a Pvideo that is sent via email and/or sms, that will be correctly tracked for analytics purposes.

**Example**

`&lt;?xml version="1.0" encoding="UTF-8" ?&gt;
&lt;COMMUNICATIONS&gt;
&lt;COMMUNICATION&gt;
   &lt;PVIDEO TITLE="Pvideo for Gian Marco Lucchino" GUID="ef63e21cadcb46239a252d64ad9398c8" SHORT_PURL="https://s.dev.doxee.com/sxByaAv" PURL="https://media-tenant01.dev.doxee.com/pvideo/t/ef63e21cadcb46239a252d64ad9398c8"&gt;
      &lt;DATA lastName="Lucchino" LABELLINK6="CTAScene6" ANIMAL_IMAGE="DOG" TEXT_MALE1="Hi, I'm Joey and I'm using a TTS to talk to you in English ma ti posso parlare anche in Italiano" imgUrl2="https://placekitten.com/50/100" imgUrl3="https://placekitten.com/100/50" LINK1="https://catflix.cl/" imgUrl1="https://placekitten.com/100/100" LINK2="https://www.doxee.com/it/" title="Pvideo for Gian Marco Lucchino" LABELLINK5="CTAScene5" DEFAULTRACK="default" TRACK="dawn" firstName="Gian Marco" videoUrl="https://wp-en.oberlo.com/wp-content/uploads/2018/10/1.-Pixabay.mp4?_=1" shipmentID="219235d4b60c41f185dd1c7bcef5eee5" guid="ef63e21cadcb46239a252d64ad9398c8" ActivationDate="20151215" videoBackgroundScene1="videos/BGSceneID.mp4" ClientFiscalCode="MRNSFN83L28E290J" email="glucchino@gmail.com" TRACK1="sweetie"/&gt;
      &lt;SCENES&gt;
         &lt;SCENE&gt;SCENE1&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE2&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE3&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE4&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE5&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE6&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE7&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE8&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE9&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE10&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE11&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE12&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE13&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE14&lt;/SCENE&gt;
         &lt;SCENE&gt;SCENE15&lt;/SCENE&gt;
      &lt;/SCENES&gt;
      &lt;TTS&gt;
         &lt;DATA&gt;
            &lt;SPEECH ID="TTS_MALE01" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Joey" LANGUAGE="en-US" GENDER="Male"&gt;Hi, I'm Joey &lt;break time='2s'/&gt;  and I'm using a TTS to talk to you in English &lt;lang xml:lang='it-IT'&gt; ma ti posso parlare anche in italiano&lt;/lang&gt;.&lt;/SPEECH&gt;
            &lt;SPEECH ID="TTS_FEMALE01" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Conchita" LANGUAGE="es-ES" GENDER="Female"&gt;Hola Gian Marco soy Conchita y estoy usando un TTS para hablar contigo.&lt;/SPEECH&gt;
            &lt;SPEECH ID="TTS_MALE03-01" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Joey" LANGUAGE="en-US" GENDER="Male"&gt;Using TTS frame sync you can make the voice start at an exact frame&lt;/SPEECH&gt;
            &lt;SPEECH ID="TTS_FEMALE03-02" TYPE="application/ssml+xml" SAMPLE_RATE="22050" RATE="medium" VOLUME="medium" SENTENCE_BREAK="500" PARAGRAPH_BREAK="650" NAME="Conchita" LANGUAGE="es-ES" GENDER="Female"&gt;Sí, eso es sin duda útil para sincronizar TTS a animación&lt;/SPEECH&gt;
         &lt;/DATA&gt;
      &lt;/TTS&gt;
      &lt;DA GUID="ef63e21cadcb46239a252d64ad9398c8" COMMUNICATION_ID="219235d4b60c41f185dd1c7bcef5eee5" CUSTOMER_EMAIL="glucchino@gmail.com" JOB_ID="102180"/&gt;
      &lt;ANALYTICS CAMPAIGN="campaign" CUSTOMER_CODE="code"&gt;
          &lt;TAG_MANAGERS&gt;
              &lt;MATOMO_TAG_MANAGER ENABLED="true" CONTAINER_ID="M-12345" ENDPOINT="matomo.doxee.com"/&gt;
              &lt;GOOGLE_TAG_MANAGER ENABLED="true" CONTAINER_ID="G-12345"/&gt;
          &lt;/TAG_MANAGERS&gt;
          &lt;ENDPOINTS&gt;
              &lt;HEADLIGHT ENABLED="true" ENDPOINT="https:hl.doxee.com"/&gt;
              &lt;CLOUD_ANALYTICS ENABLED="true" ENDPOINT="https://ca.doxee.com"/&gt;
              &lt;MATOMO ENABLED="true" ENDPOINT="matomo.doxee.com" SITE_ID="1" ANONYMIZATION="true"/&gt;
              &lt;GOOGLE_ANALYTICS_UNIVERSAL ENABLED="true" PROPERTY_ID="UA-123" ANONYMIZATION="true"/&gt;
              &lt;GOOGLE_ANALYTICS_4 ENABLED="true" PROPERTY_ID="M-123" ANONYMIZATION="true"/&gt;
              &lt;WEBHOOKS ALIAS="nurtigo" ENABLED="true" ANONYMIZATION="true" ENDPOINT="nurtigo.doxee.com"/&gt;
              &lt;WEBHOOKS ALIAS="custom" ENABLED="true" ANONYMIZATION="false" ENDPOINT="custom.com"/&gt;
         &lt;/ENDPOINTS&gt;
         &lt;TAGS NAME="campaign" VALUE="pvideo-campaign" CD="0" /&gt;
         &lt;TAGS NAME="lang" VALUE="IT" CD="1" /&gt;
         &lt;METADATA ADDITIONAL_METADATA1="additional_metadata1" ADDITIONAL_METADATA2="additional_metadata2"/&gt;              
      &lt;/ANALYTICS&gt;
   &lt;/PVIDEO&gt;
   &lt;EMAIL COMMUNICATION_NAME="219235d4b60c41f185dd1c7bcef5eee5"&gt;
      &lt;DOCUMENTS&gt;
         &lt;DOCUMENT GUID="ef63e21cadcb46239a252d64ad9398c8" PURL="https://media-tenant01.dev.doxee.com/pvideo/t/ef63e21cadcb46239a252d64ad9398c8" SHORT_PURL="https://s.dev.doxee.com/sxByaAv" DOCUMENT_NAME="219235d4b60c41f185dd1c7bcef5eee5"/&gt;
      &lt;/DOCUMENTS&gt;
      &lt;ANALYTICS CAMPAIGN="KEY-WEJT_CMP"&gt;
		 &lt;TAGS NAME="campaign" VALUE="pvideo-campaign" CD="0" /&gt;
         &lt;TAGS NAME="lang" VALUE="IT" CD="1" /&gt;	
	  &lt;ANALYTICS/&gt;
      &lt;DATA firstName="Gian Marco" lastName="Lucchino" ClientFiscalCode="MRNSFN83L28E290J"/&gt;
      &lt;DELIVERY SUBJECT="Ciao ,Gian Marco, ecco il tuo video"&gt;
         &lt;TO ADDRESS="glucchino@gmail.com"/&gt;
         &lt;CC&gt;
            &lt;ITEM ADDRESS="glucchino@doxee.com" NAME="Gian Marco Lucchino"/&gt;
         &lt;/CC&gt;
         &lt;BCC&gt;
            &lt;ITEM ADDRESS="marcello.filone@hrmgroup.it" NAME="Marcello Filone"/&gt;
         &lt;/BCC&gt;
      &lt;/DELIVERY&gt;
   &lt;/EMAIL&gt;
   &lt;SMS COMMUNICATION_NAME="219235d4b60c41f185dd1c7bcef5eee5"&gt;
      &lt;DOCUMENTS&gt;
         &lt;DOCUMENT GUID="ef63e21cadcb46239a252d64ad9398c8" PURL="https://media-tenant01.dev.doxee.com/pvideo/t/ef63e21cadcb46239a252d64ad9398c8" SHORT_PURL="https://s.dev.doxee.com/sxByaAv" DOCUMENT_NAME="219235d4b60c41f185dd1c7bcef5eee5"/&gt;
      &lt;/DOCUMENTS&gt;
      &lt;ANALYTICS CAMPAIGN="KEY-WEJT_CMP"&gt;
		 &lt;TAGS NAME="campaign" VALUE="pvideo-campaign" CD="0" /&gt;
         &lt;TAGS NAME="lang" VALUE="IT" CD="1" /&gt;	
	  &lt;ANALYTICS/&gt;      &lt;DATA firstName="Gian Marco" lastName="Lucchino" ClientFiscalCode="MRNSFN83L28E290J"/&gt;
      &lt;DELIVERY SUBJECT=""&gt;
         &lt;TO PHONE="+393293760369"/&gt;
         &lt;CC&gt;
            &lt;ITEM ADDRESS="" NAME=""/&gt;
         &lt;/CC&gt;
         &lt;BCC&gt;
            &lt;ITEM ADDRESS="" NAME=""/&gt;
         &lt;/BCC&gt;
      &lt;/DELIVERY&gt;
   &lt;/SMS&gt;
&lt;/COMMUNICATION&gt;
&lt;SCHEDULE&gt;
      &lt;DISPATCH FROM="2024-07-29T18:00:00.000Z"/&gt;
&lt;/SCHEDULE&gt; 
&lt;/COMMUNICATIONS&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}