# EPLAN API — All 99 Actions

## Project Management (12)

| Action | Description |
|--------|-------------|
| `backup` | Back up project and master data (forms, symbols) to disk |
| `restore` | Restore projects and master data |
| `compress` | Compress projects |
| `check` | Check a project and check pages |
| `synchronize` | Synchronize project data |
| `ProjectOpen` | Opens given project |
| `ProjectAction` | Runs an action on a given project, closes project afterwards |
| `projectmanagement` | Project management operations |
| `SwitchProjectType` | Change type of project |
| `SetProjectLanguage` | Sets project languages |
| `XPrjActionUpgradeProjects` | Upgrades projects to actual database scheme version |
| `XPrjConvertBaseProjectsAction` | Converts old basic projects (.ept/.epb) to new (.zw9) |

## Import / Export (18)

| Action | Description |
|--------|-------------|
| `import` | Import projects, macros, and drawings |
| `export` | Export pages/projects in graphical, DXF, DWG, PXF format |
| `import3d` | Import 3D data |
| `export3d` | Export installation spaces into 3D formats |
| `exportToGraphics` | Export pages/projects to TIF, GIF, PNG, JPG |
| `ExportNCData` | Exports NC Data for machines |
| `ExportProductionWiring` | Export Production Wiring Data for machines |
| `ExportSegmentsTemplate` | Export segment templates to file |
| `ImportSegmentsTemplate` | Import segment templates from file to project |
| `subprojects` | Export and import subprojects |
| `plcservice` | Exports/imports PLC data using specified converter |
| `devicelist` | Import, export, and delete device lists |
| `partslist` | Export/import parts and parts management items |
| `partsmanagementapi` | Export/import parts and parts management items |
| `translate` | Translate a project, export missing translations, remove languages |
| `masterdata` | Operations related to EPLAN master data |
| `ImportPrePlanningData` | Import pre-planning data |
| `XMDeleteReprTypeAction` | Removes representation type from macros |

## Settings & Customizing (10)

| Action | Description |
|--------|-------------|
| `XSettingsExport` | Exports settings to XML file |
| `XSettingsImport` | Imports project/station/company/user settings from XML |
| `XSettingsRegisterAction` | Registers Add-ons |
| `XSettingsUnregisterAction` | Unregistration of Add-ons |
| `XAfActionSetting` | Sets the value of a setting |
| `XAfActionSettingProject` | Sets the value of a project setting |
| `MfExportRibbonBarAction` | Exports main ribbon bar customizing to XML |
| `MfImportRibbonBarAction` | Imports main ribbon bar customizing from XML |
| `SaveWorkspaceAction` | Saves/creates specified workspace |
| `OpenWorkspaceAction` | Opens an existing workspace |

## Property Operations (8)

| Action | Description |
|--------|-------------|
| `XEsGetPropertyAction` | Gets selected objects and gets the property |
| `XEsSetPropertyAction` | Gets selected objects and sets the property |
| `XEsGetPagePropertyAction` | Gets special property of first selected page |
| `XEsSetPagePropertyAction` | Sets special property of selected pages |
| `XEsGetProjectPropertyAction` | Gets special property of current project |
| `XEsSetProjectPropertyAction` | Sets special property of current project |
| `XEsUserPropertiesExportAction` | Exports user properties to file |
| `XEsUserPropertiesImportAction` | Imports user properties to project from file |

## Data Export/Import (8)

| Action | Description |
|--------|-------------|
| `XMExportConnectionsAction` | Export connections of a project |
| `XMExportFunctionAction` | Export functions of a project |
| `XMExportLocationBoxesAction` | Export location boxes of a project |
| `XMExportPagesAction` | Export pages of a project |
| `XMExportPipeLineDefsAction` | Export pipeline definitions of a project |
| `XMExportPotentialDefsAction` | Export potential definitions of a project |
| `XMImportDCArticleDataAction` | Imports data configuration into EPLAN article database |
| `XMActionDCImport` | Imports data configuration file into EPLAN project |

## Macros (5)

| Action | Description |
|--------|-------------|
| `generatemacros` | Generate macros from project |
| `preparemacros` | Prepare project for macro generation |
| `XGedUpdateMacroAction` | Updates macros (opens/closes project automatically if needed) |
| `XMIaInsertMacro` | Insert macro (via GED interaction) |
| `XMActionDCCommonExport` | Starts export for external editing |

## AutomationML / Manufacturer-Specific (4)

| Action | Description |
|--------|-------------|
| `XAMlExportProductionData2RASCenterAction` | Export construction spaces to AutomationML for Rittal RiPanel Processing Center |
| `XAMlExportProductionData2SmartMountingAction` | Export construction spaces to AutomationML for Rittal RiPanel |
| `PlcDcAMLExchangerGeneral` | General AutomationML PLC exchange |
| `RegisterCustomPropertyEditorAction` | Registers/unregisters a custom editor dialog for a property |

## PLC / Parts / Devices (10)

| Action | Description |
|--------|-------------|
| `XPamConvertPartDatabaseToArticleDatabaseAction` | Converts parts databases from V2.9 to V2022 |
| `XPamsDeviceSelectionAction` | Selects device or updates device information |
| `XPamSelectPart` | Starts part selection (configured database) |
| `XPartsSetDataSourceAction` | Changes parts management database type setting |
| `XDLInsertDeviceAction` | Starts interaction for inserting a device |
| `XEGActionInsertSymRef` | Find symbol references for inserting |
| `XPlaUpdateDetailAction` | Updates detail engineering for selected planning objects |
| `XCCreateGravingtextAction` | Generates engraving text from cable DTs (VASS standard) |
| `XCMRemoveUnnecessaryNDPsAction` | Removes unnecessary net definition points |
| `XCMUniteNetDefinitionPointsAction` | Unites net definition points on same net |

## Graphical / Wiring / Cable (9)

| Action | Description |
|--------|-------------|
| `XCabCalculateEnclosureTotalWeightAction` | Calculates total cabinet weight |
| `InsertModelViewAction` | Insert model view object on a page |
| `Topology` | Topology-related operations |
| `UpdateSegmentsFilling` | Calculates CABLINGSEGMENT_FILLING for all segments |
| `generate` | Generate connections and generate cables |
| `changelayer` | Changes graphical layer properties |
| `graphicallayertable` | Import/export graphical layer table |
| `EsCorrectConnections` | Merges graphical properties into one signal definition point per signal |
| `CleanWorkspaceAction` | Cleans an existing workspace |

## Other Actions (10)

| Action | Description |
|--------|-------------|
| `edit` | Opens a project/page/device, can set cursor at X/Y coordinates |
| `search` | Search items in a project |
| `label` | Create labels for projects |
| `print` | Print projects and pages |
| `reports` | Update all project evaluations |
| `renumber` | Numbering functionality |
| `selectionset` | Get current project, selected projects, selected pages |
| `navigateToEEC` | Navigate to an object in the EPLAN Engineering Configuration |
| `gedRedraw` | GED redraw |
| `XSDPreviewAction` | Opens/closes preview of a project page or macro |

## Script-Related (4)

| Action | Description |
|--------|-------------|
| `ExecuteScript` | Runs the given script |
| `RegisterScript` | Register a script |
| `UnregisterScript` | Unregisters a script |
| `EplApiModuleAction` | Loads and registers an API Add-in |

## GED Interaction Actions (2)

| Action | Description |
|--------|-------------|
| `XGedClosePage` | Closes all selected pages |
| `XGedStartInteractionAction` | Starts an interaction of the graphical editor |
