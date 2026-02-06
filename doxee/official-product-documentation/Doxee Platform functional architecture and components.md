| DOXEE PLATFORM®                                 |  |
|-------------------------------------------------|--|
| Functional architecture and platform components |  |
| V 1.5 – 10 June 2025                            |  |
| Table of Contents                               |  |
| How to use this document 5                      |  |
| Doxee Platform® 6                               |  |
| DESIGN 8                                        |  |
| Data Designer 8                                 |  |
| Data Transformation (DP3 only) 9                |  |
| Template Designer 9                             |  |
| Business Designer 10                            |  |
| Template Designer 10                            |  |
| Video Designer 11                               |  |
| Process Designer 12                             |  |
| Process Designer 12                             |  |
| Batch Workflows 13                              |  |
| Batch Workflows 13                              |  |
| On-Demand Workflows 14                          |  |
| On-Demand Workflows 14                          |  |
| Output Management 14                            |  |
| ENGAGEMENT 15                                   |  |
| Interactive Documents 15                        |  |
| Workplace 16                                    |  |
| Composer 16                                     |  |
| Personalized Forms & Microsites 16              |  |
| Pweb 17                                         |  |
| Interactive Videos 17                           |  |
| Pvideo 18                                       |  |
| Digital Archive 18                              |  |
| Digital Archiving 20                            |  |

