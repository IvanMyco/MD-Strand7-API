---
title: "Import-Export Utilities"
source: "Strand7 R246 API Manual"
pages: 78–96
---

# Import-Export Utilities

Output Parameters

DispScale
The scaling factor or percentage applied.

ScaleType
The manner of scaling used, either dsPercent or dsAbsolute.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError


## Import/Export Utilities


Import/Export Utilities


---

### `St7ImportST7File`

Imports a specified Strand7 text file format model.

**Syntax**

```c
long St7ImportST7File(long uID, char* FileName, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the Strand7 text-file to be imported.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportIGESFile`

Imports a geometry file in IGES format.

**Syntax**

```c
long St7ImportIGESFile(long uID, char* FileName, long*
Integers, double* Doubles, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the IGES file to be imported.
- `Integers[0..6]` — [ipImportGeomProp] - Default property ID number. [ipImportGeomCurvesToBeams] - Convert unreferenced curves to beam elements, either btTrue or btFalse. [ipImportGeomGroupsAs] - Geometry groups import, one of ggNone, ggAuto, ggSubfigures or ggLevels. [ipImportGeomColourAsProperty] - Import geometry colour definitions as property definitions, either btTrue or btFalse. [ipImportGeomBlackReplacement] - Black replacement colour as a 32 bit RGB value. [ipImportGeomLengthUnit] - specifies a length unit for the import file, one of luGeomNONE, luGeomINCH, luGeomMILLIMETRE, luGeomFEET, luGeomMILES, luGeomMETRE, luGeomKILOMETRE, luGeomMIL, luGeomMICRON, luGeomCENTIMETRE, luGeomMICROINCH, or
- `luGeomUNSPECIFIED` — 
- `Doubles[0..0]` — [ipImportGeomTol] - Relative tolerance used when importing geometry.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportACISFile`

Imports a geometry file in the ACIS format.


Import/Export Utilities

**Syntax**

```c
long St7ImportACISFile(long uID, char* FileName, long*
Integers, double* Doubles, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the ACIS file to be imported.
- `Integers[0..6]` — [ipImportGeomProp] - Default property ID number. [ipImportGeomACISBodiesAsGroups] - Imports ACIS bodies as groups, either btTrue or btFalse. [ipImportGeomCurvesToBeams] - Imports unused curves as beams, either btTrue or btFalse. [ipImportGeomLengthUnit] - specifies a length unit for the import file, one of luGeomNONE, luGeomINCH, luGeomMILLIMETRE, luGeomFEET, luGeomMILES, luGeomMETRE, luGeomKILOMETRE, luGeomMIL, luGeomMICRON, luGeomCENTIMETRE, luGeomMICROINCH, or
- `luGeomUNSPECIFIED` — 
- `Doubles[0..0]` — [ipImportGeomTol] - Relative tolerance used when importing geometry.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportSTEPFile`

Imports a geometry file in the STEP format.

**Syntax**

```c
long St7ImportSTEPFile(long uID, char* FileName, long*
Integers, double* Doubles, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the STEP file to be imported.
- `Integers[0..6]` — [ipImportGeomProp] - Default property ID number. [ipImportGeomBlackReplacement] - Black replacement colour as a 32 bit RGB value. [ipImportGeomColourAsProperty] - Use the geometry colours as property definitions, either btTrue or btFalse. [ipImportGeomGroupsAs] - Geometry groups import, either ggNone or ggAssemblies. [ipImportGeomLengthUnit] - specifies a length unit for the import file, one of luGeomNONE, luGeomINCH, luGeomMILLIMETRE, luGeomFEET, luGeomMILES, luGeomMETRE, luGeomKILOMETRE, luGeomMIL, luGeomMICRON, luGeomCENTIMETRE, luGeomMICROINCH, or
- `luGeomUNSPECIFIED` — 
- `Doubles[0..0]` — [ipImportGeomTol] - Relative tolerance used when importing geometry.
- `Mode` — Controls the display of a progress bar (ieQuietRun or ieProgressRun).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen


Import/Export Utilities
```


---

### `St7ImportST6BinaryFile`

Imports a Strand6 model in the binary file format.

**Syntax**

