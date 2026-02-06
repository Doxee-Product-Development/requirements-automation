# Data Transformation 3 (DT3) - Context Bible

> Compressed from 122 source files (~362KB text). Covers the complete DT3 Reference Guide and User Manual.

---

## 1. Overview

**Data Transformation 3 (DT3)** is Doxee Platform's data transformation engine for converting, mapping, and restructuring data between input and output formats. It uses a pipeline-based architecture:

```
Readers --> Mappers --> Writers
              |
        Catalogs / WebServices / DataQuality
```

**Pipeline Architecture:**
- **Readers** parse input files (CSV, XML, Flat File) into a structured data schema
- **Mappers** transform data between input and output schemas using configurable operators
- **Writers** produce output files (XML, Flat File) from the transformed data schema
- **Catalogs** provide lookup table functionality within mappers
- **Web Services** allow WSDL-based external service calls within mappers
- **Data Quality** performs legal archive quality checks

**DT3 Designer** is the web-based UI for building and managing transformation projects, consisting of:
- **Project Explorer Panel**: Lists all project resources organized by type (Flows, Readers, Mappers, Writers, Catalogs, WebServices, DataQualities, Unsupported)
- **Pipeline Editor**: Visual drag-and-drop interface for connecting resources into processing flows
- **Resource Editors**: Dedicated configuration UIs for each resource type

**Resource Lifecycle:**
- Resources can be **active** (in pipeline) or **inactive** (removed from pipeline but retained in project)
- Actions: Edit, Details, Remove (from pipeline), Put back (to pipeline), Delete (permanent)
- Resources are created via the Pipeline Editor and configured in dedicated editors

**Engine Options:**
- **Legacy engine** (Classic Mode) and **New engine** (Mapper) are functionally equivalent; the new mapper is faster
- Toggle via Mapper global settings "Enable legacy engine"

---

## 2. Readers

### 2.1 CSV Reader

**Purpose:** Reads incoming CSV files based on a configured data structure.

**Data Structure Configuration:**
- Define fields manually or import from existing CSV file
- Fields have: Name, Optional flag
- Configured structure must match incoming CSV file order
- Fields can be added, edited, deleted after initial creation
- Option to add fields to HEADER element (in addition to DOCUMENT) for Mapper visibility

**Global Actions:**

| Action | Description |
|--------|-------------|
| Import structure | Define structure from existing CSV file; overwrites existing structure |
| Download structure | Export data structure as CSV file (e.g., `DTE_xxx_Reader1.csv`) |
| Settings | Configure general CSV Reader settings |

**Settings (General):**