[INSIGHTS 20](#page-18-1)

[Customer Insights 20](#page-19-0)

[Process Insights 20](#page-19-1) [Tracking & Reporting \(DP2/DP3\) 21](#page-20-0) [Platform Reporting \(ex Infinica\) – not to be documented 21](#page-20-1) [Channel Insights 21](#page-20-2) [INTEGRATION 23](#page-21-0) [Marketplace Apps 23](#page-21-1) [APIs and Connectors 24](#page-22-0) [AUTOMATION 25](#page-23-0) [Process Engine 25](#page-23-1) [Process Engine 25](#page-24-0) [Batch Jobs 26](#page-24-1) [On-Demand Jobs 26](#page-25-0) [Omnichannel Engine 27](#page-26-0) [ADMINISTRATION 28](#page-26-1) [Platform Administration 28](#page-27-0) [Command Center 28](#page-27-1) [Batch Workloads 28](#page-28-0) [Resource Manager 29](#page-28-1) [Repository 29](#page-29-0) [Content Repository 29](#page-29-1) [Resource Explorer 30](#page-30-0) [User Manager 30](#page-30-1) [Settings 30](#page-31-0) [Doxee University 32](#page-31-1) Doxee Platform[®](#page-32-0) [Add-Ons \(delivery-managed\) 33](#page-32-0) [Add-ons for global market 33](#page-32-1) [Booster \(DEPRECATED – NOT TO BE SOLD\) 33](#page-32-2) [Content Hub \(DEPRECATED – NOT TO BE SOLD\) 33](#page-32-3) [Web Analytics Platform \(DEPRECATED – NOT TO BE SOLD\) 33](#page-32-4) [Tracking & Reporting \(DEPRECATED – NOT TO BE SOLD\) 33](#page-32-5)

[Namirial Connector 34](#page-33-0)

[Scrive Connector 34](#page-33-1)

[Zuora Connector 34](#page-33-2)

[Add-ons for Italian market 34](#page-33-3)

[Conservazione Digitale a Norma 34](#page-33-4)

[Fatturazione Elettronica 35](#page-34-0)

[Analisi e monitoraggio della Fatturazione Elettronica 36](#page-34-1)

[Portale Fatture 36](#page-35-0)

[Document Cockpit 36](#page-35-1)

[Ordine Elettronico Semplice 37](#page-35-2)

[Ordine Elettronico Completo 37](#page-35-3)

[Ordine Elettronico Pre-concordato 37](#page-36-0)

[Recapito Elettronico Certificato \(SERC/SERCQ\) 38](#page-36-1)

[e-Mail Certificata \(SERC\) 38](#page-37-0)

[e-Recapito \(SERC\) 39](#page-37-1)

[e-Recapito Qualificato \(SERCQ\) 39](#page-37-2)

[Firma Elettronica Semplice \(SES\) o Avanzata \(FEA\) 39](#page-38-0)

<span id="page-2-0"></span>How to use this document

This document provides short functional descriptions of the Doxee Platform® and its components. It is intended to be used as a content repository for sales, marketing, educational, and product documentation purposes. To this end, each entity or entry contains descriptions of varying tone, length, and detail that are appropriate for the intended touchpoint, i.e., the Doxee.com website, product marketing brochures, the Doxee University eLearning platform, and user guides. Each entry is structured in the following way:

# **[Name of the entity]**

| Entity type  | Type and hierarchical level of the entity:<br>•<br>Product brand name<br>◦<br>Platform functional scope name for marketing and sales<br>▪<br>Platform component name for marketing and sales<br>▪<br>Platform component name for whitepapers and<br>user guides |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--|
| 3-word title | Brief 3-word title using public-domain terminology for immediate<br>understanding.<br>This item will be used for Marketing & Sales communication to<br>customers and prospects.                                                                                 |  |
| Brief title  | Brief 1-sentence title for landing pages or banners.<br>This item will be used for Marketing & Sales communication to<br>customers and prospects.                                                                                                               |  |

| Brief<br>description | A brief 2-paragraph description about what it is and related benefits.<br>This item will be used for Marketing & Sales communication to<br>customers and prospects. |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Long                 | Long description for whitepapers and user guides only.                                                                                                              |
| description          | This item will not be used for any Marketing & Sales purposes.                                                                                                      |

# <span id="page-3-0"></span>Doxee Platform®

| Entity type          | Product brand name                                                                                                                                                                                                                                                                |  |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--|
| 3-word<br>title      | One communication platform. Seamless journeys.                                                                                                                                                                                                                                    |  |
| Brief title          | Enabling perfect communication through an AI-powered, intuitive, and flexible platform that boosts customer satisfaction and engagement.                                                                                                                                          |  |
| Brief<br>description | Shape your customer communication and engagement with the power of AI. Doxee Platform® is an easy-to-use, scalable platform that optimizes how businesses create, manage, and deliver data<br>driven personalized and interactive communications across every customer touchpoint |  |

Doxee Platform® is an AI-powered low-code/no-code enterprise platform for customer communication and engagement. It provides an ecosystem of interoperable software components within a single platform, ensuring seamless support for the customer journey at every touchpoint. Doxee Platform® leverages the latest AI-powered technologies to enhance user experience, covering data, template, video and workflow design, customer interaction and engagement with a business workplace, interactive communications, interactive personalized microsites and videos, digital archive, customer insights, customer data hub, platform reporting, omnichannel process automation with process engine and monitoring, and platform administration tools for a full SaaS experience. Doxee Platform® offers marketplace apps for major cloud CRMs and ERPs like Salesforce®, SAP®, and Microsoft® Dynamics 365®, on top of the out-of-the-box APIs and connectors. The platform empowers the construction of complex, mission-critical templates and workflows with elastic scalability, high performance, and efficiency, even for large volumes of data. It also transforms customer interactions by leveraging data to create personalized, interactive communications that align with customer needs and expectations.

The Doxee Platform® includes out-of-the-box product components as part of the standard installation, with optional add-ons available at client request. The Doxee Platform's functional architecture is first introduced at a high level, followed by a detailed examination of its components. The Doxee Platform® covers 6 functional scopes, including design, engagement, insights, integration, automation, and administration.

# **Long description**

# Design

Design personalized interactive communications.

**Data Designer** 

**Template Designer** 

Video Designer

**Process Designer** 

# Engageme

Enhance custo experiences.

Interactive Do
Interactive Fo

Interactive Vid

# **Integration**

Seamlessly integrate CRM/ERP through Marketplace Apps, API, and Connectors.

Marketplace Apps

**API & Connectors** 

# **Automatic**

Enhance produ omnichannel p

Process Engin

Omnichannel I

**Digital Archive** 

# **AI Foundation**

Enhance customer intelligence with the power of AI.

**Template & Content Generation** 

**Template Migration** 

Composer Cop

**Engagement S** 

## <span id="page-5-0"></span>**DESIGN**

| Entity type | The platform functional scope name for marketing and sales |
|-------------|------------------------------------------------------------|
|-------------|------------------------------------------------------------|

| 3-word title         | Collaborative communication design.                                                                                                                                                                                                                                                                                    |  |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--|
| Brief title          | Design personalized interactive communications.                                                                                                                                                                                                                                                                        |  |
| Brief<br>description | Empower your team to easily design templates, videos, and workflows<br>that drive personalized, interactive, and engaging customer<br>communication.<br>Doxee Platform® provides easy-to-use design capabilities and AI<br>powered tools for businesses to create, manage, and optimize their<br>customer experiences. |  |
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                    |  |

# <span id="page-6-0"></span>Data Designer

| Entity type          | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides                                                                                                                                              |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | Data transformation designer                                                                                                                                                                                                                            |
| Brief title          | Transform raw data into ready-to-use, communication-grade output.                                                                                                                                                                                       |
| Brief<br>description | Effortlessly transform and manage your data to create meaningful,<br>customer-centric outputs. Doxee Data Designer's visual designer with<br>intelligent business logic mapper ensures that your data is ready for<br>seamless communication workflows. |

Doxee Platform® Data Designer is a visual low-code designer for data management specialists to process data from different sources, including formats like CSV, XML, Flat Files, TXT, PDF, and AFP.

It simplifies the parsing and transformation of data structures, application of business logic, data mapping, data enrichment, data quality, data sampling, data formatting, and data anonymization, supporting seamless customer communication workflows.

The intuitive web user interface minimizes training needs, allowing efficient handling of complex data transformation and integration tasks.

# **Long description**

This component enhances and organizes data for business communication. By mapping input and output variables, users can apply parsing, data cleaning, and formatting cycles to make information more readable and presentable. Supporting a wide range of input formats and infinite variable relationships, it streamlines the integration of Doxee Platform® functionality into any application context, accelerating go-tomarket timelines and optimizing key customer communication processes.

Doxee Platform® Data Designer also enables the combination of data from different sources, breaking down silos and facilitating integrations across domains and systems. This capability supports digital transformation, extending customer-centric strategies across the organization while unlocking the full potential of data to enhance communication and operational efficiency.

<span id="page-7-0"></span>Data Transformation (DP3 only)

## <span id="page-7-1"></span>Template Designer

| Entity type          | Platform component name for marketing and sales                                                                                                                                                                                                                                  |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | Intelligent template design                                                                                                                                                                                                                                                      |
| Brief title          | AI-enhanced tools for creating personalized interactive templates.                                                                                                                                                                                                               |
| Brief<br>description | Doxee Platform® Template Designer revolutionizes the way you design<br>and personalize communication templates, with AI-powered tools that<br>support dynamic data-driven content, conditional formatting, reusable<br>parts, and test cases for flawless customer interactions. |

# **Long description**

Doxee Platform® Template Designer is a set of AI-powered platform components for creating and managing data-driven communication templates, supporting static and dynamic content, layout components, pagination flows components, conditional formatting, business logic, and test cases. The template designer emphasizes rationalization and reusability of parts across multiple templates, enabling centralized management of styles, dynamic variables, page masters, and reusable template parts that can be shared across multiple templates. This set of tools streamlines the creation of templates for various use cases, including communications, contracts, invoices, bank statements, and personalized advertising messages. Template Designer is modeled with W3C open standards, allowing the generation of multiple output formats such as PDF, PDF/A, PDF/UA, PostScript, AFP, Word, static and interactive HTML, Text, and Formatting Objects XML.

## <span id="page-8-0"></span>Business Designer

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Long<br>description  | Doxee Platform® Business Designer is a web-based component for<br>creating and managing templates for documents and communications,<br>supporting static and dynamic content, layouts, and logic. Templates are<br>structured using an element-based model that follows W3C standards,<br>allowing the generation of outputs such as PDFs, PostScript files,<br>responsive emails, and interactive HTML documents. The platform<br>emphasizes reusability, enabling centralized management of styles,<br>dynamic variables, page masters, and reusable template parts that can be<br>shared across multiple templates. This tool streamlines the creation of<br>templates for various use cases, including communications, contracts,<br>invoices, bank statements, and personalized advertising messages. It<br>integrates fixed elements, like logos, with variable data sourced from<br>customer databases or business systems. Templates can define formatting<br>at the template level, ensuring consistency, saving time, and reducing<br>errors. Business Designer also features a building-blocks model, where<br>reusable components can include logic and parameters, supporting high<br>flexibility and scalability. Components can be local to a single template or<br>shared as collections across templates, ensuring consistency and efficiency<br>in managing document content and styles. |

## <span id="page-9-0"></span>Template Designer

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Long<br>description  | Doxee Platform® Template Designer Desktop Edition is a rich-client<br>application installed on the user's computer, offering functionality identical<br>to Business Designer for creating templates used in generating documents<br>and digital communications on demand. It simplifies the design of layouts<br>and formatting for static and dynamic content through an intuitive<br>interface that requires no specialized knowledge, making it accessible to<br>business users across various departments, including marketing,<br>operations, customer support, and HR. Designed for efficiency and ease of<br>use, Template Designer Desktop Edition supports creating templates for<br>invoices, contracts, quotes, and account statements, seamlessly<br>integrating with Doxee's customer experience products. To accelerate<br>time-to-market for managing large numbers of document templates, users<br>can import Word files directly into the tool, minimizing the need for<br>manual recreation and reducing onboarding time while supporting a<br>streamlined workflow. |

## <span id="page-9-1"></span>Video Designer

| Entity type     | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides |
|-----------------|------------------------------------------------------------------------------------------------------------|
| 3-word<br>title | Personalized and interactive videos designer                                                               |
| Brief title     | Design personalized, interactive, and engaging video experiences at scale<br>with AI-powered tools.        |

| Brief<br>description | Create personalized and interactive video experiences that engage your<br>customers on a scale. Doxee Platform Video Designer offers AI-powered<br>tools for non-linear video editing, enabling you to deliver unique, dynamic<br>videos tailored to individual preferences.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Long<br>description  | Doxee Platform® Video Designer is an AI-powered web-based non-linear<br>video editing component for creating and managing templates for<br>personalized and interactive HTML5 videos. It enables the visual<br>composition of video timelines using stock content and dynamic templates,<br>emphasizing ease of use. Video transforms customer data into<br>personalized and interactive video experiences, incorporating elements like<br>personalized text, banners, images, voice (via text-to-speech and audio<br>libraries), and tailored scenes based on recipient data to deliver unique<br>narratives. Video includes interactive features like in-depth pop-ups, links<br>to data collection landing pages, and calls to action for actions like<br>purchases or payments. Its user-directed storytelling or UDS feature<br>empowers recipients to navigate their storytelling paths, turning videos<br>into a dynamic, bi-directional communication tool that engages viewers<br>while providing insights into their preferences. By combining personalized<br>content with interactivity, Video enhances audience engagement, shortens<br>the conversion funnel, and drives high conversion rates. |

## <span id="page-10-0"></span>Process Designer

| Entity type          | Platform component name for marketing and sales                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Entity<br>name       | Automated process designer                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Brief title          | Easily transform end-to-end business cases into efficient, scalable, and<br>automated CCM processes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Brief<br>description | Build end-to-end document automation and communication processes<br>with a powerful, flexible designer that integrates automated and<br>interactive user-driven steps for seamless business process execution.                                                                                                                                                                                                                                                                                                                                                                              |
| Long<br>description  | Doxee Platform® Process Designer is a set of platform components for<br>creating and configuring document and communication generation<br>processes on the Doxee Platform®, incorporating both automated and<br>interactive user-driven steps. Users define processes by arranging<br>activities and human tasks, each with configurable parameters. It is a<br>solution for configuring production processes that transform raw data into<br>business communications. It defines tasks, creates logical and sequential<br>connections, and supports custom code for process configuration. |

# <span id="page-11-0"></span>Process Designer

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Long<br>description  | Doxee Platform® Process Designer is a tool for creating and configuring<br>document and communication generation processes on the Doxee<br>Platform®, incorporating both automated and interactive user-driven<br>steps. Users define processes by arranging activities and human tasks,<br>each with configurable parameters. These tasks include predefined types<br>and support for custom tasks via HTML, enabling flexibility. Activities can<br>range from data retrieval and form conversion to API calls, email sending,<br>and XSL transformations. Custom activities can be developed in Java and<br>added as components for extended functionality, with processes defined in<br>XML supporting forks, loops, and other constructs. Its intuitive interface<br>allows users to model complex workflows by connecting tasks and<br>activities. The tool integrates seamlessly with Data Designer, enabling<br>efficient data mapping for use within workflows. Users can create<br>multilevel processes that combine automated functions with manual<br>interventions, accommodating the complexities of production and<br>distribution processes. |

# <span id="page-11-1"></span>Batch Workflows

| Entity type          | Platform component name for whitepapers and user guides |
|----------------------|---------------------------------------------------------|
| 3-word title         | n/a                                                     |
| Brief title          | n/a                                                     |
| Brief<br>description | n/a                                                     |

# **Long description**

Doxee Platform® Batch Workflows is a solution for configuring production processes that transform raw data into business communications. It defines tasks, creates logical and sequential connections, and supports custom code for process configuration, making it ideal for managing large volumes of correspondence.

## <span id="page-12-0"></span>Batch Workflows

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Long<br>description  | Doxee Platform® Batch Workflow engine handles document acceptance,<br>processing, production, and multi-channel delivery, streamlining the<br>creation and distribution of extensive document batches. With scheduled<br>execution mode, intelligent parallel processes are used to ensure<br>compliance with service agreements while enabling fully automated<br>workflows for high-volume document handling. This mode supports<br>logistical tracking, manages sampling and production approvals, and<br>integrates with existing document systems. The high level of automation,<br>scalability, and process efficiency is enhanced by a cloud-based service<br>model, available in multi-environment or single-environment<br>configurations, reducing IT workload while ensuring security and<br>performance across all implementation scenarios. Batch workflow includes<br>omnichannel distributions to send communications through multiple<br>channels and protocols like SFTP, Email, SMS, PEC, and AppIO. |

## <span id="page-12-1"></span>On-Demand Workflows

| Entity type  | Platform component name for whitepapers and user guides |
|--------------|---------------------------------------------------------|
| 3-word title | n/a                                                     |
| Brief title  | n/a                                                     |

| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Long<br>description  | Doxee Platform® On-demand Workflows enable the configuration of<br>production processes to transform raw data into business<br>communications, focusing on ad-hoc or immediate requests initiated by<br>user interactions or external events. Unlike batch processes, on-demand<br>workflows execute tasks as needed and are tied to specific document<br>templates or output types. These processes are initiated and completed<br>via APIs, such as Web Services or REST, allowing for seamless integration. |

## <span id="page-13-0"></span>On-Demand Workflows

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | n/a                                                                                                                                                                                                                                                                                                                                    |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                    |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                    |
| Long<br>description  | Doxee Platform® On-Demand Workflows engine ensured scalability by<br>horizontally scaling application components to manage spikes in requests<br>and maintain consistent execution times. The platform supports end-to<br>end orchestration of document production workflows, including<br>integration with recurring billing systems. |

## <span id="page-13-1"></span>Output Management

| Entity type          | Platform component name for whitepapers and user guides |
|----------------------|---------------------------------------------------------|
| 3-word title         | n/a                                                     |
| Brief title          | n/a                                                     |
| Brief<br>description | n/a                                                     |

# **Long description**

Doxee Platform® Output Management allows users to configure the output parameters of final documents during print spool generation. It manages aspects such as file structure, accompanying indexes, overprints, format conversion, and metadata production, including indexing data for document spools. Additionally, it applies Optical Mark Recognition (OMR) to preexisting print spools, ensuring efficient document processing and management.

## <span id="page-14-0"></span>**ENGAGEMENT**

| Entity type          | The platform functional scope name for marketing and sales                                                                                                                                                                                                                                                                                                                              |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | Interactive customer engagement                                                                                                                                                                                                                                                                                                                                                         |
| Brief title          | Enhance customer engagement with interactive experiences enabled by a<br>smart workplace for business users.                                                                                                                                                                                                                                                                            |
| Brief<br>description | Doxee Platform® Engagement functionalities enable businesses to create<br>interactive and personalized customer communications, microsites, and<br>videos across multiple touchpoints. Organizations can drive deeper<br>engagement, streamline business workflows, plus enhance customer<br>interactions with dynamic content, intuitive tools, and secure archiving<br>and retrieval. |
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                                     |

# <span id="page-14-1"></span>Interactive Documents

| Entity type     | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides |
|-----------------|------------------------------------------------------------------------------------------------------------|
| 3-word<br>title | Customer correspondence management                                                                         |
| Brief title     | An efficient collaborative workspace for managing business cases with<br>interactive documents.            |

# **Brief description**

Doxee Platform® Interactive Documents enables interactive document editing, clearly defining areas where business users can make modifications and insert predefined text components.

Doxee Platform® Interactive Documents is a collaborative environment that enables seamless execution and management of workflows across various business cases. From document processing to customer interactions, teams can coordinate tasks, automate approvals, and monitor progress in real time, ensuring efficiency, compliance, and a streamlined operational experience. Moreover, Doxee Platform® Interactive Documents provides the graphical user interface for executing document workflows and processes defined in the Process Designer. It manages tasks that require human intervention and supports a broad range of interactive document creation activities, enhancing flexibility, user engagement, and external system integration.

## Key features:

- CRM enhancement tools: Facilitate tasks like managing technical support tickets, billing, and sending notifications. •
- Personalized customer service: Enables specialists to enrich one-toone communications with customized data, offers, and financial insights. •
- Customizable web portal: Allows users to configure templates and forms, add relevant data, and trigger approval workflows for document delivery. •
- Seamless system integration; connects existing ERP and CRM systems, enabling document preview and workflow validation before dispatch. •
- Task Manager coordinates all necessary tasks within interactive processes, ensuring smooth interactions between Workplace and other Doxee products. •
- Granular access control: Configuration settings (via Business Designer and Template Designer) determine which users can modify specific content blocks. •
- Flexible document structure: Controls whether blocks can be added once or multiple times and their placement based on predefined rules. •
- Customization options: Users can adjust formatting, such as font size and style. •
- Guidance tools: Interactive comments and help texts (accessible via mouse-over) assist users in document modification. •
- User-friendly interface: Editable sections are visually highlighted for clarity. •

<span id="page-15-0"></span>Workplace

**Long**

**description**

<span id="page-15-1"></span>Composer

<span id="page-15-2"></span>Personalized Forms & Microsites

| Entity type          | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | Personalized and interactive web touchpoints                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Brief title          | Deliver personalized, data-driven web experiences that engage across<br>digital channels.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Brief<br>description | Doxee Platform® Forms & Microsites deliver highly personalized and<br>interactive web environments. These microsites adapt in real-time to<br>customer data and behaviors, enabling businesses to present relevant<br>content, enable self-service actions, and guide users through seamless<br>digital journeys. With secure access via PURLs and broad omnichannel<br>distribution, Doxee Platform® Forms & Microsites boosts engagement and<br>supports a frictionless customer experience.                                                                                                                                          |
| Long<br>description  | Doxee Platform® Microsites allows businesses to create dynamic,<br>interactive web experiences tailored to individual customers.<br>Key capabilities:<br>•<br>Data-driven personalization: Customizes content, navigation, and<br>features based on customer information.<br>•<br>Interactive engagement: Supports elements like e-commerce,<br>chatbots, and self-service portals.<br>Omnichannel distribution: Microsites can be securely shared via email,<br>SMS, social media, app notifications, and chatbots through PURLs. PURLs<br>ensure that content is accessible only to the intended recipient and for a<br>limited time. |

## <span id="page-16-0"></span>Pweb

## <span id="page-16-1"></span>Interactive Videos

| Entity type     | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides |
|-----------------|------------------------------------------------------------------------------------------------------------|
| 3-word<br>title | Personalized interactive videos                                                                            |

| Brief title          | Deliver highly personalized interactive video experiences across any<br>channel.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Brief<br>description | Doxee Platform® Personalized Videos transforms customer data into<br>highly customized and interactive video experiences.<br>Main capabilities:<br>•<br>Scene & content personalization: Adjusts video components, text,<br>and visuals based on recipient data.<br>•<br>Text-to-speech integration: Converts personalized data (e.g., billing<br>details, consumption data) into narrated audio content.<br>•<br>Secure & exclusive access: Delivered via PURLs, ensuring that only<br>the intended recipient can view the content within a set timeframe.<br>•<br>Omnichannel reach: Supports distribution across multiple channels,<br>including social media, SMS, email, app notifications, and chatbots.<br>PURLs provide targeted access and can be customized with branded<br>domains for a seamless user experience.                                                                                                                                                                                                                                                                                                                                                                                                |
| Long<br>description  | Doxee Platform® Personalized Videos transforms customer data into<br>personalized, interactive video experiences. It allows for the dynamic<br>personalization of video content, adjusting scenes, components, and text<br>elements based on recipient data. With text-to-speech functionality, audio<br>content can also be personalized, conveying detailed information like<br>consumption or transaction data for a more engaging experience.<br>Personalized Videos are delivered securely through a PURL, ensuring that<br>only the intended recipient can access the content for a limited time.<br>Personalized Video supports multi-channel distribution via social media,<br>SMS, email, app notifications, and chatbots. Integrated with other Doxee<br>modules, it provides a fully personalized, multi-channel digital experience,<br>enhancing modern communication strategies.<br>Personalized URLs are secure (hash signature), permanent, or temporary,<br>unique web links to provide targeted access to resources. Each link is<br>unique and identifies a single resource, giving secure and personalized<br>access to the recipient. Served by the Doxee Platform® with support for a<br>custom domain. |

## <span id="page-17-0"></span>Pvideo

## <span id="page-17-1"></span>Digital Archive

| Entity type  | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides |
|--------------|------------------------------------------------------------------------------------------------------------|
| 3-word title | Communication archive & retrieval                                                                          |

| Brief title          | Secure, scalable archiving and fast document retrieval for communications.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Brief<br>description | Doxee Platform® Digital Archive is an integrated communication repository<br>that securely stores and manages communications produced by the Doxee<br>Platform® or uploaded from third-party systems, regardless of format or<br>delivery channel.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                      | Core functionalities:<br>•<br>Short- and long-term archiving: Supports both temporary and<br>permanent storage.<br>•<br>Automated storage & retrieval: Accessible via a web interface or API<br>integration with external systems.<br>•<br>Scalability & security: Ensures efficient handling of large document<br>volumes with encryption and permission-based access.<br>•<br>Personalized URLs (PURLs): secure unique web links with hash<br>signatures to enable personalized access to specific documents or<br>resources.                                                                                                                                                                                                                                                                                |
| Long<br>description  | Doxee Platform® Digital Archive is a document repository integrated<br>directly into the Doxee Platform's processes and applications. It stores<br>documents and metadata produced by the Doxee Platform or another third<br>party system, regardless of format or delivery channel.<br>Designed for both short- and long-term archiving and retrieval, Digital<br>Archive supports automated document storage and retrieval via a web<br>based interface or API integration with external systems.<br>It offers a secure, scalable, and flexible solution for managing large<br>document volumes, ensuring efficient access and seamless workflow<br>integration.<br>Document access is controlled through permissions and encryption,<br>ensuring that only authorized users can view sensitive information. |
|                      | Personalized URLs are secure (hash signature), permanent, or temporary,<br>unique web links to provide targeted access to communications. Each link is<br>unique and identifies a single communication, giving secure and<br>personalized access to the recipient. Served by the Doxee Platform® with<br>optional support for custom domains.                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## <span id="page-18-0"></span>Digital Archiving

## <span id="page-18-1"></span>INSIGHTS

| Entity type  | The platform functional scope name for marketing and sales |
|--------------|------------------------------------------------------------|
| 3-word title | Data-driven customer analytics                             |

| Brief title          | Gain insights into customer engagement, processes, and channels to<br>optimize communications.                                                                                            |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Brief<br>description | Measure, analyze, and optimize your customer communications with<br>Doxee Platform Analytics. Track customer engagement insights to drive<br>better decisions and achieve business goals. |
| Long<br>description  | n/a                                                                                                                                                                                       |

# <span id="page-19-0"></span>Customer Insights

| Entity type          | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | Behavioral communication analytics                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Brief title          | Turn every customer interaction into actionable data for optimization.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Brief<br>description | By collecting and analyzing data from various endpoints, companies can<br>gain valuable insights into customer behavior, preferences, and pain<br>points, which helps optimize touchpoints, identify areas for improvement,<br>and make data-driven decisions to enhance the customer journey. Doxee<br>tracks every action within communication, allowing for the measurement<br>of its effectiveness and providing key performance indicators (KPIs) to<br>improve conversion rates. Behavioral analytics enables A/B testing,<br>empowering CRM and Marketing Automation systems to create more<br>effective and consistent communication workflows. |
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

## <span id="page-19-1"></span>Process Insights

| Entity type  | Platform component name for marketing and sales |
|--------------|-------------------------------------------------|
| 3-word title | Integrated process monitoring                   |

| Brief title          | Monitor, track, troubleshoot, and optimize automated processes in real<br>time.                                                                                                                                                                                                                                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Brief<br>description | Doxee Platform® Process Insights provides extensive management and<br>monitoring features for all types of processes on the Doxee Platform®. It<br>enables users to check the execution status of applications and address<br>any processes that are not functioning properly. As such, this service is<br>essential for the daily management of the Platform's production cycle. |
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                               |

<span id="page-20-0"></span>Tracking & Reporting (DP2/DP3)

<span id="page-20-1"></span>Platform Reporting (ex Infinica) – not to be documented

# <span id="page-20-2"></span>Channel Insights

| Entity type          | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |  |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--|
| 3-word<br>title      | Platform reporting data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |  |
| Brief title          | Measure communication effectiveness and operational performance in real<br>time.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |  |
| Brief<br>description | Doxee Platform® Channel Insights tracks every action within<br>communication, allowing for the measurement of its effectiveness and<br>providing key performance indicators (KPIs) to improve conversion rates.<br>Doxee also tracks compliance with Service Level Agreements (SLAs),<br>offering channel-specific tracking and the ability to focus on individual<br>documents.<br>The reporting component eases the creation of reports to support business<br>intelligence applications, enabling management-oriented decision-making.<br>Its primary function is to provide predefined data models, reports, and<br>dashboards that seamlessly integrate with the customer's existing BI<br>solutions, offering insights into document generation processes. This<br>component extracts relevant data from the Doxee platform®, transforms<br>it into formats suitable for BI systems, and makes it accessible for detailed<br>analysis. Users can efficiently query data and create adaptable reports<br>tailored to specific needs, ensuring flexibility and precision in reporting. |  |

| Long<br>description | n/a |
|---------------------|-----|
|---------------------|-----|

## <span id="page-21-0"></span>INTEGRATION

| Entity type                                               | Platform functional scope name for marketing and sales                                                                                                                                                                                                         |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title                                              | Seamless system integration                                                                                                                                                                                                                                    |
| Brief title                                               | Seamlessly integrate CRM/ERP through Marketplace Apps,<br>API, and Connectors.                                                                                                                                                                                 |
| Brief description                                         | Simplify your system interactions with Doxee Platform®<br>integration tools, which enable seamless data flow through<br>Salesforce®, SAP®, and Microsoft® Dynamics 365®<br>marketplace apps, making your customer communications<br>centralized and efficient. |
| Whitepapers &<br>documentation: a<br>detailed description | n/a                                                                                                                                                                                                                                                            |

## <span id="page-21-1"></span>Marketplace Apps

| Entity type     | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides                                  |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title | Customer communication through CRM/ERP marketplaces                                                                                         |
| Brief title     | Design and automate your personalized and interactive communications<br>directly within your Salesforce®, SAP®, or Microsoft Dynamics 365®. |

| Brief<br>description | Doxee Platform® Marketplace Apps transforms the way businesses<br>generate, customize, and manage documents by integrating seamlessly<br>with leading CRM systems. Designed to enhance efficiency and user<br>experience, Doxee Platform® Marketplace Apps provides a powerful yet<br>intuitive solution that simplifies document creation, automates workflows,<br>and ensures consistency across business processes.<br>With the Doxee Platform® Marketplace Apps, users can effortlessly<br>generate personalized documents directly within their CRM environment,<br>leveraging pre-configured templates and dynamic data fields. Whether it's<br>contracts, proposals, reports, or customer communications, every<br>document is tailored to your business needs with just a few clicks. The<br>intuitive interface allows users to modify templates in real time, ensuring<br>adaptability to evolving business requirements without disrupting<br>workflows.<br>Beyond document creation, Doxee Platform® Marketplace Apps enhances<br>collaboration by centralizing template management, streamlining approval<br>processes, and enabling automation that reduces manual efforts. Its |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                      | flexible configuration adapts to different roles and use cases, making it an<br>essential tool for sales, marketing, customer service, and operations<br>teams.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|                      | Doxee Platform® Marketplace Apps is available for Salesforce®, Microsoft<br>Dynamics 365®, and SAP®, ensuring a smooth and native integration into<br>the existing CRMs and ERP ecosystems.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

## <span id="page-22-0"></span>APIs and Connectors

| Entity type     | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides |
|-----------------|------------------------------------------------------------------------------------------------------------|
| 3-word<br>title | Seamless integration through API & Connectors                                                              |
| Brief title     | Automate workflows and enhance communication through seamless API &<br>Connectors integration.             |

| Brief<br>description | Doxee Platform® provides REST APIs that enable the integration of on<br>demand workflows with enterprise systems, offering tailored functionality.<br>These APIs allow for different levels of integration to enhance customer<br>experience and optimize business communication management. APIs can<br>automate communication processes, triggering personalized messages<br>based on specific events, such as a purchase or request. Additionally,<br>REST APIs support on-demand job execution, archive extraction, and the<br>generation of personalized URLs for distributing interactive web content<br>and videos. |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

# <span id="page-23-0"></span>AUTOMATION

| Entity type          | Platform functional scope name for marketing and sales                                                                                                                                                                                                                                                                     |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | Scalable process automation                                                                                                                                                                                                                                                                                                |
| Brief title          | Enhance production efficiency with scalable omnichannel process<br>automation.                                                                                                                                                                                                                                             |
| Brief<br>description | Streamline and scale communication workflows with powerful process and<br>delivery automation. The Doxee Platform automates the creation,<br>orchestration, and omnichannel distribution of personalized documents<br>and communications—boosting performance, reducing manual effort, and<br>accelerating time to market. |
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                        |

## <span id="page-23-1"></span>Process Engine

| Entity type  | Platform component name for marketing and sales                                       |
|--------------|---------------------------------------------------------------------------------------|
| 3-word title | Elastic process automation                                                            |
| Brief title  | Orchestrate and scale communication automation across all systems and<br>touchpoints. |

| Brief<br>description | Doxee Platform® Process Engine is the central automation core for<br>managing large-scale document production and data-driven workflows. It<br>orchestrates human and system tasks with precision, scales across<br>enterprise workloads, and accelerates the creation of personalized<br>communications—reducing errors, enhancing efficiency, and speeding up<br>time to market. |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                                |

# <span id="page-24-0"></span>Process Engine

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Long<br>description  | Doxee Platform® Process Engine is built on the BPMN 2.0 standard,<br>automating workflows and managing both data processing and human<br>tasks that require user input (based on the process definition made with<br>Process Designer). It integrates seamlessly with enterprise systems,<br>handling the full data pipeline and transferring information to enterprise<br>applications via specific connectors. The engine's processing power<br>ensures rapid task execution and efficient time to market. It also stores<br>detailed process information in a log database for monitoring and<br>reporting, offering custom configurations to track activities and ensure<br>compliance. The Process Engine serves as the core orchestrator of all<br>resources involved in document creation. |

# <span id="page-24-1"></span>Batch Jobs

| Entity type  | Platform component name for whitepapers and user guides |
|--------------|---------------------------------------------------------|
| 3-word title | n/a                                                     |

| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Long<br>description  | Doxee Platform® Batch Job service provides robust management and<br>monitoring of Doxee Platform® batch jobs, input files, and output lots<br>associated with batch processes. It enables users to check the execution<br>status of all batch applications on the platform and address any issues<br>with processes that are not running correctly. As such, this service is<br>essential for the daily management of the platform's production cycle. |

## <span id="page-25-0"></span>On-Demand Jobs

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                           |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                               |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                               |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                               |
| Long<br>description  | Doxee Platform® On-Demand Jobs enables monitoring of Doxee<br>Platform® jobs and workflows for on-demand processes. It allows users to<br>track the status of document production jobs, but does not provide the<br>ability to make changes during the creation or execution phases of the<br>production process. |
| Entity type          | Platform component name for marketing and sales<br>Platform component name for whitepapers and user guides                                                                                                                                                                                                        |
| 3-word<br>title      | Centralized customer intelligence                                                                                                                                                                                                                                                                                 |
| Brief title          | Unify and structure customer data for insight-driven business strategies.                                                                                                                                                                                                                                         |

| Brief<br>description | Doxee Platform® Customer Data Hub primarily serves as a unified data<br>foundation, centralizing and organizing customer information such as<br>documents, communications, and interactions so it can be analyzed,<br>segmented, and utilized across various functions. While its data and<br>insights can eventually power marketing automation workflows or inform<br>customer-facing business portals, Customer Data Hub's core strength lies<br>in providing comprehensive, structured customer data that enables<br>analytics-driven decision-making. |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

## <span id="page-26-0"></span>Omnichannel Engine

| Entity type          | Platform component name for marketing and sales                                                                                                                                                                                                                                                                                                                                         |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | Omnichannel communication distribution                                                                                                                                                                                                                                                                                                                                                  |
| Brief title          | Deliver personalized communications across all digital and physical<br>touchpoints.                                                                                                                                                                                                                                                                                                     |
| Brief<br>description | Doxee Platform® Omnichannel allows the distribution of automatic and<br>centralized digital communications such as email, SMS, and traditional<br>communications intended for printing and delivery processes. The engine<br>includes omnichannel distributions to send communications through<br>multiple channels and protocols like SFTP, Email, SMS, Certified email,<br>and AppIO. |
| Long<br>description  | n/a                                                                                                                                                                                                                                                                                                                                                                                     |

# <span id="page-26-1"></span>ADMINISTRATION

| Entity type  | Platform functional scope name for marketing and sales          |
|--------------|-----------------------------------------------------------------|
| 3-word title | Centralized platform administration                             |
| Brief title  | Centralize the governance of platform resources for operations. |

| Brief<br>description | Doxee Platform® Administration provides full control over the entire<br>platform, from user access to platform monitoring to ensure smooth,<br>secure, and efficient operations across your customer communication<br>processes. |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Long<br>description  | n/a                                                                                                                                                                                                                              |

## <span id="page-27-0"></span>Platform Administration

| Entity type          | Platform component name for marketing and sales                                                                                       |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | Manage platform environments                                                                                                          |
| Brief title          | Doxee Platform® Platform Manager is a set of components to centralize<br>the platform settings, including environments and workloads. |
| Brief<br>description | n/a                                                                                                                                   |
| Long<br>description  | n/a                                                                                                                                   |

## <span id="page-27-1"></span>Command Center

| Entity type          | Platform component name for whitepapers and user guides |
|----------------------|---------------------------------------------------------|
| 3-word<br>title      | n/a                                                     |
| Brief title          | n/a                                                     |
| Brief<br>description | n/a                                                     |

# **Long description**

Doxee Platform® Command Center is a web tool to manage Doxee Platform® environments. It operates with a central instance that users can access via a web-based GUI in their browser. The application is stateless and easily scalable, allowing it to handle increasing workloads and user numbers. It provides an overview of all environments accessible to the current user. When examining a specific environment, users can view the included applications, their status, and configuration details. If users have the appropriate privileges, they can stop, restart, or make configuration changes based on a predefined set of parameters.

## <span id="page-28-0"></span>Batch Workloads

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Long<br>description  | Doxee Platform® Batch Workload enables advanced resource scheduling<br>for batch jobs, aiming to optimize the cost-effectiveness of workflows<br>based on their SLA and execution time. It allows users, with the<br>appropriate permissions, to view and configure the maximum number of<br>parallel job instances, production and delivery tasks, and memory<br>allocation for each environment. This configuration can also be applied to<br>individual workflows, with task limits specified for each one. The system<br>will delay tasks that do not align with the specified configurations. |

# <span id="page-28-1"></span>Resource Manager

| Entity type  | Platform component name for marketing and sales                                                                                       |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title | Manage platform resources                                                                                                             |
| Brief title  | Doxee Platform® Resource Manager is a set of components to centralize<br>where platform resources are stored, organized, and managed. |

| Brief<br>description | n/a |
|----------------------|-----|
| Long<br>description  | n/a |

## <span id="page-29-0"></span>Repository

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Long<br>description  | Doxee Platform® Repository enables the definition and management of<br>resources on the Doxee Platform®, allowing for their deployment across<br>specific environments. It supports the import of pre-built resources, such<br>as those developed through components like data or template design, and<br>facilitates the creation of reusable templates for multiple accounts and<br>environments. The multi-environment architecture allows resources to be<br>configured centrally, rather than individually in each environment. Once<br>configured, these resources can be deployed to the necessary<br>environments for execution. |

# <span id="page-29-1"></span>Content Repository

| Entity type          | Platform component name for whitepapers and user guides |
|----------------------|---------------------------------------------------------|
| 3-word title         | n/a                                                     |
| Brief title          | n/a                                                     |
| Brief<br>description | n/a                                                     |

# **Long description**

Doxee Platform® Content Repository is designed to store various files, primarily document templates, images, and process definitions. It can be accessed by multiple applications like Workplace, Composer, Business Designer, and Template Designer, for both reading and writing files. It relies on an SQL database to store its content and is a stateful application, with its workspace stored in the local file system.

## <span id="page-30-0"></span>Resource Explorer

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Long<br>description  | Doxee Platform® Resource Explorer is a graphical tool for accessing files<br>and folders on the Content Repository and on the local file system. It is<br>available as a stand-alone tool and is also embedded in Template Designer<br>and Process Designer. Use Resource Explorer to move files between the<br>file system and your servers, make backups, restore data, deploy files,<br>and manage versions and access rights of your remote files. |

## <span id="page-30-1"></span>User Manager

| Entity type          | Platform component name for marketing and sales                                                                                                                                       |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | User and access control                                                                                                                                                               |
| Brief title          | Manage users and access with RBAC, or Role-Based Access Control.                                                                                                                      |
| Brief<br>description | Doxee Platform® User Manager allows platform administrators to define<br>and manage users and access control following the standard role-based<br>access control or RBAC methodology. |

| Long<br>description | n/a |
|---------------------|-----|
|---------------------|-----|

# <span id="page-31-0"></span>Settings

| Entity type          | Platform component name for whitepapers and user guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word title         | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Brief title          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Brief<br>description | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Long<br>description  | Doxee Platform® Settings allow users to define and manage the main<br>elements, such as Accounts, Users, and Roles, that enable users to access<br>the Doxee Platform® and its applications by creating new users, defining<br>access roles, and defining the corresponding accounts and companies.<br>RBAC, or Role-Based Access Control, is a method of managing user access<br>to resources based on their roles within an organization. Instead of<br>assigning permissions to each user individually, RBAC groups users into<br>roles, and each role has specific permissions associated with it. This<br>system streamlines access management, improves security, and simplifies<br>administration. |

## <span id="page-31-1"></span>Doxee University

| Entity type          | Doxee University                                                                                                                                                                             |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3-word<br>title      | Doxee Platform® on-demand learning.                                                                                                                                                          |
| Brief title          | Master the Doxee Platform® with AI-powered on-demand training courses.                                                                                                                       |
| Brief<br>description | Doxee University is the AI-powered eLearning environment designed to<br>help users deepen their knowledge of the Doxee Platform® and its<br>components, at their own pace and on any device. |

# **Long description**

Doxee University is the official eLearning portal for the Doxee Platform® users. including Doxee customers, partners, and employees. The Doxee University delivers an intuitive, on-demand training experience, empowering business and technical users to develop platform-specific skills across all functional areas - from template creation to interactive document creation, data transformation, and digital archiving. With guided paths, AI-driven personalization, and certification programs, Doxee University helps your teams unlock the full value of the platform, ensuring self-sufficiency, faster onboarding, and continuous improvement.

<span id="page-32-0"></span>Doxee Platform® Add-Ons (delivery-managed)

Optional additional Doxee Platform® add-ons can be installed upon client's request, tailored to enhance functionality and meet specific needs, and are seamlessly integrated by the Doxee Professional Services team to ensure optimal performance and customization.

<span id="page-32-1"></span>Add-ons for global market

<span id="page-32-2"></span>Booster (DEPRECATED – NOT TO BE SOLD)

Doxee Platform® Booster is a marketing automation solution that enhances and expands your communications through automated workflows. It extends the capabilities of the Doxee Platform® by enabling marketing automation campaigns to optimize communication delivery. Doxee Booster goes beyond email marketing, also automating SMS, mobile push, and web notifications. With a comprehensive set of marketing automation features, Doxee Booster can significantly improve the effectiveness of your initiatives. This additional tool is designed to maximize the value of your efforts using Doxee's personalized communications.

<span id="page-32-3"></span>Content Hub (DEPRECATED – NOT TO BE SOLD)

Doxee Platform® Content Hub is a solution based on a headless CMS that allows users to manage and configure web assets for applications like Interactive Videos and Interactive Microsites, based on specific rules. It enables Doxee clients to work directly with assets in their personalized project areas, without the need for coding. Key features include generating previews, creating planning rules, assigning roles and business rules, and customer segmentation. The solution offers an intuitive interface, with dynamic dashboards and modular panels for easy monitoring and management, allowing users to tailor communications and create personalized content without needing coding expertise.

<span id="page-32-4"></span>Web Analytics Platform (DEPRECATED – NOT TO BE SOLD)

Doxee Platform® Web Analytics Platform can be enabled on Interactive Video and Interactive microsite documents by adding the appropriate configuration. Once enabled, events are processed and dispatched to [Matomo](https://matomo.org/) including custom dimensions required for reports analytics visualization and filtering.

<span id="page-32-5"></span>Tracking & Reporting (DEPRECATED – NOT TO BE SOLD)

Doxee Platform® Tracking & Reporting is essential for monitoring the entire document's lifecycle and providing insights into customer behavior. Combining production events with behavioral analytics helps improve process efficiency and communication effectiveness, boosting conversion rates. The component tracks compliance with Service Level Agreements (SLAs), offering channel-specific tracking and the ability to focus on individual documents. It enables companies to assess the effectiveness of various communications, such as emails and shared documents, and adjust based on their impact on employees, customers, or other stakeholders.

## <span id="page-33-0"></span>Namirial Connector

Doxee Platform® [Namirial](https://www.namirial.com/en/) Connector provides electronic signature solutions, integrating simple, advanced, and qualified e-signatures via third-party providers. It offers workflows for static and dynamic document signing, utilizing APIs for integration and automation of signature processes. Signature solutions can be integrated with the Process Designer.

# <span id="page-33-1"></span>Scrive Connector

Doxee Platform® [Scrive](https://www.scrive.com/) Connector is integrated with a service that allows us to manage PDF document signature requests using the API provided by the Scrive supplier. The connector provides simple electronic signature solutions which legal value can be strengthened by OTP confirmation. Scrive uses Blokchain technology to cristallize the document signature.

## <span id="page-33-2"></span>Zuora Connector

Doxee Platform® [Zuora](https://www.zuora.com/) connector enables integration with the Zuora billing system, allowing data extraction using Zuora's proprietary JQL metalanguage. Data is initially retrieved in CSV format and then converted into XML by the connector engine. It supports both Batch and On-Demand use cases, with the ability to connect to SFTP servers or Doxee endpoints. Additionally, a dedicated task can be added to a workflow to send update requests to the connector, which can then update the metadata of processed documents, such as the PURL. A Batch recovery system is also available to handle errors during document extraction in both cases.

## <span id="page-33-3"></span>Add-ons for Italian market

Gli add-ons Doxee Platform® per implementare i Trust Services in Italia consentono la completa dematerializzazione dei processi documentali grazie ai servizi di fatturazione elettronica, ordine elettronico, conservazione digitale a norma, firma digitale e SERC. Doxee S.p.A. opera come intermediario accreditato per il Sistema di Interscambio (SDI), Conservatore iscritto al Marketplace dei i Servizi di conservazione AgID, intermediario NSO tramite il canale PEPPOL accreditato presso AgID (Peppol Authority per l'Italia).

## <span id="page-33-4"></span>**Conservazione Digitale a Norma**

**Conservazione Digitale a Norma** è la soluzione Doxee Platform® per la conservazione digitale dei documenti fiscali e giuslavoristici, garantendo la piena conformità alla normativa italiana ed europea.

Doxee offre un sistema di **Conservazione Digitale a Norma** qualificato AgID, progettato per garantire la sicurezza informatica e l'affidabilità nella conservazione documentale. Il prodotto è pienamente conforme:

- Alle normative italiane ed europee in materia di conservazione digitale. •
- Allo standard internazionale **ISO 14721 (Open Archival Information System – OAIS)**. •
- Al **Codice dell'Amministrazione Digitale (CAD)** e alle relative regole tecniche. •

Doxee è un conservatore accreditato da AgID ed è presente sul **Marketplace dei servizi di conservazione**. Da oltre 10 anni, supporta centinaia di aziende nel rispetto degli obblighi normativi, con oltre **4 miliardi di documenti conservati** e più di **400 soggetti giuridici gestiti**.

Il solido asset tecnologico di Doxee Platform® assicura:

**Sicurezza logica e fisica** ai massimi livelli. •

- **Gestione di grandi volumi e picchi di produzione** con elevata affidabilità. •
- **Alta disponibilità e-business continuity**, garantite da **SLA**. •

L'interoperabilità è garantita grazie alla generazione del **rapporto di versamento**, del **pacchetto di archiviazione** e del **pacchetto di distribuzione** secondo le **regole tecniche e lo standard UNI SInCRO 11386**.

Il servizio include un **portale web** per la ricerca e consultazione dei documenti, con funzionalità avanzate tra cui:

- **Accesso e download** del singolo documento conservato. •
- **Esportazione dei pacchetti di distribuzione**. •
- **Verifica di hash, firma e validazione temporale**. •
- **Gestione di eventuali correttivi e allegati integrativi**. •

Conservazione Digitale a Norma di Doxee Platform® è la scelta ideale per un'archiviazione sicura, conforme e sempre accessibile.

## <span id="page-34-0"></span>**Fatturazione Elettronica**

La soluzione di **Fatturazione Elettronica** di Doxee Platform® è un servizio completamente gestito e interoperabile, progettato per gestire **sia il ciclo attivo (Accounts Receivables - AR) che il ciclo passivo (Accounts Payable - AP) della fatturazione elettronica**.

**Integrata nativamente nella Doxee Platform®**, garantisce **conformità alle normative italiane ed europee**, offrendo un processo di fatturazione **scalabile, affidabile e conforme alle disposizioni di legge**.

Parte degli **add-on Trust Services**, questa soluzione consente alle organizzazioni di gestire in modo efficiente i flussi di fatturazione elettronica, assicurando un'integrazione fluida con **sistemi di fatturazione standard di settore** e un costante aggiornamento normativo. Inoltre, supporta **l'intero ciclo di scambio** con il **Sistema di Interscambio (SdI)**, offrendo funzionalità dedicate alla fatturazione verso la **Pubblica Amministrazione (B2G), aziende private (B2B) e consumatori finali (B2C)**.

# **Caratteristiche principali:**

- **Conformità normativa garantita** Sempre aggiornato rispetto alle normative italiane ed europee. •
- **Integrazione completa** Connessione nativa con **ERP, CRM e sistemi finanziari**. •
- **Scalabilità e affidabilità** Progettato per gestire **alti volumi di fatture elettroniche** con prestazioni ottimizzate. •
- **Monitoraggio in tempo reale** Strumenti avanzati per il **controllo del processo e la risoluzione immediata di eventuali anomalie**. •

## <span id="page-34-1"></span>**Analisi e monitoraggio della Fatturazione Elettronica**

La soluzione include strumenti avanzati di **monitoraggio e analisi**, che forniscono alle aziende il **controllo completo sui processi di fatturazione elettronica**, con visibilità su:

- **Numero di fatture in entrata e in uscita** •
- **Ricevute individuali e stato di elaborazione** •
- **Motivi di scarto o errori rilevati** •

Grazie a un sistema di controllo in tempo reale, è possibile **identificare e risolvere tempestivamente eventuali irregolarità**, garantendo **un'operatività fluida e conforme alle normative vigenti**.

## <span id="page-35-0"></span>**Portale Fatture**

Il Doxee Platform® **Portale Fatture** offre un'interfaccia centralizzata per la visualizzazione e la gestione **dell'intero ciclo di vita** dei documenti di fatturazione elettronica.

- **Fatture Elettroniche Attive** Consente di **ricercare, visualizzare e gestire** le fatture emesse. •
- **Fatture Elettroniche Passive** Offre funzionalità analoghe per le fatture ricevute, inclusa la possibilità di **ricerca, visualizzazione dettagliata e gestione**. •

Questa funzionalità **semplifica la gestione operativa** centralizzando tutte le informazioni relative alla fatturazione elettronica e rendendo più efficiente il processo di **tracciabilità e recupero dei documenti**.

# <span id="page-35-1"></span>**Document Cockpit**

Il Doxee Platform® **Document Cockpit** è progettato per gli utenti che necessitano di **tracciare e gestire i documenti di fatturazione elettronica** in un periodo di tempo configurabile.

## **Funzionalità principali:**

- **Monitoraggio dello stato dei documenti** Permette l'interazione con le fatture **prima della consegna finale** alla destinazione prevista (es. archiviazione, stampa, invio). •
- **Gestione delle code di elaborazione** Consente la **rimozione di documenti dalle code di invio**, se necessario. •
- **Accesso ai dati aggiornati** Recupera informazioni in tempo reale dal database, assicurando un monitoraggio costante. •
- Il **Document Cockpit** è un'interfaccia **di gestione operativa**, progettata per fornire **controllo e tracciabilità** sui flussi documentali della fatturazione elettronica. •

# <span id="page-35-2"></span>Ordine Elettronico Semplice

Doxee Platform® Ordine Elettronico è la soluzione Doxee pensata per gestire lo scambio di ordini tra Pubbliche Amministrazioni (PA) italiane ed europee e i loro fornitori, nel rispetto degli standard italiani ed europei. La soluzione copre tutte le modalità previste dalla normativa e si integra perfettamente con altri servizi digitali, garantendo una gestione completa ed efficiente dei processi di ordine in ambito pubblico e privato.

Questa modalità prevede il flusso di lavoro più semplice e consiste nella gestione dell'Ordine di Acquisto (ODA) inviato dalla Pubblica Amministrazione al Nodo Smistamento Ordini (NSO). Il processo comprende:

- Ricezione dell'ordine elettronico dal sistema NSO. • ◦
  - Riconoscimento e smistamento dell'ordine verso il fornitore tramite la piattaforma Doxee. ◦
  - Notifica automatica al fornitore tramite PEC. ◦

## <span id="page-35-3"></span>Ordine Elettronico Completo

Doxee Platform® Ordine Elettronico è la soluzione Doxee pensata per gestire lo scambio di ordini tra Pubbliche Amministrazioni (PA) italiane ed europee e i loro fornitori, nel rispetto degli standard italiani ed europei. La soluzione copre tutte le modalità previste dalla normativa e si integra perfettamente con altri servizi digitali, garantendo una gestione completa ed efficiente dei processi di ordine in ambito pubblico e privato.

Questa modalità, conforme alle linee guida e alle regole tecniche, include tutte le operazioni previste nell'Ordine Elettronico Semplice, ma aggiunge la gestione dei flussi di ritorno verso l'NSO e la PA. In questa modalità, Doxee fornisce un portale web per il cliente, attraverso il quale è possibile:

- Accettare o rifiutare l'ordine, con possibilità di motivare la scelta. • ◦
  - Trasmettere gli ordini di riscontro all'NSO per aggiornare lo stato dell'ordine. ◦

## <span id="page-36-0"></span>Ordine Elettronico Pre-concordato

Doxee Platform® Ordine Elettronico è la soluzione Doxee pensata per gestire lo scambio di ordini tra Pubbliche Amministrazioni (PA) italiane ed europee e i loro fornitori, nel rispetto degli standard italiani ed europei. La soluzione copre tutte le modalità previste dalla normativa e si integra perfettamente con altri servizi digitali, garantendo una gestione completa ed efficiente dei processi di ordine in ambito pubblico e privato.

La modalità Pre-concordata permette di inviare ordini verso NSO/PA anche in formati non UBL 3.0 (lo standard previsto dalla normativa). Il sistema Doxee si occupa automaticamente della conversione dell'ordine al formato corretto.

- Il flusso di lavoro prevede: • ◦
  - Invio dell'ordine dal fornitore al sistema Doxee. ◦
  - Trasmissione e validazione dell'ordine al sistema NSO/PA tramite il canale PEPPOL, previa conversione al formato richiesto. ◦
  - Gestione degli ordini di riscontro da parte di NSO e notifiche al cliente-fornitore. ◦

# <span id="page-36-1"></span>Recapito Elettronico Certificato (SERC/SERCQ)

Il Doxee Platform® Recapito Elettronico Certificato è una soluzione affidabile e conforme alle normative europee per la trasmissione elettronica sicura di dati tra terze parti. Garantisce tracciabilità completa della comunicazione tra mittente e destinatario, fornendo evidenze documentali opponibili a terzi che certificano l'invio, la consegna e la ricezione delle informazioni trasmesse.

Le soluzioni di Recapito Elettronico Certificato rappresentano un'alternativa più veloce, efficiente e sicura rispetto ai tradizionali canali cartacei, permettendo alle aziende di gestire comunicazioni critiche in modo semplice, immediato ed economicamente vantaggioso.

Add-on Trust Service integrato nella Doxee Platform®, questa soluzione è conforme al Regolamento UE n° 910/2014 (eIDAS) e viene erogata tramite un Prestatore di Servizi Fiduciari Qualificato. Le comunicazioni trasmesse tramite Recapito Elettronico Certificato possono costituire una prova legale in caso di contenzioso, assicurando massima sicurezza, autenticità e non ripudiabilità.

# Vantaggi principali:

Validità legale garantita – Conforme agli standard eIDAS, con piena opponibilità a terzi. •

- Tracciabilità completa Monitoraggio dell'intero ciclo di vita del messaggio (invio, ricezione, apertura). •
- Maggiore efficienza operativa Comunicazioni digitali più rapide ed economiche rispetto alla carta. •
- Integrazione fluida Compatibile con ERP, CRM e sistemi di gestione documentale. •
- Esperienza utente migliorata Soluzioni personalizzabili per ottimizzare il tasso di apertura e conversione. •

I servizi disponibili sono i seguenti: e-Mail Certificata, e-Recapito, e-Recapito Qualificato.

<span id="page-37-0"></span>e-Mail Certificata (SERC)

La e-Mail Certificata (SERC) fornisce una prova certa del contenuto del messaggio, dell'ora esatta di invio alla casella del destinatario e del momento di ricezione.

- Utilizzabile come una normale e-mail, ma con valore legale e tracciabilità avanzata. •
- Garantisce l'integrità e l'autenticità del messaggio durante tutto il processo di trasmissione. •
- Maggiore sicurezza rispetto alla posta elettronica tradizionale. •

Grazie alla sua semplicità d'uso e alla protezione avanzata dei dati, la e-Mail Certificata è una soluzione ideale per tutte le organizzazioni che desiderano migliorare la sicurezza e il valore legale delle proprie comunicazioni digitali.

SERC conforme all'art. 3, n.36 e all'art. 43, c.1 del Regolamento UE n° 910/2014 (eIDAS).

<span id="page-37-1"></span>e-Recapito (SERC)

L'e-Recapito consente di certificare la consegna e l'apertura di documenti rilasciando una prova documentale opponibile a terzi.

Il destinatario riceve un'e-mail o un messaggio di testo certificato contenente un link personalizzato per accedere ai documenti a lui destinati.

Il mittente ottiene una traccia documentale completa che attesta invio, ricezione e apertura del documento, con data e ora precise.

Consente di raccogliere e tracciare l'intenzione del destinatario ad accedere ai documenti, garantendo un livello di sicurezza superiore rispetto ai canali tradizionali.

L'elevata personalizzazione della soluzione migliora l'esperienza utente, aumentando il tasso di apertura e il click-through rate.

SERC conforme all'art. 3, n.36 e all'art. 43, c.1 del Regolamento UE n° 910/2014 (eIDAS).

<span id="page-37-2"></span>e-Recapito Qualificato (SERCQ)

L'e-Recapito Qualificato (SERCQ) offre le stesse funzionalità dell'e-Recapito, con un livello di sicurezza ancora più elevato, permettendo di identificare con certezza il mittente e il destinatario.

- Certificazione elettronica della consegna e dell'apertura dei documenti, con evidenza legale opponibile a terzi. •
- Protezione avanzata grazie all'identificazione sicura del mittente e del destinatario, conforme all'art. 44 di eIDAS. •

Maggiore affidabilità per comunicazioni critiche, con un livello di sicurezza superiore ai normali strumenti digitali. •

SERCQ conforme agli artt. 3, n.36 e 37, 43 e 44 del Regolamento UE n° 910/2014 (eIDAS). Internal Note about Integrations availability:

- **e-**mail certificata (SERC): integrazione con **L**leidanetworks (*Registered e-mail*) •
- e-recapito (SERC): integrazione con **L**leidanetworks (*OPENUM*) o InPoste (*Tnotice*) •
- e-recapito qualificato (SERCQ): integrazione con InPoste (*TnoticeQ*) •

# <span id="page-38-0"></span>Firma Elettronica **Semplice (SES) o Avanzata (FEA)**

La **Firma Elettronica** è la soluzione Doxee Platform® dedicata alla digitalizzazione dei processi di firma, consentendo di firmare documenti in modo semplice e sicuro e di dematerializzare completamente l'acquisizione delle firme su contratti e documenti aziendali.

Grazie alla **Firma Elettronica Doxee**, è possibile rivoluzionare il rapporto con clienti, fornitori e partner, semplificando e velocizzando il processo di firma e garantendo al contempo il valore legale dei documenti sottoscritti. Le nostre soluzioni offrono elevata affidabilità e piena conformità normativa, permettendoti di ottimizzare e rendere più efficienti i processi di firma aziendali. **Tipologie di Firma Elettronica:**

La Firma Elettronica Semplice (FES) è una soluzione Doxee Platform® agile e intuitiva per la digitalizzazione della raccolta firme, basata su un sistema point & click.

- Processo rapido e user-friendly, ideale per clienti e fornitori. •
- Integrazione con OTP (One-Time Password) per una maggiore sicurezza e integrità del processo. •
- Dematerializzazione totale del processo di firma, eliminando la necessità di documenti cartacei. •

La Firma Elettronica Avanzata (FEA) Doxee Platform® offre standard di sicurezza elevati e garantisce l'identificazione del firmatario e la tracciabilità del consenso.

- Maggiore affidabilità e conformità normativa, conforme agli standard europei eIDAS. •
- Identificazione sicura del firmatario con raccolta del consenso e documentazione del processo. •
- Perfetta per la firma di contratti e documenti aziendali, con un livello di protezione superiore rispetto alla Firma Elettronica Semplice. •

## **Firma Digitale (FEQ)**

Alcuni documenti richiedono, per legge, l'uso di una Firma Elettronica Qualificata (QES) o di una Firma Digitale. Caratteristiche:

- Basata su certificati qualificati e chiavi crittografiche, garantisce il massimo livello di sicurezza, immutabilità e integrità dei documenti. •
- Massive Remote Signature: possibilità di firmare automaticamente grandi volumi di documenti attraverso un processo automatizzato, efficiente e veloce. •

Valore legale garantito, pienamente conforme alle normative italiane ed europee. •

# **Marcatura Temporale**

Le soluzioni di Firma Elettronica Doxee Platform® consentono di applicare un riferimento temporale certo ai documenti, garantendone l'integrità e la conformità normativa.

- Utilizzo della tecnologia Blockchain per cristallizzare data e ora del documento. •
- Marcatura temporale conforme alle normative italiane ed europee, per garantire validità legale e opponibilità a terzi. •
- Massima trasparenza e sicurezza per tutti i documenti firmati digitalmente. •