```c
long St7ImportST6BinaryFile(long uID, char* FileName, long
Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the Strand6 file to be imported.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportST6TextFile`

Imports a Strand6 model in the text file format.

**Syntax**

```c
long St7ImportST6TextFile(long uID, char* FileName, long
Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the Strand6 file to be imported.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportDXFFile`

Imports a geometry file in the DXF format.

**Syntax**

```c
long St7ImportDXFFile(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the DXF file to be imported.
- `Integers[0..5]` — [ipDXFImportFrozenLayers] - Import frozen layers, either btTrue or btFalse. [ipDXFImportLayersAsGroups] - Import geometry layers as groups, either btTrue or btFalse. [ipDXFImportColoursAsProps] - Use geometry colours as property definitions, either btTrue or btFalse. [ipDXFImportPolylineAsPlates] - Import polyline definitions as plate elements, either btTrue or btFalse. [ipDXFImportPolygonAsBricks] - Import polygon definitions as brick elements, either btTrue or btFalse. Import/Export Utilities [ipDXFImportSegmentsPerCircle] - Number of line segments used to discretise curves.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportSTLFile`

Imports a stereo-lithography file.

**Syntax**

```c
long St7ImportSTLFile(long uID, char* FileName, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the STL file to be imported.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportNASTRANFile`

Imports a NASTRAN model file.

**Syntax**

```c
long St7ImportNASTRANFile(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the NASTRAN file to be imported.
- `Integers[0..0]` — [ipNASTRANImportUnits] - Nastran file units, one of naUnits_kg_N_m , naUnits_T_N_mm, naUnits_sl_lbf_ft, naUnits_lbm_lbf_in, naUnits_sl_lbf_in or naUnits_NoUnits.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ImportANSYSFile`

Imports an ANSYS model file.

**Syntax**

```c
long St7ImportANSYSFile(long uID, char* FileName, char*
LoadCaseFilePath, long* Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the ANSYS file to be imported. Import/Export Utilities
- `LoadCaseFilePath` — Full path to the directory containing the load case data for the ANSYS file.
- `Integers[0..5]` — [ipANSYSImportFormat] - Import format, one of ieANSYSBatchImport, ieANSYSCDBImport or ieANSYSBatchCDBImport. [ipANSYSArrayParameters] Array parameter type, one of ieANSYSArrayOverwrite, ieANSYSArrayPrompt or ieANSYSArrayIgnore. [ipANSYSImportLoadCaseFiles] - Import additional load case files, either btTrue or btFalse. [ipANSYSImportIGESEntities] - Import IGES geometry definitions, either btTrue or btFalse. [ipANSYSFixElementConnectivity] - Fix element connectivity, either btTrue or btFalse. [ipANSYSRemoveDuplicateProps] - Remove duplicate property definitions, either btTrue or btFalse.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidAnsysArrayStatus, ERR7_InvalidAnsysImportFormat,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_InvalidLoadCaseFilePath, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7ImportSTAADFile`

Imports a STAAD model file.

**Syntax**

```c
long St7ImportSTAADFile(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the STAAD file to be imported.
- `Integers[0..5]` — [ipSTAADCountryType] - Default country type, one of ieSTAADAmericanCode, ieSTAADAustralianCode or ieSTAADBritishCode. [ipSTAADIncludeSectionLibrary] - Search additional beam crosssection libraries, either btTrue or btFalse. [ipSTAADStripUnderscore] - Remove underscore from group names, either btTrue or btFalse. [ipSTAADStripSectionSpaces] - Remove spaces from section names, either btTrue or btFalse. [ipSTAADLengthUnit] - Length unit, one of sdLengthUnit_in, sdLengthUnit_ft, sdLengthUnit_cm, sdLengthUnit_m, sdLengthUnit_mm, sdLengthUnit_dm or sdLengthUnit_km. [ipSTAADForceUnit] - Force unit, one of sdForceUnit_kip, sdForceUnit_lbf, sdForceUnit_kgf, sdForceUnit_MTf, sdForceUnit_N, sdForceUnit_kN, sdForceUnit_MN or sdForceUnit_dN.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_InvalidStaadCountryCodeOption,
ERR7_InvalidStaadForceUnit, ERR7_InvalidStaadLengthUnit,
ERR7_NoError, ERR7_ResultFileIsOpen


Import/Export Utilities
```


