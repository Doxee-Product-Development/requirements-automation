# Doxee Platform Design Tools -- Context Bible

> Compressed from 110 source files (~560KB text, ~30MB raw with images) across Business Designer 6.7, Template Designer 6.7, Composer 6.7, and Resource Explorer 6.7 user guides and developer guides.

---

## Tool Ecosystem Overview

The four design tools form a document lifecycle pipeline:

```
Template Designer (desktop) --> Business Designer (web) --> Composer (web) --> Output
       |                              |                          |
  Power users create           Business users edit         End users compose
  base templates (.ITX)        templates via browser       final documents
       |                              |                          |
       +--- Resource Explorer (file management, versioning, WebDAV access) ---+
```

**Shared file format**: All tools use `.ITX` files (XSL-FO based, Infinica Template XML).

**Shared infrastructure**: Doxee Content Repository (WebDAV), Process Engine, Workplace.

**Shared concepts across all tools**:
- XSL-FO standard for page-based document formatting
- XML data binding via XPath expressions
- Template parts (reusable building blocks)
- Style packages (reusable formatting)
- Page master packages (reusable page layouts)
- Role-based access control (grant/deny/only on users, groups, roles)
- Content-level permissions (editable-template, editable-document)
- AI Assistance (OpenAI, Mistral, DeepL, Gemini, Azure OpenAI) -- shared across BD and Composer
- Spell check via Hunspell dictionaries
- Versioning with check-in/check-out workflow

---

## 1. Business Designer (Web Application)

### Purpose
Web browser-based graphical editor for creating document templates. Targets business users who design serial letters, contracts, invoices, bank statements, personalized marketing, and other business communications. Templates combine static content with dynamic data (XML).

### Technical Foundation
- Web application deployed on Apache Tomcat (8.5 or 9)
- Requires: OpenJDK 17, Doxee Content Repository
- Optional: Process Engine (for preview), Composer (for preview)
- Configuration: `business-designer.properties` in `$TOMCAT/infinica/`
- Embeddable in iframe (SameSite=None cookies policy, Salesforce integration supported)
- URL rewrite via `rewrite.config` in `$TOMCAT/conf/Catalina/localhost/`

### UI Structure

| Area | Purpose |
|------|---------|
| Editor (center) | WYSIWYG template editing, element arrangement |
| Outline (left) | Hierarchical element tree, element selection |
| Palette (right) | Drag-and-drop element icons (Standard, Dynamic, Forms, Template Parts) |
| Style & Properties (right) | Format attributes, advanced XSL-FO properties |
| Data (right) | XML test data connection and field browsing |
| Left toolbar | Designer, Preview, Layout, Styles, Variables, Test Data, Other |

### Element Hierarchy

```
Page Sequences > Page Sequence > Page Content (body)
                               > Static Page Content (header, footer, left, right)
```

**Block-level elements** (stack vertically): Block (paragraph), Container, Table, List, Condition, Repeat
**Inline elements** (flow horizontally within blocks): Text, Image, Data Field, Dynamic Value, Link, Barcode, Leader

### Template Element Types

| Category | Elements |
|----------|----------|
| Standard | Block, Text, Image, Table, List, Container, Comment, Leader, Wrapper |
| Dynamic | Data Field, Dynamic Value, Condition, Condition Branch, Repeat, Variable, De-/Activate, Processing Instruction, Refreshable |
| Forms | Text Field (single-line), Text Area (multi-line), Combobox, Listbox, Radio Button, Checkbox, Button, Script, Signature |
| Building Blocks | Template Part Reference, Insertion Point, Numbering Reference, Table of Contents |
| Composer-specific | Composer Signature, Take-picture, GPS-location, Barcode Scanner |
| Special | Barcode (38+ types including QR, Datamatrix, EAN, Swiss-QR; generators: Barcode4j, Aspose), Link (internal/external), Page Number |

### Data Connection Model
- Data must be XML format
- Template links to test XML files with matching data structure (schema)
- Multiple data inputs supported (different XML sources)
- Multiple test cases per data input
- XPath expressions reference data fields
- Data Input Variable names become part of XPath paths
- Max test data XML file size: configurable (default 1MB)
- Version 6.4+: supports large XML files

### Dynamic Content System

