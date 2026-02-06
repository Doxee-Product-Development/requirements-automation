# 09 - Administration, Security, Integration & Platform UI

> Context Bible -- compressed from 71 source files (~248KB text).
> Sources: Security Configuration Guide 6.7, Settings, Task Manager 6.7, Command Center 0.3, Third-Party Integration Guide 6.7, Doxee App for Salesforce/SAP/Microsoft Dynamics, Platform UI Documentation.

---

## 1. Security Configuration

Doxee services share common security concepts. Process Engine, Content Repository, and Task Manager all use the same authentication and user store framework. Configurations are XML-based and can be shared across services via XInclude.

### 1.1 Authentication Mechanisms Overview

| Mechanism | Scheme | User Stores | Use Case |
|-----------|--------|-------------|----------|
| Basic | `Basic` | XML, SQL, LDAP/AD | Password-based login |
| Kerberos | `Negotiate` | LDAP (required) | SSO with SPNEGO tokens |
| OpenID Connect (OIDC) | `Bearer` | OIDC provider | Standard OAuth/OIDC authentication |
| Salesforce OAuth | `Bearer` | Salesforce API | Salesforce-based authentication |
| Generic OAuth (JWT) | `Bearer` | JWT claims | Custom JWT token validation |
| Infinica Authentication | `Bearer` (JWT) | Internal key-pair | Technical service-to-service access |
| SSH Keys | `SshKeys` | N/A (SFTP only) | SFTP protocol access |

**Configuration element:** `<authentication xmlns="http://www.infinica.com/auth">` placed inside the service's `<security>` element. Only one primary mechanism is recommended per service; Infinica authentication is designed to work in parallel with any other mechanism.

### 1.2 User Stores

User stores define where Doxee fetches principal (user/group) information. Configured via `<userAccessConfiguration xmlns="http://www.infinica.com/useraccess">`.

| Store Type | Backend Element | Auth Compatibility | Notes |
|------------|----------------|-------------------|-------|
| XML | `<xml>` | Basic | File-based; test/demo only; requires restart for changes |
| Database (SQL) | `<database>` | Basic | Auto-creates schema; managed via User Management app |
| LDAP/AD | `<ldap>` | Basic, Kerberos | Full AD support; SSL, paging, active flag config |
| OIDC | `<openId>` | OIDC | User info from OIDC provider claims |
| Salesforce | `<salesforce>` | Salesforce OAuth | User/group info via Salesforce API |

**Required attribute mappings** (all stores):

| Attribute | Description |
|-----------|-------------|
| `loginName` | Unique login identifier |
| `displayName` | Display name for UI |

**Caching** (all stores): Enabled by default. Max 1000 entries, 10-minute expiry. Configurable globally or per store via `<cache enabled="true"><maximumSize>1000</maximumSize><expiry>10m</expiry></cache>`.

**Technical access:** Set `<userStore technicalAccess="true">` to always use the configured technical user for store queries instead of the current user's credentials.

### 1.3 Basic Authentication

Specifies a realm and optional charset (default UTF-8):
```xml
<authentication xmlns="http://www.infinica.com/auth">
  <basic realm="My realm" charset="UTF-8" />
</authentication>
```
Credentials: `<passwordCredentials name="..." password="..."><basicConfig charset="UTF-8" /></passwordCredentials>`

### 1.4 LDAP User Store

Connects to LDAP/AD servers. Key configuration:

| Element | Description |
|---------|-------------|
| `<server>` | LDAP URL (e.g., `ldap://localhost:389/`; use `ldaps:` for SSL) |
| `<config><baseDn>` | Root of LDAP directory tree for Doxee |
| `<loginPattern>` | Maps login names (e.g., `{login}@localhost`) |
| `<allowEmptyPasswords>` | Default `false`; AD may auth without password |
| `<technicalUser>` | Login/password for Doxee system queries |
| `<users><objectClass>` | e.g., `person` |
| `<groups><objectClass>` | e.g., `groupOfUniqueNames` |
| `<groups><memberAttribute>` | e.g., `uniqueMember` |
| `<modifiable>` | Enable write access for User Management app |
| `<ssl><trustStore>` | Path to Java keystore with server certificate |
| `<paging><defaultSize>` | Speeds up principal queries |
| `<activeConfig>` | Active/inactive flag for principals |
| `<authenticationTypes>` | `<simple />` (default) or `<kerberos .../>` |

