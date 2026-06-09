---
title: "Post-Processing"
source: "Strand7 R246 API Manual"
pages: 76–77
---

# Post-Processing

FileName
Full path and name of the text file containing the user defined contour values.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_FileNotFound,
ERR7_InvalidEntity, ERR7_NoError


---

### `St7GetEntityContourFile`

Returns the user defined contour file specified for beam, plate or brick elements.

**Syntax**

```c
long St7GetEntityContourFile(long uID, long Entity, long*
FileType, char* FileName, long MaxStringLen)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type to contour, one of tyBEAM, tyPLATE or tyBRICK.
- `MaxStringLen` — Maximum number of characters allocated for FileName.

**Output Parameters**

- `FileType` — Basis of the contour values, either ucNode or ucElement.
- `FileName` — Full path and name of the text file containing the user defined contour values.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_FileNotFound,
ERR7_InvalidEntity, ERR7_NoError
```


---

### `St7SetDisplacementScale`

Sets the Displacement Scale used to draw the deformed model, when an
associated model result file is open.

**Syntax**

```c
long St7SetDisplacementScale(long uID, double DispScale,
long ScaleType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `DispScale` — The scaling factor or percentage to be applied.
- `ScaleType` — The manner of scaling to be used, either dsPercent or dsAbsolute.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetDisplacementScale`

Returns the Displacement Scale used to draw the deformed model when an
associated model result file is open.

**Syntax**

```c
long St7GetDisplacementScale(long uID, double* DispScale,
long* ScaleType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number