| Feature | Description |
|---------|-------------|
| Data Fields | Drag from Data panel; reference XML structure via XPath |
| Dynamic Values | Arbitrary XPath expressions, calculations, functions |
| Conditions | If-then-else via condition branches; XPath boolean expressions |
| Repeat | Loop over XML node sets; supports sorting (v6.3+) |
| Variables | Local (scoped) and Global (template-wide); `$varname` syntax |
| De-/Activate | Toggle element visibility (true/false slider); nestable |
| Wrap-with | Right-click to wrap existing elements with Condition or Repeat |
| Rule Editor | Visual XPath builder with functions, operators, test/run, reference docs |

### Formatting System
- **Direct formatting**: Set attributes on selected elements via Style & Properties panel
- **Style sheets**: Named format combinations, organized in groups; diamond icon in outline
- **Style inheritance**: Parent element styles cascade to children; direct formatting overrides styles
- **Style collections**: External .ITX files containing reusable style packages
- **Measurements**: cm, mm, in, pt (point), pc, px
- **Styles concept extension (v6.4)**: `composer-style` boolean attribute on Style Groups for Composer visibility

### Page Layout System

| Concept | Description |
|---------|-------------|
| Page Master | Defines page dimensions, margins, regions; default "A4" |
| Page Margins | Outer limits of entire page content |
| Body Margins | Space for main content area |
| Extents | Size of static regions (header, footer, left, right) |
| Precedence | Controls corner overlap between header/footer and left/right regions |
| Double-sided | Creates odd/even page sub-masters with separate static regions |
| Complex Page Master | Combines multiple simple page masters with iteration rules (e.g., first page + remaining pages) |
| Page Master Collection | External .ITX package for cross-template reuse |

### Template Parts (Building Blocks)
- **Local template parts**: Defined within a template, reusable only in that template
- **External template parts**: Defined in Template Part Package (.ITX), reusable across templates
- **Template Part References**: Dynamic references (not copies); changes propagate to all usages
- **Parameters**: Input fields for template part customization (type-constrained)
- **Insertion Points**: Define which template parts are available for Composer users; configurable: max-count, allow-repeats, chosen (preselected)
- **Refreshable Elements**: Content wrapped for Composer refresh capability; naming restrictions (no spaces, special chars, no leading digits)
- **Sorting**: Local template parts can be reordered via drag-and-drop in template part view

### Tables
- Insert via drag-and-drop; select rows/columns and style (with/without borders)
- Operations: add/delete rows/columns, merge cells (right/down), split cells, define column widths (drag or numeric), row heights
- Border configuration: color, type, thickness per side; preview-based editing
- Style sheets applicable to cells (not rows/columns directly)
- Common error source: column count mismatch after cell merge/split

### Numbering System (v6.2+)
- Pre-defined schemes: chapter, figure, table, appendix
- Properties: Name, Value (start), Number Format, Prefix, Suffix, Separator, Left/Right Padding, Width
- Formats: decimal, decimal-leading-zero, lower/upper-alpha, lower/upper-roman
- Numbering Reference: inline element referencing numbered blocks by ID
- Table of Contents: auto-generated from numbering scheme during rendering
- Supported in Composer and MS Word (v6.4+)

### Output Formats

| Format | Description |
|--------|-------------|
| PDF | Standard FOP renderer; primary output |
| HTML | Via Process Engine email preview |
| FO | XSL-FO source code |
| XSLT (FO) | XSL transformation source |
| Composer Preview | Live preview in Composer application |
| Custom Process Preview | Via external Process Engine calls |

### Versioning
- Enable versioning creates v1.0 (read-only)
- Checkout: locks file for exclusive editing; blue dot indicator
- Checkin: creates new version (v1.1, v1.2...); comment optional
- Discard Checkout: reverts to last checked-in version
- Version History: timeline view, indirect versions for referenced files
- Autosave: configurable interval (default 30s); requires checked-out file

### Template Comparison (v6.1+)
- Compare two templates side-by-side (any versions)
- Color coding: red (removed), blue (changed), green (added)
- Accept/reject individual changes to create merged template
- Known limitation: does not recognize Composer Elements or Free Texts

### Permission System

| Type | Scope | Description |
|------|-------|-------------|
| Role permissions | Application-wide | READER, BUSINESS_USER, POWER_USER, ADMINISTRATOR |
| Content permissions | Per-element | `editable-template` attribute; grant/deny/only syntax |
| Inheritance | Element hierarchy | Content permissions cascade down; can be overridden locally |