For Kerberos on LDAP: configure `krb5File`, `serviceName`, `keyTabFile` in `<kerberos>` element. Technical user can override with `authentication="simple"`.

### 1.5 Kerberos Authentication

Wraps Kerberos credentials in SPNEGO tokens via `Negotiate` scheme. Requires LDAP user store.

Server: `<negotiate />` (relies on LDAP Kerberos settings).
Credentials: `<kerberosCredentials serviceName="..."><negotiateConfig serviceName="..." lifetime="60m" /></kerberosCredentials>`. Default token lifetime: 1 hour.

### 1.6 OpenID Connect (OIDC)

**OIDC Client for Servers** (register at OIDC provider):

| Setting | Value |
|---------|-------|
| Application type | Web |
| Response types | Code, ID Token, Token |
| Grant types | Authorization Code, Refresh Token, JWT Bearer |
| Required scopes | openid, profile, offline |

**Redirect URLs by application:**

| Application | Redirect URL |
|-------------|-------------|
| Workplace | `https://<host>/workplace/login.hbs` |
| Business Designer | `https://<host>/tdwng/login` |
| Composer | `https://<host>/infinica-composer/login` |
| Backend services | Arbitrary HTTPS URL |

**OIDC Client for Rich Clients** (Process Designer, Resource Explorer):

| Setting | Value |
|---------|-------|
| Application type | Native |
| Redirect URL | `http://localhost/infinica/auth` |
| Response types | Code |
| Grant types | Authorization Code, Refresh Token |
| Token endpoint auth | None (public client) |

**JWT Flow:** Required for non-interactive technical access. Create RSA 2048-bit key pair with `openssl`, import to JKS keystore, upload `.crt` to OIDC provider.

**OIDC Configuration XML** (`openid.xml`):
- `<providerUrl>` -- OIDC provider main endpoint
- `<clientId>`, `<clientSecret>` -- server app credentials
- `<keyStoreUrl>`, `<keyStorePassword>`, `<keyPairAlias>` -- for JWT auth
- `<tokenTimeout>` -- auto-refresh interval
- `<accessTokenIssuer>` -- override expected issuer
- Optional: `<idTokenSignatureAlg>` (default RS256), `<validateIdTokens>` (default true)
- `<groupsClaim>` in user store config -- maps OIDC claim to Doxee groups

**Authentication flows for credentials:**

| Flow | Required Fields |
|------|----------------|
| Tokens | `<tokens><accessToken>`, `<refreshToken>` |
| JWT Grant | `userId` + key store config |
| Resource Owner Password | `userId` + `password` |

### 1.7 Salesforce OAuth

Similar to OIDC but uses Salesforce-specific API. Connected apps replace OIDC clients.

**Server App** (`Doxee Servers`): Enable OAuth, scopes: basic info + api + refresh_token + openid. Callback URLs same as OIDC. Require Secret for Web Server Flow. JWT flow: upload `.crt` under digital signatures, set Permitted Users to "Admin approved users are pre-authorized", manage profiles.

**Client App** (`Doxee Design Tools`): Callback `http://localhost/infinica/auth`, deactivate Require Secret.

**Salesforce Config XML:** `<salesforceConfig xmlns="http://www.infinica.com/salesforce">` with `<salesforceInstance>`, `<organizationInstance>`, `<clientId>`, `<clientSecret>`, key store, `<tokenTimeout>`, `<apiKeepAliveTimeout>`.

### 1.8 Generic OAuth (JWT)

Validates/generates custom JWT tokens. Server config in `<oauth>`:

| Parameter | Description |
|-----------|-------------|
| `<signature>` | Public key for signature validation |
| `<decryption>` | Private key to decrypt tokens |
| `<jwkSet>` | URL to JWK set for key discovery |
| `<iss>`, `<aud>` | Expected issuer and audience |
| `<validateTimeout>` | Reject expired tokens (default true) |
| `<requiredClaims>` | Claims that must be present |
| `<validateClaims>` | Claims with required values (any/all) |
| `<groupsClaim>`, `<groupsSeparator>` | Map claims to group membership |
| `<customAttributes>` | Map claims to Doxee user attributes |

