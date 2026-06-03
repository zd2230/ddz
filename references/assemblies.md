# EPLAN API — All 13 Assemblies Reference

---

## Eplan.EplApi.AFu — Application Framework

**Purpose:** Integrate API add-ins into EPLAN, react on events, work with actions.

### Namespace: `Eplan.EplApi.ApplicationFramework`

#### Classes (12):
| Class | Description |
|-------|-------------|
| **Action** | Performs a system task. Called via ribbon items or command line. Parameters via context class, return values via context. |
| **ActionCallingContext** | Pass parameters to an action and receive return values. |
| **ActionManager** | Retrieve Action objects. |
| **ActionParameterProperties** | Parameter description for documentation purposes. |
| **ActionProperties** | Returns description text and parameter list for an action. |
| **CommandLineInterpreter** | Execute commands in command-line style. |
| **EventHandler** | Base class for event handling. |
| **EventHandlerWrapper** | Processes EPLAN events in remoting clients (NOT EventHandler directly). |
| **EventManager** | Sends events. |
| **EventParameter** | Base class for event parameters. |
| **EventParameterString** | Event parameter of type System::String. |
| **License** | Query EPLAN licensing options (LicenseOptions). |
| **QuietModeStep** | Set quiet mode for a code block. |
| **UserRights** | Check execute permissions via rights management. Use CheckUserRights() method. |

#### Interfaces (14):
| Interface | Description |
|-----------|-------------|
| **IEplAddIn** ★ | MUST implement exactly one per DLL for EPLAN to load the assembly as an add-in. |
| **IEplAction** ★ | Declares an action. Implement this to register an action from an add-in. |
| **IEplActionChecked** | Toggle action state: 0=unchecked, 1=checked, 2=indeterminate. |
| **IEplActionEnable** | Enable/disable an action. Disabled → ribbon button grayed out. |
| **IActionCallingContext** | Interface for ActionCallingContext. |
| **ICommandLineInterpreter** | Internal use only. Fixed interface ID for W3u.exe generation. |
| **IEplAddInShadowCopy** | Pass original assembly location info to framework. |
| **IEplanEvents** | Interface declaration for EPLAN events. |
| **IEplanEventsWrapper** | Internal use only. |
| **IEventParameter** | Base interface for event parameters. |
| **IExtendedProcessor** | Extended processor with IXMLProcessor. |
| **IInterface** | Register a type as an EPLAN interface. |
| **IOptions** | Assign a settings dialog to the XML processor. |
| **IXMLProcessor** | Implement an XML processor. |

#### Delegates (3):
| Delegate | Description |
|----------|-------------|
| **EventHandlerFunction** | Register as event handler in EventHandler. |
| **EventHandlerNameFunction** | Same, with name parameter. |
| **EventHandlerNameFunctionResult** | Same, with name parameter and return value. |

#### Enums (3):
| Enum | Description |
|------|-------------|
| **LicenseOptions** | EPLAN licensing system options. |
| **LicenseType** | Local, Network (remote), or Borrowed. |
| **QuietModes** | Quiet mode types. |

### Namespace: `Eplan.EplApi.BaseRemoting`
**Purpose:** EPLAN Remoting base types.

**Enums:** `_kResponse`, `_SynchronizationMode`

### Namespace: `Eplan.EplApi.RemoteServer`
**Purpose:** EPLAN Remoting server.

**Classes:** `RemotingCallingContext`
**Interfaces:** `IRemotePostServer`, `IRemotingSynchronizer`

### Namespace: `Eplan.EplApi.Scripting`
**Purpose:** Attributes for scripts.

| Class (Attribute) | Purpose |
|-------------------|---------|
| **DeclareAction** | Mark a method → registered as EPLAN action. string parameters → action parameters. |
| **DeclareEventHandler** | Mark a function to respond to system events. |
| **DeclareMenu** | Declare a function that adds context menu items. |
| **DeclareRegister** | Called when a new script is loaded into P8. |
| **DeclareUnregister** | Called when a script is unloaded from P8. |
| **Start** | Entry point function. Called when script runs. Can have parameters. |

---

## Eplan.EplApi.Baseu — Base Library

### Namespace: `Eplan.EplApi.Base`
**Purpose:** Base functionality — exceptions, settings, coordinates, multi-language, unit parsing.

#### Classes (25):
| Class | Description |
|-------|-------------|
| **BaseException** | Base class for all API exceptions (derived from ApplicationException). |
| **Context** | Passes environment state and parameters to registered objects. |
| **ContextParameterBlock** | Parameter block supporting System.Object parameters. |
| **Decider** | Standard EPLAN decider dialog. |
| **EplAssert** | Assert class; writes to epllog.txt in advanced mode; debugger break via registry. |
| **EplTrace** | Trace output to EplLog.txt (debug + release). |
| **FileSelectDecisionContext** | Decider helper for file selection. |
| **ISOCode** | Language code management; used by MultiLangString. |
| **LanguageList** | List of languages. |
| **Languages** | Language information. |
| **ListSelectDecisionContext** | Decider helper for list selection. |
| **LockingException** | Exception for DataModel locking errors. |
| **MultiLangString** | Stores strings in multiple languages simultaneously. |
| **ParserParameter** | Configures unit parser (unit + result formatting). |
| **PathMap** | Processes EPLAN path variable strings. |
| **Progress** | Access to EPLAN progress bar. |
| **ProgressFactory** | For offline apps: RegisterProgress/UnregisterProgress. |
| **Range** | Range of setting values. |
| **SchemeSetting** | Edit settings grouped into schemes. |
| **SettingNode** | Iterate settings tree; delete nodes. |
| **Settings** | Persistent settings (like registry); unique IDs, values/lists, grouping. |
| **SysMessagesCollection** | System-wide message tree; contains BaseException objects. |
| **SysMessagesEnumerator** | Enumerates SysMessagesCollection. |
| **TraceListener** | Outputs trace to system message management + log file. |
| **UnitParser** | Read units from strings; convert between units of same group. |

