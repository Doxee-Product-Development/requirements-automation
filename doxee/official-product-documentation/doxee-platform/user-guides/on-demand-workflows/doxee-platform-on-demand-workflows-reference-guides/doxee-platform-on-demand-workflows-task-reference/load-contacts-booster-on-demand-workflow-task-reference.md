---
id: "4a969892-52ff-4922-bbfd-2a1723b4e12a"
title: "Load Contacts (Booster) On-Demand Workflow Task Reference"
slug: "load-contacts-booster-on-demand-workflow-task-reference"
category: "Doxee Platform On-Demand Workflows Task Reference"
category_path:
  - "Product guides"
  - "On-Demand Workflows"
  - "Doxee Platform On-Demand Workflows Reference Guides"
  - "Doxee Platform On-Demand Workflows Task Reference"
status: "published"
content_type: "block"
version: 2
public_version: 2
created_at: "2025-12-16T17:22:04.047Z"
modified_at: "2026-01-16T10:51:34.895Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/load-contacts-booster-on-demand-workflow-task-reference"
synced_at: "2026-01-28T20:53:52.165Z"
checksum: "f8656358e06e88d0"
---

## Description
The&nbsp;**Load Contacts (Booster)**&nbsp;task allows to create&nbsp;or update contacts on a Doxee Booster endpoint, based on an input file list of contacts and attributes.

Restraints:

- A different instance with different credentials and endpoint of Doxee Booster is used for each DP3 Account

- Contacts attributes must already exist on Doxee Booster Contact list or needs to be set up manually by delivery operators

- At least one contact attribute on Doxee Booster Contact list needs to be set as unique identifier for the contact

## Configuration
![](data:image/png;base64,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)

- In the&nbsp;**Alias**&nbsp;field, enter the name of the task that will be displayed in the workflow.

- In the&nbsp;**Identifier attribute** field, enter the&nbsp;unique identifier used on Doxee Booster (and in the input file) to identify the contact.

- Enable the&nbsp;**Update existing contacts** option to enable the update mode.

> Important

Existing contacts will only be updated if this option is selected.&nbsp;

> Note

If the contacts found in the input file do not exist in the Doxee Booster contact list, they will be automatically created and uploaded with all their attributes.

If the input file has an empty attribute for a specific contact, or if it includes an attribute that is not present on the Doxee Booster contact list, the attribute will be ignored.

## Input
The task's input must be an XML file containing the definition of the contacts to upload, based on the structure of the fields defined on Doxee Booster.

### Input tags
A communication's contact is an element without children,&nbsp;with at least one attribute (its identifier, configurable while designing the workflow).

`/COMMUNICATIONS/COMMUNICATION/BOOSTER/CONTACTS/CONTACT&nbsp;`> Important

The&nbsp;**BOOSTER**&nbsp;tag is optional, thus a communication without contacts is possible.

All the&nbsp;**CONTACT**&nbsp;attributes must exist as contact fields in the target Doxee Booster instance, otherwise the task will not load the contact and will discard the communication (or fail), reporting the unknown fields.

> Warning

The input file must contain the&nbsp;***firstname***&nbsp;(lowercase) attribute, otherwise the contact will be loaded as "anonymous" on Doxee Booster and will not be searchable.

### Example
**Input file**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;COMMUNICATIONS&gt;
	&lt;COMMUNICATION&gt;
	   &lt;BOOSTER&gt;
		  &lt;CONTACTS&gt;
			 &lt;CONTACT firstname="Scrooge" lastname="McDuck" email="s.mcduck@mcduckenterprises.com" role="ceo"/&gt;
			 &lt;CONTACT firstname="Emily" lastname="Quackfaster" email="e.quackfaster@mcduckenterprises.com" role="secretary" hair="blonde"/&gt;
			 &lt;CONTACT firstname="Donald" lastname="Duck" email="d.duck@mcduckenterprises.com" debt="infinite"/&gt;
		  &lt;/CONTACTS&gt;
	   &lt;/BOOSTER&gt;
	&lt;/COMMUNICATION&gt;