Credentials (`<oauthCredentials>`): `<signature>` (private key to sign), `<encryption>` (public key to encrypt), `<sub>` (mandatory subject), `<iss>`, `<aud>`, `<timeout>`, `<groups>`, `<customClaims>`, or a raw `<ticket>`.

### 1.9 Infinica Authentication (Service-to-Service)

Technical access between Doxee services using key-pair signed JWT tickets. Works alongside any other auth mechanism.

**Server config:** `<infinica service="..." acceptUnlistedClients="false" userNamePrefix="..." group="...">` with `<client name="..."><keys:publicKey alias="..." /></client>` entries and optional `<keys:privateKey>` for encrypted tickets.

**Credentials:** `<infinicaCredentials>` with `<client><keys:privateKey /></client>`, optional `<service><keys:publicKey /></service>`, and `<audienceSet>`.

Requires key store configuration in the application.

### 1.10 SSH Keys

SFTP-only authentication. Credentials: `<sshKeyCredentials username="..." url="..." password="..." />` where `url` points to an OpenSSH private key file.

### 1.11 Client & Technical Credentials

**Client credentials** are configured in applications that need to access other services without user interaction. Process Engine uses a credentials registry for external services. Credential types match the server's authentication mechanism.

**Technical credentials manager** (`<technicalCredentials cacheTimeout="..." maxCacheSize="...">`) caches credentials for long-running services. Each entry is named and contains credentials XML. Referenced via `<technical xmlns="http://www.infinica.com/credentials" name="..." />`. Cache timeout must be shorter than the provider's session timeout for token-based credentials.

**Current credentials** (`<currentCredentials />`): Uses the current user's credentials for downstream service calls. With `impersonation="true"`, uses the authenticating user's credentials plus impersonation info when the current user is impersonated.

**Authenticated credentials** (`<authenticatedCredentials />`): Always uses the credentials of the user who originally authenticated, without impersonation info.

### 1.12 Impersonation

Allows authenticating as user A while operating as user B, or adding groups to the authenticated subject.

**User impersonation:** Replaces user A with user B in the auth subject after successful authentication. Common for technical users operating on behalf of human users.

**Group impersonation:** Adds groups to the authenticated subject's actual groups (after user impersonation if applicable).

**Configuration:**
```xml
<impersonation enabled="true">
  <allow>
    <for>*</for>        <!-- who can impersonate (login name or group) -->
    <user>*</user>      <!-- which users can be impersonated -->
    <group>*</group>    <!-- which groups can be impersonated -->
  </allow>
</impersonation>
```

Disabled by default. Without `<allow>` entries, full impersonation is granted (security risk in production).

**HTTP headers:** `infinica-impersonate` (user), `infinica-impersonate-groups` (groups). Only works with Doxee services.

**Impersonation credentials:** Wrap actual credentials with `<impersonationCredentials user="..." live="current|authenticated"><actualCredentials>...</actualCredentials></impersonationCredentials>`.

### 1.13 Audit Logging

Supported by Content Repository, Process Engine, and Task Manager. Configured in `<security><audit><log4j>`.

**Event types logged:**
- Login success/failure
- Impersonation success/failure
- Service operations (application-specific)

**Log4j configuration elements:**

| Element | Description |
|---------|-------------|
| `<appenders>` | Log4j appenders (Console, File, etc.) |
| `<patterns>` | Message templates for each event type |
| `<levels>` | Log levels: success=info, clientError=warn, serverError=error |

**Pattern fields:** `{appName}`, `{status}`, `{message}`, `{user}`, `{impersonatedUser}`, `{resource}`, `{operation}`, `{attributes}`. Conditional output via `{:?: ...}` syntax.

**Authentication status codes:**

| Code | Meaning |
|------|---------|
| 200 | Trusted without authentication |
| 201 | Successfully authenticated |
| 202 | Trusted based on cached success |
| 401 | Invalid credentials |
| 402 | Missing credentials |
| 403 | Expired credentials |
| 404 | Account not found |
| 405 | Account expired |
| 406 | Account locked |
| 500 | Internal server error |
| 501 | Invalid configuration |
| 502 | User store access error |

**Limitations:** Malformed requests intercepted before authentication are not logged; check Tomcat access logs for those.

---

## 2. Platform Settings (RBAC)