**Role rights granularity**: 70+ individual rights controlling palette elements, preview types, property tabs, views, advanced sections. Custom roles: prefix `ROLE_`, map to predefined rights.

### AI Assistance
- Providers: OpenAI (text+images), Mistral (text), DeepL (translations), Gemini (text), Azure OpenAI (text+images)
- Modes: Free-form prompts, range-selected context modification, quick actions (translate, rephrase, summarize)
- Image generation: DALL-E-3 support via OpenAI and Azure OpenAI
- Saved chats: unlimited concurrent chats, cross-provider context preservation
- Configuration: per-provider API tokens, models, temperature, max-tokens in properties file
- DeepL: separate UI with source/target language dropdowns

### Configuration Properties (Key Settings)

| Property | Purpose |
|----------|---------|
| `icr.location` | Content Repository URL (required) |
| `icr.externalPaths` | Path strategy: PROJECT_RELATIVE, FILE_RELATIVE, ABSOLUTE |
| `composer.location` | Composer URL for preview |
| `master.templates.locations` | ICR paths to master template folders |
| `custom.component.templates.locations` | ICR paths for custom palette components |
| `extensions.templateComparison.available` | Enable template comparison |
| `extensions.imagePaste.maxSizeMB` | Max paste image size (default 4MB) |
| `extensions.autoSave.intervalInSeconds` | Autosave interval (default 30s) |
| `spellcheck.dictionaries.*` | Hunspell dictionary configuration |
| `openai.*`, `mistral.*`, `deepl.*`, `gemini.*`, `azure.openai.*` | AI provider configurations |

### Keyboard Shortcuts (Selection)

| Shortcut | Action |
|----------|--------|
| Ctrl+S | Save |
| Ctrl+O | Open |
| Ctrl+Z / Ctrl+Y | Undo / Redo |
| Alt+Up/Down | Move element (same level) |
| Ctrl+Shift+Up/Down | Move as child |
| Alt+Shift+C | AI Assistance |
| Alt+Shift+R | Search & Replace |
| Tab (in lists) | Create/increase list level (v6.4+) |
| Shift+Tab | Reverse list level |

---

## 2. Template Designer (Desktop Application)

### Purpose
Desktop Java application for power users and developers to create and maintain base templates. Provides full XSL-FO control including advanced features not available in Business Designer (charts, assertions, tracing, IDX export). Used to create templates, template part packages, style packages, page master packages, and metadata packages.

### Installation & Requirements
- Desktop application (Java-based)
- Requires license file activation
- Connects to Doxee Content Repository via WebDAV (embedded Resource Explorer)
- FOP renderer included; supports alternative renderers (XMLMind XFC, XEP, IBEX)
- Hyphenation requires separate `fop-hyph.jar` download

### UI Structure

| Component | Purpose |
|-----------|---------|
| Designer View | WYSIWYG template editing with grid, labels, control characters toggle |
| Outline View | Full document structure tree with drag-and-drop reordering |
| Properties View | All XSL-FO attributes; quick properties + Advanced categories |
| Palette | Standard, Forms, Dynamic, Building Blocks drawers |
| Events View | Runtime messages from XSL transformation |
| Problems View | Validation errors and warnings |
| XPath Editor | Test and validate XPath expressions with live results |
| Dependencies View | Cross-file reference analysis (requires database) |
| Search & Replace | Find/replace across template content |
| Metadata View | Key-value metadata management |

### File Operations

| Operation | Description |
|-----------|-------------|
| New | Create: Template, Page Master Package, Template Part Package, Style Package, Metadata Package |
| Import | RTF files, XSL-FO files |
| Export | Text, XSL:FO, FO, XSL:IDX, IDX |
| Save | Local or remote (WebDAV) |

### Element Types (Superset of Business Designer)

All Business Designer elements plus:

| Element | Description |
|---------|-------------|
| Chart | Bar, Pie, Line, Scatter, Spider; XML chart-definition + chart-data inputs |
| Instream Foreign Object | SVG code or renderer-specific extensions |
| Assertion | Validation rules evaluated during XSL transformation |
| Static Page Content | Content for header/footer/left/right regions |
| Namespace | XML namespace declarations |
| External Document | Reference to external ITX files |
| Free Text | Raw FO code injection around elements |
| Output Configurations | Control which components included in XSL generation |

### Document Structure Nodes (Outline)

