---
id: "1fee97e2-611a-4119-98eb-c0766a1bf979"
title: "Quick Start"
slug: "6-6-template-designer-user-guide-quick-start-1"
category: "Template Designer"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Template Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-10-14T13:25:53.455Z"
modified_at: "2025-11-18T10:26:30.578Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/6-6-template-designer-user-guide-quick-start-1"
synced_at: "2026-01-28T21:03:58.449Z"
checksum: "84b9a79349bfced0"
---

Navigate to other release versions of Doxee Platform Template Designer

[6.6](https://docs.doxee.com/docs/en/template-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/template-designer-6-7)

This chapter provides a quick introduction to the basic functionality of Template Designer. Detailed explanations of the individual features and components can be found in the subsequent chapters.

## 
## Creating a template
A new template can be created by clicking the *New Template *entry in the menu or toolbar. This prompts the user for a file type (confirm the pre-selected "Template" for now) and for a file location to save the template. An empty template is created and displayed in the editor. Content can be added by typing in the graphical editor, or by inserting elements from the palette. Menus and toolbar icons provide multiple ways to format the content.

> Note

The content of the template is available both in the graphical editor and in the *Outline *view. Selecting an item in one of the views will automatically also select it in the other view (called "selection synchronization") if the element is displayed there.

## Adding dynamic content
For adding dynamic content to your template, you should have an XML file with a data sample ready. If you do not have one, you can skip this chapter and explore templates with static content for now.

Add a new Data Input element by right-clicking either on the background of the *Data Inputs *view (if presently open) or on the Data Inputs node of the *Outline *view. In the context menu, select *Add new Data Input*. In the dialog that opens, provide the path to your sample XML file.

After adding the reference to your sample XML, you can browse its content as a tree. Add a reference to a data field to your template either via drag-and-drop or copy/paste and select the *Dynamic Value *option when prompted for the type of field that you want to create.

## Preview
> Note

The preview feature requires that a PDF viewer is installed on your computer.

At any time during template design, you can preview a PDF version of your document (template with sample XML data) by clicking the *PDF (FOP) *preview tab. At the first time, please allow a few seconds for the PDF viewer to start up.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}