The Settings service manages the organizational hierarchy: **Accounts > Companies > Users > Roles > Profiles**.

### 2.1 Entity Status Lifecycle

All entities share the same status flow: **Created -> Applying -> Applied -> Saved -> Failed**.

### 2.2 Accounts

Top-level organizational entity. Fields:

| Field | Mandatory | Description |
|-------|-----------|-------------|
| Account name | Yes | Alphanumeric, spaces, special chars |
| Salesforce Case | No | Linked Salesforce case number |
| Profiles | No | Associated profiles (one per type) |
| Tags | No | Up to 10 tags, max 20 chars each |

Batch and On-Demand profiles determine which tasks can be used in workflow design. Only one profile per type per account.

### 2.3 Companies

Belong to exactly one account. An account may have multiple companies.

| Field | Mandatory | Description |
|-------|-----------|-------------|
| Company name | Yes | Alphanumeric, spaces, special chars |
| Account | Yes | Parent account |
| Profiles | Conditional | Required for invoice creation (Electronic Invoicing scope) |
| Tags | No | Up to 10 tags, max 20 chars each |

### 2.4 Users

Local and SSO users. SSO users identified by `@<domain>` suffix on username. Local users cannot self-edit profiles or change passwords in current version.

| Field | Mandatory | Description |
|-------|-----------|-------------|
| Username | Yes | Unique identifier |
| Email | Yes | User email |
| First name | Yes | Given name |
| Last name | Yes | Family name |
| Localization | Yes | UI language (English or Italiano) |
| Status | Yes | Enabled or Disabled |
| Tags | No | Up to 10 tags |

**Password management:** System generates temporary passwords on user creation (CSV download). Admins can generate new temporary or permanent passwords. Cannot generate passwords for SSO users.

**Default role assignment:** Users with no roles cannot access any data on the platform.

### 2.5 Roles

Define permissions for services, dashboards, and functions. A role may be assigned to multiple users; a user may have multiple roles.

**Role configuration sections:**

| Section | Description |
|---------|-------------|
| General Information | Role name, environments, platforms, accounts, companies, dashboards |
| Services | Which platform services are available |
| Permissions | Granular per-service permissions |
| Users | Associated users (by username; includes federated SSO users) |
| Attributes | DP2-to-DP3 role mapping (`<platform_instance>-client`, `<platform_instance>-group`) |
| Tags | Up to 10 tags |

**Typical role examples:** Deployer, Editor, Batch jobs manager/viewer, On-demand jobs manager/viewer.

Home Page service is enabled by default for all roles.

### 2.6 Profiles

Associated with Accounts and Companies. Define scope-specific configurations.

| Scope | Level | Description |
|-------|-------|-------------|
| Batch Workflows | Account | Tasks available for batch workflow design |
| On-Demand Workflows | Account | Tasks available for on-demand workflow design |
| Electronic Invoicing | Company | Company data for invoice autofill |

### 2.7 Common UI Functionalities

- **Toolbar:** Pagination, filter toggle, column configuration
- **Filtering:** Add filter > set criteria > Apply. Applied filters shown above table.
- **Column customization:** Select visible columns; resizable; Reset to defaults
- **History panel:** All entity detail views show change history with status icon, timestamp, and user

---

## 3. Task Manager

Server-side component for handling tasks, required by Workplace and Process Engine. Communicates via SOAP interface.

### 3.1 System Requirements

- OpenJDK, Apache Tomcat
- Relational database and/or local filesystem for task storage
- Most JDBC-enabled databases supported

### 3.2 Installation

1. Stop Tomcat
2. Copy `infinica-task-manager.war` to `$TOMCAT/webapps`
3. Copy `infinica/` config directory to `$TOMCAT/`
4. Edit configuration files
5. Start Tomcat; check logs
6. Verify: `http://localhost:8080/infinica-task-manager/tasks`

### 3.3 Configuration (`infinica/tasks.xml`)

Main structure: `<taskManagers><taskManager>` containing `<storage>`, `<keyStores>`, `<userAccessConfiguration>`, `<security>` (with `<authentication>` and `<roles>`), `<caseSensitivePrincipals>`, `<server>`.

### 3.4 Storage Configuration