| Node | Purpose |
|------|---------|
| Namespaces | XML namespace declarations |
| Page Masters | Page dimension/margin/region definitions |
| Bookmarks | PDF bookmark tree (reference blocks by ID) |
| Page Sequences | Container for Page Sequence elements |
| Template Parts | Local reusable building blocks |
| External Resources | References to external ITX packages |
| Data Inputs | XML test data connections |
| Style Packages | Local and external style definitions |
| Output Configurations | XSL generation component selection |

### Access Control System (Shared with BD/Composer)
Two properties per element:
- `editable-template` (for Business Designer) -- defaults to `true`
- `editable-document` (for Composer) -- defaults to `false`

Three assignment modes:
- `grant:user:X,group:Y` -- allow listed principals
- `deny:user:X` -- deny listed principals (overrides grant)
- `only:group:A` -- exclusive access, breaks inheritance

### Views System

| View | Shortcut | Purpose |
|------|----------|---------|
| Outline | Alt+Shift+O | Document structure navigation |
| Properties | Alt+Shift+T | Element attribute editing |
| Events | Alt+Shift+E | XSL transformation messages |
| Problems | Alt+Shift+R | Validation errors |
| XPath Editor | Alt+Shift+H | XPath testing with live preview |
| Dependencies | Alt+Shift+D | Cross-file reference graph |
| Search & Replace | Alt+Shift+F | Find/replace |
| Metadata | Alt+Shift+M | Template metadata |
| Resource Explorer | Alt+Shift+X | File browser |

### Styles System
- Styles created at element level; inherit through hierarchy
- Style groups organize related styles
- Inline styles: character-level formatting (bold, italic, etc.)
- Block styles: paragraph-level formatting (alignment, spacing)
- Style packages: external .ITX files for cross-template reuse
- Conflict resolution: local styles override external; deepest external wins

### Internationalization & Hyphenation
- Language codes assigned at Page Sequence or block level
- Hyphenation requires language + country codes + `hyphenate=true`
- Separate `fop-hyph.jar` needed (licensing restrictions)
- Can activate/deactivate per block

### Master Templates
- "Templates for templates" stored in configurable ICR folder
- Users create new templates from master templates
- Strategy: flat or hierarchical resource copying
- Optional prefix/suffix for copied resource filenames

### Preview Processes (Advanced)
- External Process Engine rendering for custom post-processing
- Configurable: engine URI, process path, renderer (fop/xfc/xep), format (pdf/docx/rtf/odt/ps/html)
- Process inputs: xsl, xml, baseUri, templateUri, metadata, type, target.format, target.renderer
- Process outputs: document, xslResult, xslMessages, xslErrors, rendererMessages, pdfaValidationResult

### PDF/A Validation
- Available via preview process returning pdfaValidationResult
- Validates PDF output against PDF/A archival standards

### Tracing
- Trace properties on elements for debugging XSL transformation
- Helps identify rendering issues in complex templates

### Developer Guide Configuration

| File | Purpose |
|------|---------|
| Preferences > FO | FOP config, alternative renderers, PDF viewer settings |
| Preferences > Composer Previews | Embedded Composer preview setup |
| Preferences > Dependencies | Database path for cross-file dependency indexing |
| Preferences > External Calls | Custom menu items executing external commands |
| Preferences > Preview Processes | External Process Engine preview configuration |
| Preferences > Spelling | Dictionary configuration |
| Preferences > Versioning | Auto-checkout behavior (Always/Ask/Never) |

---

## 3. Composer (Web Application)

### Purpose
Web browser-based interactive document composition tool for end users. Users open rendered documents (from templates + real data) and can edit allowed areas, insert building blocks at insertion points, fill forms, add signatures, and produce final output. Composer operates on IDX documents (intermediate format generated from ITX templates).

### Technical Foundation
- Web application deployed on Apache Tomcat (8.5 or 9)
- Requires: OpenJDK 17, Doxee Content Repository
- Configuration: `composer.properties` in `$TOMCAT/infinica/`
- Can be standalone or embedded in Workplace
- URL rewrite required (same pattern as Business Designer)
- SameSite cookies policy for iframe embedding

### UI Structure

| Area | Purpose |
|------|---------|
| Editor (center) | Document editing with element overlays |
| Outline (left) | Document structure tree |
| Right Panel | Palette Elements, Styles, Insertion Points, Refreshables, Library |
| Floating Toolbar | Context-sensitive formatting buttons (bold, italic, lists, links, AI quick actions) |