| Parameter | Description |
|-----------|-------------|
| Separator | Character delimiter: Pound (#), Tab, Pipe (\|), Comma (,), Semicolon (;) |
| Encoding | Character encoding of the CSV file |
| First line contains field names | Header row contains field names |
| Schema name | View/edit current data schema name |
| Manage schemas | Download, rename, delete schemas; view which resources use each schema |

**Data Schema Management:**
- Schemas can be shared across multiple components
- Blue dot indicator shows schemas in use by resources
- Actions: Download, Rename, Delete (only if not in use)
- "Applied to" section shows all components using the schema

---

### 2.2 XML Reader

**Purpose:** Reads incoming XML files based on a hierarchical data schema (elements and attributes).

**Data Structure:** Ordered hierarchical schema with:
- **Root element** (single, required)
- **Elements** (nested, may contain child elements)
- **Attributes** (properties of elements)
- **Document node** (indicates the repeated document entity in the input file)

**Element/Attribute Parameters:**

| Parameter | Description |
|-----------|-------------|
| Name | Element/attribute name |
| Type | Data type (string default) |
| Min Occurs | Minimum occurrences (0 = optional) |
| Max Occurs | Maximum occurrences (Unbounded checkbox for unlimited) |

**Available Structure Actions:**

| Action | Description |
|--------|-------------|
| Add element | Add sibling element at same level |
| Add child element | Add nested child element |
| Add attribute | Add attribute to element |
| Set as Document node | Mark as document entity (required for processing) |
| Duplicate | Clone element or attribute |
| Delete | Remove element/attribute (Root cannot be deleted) |

**Global Actions:**

| Action | Description |
|--------|-------------|
| Import structure | Import from exported DT schema/structure, XML, or XSD file |
| Download structure | Export as XML (e.g., `Reader_1_structure.xml`) |
| Settings | Configure general XML Reader settings |

**Settings (General):**

| Parameter | Description |
|-----------|-------------|
| Schema name | View/edit current data schema |
| Manage schemas | Download, rename, delete schemas |
| Elements namespace | Qualified (include prefix) or Unqualified |
| Trim values | Delete blank spaces from input XML elements |
| Attributes namespace | Qualified or Unqualified |

---

### 2.3 Flat File Reader

**Purpose:** Reads incoming flat files (fixed-length or character-separated records).

**Data Structure:** Record-based with configurable identifiers and fields.

**Record Configuration:**

| Parameter | Description |
|-----------|-------------|
| Separator | Character delimiter: Comma, Pipe, Pound, Semicolon, Space, Tab |
| Identifiers | Rules for recognizing record types in the flat file |
| Fields | Parsable by position or fixed length |

**Record Identifiers:**
- **SD (Fixed identifier)**: Match value at a given position
- **FD (Positional identifier)**: Match value using separator count
- Identifiers can be combined using boolean expressions (AND, OR, NOT, parentheses)
- Syntax checking available via CHECK link

**Field Configuration:**

| Parameter | Description |
|-----------|-------------|
| Name | Field identifier name |
| Position | Relative position (starting at 0) for character-delimited format |
| Default value | Used when read value is null or blank |
| Optional | Whether null values are accepted |
| Padding | Left/Right padding with configurable character and length |
| Trim | None, Both, Left, Right (blank space removal) |

**Global Actions:**

| Action | Description |
|--------|-------------|
| Import structure | Import from XML structure file (previously exported) |
| Download structure | Export as XML (e.g., `FFReader_structure.xml`) |
| Settings | Configure general Flat File Reader settings |

**Settings (General):**

| Parameter | Description |
|-----------|-------------|
| Ignore unmapped rows | Skip rows not matching any record definition |
| Schema name | View/edit current data schema |
| Manage schemas | Download, rename, delete, view usage |

---

## 3. Mapper and Operators

### 3.1 Mapper Overview

The Mapper transforms data from input to output schema using operators connected in a visual mapping area.

**Configuration:**
- Select input and output data structures from connected Reader/Writer schemas
- Clone data structures to modify independently of other resources
- Auto-connect child nodes with matching names (when input/output structures match)

**Mapping Area Actions:**

| Action | Description |
|--------|-------------|
| Direct connection | Connect input element to output element (drag-and-drop) |
| Add operator | Drag operator from panel to mapping area |
| Connect to operator | Wire input/output elements to operator inputs/outputs |
| Logical clone | Create visual repetition of output element for complex transformations |
| Disconnect all | Remove all connections from selected node |
| Show connections | Display all connections for current element |

**Custom Operators:**
- User-defined operator groups reusable across transformations
- Created with named input/output parameters (simple or complex/hierarchical)
- Configured using built-in operators in a sub-mapping area
- Exportable as XML files; importable from file
- Naming: letters, numbers, underscore, hyphen (cannot start with number)

**Global Settings:**

| Parameter | Description |
|-----------|-------------|
| Enable legacy engine | Switch between legacy and new (faster) mapper engine |
| Auto-hide empty columns | Compact mapping area view |
| Auto-hide empty rows | Compact mapping area view |
| Page navigation | Switch between Mapper workspace pages |
| Manage schemas | Download, rename, delete schemas |

---

### 3.2 Operator Reference

All operators follow a consistent structure: Description, Input (name, data type), Output (name, data type), Settings, Special cases.

#### 3.2.1 Aggregation Operators (6)

| Operator | Input | Output | Description | Settings |
|----------|-------|--------|-------------|----------|
| **Average** | in0 (Number) | out0 (Number) | Arithmetic mean of all instance values | None |
| **Counter** | in0 (Any) | out0 (Number) | Counts instances of input node | None |
| **Max** | in0 (Number) | out0 (Number) | Maximum value across all instances | None |
| **Min** | in0 (Number) | out0 (Number) | Minimum value across all instances | None |
| **SumIncremental** | inc (Number), #state (Any) | out0 (Number) | Incremental sum; resets at state changes | None |
| **Summary** | in0 (Number) | out0 (Number) | Sum of all instance values | None |

**Common special cases (all aggregation):** NULL input -> 0 + warning; NULL value -> 0 + warning; NON NUMERIC -> 0 + warning.

---

#### 3.2.2 Boolean Operators (7)

| Operator | Input | Output | Description | Settings |
|----------|-------|--------|-------------|----------|
| **And** | in0 (Boolean), in1 (Boolean) | out0 (Boolean) | Logical AND | None |
| **Compare** | in0 (Number), in1 (Number) | out0 (Boolean) | Numeric comparison | Comparison type: =, <=, >=, <, >, != |
| **ComplexIf** | in0..inN (Any) | out0 (Any) | Boolean expression with multiple inputs | Expression builder with AND/OR/NOT/>=/<=/>/</= |
| **Not** | in0 (Boolean) | out0 (Boolean) | Logical NOT | None |
| **Or** | in0 (Boolean), in1 (Boolean) | out0 (Boolean) | Logical OR | None |
| **SimpleIf** | bool (Boolean), value-true (Any), value-false (Any) | out0 (Any) | Conditional value selection | Enable Inputs: All / True values only / False values only |
| **Switch** | in0..inN (Any) | out0 (Any) | Multiple boolean expressions linked to different data outputs | Expression builder per case |

**ComplexIf/Filter Expression Operators:** AND, OR, NOT, >=, <=, >, <, = (used in boolean expressions for ComplexIf, Filter, Switch operators).

---

#### 3.2.3 Common Operators (23)

| Operator | Input | Output | Description |
|----------|-------|--------|-------------|
| **AddressNormalizer** | in0..inN (String) | out0..outN (String) | Normalizes address fields using external normalization service |
| **AdvancedScript** | in0..inN (Any) | out0..outN (Any) | Executes custom JavaScript/Groovy script with multiple I/O |
| **BinaryCodec** | in0 (String) | out0 (String) | Encodes/decodes binary data (Base64, Hex) |
| **Catalog** | in0..inN (String) | Record (String), K1 (String) | Lookup value in catalog component; settings: catalog name, key columns |
| **Constant** | None | out0 (String) | Outputs constant value from settings |
| **DataQuality** | in0..inN (Any) | out0..outN (Any) | Calls Data Quality component for Legal Archive checks |
| **DocumentInfo** | in0 (Any) | out0 (String) | Returns document metadata (name, index, count, etc.) |
| **Filter** | node (Any), in0..inN (Any) | out0 (Any) | Filters instances using boolean expression (AND/OR/NOT/>=/<=/>/</=) |
| **GroupBy** | groups/lines (Any), key (Number) | groups/lines (Any), key (Number) | Groups instances by key value |
| **GUIDGenerator** | in0 (Any) | out0 (String) | Generates unique GUID |
| **NodeDiff** | node (Any), #state (Integer) | groups (Boolean), lines (Boolean) | Detects data changes between instances |
| **NodeExist** | in0 (Any) | out0 (Boolean) | Checks if input node exists in data |
| **NodeSelector** | in0..inN (Any) | out0 (Any) | Selects specific node from input based on settings |
| **Parity** | in0 (Number) | out0 (Boolean) | Checks if number is even/odd |
| **Progressive** | in0 (Any) | out0 (Number) | Generates progressive counter |
| **ProgressiveAdvanced** | in0 (Any), #state (Any) | out0 (Number) | Progressive counter with state-based reset |
| **Random** | in0 (Any) | out0 (Number) | Generates random number |
| **RowParity** | in0 (Any) | out0 (Boolean) | Checks if row position is even/odd |
| **Script** | in0 (Any) | out0 (Any) | Executes custom JavaScript script |
| **Sort** | in0..inN (Any) | out0 (Any) | Sorts values; settings: Order (ASC/DESC), Type (string/number/date), Format, Locale |
| **SystemVariable** | None | out0 (String) | Returns system variable value (e.g., date, filename) |
| **Variable** | in0 (Any) | out0 (Any) | Stores and retrieves variable values across transformations |
| **WebService** | in0..inN (Any) | out0..outN (Any) | Calls external web service defined in WebService component |

---

#### 3.2.4 Date Operators (8)

| Operator | Input | Output | Description | Settings |
|----------|-------|--------|-------------|----------|
| **DateAdd** | date (Date), value (Number) | out0 (Date) | Adds time interval to date | Interval type (day/month/year/hour/minute/second) |
| **DateCompare** | in0 (Date), in1 (Date) | out0 (Boolean) | Compares two dates | Comparison: =, <=, >=, <, >, != |
| **DateDiff** | in0 (Date), in1 (Number) | out0 (Number) | Subtracts time interval from date | Interval type |
| **DateTimeInfo** | in0 (Date) | out0 (Number) | Returns specific date component | Info type (year/month/day/hour/etc.), Locale |
| **FormatDate** | in0 (Date) | out0 (String) | Formats date to string | Input format, Output format, Input locale, Output locale |
| **IsDate** | in0 (Any) | out0 (Boolean) | Checks if input matches date format | Date format pattern |
| **Now** | in0 (Any) | out0 (Date) | Returns current date/time | Output format |
| **Timestamp-Date** | in0 (Variable) | out0 (Variable) | Converts between timestamp and date | Conversion direction |

---

#### 3.2.5 Math Operators (9)

| Operator | Input | Output | Description | Settings |
|----------|-------|--------|-------------|----------|
| **Abs** | in0 (Number) | out0 (Number) | Absolute value | None |
| **Division** | in0 (Number), in1 (Number) | out0 (Number) | Divides in0 by in1 | None |
| **FormatNumber** | in0 (Number) | out0 (String) | Formats number to string | Format pattern, Locale |
| **IsNumeric** | in0 (Any) | out0 (Boolean) | Checks if input is numeric | None |
| **Mod** | in0 (Number), in1 (Number) | out0 (Number) | Modulo (remainder) | None |
| **Multiplication** | in0 (Number), in1 (Number) | out0 (Number) | Multiplies two numbers | None |
| **Positive** | in0 (Number) | out0 (Number) | Checks positive/negative/zero | None |
| **Subtract** | in0 (Number), inN (Number) | out0 (Number) | Subtracts multiple inputs | None |
| **Sum** | in0 (Number), inN (Number) | out0 (Number) | Adds multiple inputs | None |

---

#### 3.2.6 String Operators (20)

| Operator | Input | Output | Description | Settings |
|----------|-------|--------|-------------|----------|
| **Case** | in0 (String) | out0 (String) | Converts to upper/lower case | Case type: Upper/Lower |
| **Compare** (String) | in0 (String) | out0 (Boolean) | Compares input to settings value | Comparison value, Case sensitive flag |
| **Concatenate** | in0..inN (String) | out0 (String) | Concatenates multiple strings | None |
| **Contains** | in0 (String) | out0 (Integer) | Position of first occurrence of settings substring | Substring, Case sensitive |
| **DynamicContains** | value (String), substring (String) | out0 (Integer) | Position of first occurrence; substring from input | None |
| **DynamicReplace** | string (String), search (String), replace (String) | out0 (String) | Replaces substring using input values | None |
| **DynamicSubstring** | string (String), start (Number), length (Number) | out0 (String) | Extracts substring using input parameters | None |
| **Encrypt** | in0 (String) | out0 (String) | Encrypts using RSA-2048 | Encryption key |
| **Hash** | in0 (String) | out0 (String) | Calculates hash of input string | Hash algorithm |
| **IsEmpty** | in0 (String) | out0 (Boolean) | Checks if string is empty | None |
| **Length** | in0 (String) | out0 (Number) | Returns string length (character count) | None |
| **MultiReplace** | in0 (String) | out0 (String) | Multiple substitutions in one operation | List of search/replace pairs |
| **Pad** | in0 (String) | out0 (String) | Extends string to desired length with padding | Pad char, Length, Direction (Left/Right) |
| **Prefix-Suffix** | in0 (String) | out0 (String) | Adds text before/after string | Prefix text, Suffix text |
| **Replace** | in0 (String) | out0 (String) | Replaces substring with settings value | Search string, Replace string |
| **Split** | in0 (String) | out0 (String) | Extracts value at position from delimited string | Separator, Position index |
| **StringJoin** | in0..inN (String) | out0 (String) | Concatenates with separator | Separator character |
| **Substring** | in0 (String) | out0 (String) | Extracts substring | Start position, Length |
| **Tokenize** | in0 (String) | out1..outN (String list) | Splits into multiple outputs (1-50) | Mode: Delimiter/Fixed length; Separator; Token count |
| **Trim** | in0 (String) | out0 (String) | Removes spaces from string ends | Direction: Left/Right/Both |

**Common special cases (most string operators):** NULL input -> empty string + warning; NULL value -> empty string + warning. Contains/DynamicContains return -1 on NULL. Length returns -1 on NULL. Compare (String) returns -1 on NULL.

---

## 4. Writers

### 4.1 XML Writer

**Purpose:** Produces output XML files based on a hierarchical data schema.

**Data Structure:** Same hierarchical model as XML Reader (Root, Elements, Attributes) with additional node types:

| Node Type | Description |
|-----------|-------------|
| **Root node** | Contains all elements in the structure |
| **Shipment node** | Smallest indivisible shippable item (e.g., paper envelope, email). Must be repeatable child of Root |
| **Document node** | Single document layout/template. Must be repeatable child of Shipment |
| **Shipment ID** | Unique ID attribute; must be direct child of Shipment node. Optional for basic writing, mandatory for Document Composition schema |

**Element Types:** builtin:string (default), builtin:int, builtin:date, builtin:boolean, builtin:binary. Custom types require Classic Mode.

**Schema Tab (Element/Attribute Properties):**

| Parameter | Description |
|-----------|-------------|
| Name | Element/attribute name |
| Type | Data type from builtin list |
| Min Occurs | Minimum occurrences (0 = optional) |
| Max Occurs | Maximum (Unbounded checkbox) |
| Required | For attributes: mandatory flag |

**Settings Tab (per-node writer settings):**

| Parameter | Description |
|-----------|-------------|
| Write output as CDATA | Use CDATA section for special characters |
| Assigned variable | Assign node value to variable (useful for output filename composition) |
| Include in output | Always / Never / Only on some conditions |

**Values Tab:**
- Assign constant output values to elements
- Enable conditional output using logical expressions

**Conditional Output Logical Operators:**

| Operator | Description |
|----------|-------------|
| = | Numeric equality |
| != | Numeric inequality |
| >=, <=, >, < | Numeric comparison |
| Contains | String contains substring |
| Starts with | String starts with value |
| Ends with | String ends with value |
| Regex | Regular expression match |
| Changed | Different from previous page |
| Changed not empty | Different from previous and not empty |
| Is empty / Is not empty | Empty/non-empty check |
| Is numeric | Numeric value check |

**Boolean operators in expressions:** AND, OR, NOT, parentheses for grouping. Syntax check via CHECK link.

**Global Actions:**

| Action | Description |
|--------|-------------|
| Import structure | Import from XML, XSD, or exported DT schema |
| Download structure | Export as XML (e.g., `Writer_structure.xml`) |
| Settings | Configure general XML Writer settings |

**General Settings:**

| Parameter | Description |
|-----------|-------------|
| Indentation | None / Tab / Single space / Double space / No space |
| Scope | Description of output file purpose (reported in completion logs) |
| Add XML declaration | Include XML version/encoding declaration (default: on) |
| Preserve namespaces | Keep namespaces from imported XML |
| Schema name | View/edit data schema |
| Manage schemas | Download, rename, delete schemas |

---

### 4.2 Flat File Writer

**Purpose:** Produces output flat files (fixed-length or character-separated records).

**Data Structure:** Same hierarchical model as XML Writer (Root, Elements, Attributes) with a Document root designation.

**Element Types:** builtin:string (default), builtin:int, builtin:date, builtin:boolean, builtin:binary. Custom types require Classic Mode.

**Settings Tab (per-node writer settings):**

| Parameter | Description |
|-----------|-------------|
| Node name alias | Name for the header record |
| Enable | Enable/disable writing this node |
| Add record header | Enable header generation within a record |
| Assigned variable | Assign node value to variable |
| Custom formatting | Override general writer settings for this field |

**Custom Node Formatting:**

| Parameter | Options |
|-----------|---------|
| Alignment | Left (filler right) / Right (filler left) |
| Text delimiter | None, single quote ('), double quote (") |
| Field type: Separated | Separator: None, Tab, Pipe (\|) |
| Field type: Fixed | Length + Padding: Zero / Space |

**Values Tab:**
- Same as XML Writer: constant assignment and conditional output with logical expressions

**Global Actions:**

| Action | Description |
|--------|-------------|
| Import structure | Import from XML or XSD file |
| Download structure | Export as XML (e.g., `Writer_structure.xml`) |
| Settings | Configure general Flat File Writer settings |

**General Settings (applied to all nodes without custom settings):**

| Parameter | Options / Description |
|-----------|----------------------|
| Element alignment | Left / Right |
| Element text delimiter | None / ' / " |
| Element field type | Separated (None/Tab/Pipe) or Fixed (auto-length + Padding: Zero/Space) |
| Attribute alignment | Left / Right |
| Attribute text delimiter | None / ' / " |
| Attribute field type | Separated (None/Tab/Pipe) or Fixed (auto-length + Padding: Zero/Space) |
| Use indentation | Indentation character: None / Tab |
| Line separator | None / CR (MacOS) / LF (Unix) / CR+LF (DOS/Windows) |
| Scope | Description reported in processing logs |
| Schema name | View/edit data schema |
| Manage schemas | Download, rename, delete schemas |

---

## 5. Catalogs

**Purpose:** Lookup tables for data enrichment within Mapper transformations.

**Data Structure:**
- Column-based: each column has a Name
- Row-based: data entered in rows with values per column
- Actions: Add row, Duplicate row, Delete row

**Usage:** Referenced by the Catalog operator in the Mapper. Input key columns are matched against catalog data to retrieve corresponding values.

**Global Actions:**

| Action | Description |
|--------|-------------|
| Settings | Configure catalog resource general settings |
| Manage schemas | Download, rename, delete schemas |

---

## 6. Web Services

**Purpose:** External WSDL-based service integration within Mapper transformations.

**Constraints:**
- Only **Document/Literal wrapped** style is supported
- Only **simple objects** are supported (no complex nested structures)

**Configuration:**
- Import WSDL from URL
- Configure service address (can be changed independently of WSDL)
- Update/re-download WSDL to refresh service definition

**Usage:** Referenced by the WebService operator in the Mapper. Input parameters are mapped to service request fields; response fields are mapped to outputs.

**Global Actions:**

| Action | Description |
|--------|-------------|
| Configure web service | Import/update WSDL, change address |

---

## 7. Data Quality

**Purpose:** Legal Archive quality validation checks.

**Supported Checks (Legal Archive profile):**
- Index Consistency
- File Size validation
- Various PdV (Pacchetto di Versamento) checks

**Usage:** Referenced by the DataQuality operator in the Mapper for inline quality validation during transformation.

---

## 8. Programs and Projects

### 8.1 Project Explorer Panel

**Resource Types:**

| Type | Description |
|------|-------------|
| Readers | CSV Reader, XML Reader, Flat File Reader |
| Mappers | Data transformation mapping configurations |
| Writers | XML Writer, Flat File Writer |
| Catalogs | Lookup table resources |
| WebServices | WSDL-based external service resources |
| DataQualities | Legal Archive quality check resources |
| Unsupported | Resources from imported projects not supported in DT3 UI |

**Flows:** Auto-generated based on pipeline connections. Show the processing sequence of resources.

### 8.2 Pipeline Editor

**Features:**
- Create new resources (right-click or toolbar)
- Connect resources by dragging from output port to input port
- Disconnect resources
- Rearrange resource positions via drag-and-drop
- Zoom in/out for navigation

**Pipeline Rules:**
- Readers must connect to Mappers
- Mappers must connect to Writers
- Catalogs and WebServices are referenced by Mapper operators (not directly connected in pipeline)

### 8.3 Data Schema Management

Data schemas are shared across resources. Key behaviors:
- If a Reader and Mapper share the same schema, editing in the Mapper is locked (must edit in Reader)
- Schemas can be cloned for independent modification
- "Applied to" section shows all resources using a schema
- Changes to a shared schema affect all resources using it

**Schema Actions (available in all resource editors):**

| Action | Description |
|--------|-------------|
| Download | Export schema to local filesystem |
| Rename | Change schema name |
| Delete | Remove schema (only if not in use by any resource) |

---

## Appendix: Operator Quick Reference by Category

### Aggregation (6)
Average, Counter, Max, Min, SumIncremental, Summary

### Boolean (7)
And, Compare (Numeric), ComplexIf, Not, Or, SimpleIf, Switch

### Common (23)
AddressNormalizer, AdvancedScript, BinaryCodec, Catalog, Constant, DataQuality, DocumentInfo, Filter, GroupBy, GUIDGenerator, NodeDiff, NodeExist, NodeSelector, Parity, Progressive, ProgressiveAdvanced, Random, RowParity, Script, Sort, SystemVariable, Variable, WebService

### Date (8)
DateAdd, DateCompare, DateDiff, DateTimeInfo, FormatDate, IsDate, Now, Timestamp-Date

### Math (9)
Abs, Division, FormatNumber, IsNumeric, Mod, Multiplication, Positive, Subtract, Sum

### String (20)
Case, Compare (String), Concatenate, Contains, DynamicContains, DynamicReplace, DynamicSubstring, Encrypt, Hash, IsEmpty, Length, MultiReplace, Pad, Prefix-Suffix, Replace, Split, StringJoin, Substring, Tokenize, Trim

**Total: 73 operators across 6 categories**