| Storage Type | Element | Config Attributes |
|-------------|---------|-------------------|
| Filesystem | `<filesystem>` | `base` (directory path) |
| SQL | `<sql>` | `url` (JDBC), `user`, `password`, `jdbcDriver`, `<properties>` |
| MongoDB | `<mongo>` | `databaseName`, `host`, `port`, `dataStoreProvider` |

Tasks must be stored in SQL. Payloads can be SQL or filesystem. Simplified config: just `<sql url="jdbc:..." />` stores everything in the database. Auto-creates tables (except Oracle sequences -- run SQL scripts manually).

### 3.5 Task Manager Roles

| Role | Permissions |
|------|------------|
| `admin` | Full permission on all operations; includes all other roles |
| `contributor` | Register task type providers (typically technical users) |
| `manager` | Technical management tasks, runtime/debug info |
| `supervisor` | Read tasks/attributes/payload, change attributes, delete tasks (global or per-task) |
| `viewer` | Read all tasks (no modification or payload access) |
| `watcher` | Query all watchers regardless of owner (typically technical users) |

Roles assigned via `<role name="..." loginName="...">` or `<role name="..."><assignment loginName="..." /></role>` for multiple principals. Prefer `loginName` over `id` for readability.

### 3.6 Key Store Configuration

Configured in `<keyStores xmlns="http://www.infinica.com/keystores" default="...">`. Each `<keyStore id="..." url="..." password="..." />` references a JKS file. Keys referenced via `<keys:publicKey alias="..." />` or `<keys:privateKey alias="..." />`.

**Auto-creation** (test/demo only): `<autoCreate enabled="true"><keyPair alias="..." algorithm="RSA" size="4096" /></autoCreate>`. Never use in production.

### 3.7 Case Sensitivity

Principal names are case-sensitive by default. Set `<caseSensitivePrincipals>false</caseSensitivePrincipals>` to disable (not recommended). MS SQL Server is always case-insensitive regardless of this setting. MySQL scripts create case-sensitive tables.

### 3.8 HTTP Probes

| Probe | Purpose | Default Timeout |
|-------|---------|----------------|
| Startup | Application startup complete | Synchronous (immediate) |
| Liveness | Application alive (DB connection test) | 30 seconds |
| Readiness | Below max capacity | 30 seconds |

Config: `<probes><startup port="..." /><liveness port="..." timeout="..." /><readiness port="..." timeout="..." /></probes>`. Probes disabled by default unless configured. Response: 204 (positive) or 503 (negative). Set `maxReadinessRequests` close to Tomcat max simultaneous requests.

---

## 4. Command Center

GUI tool for configuring Doxee environments for Hosted SaaS deployments. Produces a ZIP file for deployment.

### 4.1 Configuration Workflow

1. **Select environment:** Login at `https://cc.cloud.infinica.com/environments`, select Organization > Environment
2. **Basic information:**
   - Environment Name (alphanumeric + dashes)
   - Platform: Infinica Legacy, Infinica Cloud Platform, or Doxee Platform 3
   - Platform Version (with end-of-support date)
   - Enable/disable individual modules
3. **Environment configuration:** Customize fields (mandatory marked with asterisk). Yellow warning for unfilled mandatory fields. Blue warning for fields that changed from mandatory to optional. Override Fields toggle for per-component sub-item configuration.
4. **Summary & Export:**
   - Export as ZIP
   - Save and Deploy Changes, or Save without Deploying
   - Optional: include format for reimport, include documentation

### 4.2 Synchronize Changes

After deployment, synchronize in **ArgoCD** (accessible from Command Center home). Click Sync > select **Prune** checkbox to delete older configs > Synchronize.

### 4.3 Activate/Deactivate Environments

Toggle the **Active** option on the Command Center home page to deactivate environments (e.g., to save costs).

---

## 5. CRM Integrations

### 5.1 Doxee App for Salesforce

**Prerequisites:** Salesforce + Doxee i-Edition.

**Installation:** Obtain installation link from Doxee consultant. Log in with Salesforce admin credentials. Select audience, check acknowledgment, click Install.

**Permission Sets** (created during installation):

| Permission Set | Access Level |
|---------------|-------------|
| Doxee Setup and Administration | All features |
| Doxee Connector User | Composer and Workplace components |
| Doxee Business Designer | Business Designer component access |
| Doxee Business Designer User | Template creation in Business Designer |