&lt;/COMMUNICATIONS&gt;`> Note

In the input file, it is possible set the content of an attribute as a variable. In the following example, $PURL$ and $SHORT_PURL$:

**Input file with variables**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;COMMUNICATIONS&gt;
	&lt;COMMUNICATION&gt;
	   &lt;BOOSTER&gt;
		  &lt;CONTACTS&gt;
			 &lt;CONTACT firstname="Marcello" FirstName="Marcello" LastName="Rossi" Identifier="mrossi@example.com" Indirizzo="$PURL$" SPurl="$SHORT_PURL$"/&gt;
		  &lt;/CONTACTS&gt;
	   &lt;/BOOSTER&gt;
	&lt;/COMMUNICATION&gt;
&lt;/COMMUNICATIONS&gt;`## Output
The task's output is the input XML file with added tags and attributes to provide details on the status of the loading operation and notify of any errors.&nbsp;

### Output tags
The task adds&nbsp;the attribute&nbsp;**BOOSTER_LOADER_STATUS**&nbsp;to each loaded contact, with one of the following values:

Value

Description

**CREATED**

The contact did not exist and has been created.

**UPDATED**

The contact already existed and has been updated.

**UNCHANGED**

The contact already existed and has been skipped (this happens only if the task is configured to not update existing contacts).

In case of errors, the task adds&nbsp;an **ERROR** element to the contact, which may in turn contain the following elements, depending on the value of its attribute&nbsp;**ERROR_CODE**:

ERROR_CODE

Child element

Optional

Repeatable

Value

**MISSING_IDENTIFIER**

MISSING_IDENTIFIER

![(error)](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48Y2lyY2xlIGZpbGw9IiNERTM1MEIiIGN4PSI4IiBjeT0iOCIgcj0iOCIvPjxwYXRoIGQ9Ik05LjQ4NSA4LjA3MWwyLjEyMiAyLjEyMWExIDEgMCAxIDEtMS40MTUgMS40MTVsLTIuMTItMi4xMjItMi4xMjIgMi4xMjJhMSAxIDAgMSAxLTEuNDE0LTEuNDE1bDIuMTItMi4xMi0yLjEyLTIuMTIyQTEgMSAwIDEgMSA1Ljk1IDQuNTM2bDIuMTIxIDIuMTIgMi4xMjEtMi4xMmExIDEgMCAxIDEgMS40MTUgMS40MTRMOS40ODUgOC4wN3oiIGZpbGw9IiNGRkYiLz48L2c+PC9zdmc+)

![(error)](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48Y2lyY2xlIGZpbGw9IiNERTM1MEIiIGN4PSI4IiBjeT0iOCIgcj0iOCIvPjxwYXRoIGQ9Ik05LjQ4NSA4LjA3MWwyLjEyMiAyLjEyMWExIDEgMCAxIDEtMS40MTUgMS40MTVsLTIuMTItMi4xMjItMi4xMjIgMi4xMjJhMSAxIDAgMSAxLTEuNDE0LTEuNDE1bDIuMTItMi4xMi0yLjEyLTIuMTIyQTEgMSAwIDEgMSA1Ljk1IDQuNTM2bDIuMTIxIDIuMTIgMi4xMjEtMi4xMmExIDEgMCAxIDEgMS40MTUgMS40MTRMOS40ODUgOC4wN3oiIGZpbGw9IiNGRkYiLz48L2c+PC9zdmc+)

The name of the identifier field that is missing

**UNKNOWN_ATTRIBUTES**

UNKNOWN_ATTRIBUTE