### Document Composition Elements

| Element | Capabilities in Composer |
|---------|--------------------------|
| Text | Edit, format, copy/paste (with/without formatting) |
| Paragraph | Alignment, margins, padding, keep-together properties |
| Image | Insert from ICR, upload via file picker; mime-type and size restrictions |
| Table | Insert with configurable rows/columns/width; add/delete rows/columns; merge cells; background colors; column widths; vertical alignment |
| List | Numbered and bulleted; types: decimal, alpha, roman, circle, disc, square; prefix/suffix support; auto-continuation on Enter |
| Link | Internal (block ID) or external (URL); drag-drop or floating toolbar creation |
| Form Fields | Text field, text area, combobox, listbox, checkbox, radio button, button |
| Page Break | Manual insertion via drag-drop; renders as placeholder |
| Insertion Point | Add/remove/move/refresh/modify building blocks; parameter dialogs; preview |
| Refreshable | Update content from external data; show-different-only filter; preview; update-all |
| Content Flipper | NOT supported in current version |

### Editability Model
Template designers control what Composer users can edit:
- `editable-document=true/false` on each element (set in Template Designer or Business Designer)
- Permission-based: `grant:user:X`, `deny:group:Y`, `only:role:Z`
- Inheritance: child elements inherit parent editability
- Form fields have separate editability rules

### Building Blocks (Insertion Points)
1. **Adding**: Drag-and-drop from right panel or click add button; parameter dialog if configured
2. **Moving**: Drag puzzle icon within same insertion point only
3. **Removing**: Click bin icon in editor or right panel
4. **Refreshing**: Click refresh icon to update content from template
5. **Modifying**: Edit parameters via edit button or double-click puzzle icon
6. **Constraints**: max-count limits, allow-repeats configuration, chosen (preselected) blocks

### Refreshable Elements
- Content wrapped as refreshable in Business Designer
- Right panel shows all refreshables; click to scroll to location
- Yellow rectangle indicates content differs from template
- "Show different only" filter for large documents
- Preview before updating; Update All button for batch refresh
- Warning: update overwrites existing editable content

### Page Settings
- Page format (A4, Letter, etc.) and custom dimensions
- Body margins: top, bottom, left, right
- Header/footer region extents
- Orientation: portrait/landscape

### Supported Units

| Unit | Description |
|------|-------------|
| cm | Centimeters |
| mm | Millimeters |
| in | Inches |
| pt | Points (1pt = 1/72 inch) |
| pc | Picas (1pc = 12pt) |
| px | Pixels |

### Editor View Settings
- Zoom (keyboard: Ctrl+/-, Ctrl+0 reset; mouse: Ctrl+scroll)
- Page fit modes: Fit Width, Fit Page
- Show/hide: Outline panel, Right panel, Floating toolbar
- Page gap configuration

### Text Element Properties
- Font: family, size, bold, italic, underline, strikethrough, color
- Alignment: left, center, right, justify
- Spacing: letter-spacing, word-spacing
- Subscript/superscript support
- Hyphenation (when configured)

### Table Operations

| Operation | Method |
|-----------|--------|
| Insert table | Drag from Palette; configure rows, columns, width |
| Add row | Plus icon at bottom or between rows |
| Add column | Plus icon at right or between columns |
| Delete row/column | Select via overlay, click bin icon |
| Merge cells | Select cells, use merge option |
| Column width | Select column, edit in right panel |
| Row height | Select row, edit in right panel |
| Background color | Per table, row, or cell |
| Borders | Per table, row, column, or cell; color, type, thickness |
| Vertical alignment | Top, middle, bottom per cell |

### GPS Location
- Captures device GPS coordinates (latitude, longitude, altitude, accuracy)
- Requires composer-element-type=gps-location-button configured in template

### Features NOT Supported in Current Version
- Autocomplete (depends on form elements and Process Engine)
- Change Tracking / History
- Content Flipper
- Shift+Enter (soft break) in lists
- List property modification (shows template-defined properties only)
- Cell splitting