---

### `St7ImportSAP2000File`

Imports a SAP2000 model file.

**Syntax**

```c
long St7ImportSAP2000File(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the SAP2000 file to be imported.
- `Integers[0..3]` — [ipSAP2000ConvertBlackTo] - Black replacement colour as a 32 bit RGB value. [ipSAP2000DecimalSeparator] - Decimal character, either ieSAP2000Period or ieSAP2000Comma. [ipSAP2000ThousandSeparator] - Thousands character, one of ieSAP2000Period, ieSAP2000Comma, ieSAP2000Space or ieSAP2000None. [ipSAP2000MergeDuplicateFreedomSets] - Merges duplicate freedom sets in the imported file, either btTrue or btFalse.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotReadImportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ExportImageFile`

Exports the Strand7 graphics as an image file.

**Syntax**

```c
long St7ExportImageFile(long uID, char* FileName, long
ImageType, long Width, long Height)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the image file to be created.
- `ImageType` — Type of image file generated, one of itBitmap8Bit, itBitmap16Bit, itBitmap24Bit or itJPEG.
- `Width` — Pixel width for the image.
- `Height` — Pixel height for the image.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotSaveImageFile, ERR7_CantDoWithModalWindows,
ERR7_FileNotOpen, ERR7_InsufficientRamToCreateImage,
ERR7_InvalidFileName, ERR7_InvalidFileUnit,
ERR7_InvalidImageDimensions, ERR7_InvalidImageType,
ERR7_ModelWindowWasNotCreated,
ERR7_ModelWindowWasNotShowing, ERR7_NoError
```


---

### `St7ExportST7File`

Exports the current model in the Strand7 text file format.


Import/Export Utilities

**Syntax**

```c
long St7ExportST7File(long uID, char* FileName, long Mode,
long ExportFormat)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the Strand7 text-file to be created.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.
- `ExportFormat` — Controls the export format for backwards compatibility, one of ieSt7ExportCurrent, ieSt7Export106, ieSt7Export21x, ieSt7Export22x or ieSt7Export23x.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotWriteExportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_InvalidSt7ExportFormat, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7ExportIGESFile`

Exports the current Strand7 geometry as an IGES format geometry file.

**Syntax**

```c
long St7ExportIGESFile(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the IGES file to be created.
- `Integers[0..6]` — [ipExportGeomColour] - Export colours, one of ieFaceColour, ieGroupColour or iePropertyColour. [ipExportGeomFullGroupPath] - Export the full group definition, either btTrue or btFalse. [ipExportGeomGroupsAsLevels] - Export the groups as levels, either btTrue or btFalse. [ipExportGeomFormatProtocol] - Export format, one of ifBoundedSurface, ifTrimmedParametricSurface, ifOpenShell or ifManifoldSolidBRep. [ipExportGeomPeriodicFace] - Periodic face control one of ieSeamOnlyAsRequired, ieSplitOnFaceBoundary or ieSplitIntoHalves. [ipExportGeomKeepAnalytic] - Export the analytic geometry definitions, either btTrue or btFalse.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotWriteExportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidGeometryFormatProtocol,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ExportSTEPFile`

Exports the current Strand7 geometry as a STEP format geometry file.

**Syntax**

```c
long St7ExportSTEPFile(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Import/Export Utilities Strand7 model file ID number.
- `FileName` — Full path and name for the STEP file to be created.
- `Integers[0..6]` — [ipExportGeomColour] - Export colours, one of ieFaceColour, ieGroupColour or iePropertyColour. [ipExportGeomFullGroupPath] - Export the full group definition, either btTrue or btFalse. [ipExportGeomGroupsAsLevels] - Export the groups as levels, either btTrue or btFalse. [ipExportGeomFormatProtocol] - Export format, either spConfigControlDesign or spAutomotiveDesign. [ipExportGeomPeriodicFace] - Periodic face control one of ieSeamOnlyAsRequired, ieSplitOnFaceBoundary or ieSplitIntoHalves. [ipExportGeomKeepAnalytic] - Export the analytic geometry definitions, either btTrue or btFalse.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotWriteExportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidGeometryFormatProtocol,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ExportDXFFile`