![(error)](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48Y2lyY2xlIGZpbGw9IiNERTM1MEIiIGN4PSI4IiBjeT0iOCIgcj0iOCIvPjxwYXRoIGQ9Ik05LjQ4NSA4LjA3MWwyLjEyMiAyLjEyMWExIDEgMCAxIDEtMS40MTUgMS40MTVsLTIuMTItMi4xMjItMi4xMjIgMi4xMjJhMSAxIDAgMSAxLTEuNDE0LTEuNDE1bDIuMTItMi4xMi0yLjEyLTIuMTIyQTEgMSAwIDEgMSA1Ljk1IDQuNTM2bDIuMTIxIDIuMTIgMi4xMjEtMi4xMmExIDEgMCAxIDEgMS40MTUgMS40MTRMOS40ODUgOC4wN3oiIGZpbGw9IiNGRkYiLz48L2c+PC9zdmc+)

![(tick)](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48Y2lyY2xlIGZpbGw9IiMwMDg3NUEiIGN4PSI4IiBjeT0iOCIgcj0iOCIvPjxwYXRoIGQ9Ik0xMC4yNDIgNC40NzRhLjk0MS45NDEgMCAwIDEgMS42MzQuOTM0TDguMTEgMTEuOTk2YS45NDEuOTQxIDAgMCAxLTEuNTQuMTM2TDQuMjE4IDkuMzA4YS45NDEuOTQxIDAgMSAxIDEuNDQ2LTEuMjA1TDcuMTUgOS44ODZsMy4wOTMtNS40MTJ6IiBzdHJva2U9IiNGRkYiIHN0cm9rZS13aWR0aD0iLjIiIGZpbGw9IiNGRkYiIGZpbGwtcnVsZT0ibm9uemVybyIvPjwvZz48L3N2Zz4=)

The name of one of the unknown attributes

*other*

ERROR_MESSAGE

![(tick)](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48Y2lyY2xlIGZpbGw9IiMwMDg3NUEiIGN4PSI4IiBjeT0iOCIgcj0iOCIvPjxwYXRoIGQ9Ik0xMC4yNDIgNC40NzRhLjk0MS45NDEgMCAwIDEgMS42MzQuOTM0TDguMTEgMTEuOTk2YS45NDEuOTQxIDAgMCAxLTEuNTQuMTM2TDQuMjE4IDkuMzA4YS45NDEuOTQxIDAgMSAxIDEuNDQ2LTEuMjA1TDcuMTUgOS44ODZsMy4wOTMtNS40MTJ6IiBzdHJva2U9IiNGRkYiIHN0cm9rZS13aWR0aD0iLjIiIGZpbGw9IiNGRkYiIGZpbGwtcnVsZT0ibm9uemVybyIvPjwvZz48L3N2Zz4=)

![(error)](data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48Y2lyY2xlIGZpbGw9IiNERTM1MEIiIGN4PSI4IiBjeT0iOCIgcj0iOCIvPjxwYXRoIGQ9Ik05LjQ4NSA4LjA3MWwyLjEyMiAyLjEyMWExIDEgMCAxIDEtMS40MTUgMS40MTVsLTIuMTItMi4xMjItMi4xMjIgMi4xMjJhMSAxIDAgMSAxLTEuNDE0LTEuNDE1bDIuMTItMi4xMi0yLjEyLTIuMTIyQTEgMSAwIDEgMSA1Ljk1IDQuNTM2bDIuMTIxIDIuMTIgMi4xMjEtMi4xMmExIDEgMCAxIDEgMS40MTUgMS40MTRMOS40ODUgOC4wN3oiIGZpbGw9IiNGRkYiLz48L2c+PC9zdmc+)

If present, the message related to the error

> Note

