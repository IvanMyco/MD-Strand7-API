---
title: "Tools"
source: "Strand7 R246 API Manual"
pages: 970–974
---

# Tools

CaseNum
Result case number.

Brick
Brick number.

Quantity
Result quantity; one of rtBrickStress, rtBrickStrain, rtBrickNodeReact or
rtBrickFlux.
Output Parameters

Doubles[..]
An array defining the specified brick result quantity at each Gauss point on
the brick.
The results at the ith Gauss point are stored in a block starting at:

Doubles[(i-1)*kBrickResFileStressSize] - for rtBrickStress
Doubles[(i-1)*kBrickResFileStrainSize] - for rtBrickStrain.
Doubles[(i-1)*kBrickResFileReactSize] - for rtBrickNodeReact.
Doubles[(i-1)*kBrickResFileFluxSize] - for rtBrickFlux.
See Custom Results for additional information.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResFileInvalidCase,
ERR7_ResFileInvalidQuantity, ERR7_ResFileNotOpen,
ERR7_ResFileQuantityNotExist


---

### `St7ToolConvertPatchLoads`

Converts all load patches in a specified load case to distributed beam loads.

**Syntax**

```c
long St7ToolConvertPatchLoads(long uID, long CaseNum, bool
Overwrite)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `CaseNum` — Load case number.
- `Overwrite` — btTrue to overwrite the existing beam loads.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_NoError,
ERR7_NoPatchLoadsCreated, ERR7_ResultFileIsOpen
```


---

### `St7ToolAttachParts`

Generates attachment links based on the specified attachment attributes.

**Syntax**

```c
long St7ToolAttachParts(long uID, long* Integers, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..5]` — [ipDoEnds] - Attach beam ends, btTrue or btFalse. [ipDoEdges] - Attach plate edges, btTrue of btFalse. [ipDoFaces] - Attach brick/plate faces, btTrue or btFalse. [ipSelectedOnly] - Act on selected elements only, btTrue or btFalse. [ipDeleteExisting] - Delete existing attachments, btTrue or btFalse. [ipAllBrickFaces] - btTrue to attach to all brick faces, btFalse to attach only to free (exposed) brick faces.
- `Doubles[0..0]` — [ipAngleDelta] - Angle tolerance used when calculating attachment directions.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidAttachPartsParams,
ERR7_InvalidFileUnit, ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7ToolAlignBeamAxes`

Aligns the local beam axes with the axis of a specified UCS.

**Syntax**

```c
long St7ToolAlignBeamAxes(long uID, long BeamNum, long
BeamAxis, long BeamAxisType, long UCSAxis, long UCSId)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BeamNum` — Beam number to align.
- `BeamAxis` — The 1 or 2 local beam axis to align.
- `BeamAxisType` — Local beam axis type - axBeamLocal or axBeamPrincipal.
- `UCSAxis` — The 1,2 or 3 UCS axis to align with.
- `UCSId` — ID number for the UCS to align with.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidAxisSystem, ERR7_InvalidAxis,
ERR7_InvalidBeamAxisType, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_InvalidUCSID, ERR7_NoError,
ERR7_ResultFileIsOpen, ERR7_ToolOperationFailed
```


---

### `St7ToolAlignPlateAxes`

Aligns the local plates axes with the axis of a specified UCS.

**Syntax**

```c
long St7ToolAlignPlateAxes(long uID, long PlateNum, long
PlateAxis, long UCSAxis, long UCSId)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number to align.
- `PlateAxis` — The 1,2 or 3 local plate axis to align.
- `UCSAxis` — The 1,2 or 3 UCS axis to align with.
- `UCSId` — ID number of the UCS to align with.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidAxisSystem, ERR7_InvalidAxis,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidUCSID, ERR7_NoError, ERR7_ResultFileIsOpen,
ERR7_ToolOperationFailed
```


---

### `St7ToolPolygonToFace`

Converts one or more beam polygons to geometric faces. The beam elements
used in the conversion must be selected via the St7SetEntitySelectState function.

**Syntax**

```c
long St7ToolPolygonToFace(long uID, long* Integers, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..4]` — [ipPolyToFaceFaceID] - Face ID number for new faces. [ipPolyToFaceGroupIndex] - Group number for new faces. [ipPolyToFacePropertyNumber] - Plate property number for new faces. [ipPolyToFaceDeleteBeams] - Delete beams after conversion, either btTrue or btFalse. [ipPolyToFaceKeepSelected] - Keep beams selected, either btTrue or btFalse.
- `Doubles[0..0]` — [ipPolyToFaceEdgeTolerance] - Angle tolerance between adjacent polygon edges (degrees). Edges within tolerance may be smoothed via curve fitting.