### AI Assistance (Same as Business Designer)
- Identical provider support and UI pattern
- Quick actions available in floating toolbar for range-selected text
- DeepL with Translate Selection button

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl+S | Save |
| Ctrl+Z / Ctrl+Y | Undo / Redo |
| Ctrl+C / Ctrl+X / Ctrl+V | Copy / Cut / Paste |
| Ctrl+A | Select all |
| Ctrl+B / Ctrl+I / Ctrl+U | Bold / Italic / Underline |
| Ctrl+F | Search & Replace |
| Ctrl+P | Print |
| Ctrl+Plus/Minus | Zoom in/out |
| Ctrl+0 | Reset zoom |
| Alt+Shift+C | AI Assistance |
| Escape | Close dialog / Deselect |

### Developer Guide -- Configuration

#### composer.properties (Key Settings)

| Property | Purpose |
|----------|---------|
| `icr.location` | Content Repository URL (required) |
| `userAccessManager.location` | useraccess.xml path (required) |
| `font.folder.location` | Custom font directory |
| `fop.config.xml.location` | FOP renderer configuration |
| `application.title` | Browser tab title |
| `extensions.imagePaste.available` | Enable image paste (default true) |
| `extensions.imagePaste.maxSizeMB` | Max paste image size (default 4MB) |
| AI settings | Same pattern as Business Designer |

#### User Access Configuration
- Supports multiple user store types: LDAP, Active Directory, Database, Properties file, OAuth/OIDC
- Security configuration: session timeout, CSRF protection, CORS settings
- Role-based access with custom role definitions
- Group-based permission inheritance

#### Security Configuration
- Content Security Policy (CSP) headers
- Cookie SameSite policy
- HTTPS enforcement (configurable)
- Session management: timeout, concurrent sessions
- CORS configuration for API access

---

## 4. Resource Explorer (Desktop Tool)

### Purpose
Graphical file management tool for WebDAV servers (Doxee Content Repository) and local file systems. Available standalone and embedded in Template Designer and Process Designer. Manages files, versions, access rights, and data transfers.

### Installation
- Copy distribution folder; run `resource-explorer.bat`
- No separate installation required

### UI Structure
- Menu bar with address field and action icons
- Tree view (left): local file system + Registered Hosts (WebDAV connections)
- Content pane (right): file/folder listing with configurable columns
- Multiple tabs for quick location switching
- Home directory button per connection

