---
id: "a4418659-fc8f-4cc2-9612-a173e6e33711"
title: "Fundamental concepts of the Business Designer, functionality of templates"
slug: "6-6-business-designer-user-guide-fundamental-concepts-of-the-business-designer-functionality-of-templates"
category: "Business Designer"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Business Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-13T11:11:16.965Z"
modified_at: "2025-11-18T10:37:44.835Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-business-designer-user-guide-fundamental-concepts-of-the-business-designer-functionality-of-templates"
synced_at: "2026-01-28T20:59:55.325Z"
checksum: "19ecbbbf37ededd9"
---

Navigate to other release versions of Doxee Platform Business Designer

[6.6](https://docs.doxee.com/docs/en/business-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/business-designer-6-7)

## Purposes of the Business Designer
The Business Designer is used to create templates for documents via web browser. These can be templates for serial letters, customer contracts, registration documents, personalized advertising messages, invoices, bank statements etc.

The Business Designer is part of the Doxee solutions for creating and distributing printable and electronic business communication. The Business Designer enables you to create and complete templates with variable data (e.g. data from a customer database). These templates will be generated to actual individualized documents by the use of further software.

## Elements of templates
In templates static content (e.g. fixed text, header, company logo) is combined with dynamic content (e.g. name, address, customer number). So templates contain **static elements **and **dynamic elements**, whereby there are several types of dynamic elements that can be used to control content for a variety of purposes:

These can be **data fields **- to insert data from the data source linked to the template.

**Condition elements **are used for content rules based on the data used, i.e. to generate certain content depending on the data situation. E.g. a personalized salutation ("Dear Sir/ Dear Ms") is generated this way, or you can insert specific marketing texts that depend on the customer status. Furthermore, **calculations **based on the incoming data (subtotals etc.) can be inserted, which allows e.g. the generation of accounts.

With **logical operations **contents can be controlled on the basis of data queries. And last but not least, **formatting rules **based on the data can be added (e.g. numbers above certain limits can be automatically colored red).

## Data connection
Data that is included in Business Designer templates must be available in XML format. This means that the data coming from your database may first have to be converted to XML format. This can be done by a data preparation process.

The **data structure **(XML schema) is relevant for the template, i.e. which data fields exist and how they are arranged in a tree structure. Therefore, only a **test XML file **which has the corresponding data structure (all required fields) is included in the template. This allows dynamic data elements (references to the data structure) to be inserted into the template.

The fields can also originate from different data sources, i.e. two or more XML files with different structures are integrated.

## Overall process - embedding the Business Designer in the software architecture
Only in connection with the "real" data, the actual individual documents can be created from a template. This can be done fully automated with the Doxee products *Process Designer *or *Process Engine*, or semi-automatically and manually with the *Workplace*, *Composer *or *Process Designer*.

**Process Designer **- is a supporting tool for the Process Engine. It provides a graphical user interface for creating, editing and testing process definitions which can be executed by the Process Engine. The Process Designer covers all features that can be included in an Infinica Process Definition file (IPD) which allows to create processes completely graphically and eliminates the need to manually edit XML files.

**Doxee Content Repository **- is a network based file system which allows multiple users to use the same files of Doxee products. Any kind of file can be stored in the Content Repository.

**Workplace **- is a web application for interactive execution of Doxee business cases and provides an interface for user input. Within the application a list of so called "Human Tasks" is displayed which can be edited via forms.

## File management, templates and collections
- **Templates **are saved as files with the **ending .ITX**. In addition to the template files, you can create "collections" to easily reuse content or formats:

- **Blocks**: Content that always stays the same, i.e. content you use in several templates, can be saved as "template parts" in a collection of template parts. You can create any number of template part collections for different purposes (e.g. "Building Blocks_Invoices.itx", "Blocks_Minder.itx" etc.).

- **Page settings**: To avoid having to specify the page settings for print documents (page spacing, portrait/landscape format, etc.) over and over again, you can save them as "Page Master" in a collection and easily apply them to a new template. You can put all Page Masters into one collection or split them into several collections.

- **Styles**: Formatting text (font style, font size, paragraph alignment, etc.) can be very complex. As with text processing programs, to save time and standardize formats, you can work with style sheets in the Business Designer. If you save style sheets in a style sheet collection, you can use them in all the Business Designer templates. The collections are also saved as files with the .ITX ending. Modules, Page Masters and Styles can also be created within a template - they will only be available in that specific template and marked as **local**. In contrast to those that are included from a collection, they will be marked as **external**.

- **Global variable package**: Global variables can be stored in their own packages to centrally manage a variety of content.

## Technical information
The templates created with the Business Designer follow the XSL-FO standard. The Business Designer is a graphical designer for XSL files and the files are stored as ITX files.

**XSL-FO **(Extensible Stylesheet Language - Formatting Objects) is an XML-based markup language that describes how text, images, lines and other graphical elements are arranged on a page. It is possible to create high-quality print products either on paper or on screen using XSL-FO. Unlike the XHTML/HTML format, which is primarily suitable for browser applications, XSL-FO is used in the printing and archiving sector, i.e. where many pages are generated within a document. XSL-FO was defined as the standard language for converting XML documents into print formats in 2001 by the World Wide Web Consortium (W3C). ([https://www.w3.org/TR/xsl/](https://www.w3.org/TR/xsl/))

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}