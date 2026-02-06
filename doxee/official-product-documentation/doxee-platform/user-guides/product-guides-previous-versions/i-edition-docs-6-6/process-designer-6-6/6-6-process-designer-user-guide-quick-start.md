---
id: "b1bae702-1607-4b14-a540-fcda14e9608e"
title: "Getting Started"
slug: "6-6-process-designer-user-guide-quick-start"
category: "Process Designer"
category_path:
  - "Product guides"
  - "Previous versions"
  - "i-Edition 6.6"
  - "Process Designer"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-08-08T07:07:52.202Z"
modified_at: "2025-08-20T19:15:51.866Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/6-6-process-designer-user-guide-quick-start"
synced_at: "2026-01-28T21:00:58.222Z"
checksum: "a0cfbed34b1ee532"
---

Navigate to other release versions of Doxee Platform Process Designer

[6.6](https://docs.doxee.com/docs/en/process-designer-6-6)

[6.7](https://docs.doxee.com/docs/en/process-designer-6-7)

This chapter provides a quick introduction to the basic functionality of Process Designer. Detailed explanations of the individual features and components can be found in the subsequent chapters.

## Creating a process
A new process can be created by clicking the *New Process* entry in the menu or toolbar. This opens an editor with an empty editing area. Process components can be added via the palette on the right side of the editor. Select an entry in the category *Elements* and click somewhere in the editor area to add one of the standard process elements. Specific activities can be added the same way, by selecting a palette entry from one of the subcategories of the category *Activity Modules*, which represent the modules available in the currently active Process Engine. Create a connection between two elements by selecting the connection in the palette category *Connections*, clicking on the source element and then on the target element. Process components can be deleted by selecting them and using the *delete* entry in the menu or toolbar. A single component can also be deleted using the delete button in the button pad. Process elements can be moved via drag and drop. Resizing elements works by selecting the element and dragging a point of the selection border.

Basic process component attributes such as id or name can be configured via the *Properties *view in the *Main* tab while the element is selected in the editor. Diagnostic logging and data logging is available via the *Properties* view in the *Log* tab. Namespaces, Constants and the credentials registry for the process can be defined and modified via the *Outline* view, using the context menu which is opened by right clicking on the node of the tree. The *Layout process* menu entry applies an automatic layout to the process. Default colours for process element types can be changed in the *Preferences* dialog under *Style*.

Save the process with the *Save As…* entry in the menu or the *Save* entry in the menu or toolbar. An existing process can be loaded using the *Open File* entry in the menu or toolbar. Processes which have not been created using Process Designer can also be opened and will receive an automatically generated layout.

## Mappings
Select a process element which can contain mappings in the editor and switch to the *Data *tab in the properties view in order to edit mappings. This tab provides all controls necessary for defining the mappings of a process. It contains a list of the existing mappings (blue boxes). For activities/wait elements/tasks there are three separate lists, one with only input mappings, one with only output mappings and one with both. The tabs at the top can be used to switch between them. Add mappings by clicking the *Add* button at the bottom of the list. The lists for activities/wait elements/tasks can also contain parameter place-holders representing the expected inputs and outputs of the element (light blue, rounded boxes). Turn them into a mapping by double clicking or using the *Add* button on the right side of the place-holder.

Existing mappings can be modified using the controls within the box. The arrow to the left of the mapping box can be used to open its full version, providing additional modification options. The first control is the drag handle. It can be used to change the order of mappings in the list via drag and drop. On the right side of the drag handle, there are the source type button and the source value control. The source value button can be used to select a type for the source. When *auto* is selected, which is the default, Process Designer derives the type from the input provided in the source value control, which specifies the value of the mapping source. Prefixing the input with a "$" makes it a variable source, enclosing it with "{" and "}" makes it an xpath. An input containing pairs of "{" and "}" is interpreted as parametrized literal. Leaving the field empty makes it a null source. Any other input is taken as literal. The url source always has to be selected manually, using the button. In the full version of the mapping box it is also possible to add, modify and delete additional mapping sources. The full version also provides a *default* tab, where default values can be added, modified and deleted. The two fields on the right side of the box can be used to specify the name and type of the target variable. The full version also contains a checkbox for setting the *required* flag. Mappings can be copied, cut and deleted using the context menu available through right click on the box.

Additional options for editing mappings are available in data mode. For more information see section [Data Mode](/doxee-platform/docs/6-6-process-designer-process-designer-user-guide-data-mode).

## Testing a process
A process can be executed directly from Process Designer, if a suitable Process Engine is configured. To configure a Process Engine open the preferences window using *Edit* &gt; *Preferences* in the menu and select *Process Engine Configuration*. Click on the *Add* button to add a new configuration to the list. A name will be automatically generated for the new configuration and can be changed through the *Config Name* field. Each configuration has one of three possible types. In this chapter we will use the managed type, which starts a local command line version of the Process Engine as a standalone webservice. Select *managed *from the *Type* combo box. Enter the path where the Engine is installed into the *Path* field and any free port number into the *Port* field. Click on *Test Engine* and wait for a success message to verify that it works. Click *OK* to confirm the configuration and close the preferences window. In the drop down menu in the toolbar you can now select your configuration. Click on the name of the selected configuration in the toolbar in order to start the Process Engine and wait for it to start.

Click on the *Execute Process* button in the toolbar. If no process has been executed for the active process before, the *Launch Configurations* dialog opens. Otherwise the last process execution used for the active process is executed again. The dialog can also be opened by selecting the *Launch Configurations…* entry in the menu or dropdown next to the *Execute Process* button. When the dialog opens, the first launch configuration for the currently open process is displayed, if no such configuration existed before, it is created. On the right side of the dialog the configuration can be defined. Any variables which are mapped into the process in the start element can be defined in the *Parameters* tab.

Click on the *Launch* button to start the process. If it has not been specified before, Process Designer will ask if it should switch to the *Test* perspective upon execution. If the user chooses to not open the *Test* perspective, it can be opened manually, using the button on the right side of the toolbar. The *Test* perspective includes views which make it possible to inspect the results of the execution. The *Process Execution List* shows process executions which have been started from the Process Designer. Selecting an execution from this list will update the *Properties*, *Log View* and *Pipeline View* with the data from this execution.

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}