Assign via Permission Sets > Manage Assignments > Add Assignments, or via user profile > Edit Assignments.

**Public Groups:** Assign users to groups matching Doxee Workplace process steps. Users must have a group assigned to log in to Workplace.

**Custom Settings** (Setup Overview > Doxee Settings):

| Setting | Description |
|---------|-------------|
| Administrator Contact Email | Contact person email |
| Process End URL | Final redirect URL after process completion |
| Business Designer Server Address | `{name}.cloud.infinica.com` domain |

**Connected App:** Enable OAuth Settings with scopes: identity URL, unique user identifiers, manage user data via APIs, perform requests at any time. Uncheck PKCE. Check Require Secret for Refresh Token Flow, Enable Authorization Code, Require Secret for Web Server Flow, Introspect all tokens. Copy Consumer Key and Consumer Secret to setup XML and send to Doxee.

**Callback URLs:**
- Workplace: `https://<host>/infinica-workplace/login.hbs`
- Business Designer: `https://<host>/infinica-business-designer/login`
- Content Repository: `https://<host>/infinica-content-repository/`
- Rich clients: `http://localhost/infinica/auth`

**Doxee Query Builder:** Create SOQL queries via graphical wizard. Access via App Launcher > Doxee Setup > Doxee Query Builder. Steps: select object > select fields > add filters/sorting > name and save query.

**Doxee Lightning Component:** Embed Doxee processes in Salesforce pages via Lightning App Builder. Drag "Doxee Workplace" component into page layout. Configure: select process, link queries (main query gets current object ID, subsequent queries chain from previous results), set display size.

### 5.2 Doxee App for SAP (Sales Cloud)

Enables document creation directly in SAP CRM with personalized CRM data. Uses Mashup feature to embed in any object entity.

**Configure Doxee Work Center:**
1. Administrator > General Settings > Custom Work Center > Add new (type: Work Center)
2. Add 3 Work Center Views: Query Builder, Business Designer, Configuration Manager
3. Assign work center to business role (General Settings > Business Roles > Edit > Work Center and View Assignments)
4. Start Adaptation on work center view pages; add Mashup for each view (Infinica Query Builder, Infinica Business Designer, Infinica Configuration Manager)
5. Configure Doxee component URLs in Configuration Manager (provided by Doxee)

**Business Designer:** Navigate to Doxee workspace > Doxee Business Designer for template design.

**Query Builder:** Map dynamic template fields to CRM data objects. New query > choose destination > select entity > select fields > optional filter/sorting > name and save. Download XML structure for template design. Use query ID for Mashup configuration.

**Configure Mashup Tab:**
- Cloud test: Administrator > Mashup Authoring > New (URL or HTML mashup). Set process name, parameter mapping, URL from BTP Cloud Foundry routes.
- Cloud development: SAP Cloud Application Studio > MashupAuthoring > right-click > new mashup.
- Configure tab: User Menu > Start Adaptation > navigate to page > Edit section > Add > link mashup (Full Width, Height 100%).

### 5.3 Doxee App for Microsoft Dynamics 365

**Installation:** Import `.zip` file at `https://make.powerapps.com` (Solutions > Import Solution). Options: Upgrade, Phase for Upgrade (patch), or Update (overwrite). Solution appears as "Doxee Workspace".

**Configuration (Doxee Document Management App):**

**iFrame Configuration:**

| Field | Description |
|-------|-------------|
| Name | Unique iFrame name |
| Process name | Path to process (relative to Content Repository root) |
| Reference | Unique name for Power Apps linking |
| Global Configuration ID | Name of Global Configuration Setup |

**Global Configuration:**

| Field | Description |
|-------|-------------|
| Base URL | Workplace URL |
| Authentication Type | Basic (username/password) or OAuth (AppId/Secret) |

**Variables:** Define any number of process variables; must match process start element inputs.

**Query Configuration:**

| Field | Mandatory | Description |
|-------|-----------|-------------|
| Name | Yes | Unique query name |
| Entity | Yes | Source object for data |
| iFrame Config ID | Yes | Linked iFrame configuration |
| Filter (Columns) | No | Select data columns |
| Filter (Criteria) | No | Influence query results |
| Linked Tables | No | Join parent/child objects |
| Query Parameters | No | Dynamic runtime variables (e.g., current object ID) |