#### Interfaces (3): `IContext`, `IEplProgress`, `ISettings`

#### Structs (3):
| Struct | Description |
|--------|-------------|
| **PointD** | 2D coordinates. |
| **PointD3D** | 3D coordinates. |
| **RectangleD** | Area in coordinate space. |

#### Enums (9):
`EnumDecisionIcon`, `EnumDecisionReturn`, `EnumDecisionType`, `ISettings.CreationFlag`, `ISettings.SettingType`, `ISOCode.Language`, `MessageLevel`, `Unit`, `UnitGroup`

---

## Eplan.EplApi.DataModelu — Core Data Model

### Namespaces (10):

| Namespace | Content |
|-----------|---------|
| **Eplan.EplApi.DataModel** | Core: Project, Page, Function, Placement (all derive from StorableObject). |
| **Eplan.EplApi.DataModel.E3D** | 3D placements in layout space. |
| **Eplan.EplApi.DataModel.EObjects** | Special items: cables, terminal strips, plugs. |
| **Eplan.EplApi.DataModel.Filters** | Filter classes for functions, pages. |
| **Eplan.EplApi.DataModel.Graphics** | Graphical items: lines, circles, images, texts. |
| **Eplan.EplApi.DataModel.Helpers** | Helper classes. |
| **Eplan.EplApi.DataModel.MasterData** | SymbolLibrary, Symbol, FunctionDefinitionLibrary, WindowMacro. |
| **Eplan.EplApi.DataModel.Planning** | Pre-planning module classes. |
| **Eplan.EplApi.DataModel.Revisions** | Objects created by revisions. |
| **Eplan.EplApi.DataModel.Topology** | Topology routing paths. |

---

## Eplan.EplApi.EServicesu — Electrotechnical Services

| Namespace | Content |
|-----------|---------|
| **Eplan.EplApi.EServices** | Electrotechnical messages and verifications. |
| **Eplan.EplApi.EServices.Ged** | Custom GED interaction implementations. |

---

## Eplan.EplApi.HEServicesu — Higher Services

| Namespace | Content |
|-----------|---------|
| **Eplan.EplApi.HEServices** | Project backups, master data backup, report creation, printing, labeling, parts management. |
| **Eplan.EplApi.HEServices.Exceptions** | All HEServices exception classes. |

---

## Eplan.EplApi.Guiu — GUI Extensions

| Namespace | Content |
|-----------|---------|
| **Eplan.EplApi.Gui** | Ribbon buttons, UI extension points. |

---

## Eplan.EplApi.MasterDatau — Master Data

| Namespace | Content |
|-----------|---------|
| **Eplan.EplApi.MasterData** | Parts management, master data operations. |

---

## Eplan.EplApi.RemoteClientu — Remoting Client

| Namespace | Content |
|-----------|---------|
| **Eplan.EplApi.RemoteClient** | EPLAN Remoting client. |

---

## Eplan.EplApi.Remotingu — Remoting Common

| Class/Interface | Description |
|----------------|-------------|
| **CallingContext** | EPLAN server calling context. |
| **EplanResponse** | EPLAN server response. |
| **IEplanRemoting** | EPLAN communication interface. |
| **IEplanRemotingCallBack** | Callback to send response to client. |

---

## Eplan.EplApi.Starteru — Offline App Starter

| Class | Description |
|-------|-------------|
| **AssemblyResolver** | Resolve and load EPLAN API DLLs from bin path. |
| **ComHelper** | Initialize DCOM security for ELM (call on main thread). |
| **EplanFinder** | Find matching installed EPLAN version. |
| **EplanSignedAssemblyAttribute** | Attribute for EPLAN assemblies with own license. |
| **SelectEplanDialog** | Dialog to select EPLAN installation. |
| **EplanData** (struct) | All info about an EPLAN installation. |

---

## Eplan.EplApi.Systemu — Cross-Process

| Class | Description |
|-------|-------------|
| **EplApplication** | Use EPLAN functions in other processes. |

Enums: `LicenseRuntimeCheckCommands`, `LicenseRuntimeCheckModes`, `PartsDatabaseItemType`, `QuietModes`

---

## Eplan.IdentityClient.Authentification

| Namespace | Key Items |
|-----------|-----------|
| **Eplan.IdentityClient** | `EplanCloudResourceDeprecationArgs` |
| **Eplan.IdentityClient.Authentification** | `ProductInfo`, `IEIdentityClient` |

---

## Eplan.IdentityClient.Types

| Namespace | Key Items |
|-----------|-----------|
| **Eplan.IdentityClient** | `AuthenticationData`, `EProxySettings`, `IdentityClientResponse` |
| Enums: | `ApplicationMode`, `IdentityStatusCode` |
