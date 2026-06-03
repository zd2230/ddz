# EPLAN API — Quick Reference Card

##   Key Interfaces (Must-Know)

| Interface | Assembly | Purpose |
|-----------|----------|---------|
| **IEplAddIn** | Eplan.EplApi.AFu | Entry point: exactly 1 per DLL |
| **IEplAction** | Eplan.EplApi.AFu | Register an action |
| **IEplActionEnable** | Eplan.EplApi.AFu | Enable/disable action |
| **IEplActionChecked** | Eplan.EplApi.AFu | Toggle action (0=off, 1=on, 2=indeterminate) |
| **IEplRemoting** | Eplan.EplApi.Remotingu | Remoting communication |

##   Script Attributes

| Attribute | When it fires |
|-----------|---------------|
| `[Start]` | Script entry point |
| `[DeclareAction]` | Register method as action |
| `[DeclareEventHandler("EventName")]` | Subscribe to event |
| `[DeclareRegister]` | Script loaded into P8 |
| `[DeclareUnregister]` | Script removed from P8 |
| `[DeclareMenu]` | Add context menu items |

##   13 System Events Summary

| Category | Events |
|----------|--------|
| App Lifecycle | `OnMainStart`, `OnMainEnd` |
| Project Lifecycle | `OnPostOpenProject`, `OnUserPreCloseProject` |
| UI | `OnLoadWorkspace`, `OnResetRibbon` |
| Action Hooks | `onActionStart.String.*`, `onActionEnd.String.*` |
| Editor | `Ged.Redraw`, `NCSettingsMachineTools.Redraw` |
| Data Dirty | `Page.ConnectionDirty`, `Project.CablingDirty`, `RefreshPageFilter` |

##   Layer Architecture

```
Layer 5: Cloud       → IdentityClient (Authentification + Types)
Layer 4: UI          → Guiu (ribbon buttons)
Layer 3: Logic       → HEServicesu (backup/report/print/label)
                        EServicesu (verification/GED)
Layer 2: Data        → DataModelu (project/page/function/3D/graphics)
                        MasterDatau (parts management)
Layer 1: Foundation  → AFu (add-in framework/actions/events)
                        Baseu (settings/coordinates/multilang/exceptions)
Layer 0: Startup     → Starteru (offline apps)
                        Systemu (cross-process EplApplication)
                        Remotingu/RemoteClientu (inter-process communication)
```

##   Common Task → Right Assembly

| Task | Assembly |
|------|----------|
| Create an EPLAN plugin DLL | Eplan.EplApi.AFu |
| Write a C# script | Eplan.EplApi.AFu (Scripting) |
| Access project/page data | Eplan.EplApi.DataModelu |
| Place macros | Eplan.EplApi.DataModelu |
| Generate reports | Eplan.EplApi.HEServicesu |
| Export/import projects | Use Actions: `import`/`export` |
| Add ribbon buttons | Eplan.EplApi.Guiu |
| Query/modify settings | Eplan.EplApi.Baseu (Settings) |
| Multi-language text | Eplan.EplApi.Baseu (MultiLangString) |
| Unit conversion | Eplan.EplApi.Baseu (UnitParser) |
| Offline application | Eplan.EplApi.Starteru + Systemu |
| Remoting client | Eplan.EplApi.RemoteClientu |
| 3D layout space | Eplan.EplApi.DataModelu (E3D namespace) |
| Cable/terminal management | Eplan.EplApi.DataModelu (EObjects) |
| License check | Eplan.EplApi.AFu (License) |
| Permission check | Eplan.EplApi.AFu (UserRights) |
| Cloud authentication | Eplan.IdentityClient.* |
| PLC data exchange | Actions: `plcservice` + XML Converters |
| Label printing | Actions: `label` + Label XML converter |

##   Top 10 Most Common Actions

| # | Action | What it does |
|---|--------|-------------|
| 1 | `import` | Import projects/macros/drawings |
| 2 | `export` | Export pages/projects (DXF/DWG/PDF) |
| 3 | `print` | Print projects and pages |
| 4 | `reports` | Update all project evaluations |
| 5 | `check` | Run project check |
| 6 | `backup` / `restore` | Backup/restore project + master data |
| 7 | `generate` | Generate connections and cables |
| 8 | `renumber` | Renumbering/DT assignment |
| 9 | `translate` | Translation + missing words export |
| 10 | `label` | Create labels |
