# EPLAN API — Events, Interactions & XML Converters

---

## 13 System Events

| # | Event | Description |
|---|-------|-------------|
| 1 | `Eplan.EplApi.OnMainStart` | Fired when EPLAN main application starts |
| 2 | `Eplan.EplApi.OnMainEnd` | Fired when EPLAN main application is ending |
| 3 | `Eplan.EplApi.OnPostOpenProject` | Fired after a project is opened |
| 4 | `Eplan.EplApi.OnUserPreCloseProject` | Fired before user closes a project |
| 5 | `Eplan.EplApi.OnLoadWorkspace` | Fired when a workspace is loaded |
| 6 | `Eplan.EplApi.OnResetRibbon` | Fired when ribbon is reset |
| 7 | `onActionStart.String.*` | Wildcard — fired BEFORE any action string starts |
| 8 | `onActionEnd.String.*` | Wildcard — fired AFTER any action string completes |
| 9 | `Ged.Redraw` | Fired on graphical editor redraw |
| 10 | `NCSettingsMachineTools.Redraw` | Fired on NC settings machine tools redraw |
| 11 | `Page.ConnectionDirty` | Fired when page connections become dirty |
| 12 | `Project.CablingDirty` | Fired when project cabling becomes dirty |
| 13 | `RefreshPageFilter` | Fired to refresh page filter |

### Event Subscription Pattern (C#)
```csharp
// In Add-In:
[DeclareEventHandler("Eplan.EplApi.OnPostOpenProject")]
public void OnProjectOpened(IEventParameter param)
{
    // Handle project opened
}

// Or using EventHandler class:
var handler = new EventHandler();
handler.AddEventHandler("Eplan.EplApi.OnPostOpenProject", 
    new EventHandlerFunction(MyHandlerFunction));
```

---

## 5 GED Interactions

| # | Interaction | Description |
|---|-------------|-------------|
| 1 | `XGedIaFormatDefPoints` | Format definition points in GED |
| 2 | `XGedIaFormatGraphic` | Format graphic in GED |
| 3 | `XGedIaFormatSymbol` | Format symbol in GED |
| 4 | `XGedIaFormatText` | Format text in GED |
| 5 | `XMIaInsertMacro` | Insert macro interaction |

---

## 29 XML Converters

### Device List Converters (4)
| Converter | Format |
|-----------|--------|
| `XDLCsvCommaSepImporterExporter` | CSV comma-separated |
| `XDLCsvImporterExporter` | CSV standard |
| `XDLTxtImporterExporter` | TXT |
| `XDLXmlExporter` | XML export |

### Language Database (2)
| Converter | Format |
|-----------|--------|
| `XTrLanguageDbXml2E21UnicodeTabConverter` | Language DB → E21 Unicode tab |
| `XTrLanguageDbXml2TabConverterImpl` | Language DB → tab |

### Parts List (2)
| Converter | Format |
|-----------|--------|
| `XPalCSVConverter` | CSV |
| `XPalXmlExporter` | XML export |

### Parts Management Import/Export (3)
| Converter | Format |
|-----------|--------|
| `IXPartsImportExportEdz` | EDZ format |
| `XPamExportXml` | XML export |
| `XPamImportXml` | XML import |

### Label (1)
| Converter | Format |
|-----------|--------|
| `XmlLblXmlExportConverterImpl` | Label XML export |

### PLC Data Exchange — AutomationML (11)
| Converter | Target System |
|-----------|--------------|
| `PlcDcExchangerBeckhoffTC3AML` | Beckhoff TwinCAT 3 |
| `PlcDcExchangerBoschAML` | Bosch |
| `PlcDcExchangerLogiCals3AML` | LogiCals 3 |
| `PlcDcExchangerMitsubishiAML` | Mitsubishi (generic) |
| `PlcDcExchangerMitsubishi110AML` | Mitsubishi v1.10 |
| `PlcDcExchangerOmron120AML` | Omron v1.20 |
| `PlcDcExchangerPhoenixContactAML` | Phoenix Contact |
| `PlcDcExchangerRockwellArchitectAML` | Rockwell Architect |
| `PlcDcExchangerSiemensTIA15AML` | Siemens TIA Portal V15 |
| `PlcDcExchangerSiemensTIA151AML` | Siemens TIA Portal V15.1 |
| `PlcDcExchangerSiemensTIA16AML` | Siemens TIA Portal V16 |

### PLC Data Exchange — AutomationML continued (6)
| Converter | Target System |
|-----------|--------------|
| `PlcDcExchangerSiemensTIA17AML` | Siemens TIA Portal V17 |
| `PlcDcExchangerSiemensTIA18AML` | Siemens TIA Portal V18 |
| `PlcDcExchangerSiemensTIA19AML` | Siemens TIA Portal V19 |
| `PlcDcExchangerSiemensTSTAML` | Siemens TST |
| `PlcDcExchangerGeneral` / `PlcDcAMLExchangerGeneral` | General AML exchange |

### PLC Data Exchange — XML-Based (6)
| Converter | Target System |
|-----------|--------------|
| `PlcDcXMLExchangerABB` | ABB |
| `PlcDcXMLExchangerBandR` | B&R |
| `PlcDcXmlExchangerRexroth` | Rexroth |
| `PlcDCXmlExchangerSchneider` | Schneider Electric |
| `PlcDcXMLExchangerSiemens` | Siemens (generic XML) |
| `PlcDcXMLExchangerUniversal` | Universal XML |