For more information on the possible error codes, see&nbsp;[Error codes](/doxee-platform/docs/load-contacts-booster-on-demand-workflow-task-reference#error-codes) below.

### Example
**Successfully processed**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;COMMUNICATIONS&gt;
	&lt;COMMUNICATION&gt;
	   &lt;BOOSTER&gt;
		  &lt;CONTACTS&gt;
			 &lt;CONTACT firstname="Scrooge" lastname="McDuck" email="s.mcduck@mcduckenterprises.com" role="ceo" BOOSTER_LOADER_STATUS="UPDATED"/&gt;
			 &lt;CONTACT firstname="Emily" lastname="Quackfaster" email="e.quackfaster@mcduckenterprises.com" role="secretary" hair="blonde" BOOSTER_LOADER_STATUS="CREATED"/&gt;
			 &lt;CONTACT firstname="Donald" lastname="Duck" email="d.duck@mcduckenterprises.com" debt="infinite" BOOSTER_LOADER_STATUS="UPDATED"/&gt;
		  &lt;/CONTACTS&gt;
	   &lt;/BOOSTER&gt;
	&lt;/COMMUNICATION&gt;
&lt;/COMMUNICATIONS&gt;`**Processed with errors**

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;COMMUNICATIONS&gt;
    &lt;COMMUNICATION&gt;
       &lt;BOOSTER&gt;
          &lt;CONTACTS&gt;
             &lt;CONTACT firstname="Scrooge" lastname="McDuck"&gt;
                &lt;ERROR CODE="MISSING_IDENTIFIER"&gt;
                    &lt;MISSING_IDENTIFIER&gt;email&lt;/MISSING_IDENTIFIER&gt;
                &lt;/ERROR&gt;
             &lt;/CONTACT&gt;
             &lt;CONTACT firstname="Emily" lastname="Quackfaster" email="e.quackfaster@mcduckenterprises.com" role="secretary" hair="blonde"&gt;
                &lt;ERROR CODE="UNKNOWN_ATTRIBUTES"&gt;
                    &lt;UNKNOWN_ATTRIBUTE&gt;role&lt;/UNKNOWN_ATTRIBUTE&gt;
                    &lt;UNKNOWN_ATTRIBUTE&gt;hair&lt;/UNKNOWN_ATTRIBUTE&gt;
                &lt;/ERROR&gt;
             &lt;/CONTACT&gt;
             &lt;CONTACT firstname="Donald" lastname="Duck" email="d.duck@mcduckenterprises.com" debt="infinite"&gt;
                &lt;ERROR CODE="VALIDATION_ERROR"&gt;
                    &lt;ERROR_MESSAGE&gt;debt: This value is not valid.&lt;/ERROR_MESSAGE&gt;
                &lt;/ERROR&gt;
             &lt;/CONTACT&gt;
             &lt;CONTACT firstname="Fethry" lastname="Duck" email="f.duck@mcduckenterprises.com"&gt;
                &lt;ERROR CODE="GENERIC_ERROR"&gt;
                    &lt;ERROR_MESSAGE&gt;Service Unavailable&lt;/ERROR_MESSAGE&gt;
                &lt;/ERROR&gt;
             &lt;/CONTACT&gt;
          &lt;/CONTACTS&gt;
       &lt;/BOOSTER&gt;
    &lt;/COMMUNICATION&gt;
&lt;/COMMUNICATIONS&gt;`## Error management
> Difference between batch and on-demand workflow tasks

The Batch workflow task discards a communication if one of its contacts cannot be loaded due to one of the errors listed below, while the On-Demand workflow task fails immediately.

In general, when the Batch workflow task would discard a communication, the On-Demand task fails, since it does support the possibility to discard a communication.

### Error codes
ERROR_CODE

Source

Meaning

**UNKNOWN_STATUS_CODE**

Facility

Doxee Booster answered with an unexpected status code to the contact create or update request.

This error code is meant to highlight changes to the Doxee Booster that don't break the integration but could result in some unexpected behavior.

**VALIDATION_ERROR**

Facility

The contact cannot be created or update due to a validation error on one or more of its fields.

**MISSING_IDENTIFIER**

Task

The contact is missing the identifier field.

**UNKNOWN_ATTRIBUTES**

Task

The contact has at least one field that does not exist on Doxee Booster.

**DUPLICATE_ENTRY**

Facility

The contact cannot be created as it already exists.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}