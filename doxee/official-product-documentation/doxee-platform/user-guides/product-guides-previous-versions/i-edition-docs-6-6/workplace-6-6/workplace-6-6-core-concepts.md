---
id: "6feadcd4-b60d-43e8-9721-4beb204c3390"
title: "Core concepts of Workplace 2"
slug: "workplace-6-6-core-concepts"
category: "Workplace 2"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Workplace 2"
status: "draft"
content_type: "block"
version: 3
public_version: 3
created_at: "2025-07-28T16:38:42.377Z"
modified_at: "2025-09-01T13:41:44.351Z"
authors:
  - name: "Davide Daccico"
    email: "ddaccico@doxee.com"
  - name: "Dominika Kassovicova"
    email: "dkassovicova@doxee.com"
source_url: "https://docs.doxee.com/docs/en/workplace-6-6-core-concepts"
synced_at: "2026-01-28T21:04:50.951Z"
checksum: "a5be6f222d11adf3"
---

Workplace 2 was designed and built for interactive B2C communication in service-oriented environments. It provides an intuitive and user-friendly portal interface where users can start Business Cases, edit tasks, and keep an overview over ongoing customer communications workflows. It serves as a touchpoint between the Business User and a type of Process Engine-orchestrated process that is called Business Case.

**Business Cases** are Workplace-specific process definitions. They are interactive processes, which means that they may require user input in order to produce personalized digital documents and deliver them to the end customer. Like other processes, Business Cases are created as IPD files in Process Designer and executed in the background by Process Engine. Workplace acts as a client by enabling user interaction with Process Engine.

**Business Cases** **Instances **are instantiated Business Cases in Workplace 2.

**Human Tasks** are the key touchpoints between Process Engine and the user. These are process steps requiring user input, for example selecting the terms of a service contract or approving the payment of a bill. Some Human Tasks extend the functionality of Workplace to other Doxee applications like Composer and Business Designer. The default Workplace installation includes a set of predefined Human Tasks which cover the most frequent actions taken by a user in a Business Case. These can be used by Workplace administrators for building new Business Cases in Process Designer.

**Task Manager** is the backend component which coordinates all necessary tasks within interactive processes, ensuring smooth interactions between Workplace and other Doxee products.

### FAQ
#### What is the difference between a Business Case and a Business Case Instance?
Business Cases are interactive processes. Once a Business Case has been started, for example by a Workplace user, it becomes a Business Case Instance and receives a unique ID. This helps distinguishing many different instances of the same Business Case which may be running simultaneously.

Infinica Process Definition (IPD) is an XML-based file format for storing Infinica process definitions. Processes can either be written manually in the IPD format in a text editor, or created in the GUI tool Process Designer and exported in IPD format.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}