Exports the current Strand7 geometry as a DXF format geometry file.

**Syntax**

```c
long St7ExportDXFFile(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the DXF file to be created.
- `Integers[0..4]` — [ipDXFExportPlatesBricks3DFaces] - Export plates and bricks as AutoCAD 3D faces, either btTrue or btFalse. [ipDXFExportGroupsAsLayers] - Export groups as AutoCAD layers, either btTrue or btFalse. [ipDXFExportPropColoursAsEntityColours] - Export property colours as AutoCAD entity colours, either btTrue or btFalse. [ipDXFExportBeamsAs] - Beam element export, one of bmLine, bmSection or bmSolid. [ipDXFExportPlatesAs] - Plate element export, either plSurface or plSolid.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotWriteExportFile, ERR7_FileNotOpen,
ERR7_InvalidDXFBeamOption, ERR7_InvalidDXFPlateOption,
ERR7_InvalidFileUnit, ERR7_InvalidImportExportMode,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ExportNASTRANFile`

Exports the current Strand7 model as a NASTRAN model file.

**Syntax**

```c
long St7ExportNASTRANFile(long uID, char* FileName, long*
Integers, double* Doubles, long Mode)


Import/Export Utilities
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the NASTRAN file to be created.
- `Integers[0..9]` — [ipNASTRANFreedomCase] - Exported freedom case. [ipNASTRANLoadCase] - Exported load case for non-structural mass attributes. [ipNASTRANSolver] - Nastran solver type, one of ieNASTRANSolverLSA, ieNASTRANSolverNFA or ieNASTRANSolverLBA. [ipNASTRANExportUnits] - Units for exported file, one of naUnits_kg_N_m, naUnits_T_N_mm, naUnits_sl_lbf_ft, naUnits_lbm_lbf_in, naUnits_sl_lbf_in or naUnits_NoUnits. [ipNASTRANBeamStressSections] - Number of sections defined for exported beam elements. [ipNASTRANBeamSectionGeometry] - Export beam section geometry, either ieNASTRANExportGeometryProps or ieNASTRANExportPropsOnly. [ipNASTRANExportHeatTransfer] - Export heat transfer property data, either btTrue or btFalse. [ipNASTRANExportNSMass] - Export non-structural mass attributes, either btTrue or btFalse. [ipNASTRANExportUnusedProps] - Export unreferenced material properties, either btTrue or btFalse. [ipNASTRANTemperatureCase] - Load case from which reference temperature is exported.
- `Doubles[0..0]` — [ipNASTRANExportZeroFields] - Zero tolerance. Parameters with magnitude less than this value are set to zero on export.
- `Mode` — Controls the display of a progress bar, either ieQuietRun or ieProgressRun.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_CannotWriteExportFile, ERR7_FileNotOpen,
ERR7_InvalidFileUnit, ERR7_InvalidFreedomCase,
ERR7_InvalidImportExportMode, ERR7_InvalidUnits,
ERR7_NoError, ERR7_ResultFileIsOpen, ERR7_UnknownSolver
```


---

### `St7ExportANSYSFile`

Exports the current Strand7 model as an ANSYS model file.

**Syntax**

```c
long St7ExportANSYSFile(long uID, char* FileName, long*
Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FileName` — Full path and name for the ANSYS file to be created.
- `Integers[0..8]` — [ipANSYSExportFormat] - Export format, one of ieANSYSBatch1Export, ieANSYSBatch3Export, ieANSYSBlockedCDBExport or ieANSYSUnblockedCDBExport. [ipANSYSFreedomCase] - Exported freedom case. [ipANSYSLoadCase] - Exported load case for pre-load and non-structural mass attributes. [ipANSYSUnits] Units for the exported file, one of anUnits_NoUnits, anUnits_kg_m_C, anUnits_g_cm_C, anUnits_T_mm_C, anUnits_sl_ft_F or anUnits_lbm_in_F. [ipANSYSEndRelease] Export partial beam end-release attributes, either ieANSYSEndReleaseFixed or ieANSYSEndReleaseFull.