"View Records" button shows live query results. "Save" generates Fetch XML for template dynamic data. Sample Data generates example XML for clipboard.

**Power Apps Integration:** At `https://make.powerapps.com` (main Dataverse), select table > Forms > choose form. Add 1-column tab, add text editor component to section, select table column. Under Components, add InfinicaWorkplace (from "Get more components" > "Built by others"). Set Configuration Reference to iFrame configuration reference. Save and publish.

---

## 6. Platform UI

### 6.1 Password Policy (Local Users)

| Rule | Value |
|------|-------|
| Minimum length | 12 characters |
| Uppercase letters | At least 1 |
| Lowercase letters | At least 1 |
| Numbers | At least 1 |
| Special characters | At least 1 |
| Password history | Must differ from last 24 passwords |
| Username restriction | Cannot equal username |
| Expiry | 90 days |
| Account lockout | 3 failed attempts = 15-minute block |

### 6.2 Navigation

**Navigation bar:** Doxee logo, service menu icon, current service name, tenant selector, user profile icon.

**Tenant selection:** Dropdown to switch between tenants.

**Sign out:** Via user profile icon.

### 6.3 Available Services

Services accessed via the hamburger menu. Available services depend on user permissions and licenses:

Activities, Analytics, Batch Jobs, Batch Workloads, Batch Workflows, Data Transformation 3, Digital Archiving (Stores/Portal), Documents, Home, Invoices, On-Demand Jobs, On-Demand Workflows, Repository, Settings, SMS. The "Other" section may contain custom or external (DP2) services.

### 6.4 EI-EO Services Navigation

Electronic Invoicing / Electronic Ordering services (Activities, Analytics, Documents, Invoices) have their own navigation bar variant with service menu and tenant selector.

### 6.5 Common Functionalities (Standard Services)

- **Search:** Global text search across all table fields
- **Search filters:** Column-specific filters (Batch Jobs, On-Demand Jobs views only)
- **Column configuration:** Select/reorder visible columns; Reset to defaults
- **Reload:** Refresh table data
- **Details panel:** Click element name to view details; content varies by element type

### 6.6 Common Functionalities (EI-EO Services)

**Search filter types:**

| Type | Description |
|------|-------------|
| Text | Single text string |
| List | One or more text strings |
| Multiple selection | Checkboxes |
| Amount range | Numeric From-To |
| Date | Today, Yesterday, Last week, Last month, Custom range |

Filters not applied in real-time -- click **Search** to execute.

**Table tools:**

| Tool | Description |
|------|-------------|
| Sort | By column, ascending/descending |
| Configure table | Select/reorder columns |
| View details | Open details panel |
| Reload | Refresh data |
| Export CSV | Max 100,000 records |
| Export Excel | Max 30,000 records |
| Shortcut to Analytics | View invoices in Analytics |
| Download | Download selected invoices |
| Approve/Reject | Approve or reject selected invoices |

Pre-selected columns (light blue checkbox) cannot be disabled or moved.

### 6.7 Home Page

**Dashboards widget:** Shows last 4 favorited dashboards. "ALL DASHBOARDS" button opens full view. Dashboards open in new browser tabs. Charts support hover tooltips and rectangular zoom (CTRL+Z to zoom out).

**Services widget:** Shows last 4 favorited services. "ALL SERVICES" button opens full view. Services open in new browser tabs.

---

## 7. Third-Party Integration

### 7.1 Apache FOP 2.8+

FOP 2.8+ changed PNG image embedding behavior, potentially causing PDF viewer errors. Add to FOP configuration root:
```xml
<image-loading>
  <penalty value="2000" class="org.apache.xmlgraphics.image.loader.impl.PreloaderRawPNG"/>
  <penalty value="2000" class="org.apache.xmlgraphics.image.loader.impl.ImageLoaderRawPNG"/>
</image-loading>
```

### 7.2 Oracle Database

**Automatic sequence generation** does not work correctly for Oracle. Execute matching SQL scripts before starting the application.

**Query performance (Oracle 18c+):** `select * from all_sequences` may be very slow, causing long startup times (executed multiple times by Hibernate). Mitigation:
```sql
begin
    dbms_stats.gather_dictionary_stats;
    dbms_stats.gather_fixed_objects_stats;
end;
```