### Connection Management
- Right-click "Registered Hosts" > Configure Hosts
- Per host: Label, URL, User, Password (optional; prompts if blank)
- Supports: local file system (file://), HTTP/WebDAV (http/https), SFTP (sftp)

### Supported Protocols

| Protocol | Features |
|----------|----------|
| file:// | Local file system + mounted shares; no user-based access control |
| http/https | WebDAV; directory listings, properties, ACLs, versioning |
| sftp | SSH file transfer; directory listings, deletion, key-based auth |

### File Operations

| Action | Methods |
|--------|---------|
| Create folder | Context menu, Ctrl+Shift+N |
| Copy/Move | Cut/Copy/Paste, Drag/Drop (Ctrl=copy, Shift=move) |
| Delete | Icon bar, context menu, Del key |
| Rename | Icon bar, context menu, F2 |
| Lock/Unlock | Context menu; locked files editable only by locker |
| Steal Lock | Context menu (admin only) |

### Versioning

| State | Description |
|-------|-------------|
| Non-versioned | Default; previous content lost on overwrite |
| Enable versioning | Creates v1 from current content |
| Checked-in | Write-protected; read-only |
| Checked-out | Working copy created; file locked for current user |
| Checkin | Persists changes as new version |
| Discard checkout | Reverts to last checked-in version |

Folder-level versioning: recursively applies to all files in folder (existing files only; new files unaffected).

### User Access Rights
- Configure via Properties dialog > Security tab
- Add users/groups; assign permissions
- Available permissions depend on Content Repository configuration

### ZIP Import/Export
- Export files/folders to ZIP with optional: ACLs, checked-out content, version history, auto-generated content
- Import from ZIP to repository with same options
- Filter support on import/export (property-based conditions)
- Scheduled import: upload ZIP to server for later processing
- Deployment mode: available if server supports it

### Search and Filter

| Feature | Description |
|---------|-------------|
| Simple Search | By resource name (wildcards: *, ?) and/or file content; file/folder/both filter |
| Advanced Search | Property-based conditions with operators: equals, like, contains, <, > |
| Multiple conditions | AND by default; OR connectors between condition sets |
| Negation | Toggle per condition |
| Filter presets | Save/recall named filter configurations |
| Local filtering | Applied client-side; no server round-trip; available for all host types |

### Resource Access Layer (RAL) Configuration

Connection settings via Java VM parameters (`-Dscheme.property`):

| Property | Default | Description |
|----------|---------|-------------|
| connectionPoolTimeout | 60s | Connection establishment + pool wait |
| connectionTimeout | 10s | Server connection only |
| requestTimeout | 5m | Server response timeout |
| maxConnections | 1000 | Total connection pool size |
| maxConnectionsForRoute | 50 | Per-server connection limit |
| proxyHost/Port/User/Password | - | HTTP proxy configuration |
| username/password | - | Default credentials |

SSL: Custom certificates via Java trust store (`JAVA_HOME/lib/security/cacerts`) or custom keystore (`-Djavax.net.ssl.trustStore`).

SFTP: SSH host keys via known_hosts file; bypass with `-Dinfinica.trustAllSshKeys=true` (not recommended for production).

---

## Cross-Tool Data Model

### ITX File Structure
```
ITX File (.itx)
├── Namespaces
├── Page Masters (simple, compound, complex)
├── Bookmarks
├── Page Sequences
│   └── Page Sequence
│       ├── Page Content (body)
│       │   └── Block-level elements (blocks, containers, tables, lists, conditions, repeats)
│       │       └── Inline elements (text, images, data fields, dynamic values, links, barcodes)
│       └── Static Page Content (header, footer, left, right)
├── Template Parts (local building blocks)
├── External Resources (references to packages)
├── Data Inputs (test XML connections)
├── Style Packages (formatting definitions)
├── Output Configurations
├── Global Variables
├── Decimal Formats
├── Numbering Schemes
└── Metadata (key-value pairs)
```

### Package Types (All .ITX)

| Package | Contents | Created In |
|---------|----------|------------|
| Template | Full document template | BD, TD |
| Template Part Package | Reusable building blocks | BD, TD |
| Style Package | Reusable style groups/sets | BD, TD |
| Page Master Package | Reusable page layouts | BD, TD |
| Metadata Package | Reusable key-value metadata | TD |
| Global Variable Package | Reusable variable definitions | BD |

### Supported Image Formats (FOP Renderer)
GIF, BMP, EPS (PostScript only), JPEG, PNG, SVG (with limitations), TIFF (with limitations), EMF (RTF only)

### Barcode Types
38+ types supported including: QR Code, DataMatrix, EAN-8, EAN-13, Code 128, Code 39, UPC-A, UPC-E, Swiss QR (v6.4+). Two generators: Barcode4j, Aspose.

### XPath Functions (Rule Editor)
Categories: String, Numeric, Boolean, Date/Time/Duration, Node, Sequence, Context.
Key functions: `current-date()`, `format-date()`, `format-number()`, `concat()`, `substring()`, `translate()`, `sum()`, `count()`, `position()`, `last()`.

---

## Shared AI Configuration Reference

All tools share the same AI provider configuration pattern:

| Provider | Capabilities | Key Config Properties |
|----------|-------------|----------------------|
| OpenAI | Text + Images (DALL-E) | `openai.enabled`, `openai.api.token`, `openai.model` (default: gpt-3.5-turbo), `openai.max-tokens`, `openai.temperature` (0-2), `openai.image.model` (dall-e-3), `openai.image.size` |
| Mistral | Text only | `mistral.enabled`, `mistral.api.token`, `mistral.model` (default: mistral-small-latest), `mistral.temperature` (0-1) |
| DeepL | Translation only | `deepl.enabled`, `deepl.api.token`, `deepl.base-url` |
| Gemini | Text only | `gemini.enabled`, `gemini.api.token`, `gemini.model` (default: gemini-1.5-flash-latest) |
| Azure OpenAI | Text + Images (DALL-E-3) | `azure.openai.enabled`, `azure.openai.api.token`, `azure.openai.base-url`, `azure.openai.deployment-name`, `azure.openai.image.*` |

---

## Version History Highlights

| Version | Key Features |
|---------|-------------|
| 6.1 | Template Comparison, Learning Center, AI Assistance |
| 6.2 | Numbering schemes |
| 6.3 | Repeat sorting, column width drag |
| 6.4 | Large XML support, Swiss QR barcode, List improvements (Tab/Shift+Tab), Styles in Composer, Numbering in Composer/Word, Pagemaster refactoring, Library feature |
| 6.6 | Current stable release |
| 6.7 | Latest release |
