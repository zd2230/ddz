---
name: eplan-api
description: >
  EPLAN Platform API 2026 complete reference — assemblies, namespaces, classes, interfaces, actions, events, GED interactions, and XML converters. 
  Use this skill whenever the user mentions EPLAN API, EPLAN plugin/add-in development, Eplan.EplApi, EPLAN scripting, EPLAN automation, EPLAN offline application, EPLAN Electric P8 API, EPLAN Data Portal integration, EPLAN parts management API, EPLAN GED/Graphical Editor interaction, or any EPLAN-related programming task.
---

# EPLAN Platform API 2026 — Complete Knowledge Base

This skill provides a comprehensive reference for the EPLAN Platform API (version 2026.0.3). Use it whenever you need to answer questions about EPLAN development, find the right class/interface, look up actions, events, converters, or understand the API architecture.

## How To Use This Skill

The reference files contain the complete indexed knowledge. Read them as needed:

| File | Content | When to Read |
|------|---------|--------------|
| `references/assemblies.md` | All 13 assemblies with namespaces, classes, interfaces, enums | Architecture questions, finding where a class lives |
| `references/actions.md` | All 99 API actions with descriptions | "What action does X?", "How to automate Y?" |
| `references/events.md` | All 13 system events | "When does event X fire?", "How to subscribe to Y?" |
| `references/interactions-converters.md` | 5 GED interactions + 29 XML converters | GED format interactions, import/export converters |
| `references/quick-ref.md` | Cheat sheet: common patterns, key interfaces | Quick lookup during development |

## Architecture Overview

```
Eplan Platform API 2026.0.3
├── Eplan.EplApi.AFu         → Application Framework (AddIn/Action/Event/License/Scripting)
├── Eplan.EplApi.Baseu       → Base library (Exception/Settings/Coordinates/MultiLang)
├── Eplan.EplApi.DataModelu   → Core data model (Project/Page/Function/Graphics/Topology/Revisions)
├── Eplan.EplApi.EServicesu   → Electrotechnical verification + GED interactions
├── Eplan.EplApi.HEServicesu  → High-level services (backup/report/print/label/parts)
├── Eplan.EplApi.Guiu         → GUI extensions (ribbon buttons, dialogs)
├── Eplan.EplApi.MasterDatau  → Master data + parts management
├── Eplan.EplApi.RemoteClientu → Remoting client
├── Eplan.EplApi.Remotingu    → Remoting interfaces (IEplanRemoting)
├── Eplan.EplApi.Starteru     → Offline app launcher (AssemblyResolver/EplanFinder)
├── Eplan.EplApi.Systemu      → Cross-process (EplApplication)
├── Eplan.IdentityClient.Authentification → Cloud authentication
└── Eplan.IdentityClient.Types           → Cloud auth data types
```

## Key Development Patterns

### 1. Creating an Add-in (Plugin DLL)
- Implement `IEplAddIn` — exactly ONE class per DLL
- Implement `IEplAction` for each action
- Use `IEplActionEnable` to control enabled/disabled state
- Use `IEplActionChecked` for toggleable actions (0=off, 1=on, 2=indeterminate)

### 2. Script Development
- Use C# attributes from `Eplan.EplApi.Scripting` namespace
- `[DeclareAction]` — register a method as an EPLAN action
- `[Start]` — mark the entry point function
- `[DeclareEventHandler]` — subscribe to system events
- `[DeclareRegister]` / `[DeclareUnregister]` — lifecycle hooks
- `[DeclareMenu]` — add context menu items

### 3. Offline Applications
- Use `AssemblyResolver` (from Starteru) to load EPLAN API DLLs
- Call `ComHelper.InitializeComSecurity()` on main thread
- Use `EplanFinder` to locate installed EPLAN versions
- Work with `EplApplication` (from Systemu) to call EPLAN functions

### 4. Working with Projects/Data
- `Eplan.EplApi.DataModel` — all `StorableObject` subclasses
- `Project`, `Page`, `Function`, `Placement` — core types
- `Eplan.EplApi.DataModel.E3D` — 3D placement in layout space
- `Eplan.EplApi.DataModel.EObjects` — cables, terminal strips, plugs
- `Eplan.EplApi.DataModel.Planning` — pre-planning module
- `Eplan.EplApi.DataModel.Revisions` — revision management
- `Eplan.EplApi.DataModel.Topology` — routing path topology

### 5. Remoting (Inter-Process Communication)
- Server: `IRemotePostServer`, `IRemotingSynchronizer`
- Client: `Eplan.EplApi.RemoteClient` namespace
- Common: `IEplanRemoting`, `IEplanRemotingCallBack`, `CallingContext`, `EplanResponse`
- Use `EventHandlerWrapper` (not `EventHandler`) in remoting clients

### 6. License & Permissions
- `License` class → query `LicenseOptions` (Local/Network/Borrowed)
- `UserRights.CheckUserRights()` → verify action permissions
- `EplanSignedAssemblyAttribute` — required for assemblies with own license

## Loading Strategy

For most questions, start with `references/quick-ref.md`. For detailed queries, open the relevant specialized reference file. For "how does X work" or architectural questions, open `references/assemblies.md`.
