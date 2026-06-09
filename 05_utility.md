---
title: "Utility"
source: "Strand7 R246 API Manual"
pages: 27–46
---

# Utility

Initialisation and File Management
Maximum number of characters allocated for ErrorString.
Output Parameters

ErrorString
Error message string corresponding to iErr.
Errors


## ERR7_InvalidErrorCode, ERR7_NoError


---

### `St7GetSolverErrorString`

Returns the error message corresponding to a specified Strand7 solver error code.
Error codes corresponding to a Strand7 API error should be processed using the
St7GetAPIErrorString function described above.

**Syntax**

```c
long St7GetSolverErrorString(long iErr, char* ErrorString,
long MaxStringLen)
```

**Input Parameters**

- `iErr` — Strand7 solver error code.
- `MaxStringLen` — Maximum number of characters allocated for ErrorString.

**Output Parameters**

- `ErrorString` — Error message string corresponding to iErr.

**Errors**

```
ERR7_InvalidErrorCode, ERR7_NoError
```


---

### `St7TransformToUCS`

Transforms a position vector specified in the Global Cartesian coordinate system
to an arbitrary UCS.

**Syntax**

```c
long St7TransformToUCS(long uID, long UCSId, double* XYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — ID number for the specified UCS.

**Output Parameters**

- `XYZ[0..2]` — The position vector as a 3 element array. This array should initially hold the XYZ Global Cartesian position coordinates to be transformed. The transformed coordinates are returned in this array based on the 123 axis convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownUCS
```


---

### `St7TransformToXYZ`

Transforms a position vector specified in an arbitrary UCS to the Global Cartesian
coordinate system.

**Syntax**

```c
long St7TransformToXYZ(long uID, long UCSId, double* XYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — ID number for the specified UCS.

**Output Parameters**

- `XYZ[0..2]` — The position vector as a 3 element array. This array should initially hold the 123 axis position coordinates to be transformed. The transformed coordinates are returned in this array according to the XYZ Global Cartesian coordinate convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownUCS
```


---

### `St7VectorTransformToUCS`

Transforms a vector (e.g. force) specified in the Global Cartesian coordinate
system to an arbitrary UCS reference frame.

**Syntax**

```c
long St7VectorTransformToUCS(long uID, long UCSId, double*
Position, double* VXYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — ID number for the specified UCS.
- `Position[0..2]` — The position as a 3 element array. This array should hold the XYZ Global Cartesian position coordinates of the reference point of the vector to be transformed. The coordinates are not transformed by this function. If this is required, use St7TransformToUCS.

**Output Parameters**

- `VXYZ[0..2]` — The vector defined as a 3 element array. This array should initially hold the vector in the XYZ Global Cartesian system. The transformed vector is returned in this array based on the 123 axis convention.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownUCS
```


---

### `St7VectorTransformToXYZ`

Transforms a vector (e.g. force) specified in a User Coordinate System to the
Global Cartesian system.

**Syntax**

```c
long St7VectorTransformToXYZ(long uID, long UCSId, double*
Position, double* VXYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `UCSId` — ID number for the specified UCS.
- `Position[0..2]` — The position as a 3 element array. This array should hold the XYZ Global Cartesian position coordinates of the reference point of the vector to be transformed. The coordinates are not transformed by this function.

**Output Parameters**

- `VXYZ[0..2]` — The vector defined as a 3 element array. This array should initially hold the vector in the UCS reference frame. The transformed vector is returned in this array based on the Global Cartesian system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_UnknownUCS
```


---

### `St7SetCleanMeshData`

Specifies the settings used by the St7CleanMesh function.

**Syntax**

```c
long St7SetCleanMeshData(long uID, long* Integers, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..14]` — [ipMeshToleranceType] - Tolerance type, either ztAbsolute or ztRelative. [ipActOnWholeModel] - Clean whole model, either btTrue or btFalse. [ipZipNodes] - Clean nodes, either btTrue or btFalse. [ipRemoveDuplicateElements] - Remove duplicate elements, either btTrue or btFalse. [ipFixElementConnectivity] - Repair element connectivity, either btTrue or btFalse. [ipDeleteFreeNodes] - Delete unconnected nodes, either btTrue or btFalse. [ipDoBeams] - Act on beam elements, either btTrue or btFalse. [ipDoPlates] - Act on plate elements, either btTrue or btFalse. [ipDoBricks] - Act on bricks, either btTrue or btFalse. [ipDoLinks] - Act on links, either btTrue or btFalse. [ipZeroLengthLinks] - Allow zero length links, either btTrue or btFalse. [ipZeroLengthBeams] - Allow zero length beams, either btTrue or btFalse. [ipNodeAttributeKeep] - Keep attributes from nodes, either naLower or naHigher. [ipNodeCoordinates] - Move nodes, one of ncAverage, ncLowerNode, ncHigherNode or ncSelectedNode. [ipAllowDifferentProps] - Allow duplicate elements of different properties, either btTrue or btFalse.
- `Doubles[0..0]` — [ipMeshTolerance] - Zip tolerance, scaled based on Integers[ipMeshToleranceType].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidNodeCoordinateKeepType,
ERR7_InvalidZipTolerance, ERR7_InvalidZipType, ERR7_NoError
```


---

### `St7GetCleanMeshData`

Returns the current settings used by the St7CleanMesh function.

**Syntax**

```c
long St7GetCleanMeshData(long uID, long* Integers, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Integers[0..14]` — [ipMeshToleranceType] - Tolerance type, either ztAbsolute or ztRelative. [ipActOnWholeModel] - Clean whole model, either btTrue or btFalse. [ipZipNodes] - Clean nodes, either btTrue or btFalse. [ipRemoveDuplicateElements] - Remove duplicate elements, either btTrue or btFalse. [ipFixElementConnectivity] - Repair element connectivity, either btTrue or btFalse. [ipDeleteFreeNodes] - Delete unconnected nodes, either btTrue or btFalse. [ipDoBeams] - Act on beam elements, either btTrue or btFalse. [ipDoPlates] - Act on plate elements, either btTrue or btFalse. [ipDoBricks] - Act on bricks, either btTrue or btFalse. [ipDoLinks] - Act on links, either btTrue or btFalse. [ipZeroLengthLinks] - Allow zero length links, either btTrue or btFalse. [ipZeroLengthBeams] - Allow zero length beams, either btTrue or btFalse. [ipNodeAttributeKeep] - Keep attributes from nodes, either naLower or naHigher. [ipNodeCoordinates] - Move nodes, one of ncAverage, ncLowerNode, ncHigherNode or ncSelectedNode. [ipAllowDifferentProps] - Allow duplicate elements of different properties, either btTrue or btFalse.
- `Doubles[0..0]` — [ipMeshTolerance] - Zip tolerance, scaled based on Integers[ipMeshToleranceType].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7CleanMesh`

Performs a mesh cleaning operation on the Strand7 model using the current
settings specified via the St7SetCleanMeshData function.

**Syntax**

```c
long St7CleanMesh(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DeleteUnusedNodes`

Deletes the unused nodes in a Strand7 model. A node is unused if it is not
referenced by the connectivity of any element in the model.

**Syntax**

```c
long St7DeleteUnusedNodes(long uID, long* NumDeleted)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumDeleted` — Number of unused nodes deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7InvalidateElement`

Marks a specified element as invalid to be subsequently removed using the
St7DeleteInvalidElements function.

**Syntax**

```c
long St7InvalidateElement(long uID, long Entity, long
EltNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.
- `EltNum` — Element number to invalidate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7DeleteInvalidElements`

Deletes all elements marked as invalid from a Strand7 model.

**Syntax**

```c
long St7DeleteInvalidElements(long uID, long Entity, long*
NumDeleted)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Strand7 entity type, one of tyNODE, tyBEAM, tyPLATE, tyBRICK, tyLINK, tyVERTEX, tyGEOMETRYEDGE, tyGEOMETRYFACE or tyLOADPATH.

**Output Parameters**

- `NumDeleted` — Number of entities deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetPlateUV`

Returns the local plate UV coordinates corresponding to an XYZ position. The XYZ
position should be located approximately on the surface of the element.

**Syntax**

```c
long St7GetPlateUV(long uID, long PlateNum, double* XYZ,
double* UV)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `PlateNum` — Plate number.
- `XYZ[0..2]` — A 3 element array containing coordinates of the point in the Global Cartesian Coordinate system.

**Output Parameters**

- `UV[0..1]` — A 2 element array containing the local UV plate coordinates.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetBrickUVW`

Returns the local brick UVW coordinates corresponding to an XYZ position. The
XYZ position should be located approximately within the brick.

**Syntax**

```c
long St7GetBrickUVW(long uID, long BrickNum, double* XYZ,
double* UVW)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `BrickNum` — Brick number.
- `XYZ[0..2]` — A 3 element array containing coordinates of the point in the Global Cartesian Coordinate system.

**Output Parameters**

- `UVW[0..2]` — A 3 element array containing the local brick UVW coordinates. See Brick Local Coordinates for further information.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetNumElementResultGaussPoints`

Returns the number of Gauss points used to store result quantities for a specified
entity type.

**Syntax**

```c
long St7GetNumElementResultGaussPoints(long uID, long
Entity, long NumNodes, long* NumGauss)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Entity type, either tyPLATE or tyBRICK.
- `NumNodes` — Number of nodes for the element type.

**Output Parameters**

- `NumGauss` — Number of result Gauss points.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity,
ERR7_InvalidEntityNodes, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7ConvertElementResultNodeToGaussPoint`

Converts element nodal results to Gauss point results via interpolation. It is
important to specify the un-averaged nodal quantities in order to capture the
true element Gauss point values.

**Syntax**

```c
long St7ConvertElementResultNodeToGaussPoint(long uID, long
Entity, long NumNodes, long NumColumns, double*
NodeDoubles, long* NumGauss, double* GaussDoubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Entity` — Entity type, either tyPLATE or tyBRICK.
- `NumNodes` — Number of nodes in the element.
- `NumColumns` — Number of result quantities contained in the NodeDoubles array.
- `NodeDoubles[0..NumNodes*NumColumns-1]` — An array containing the elemental nodal result quantities, arranged in blocks of length NumColumns. The start of the ith block, relating to the ith node in the element’s definition, is at NodeDoubles[(i-1)*NumColumns].

**Output Parameters**

- `NumGauss` — Number of result Gauss points for the element; a maximum of 9 for tyPLATE, or 27 for tyBRICK.
- `GaussDoubles[0..NumGauss*NumColumns-1]` — An array containing the interpolated Gauss point result quantities, arranged in blocks of length NumColumns. The start of the ith block, relating to the ith Gauss point in the element’s definition, is at GaussDoubles[(i-1)*NumColumns].

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_ExceededMaxNumColumns, ERR7_FileNotOpen,
ERR7_InvalidEntity, ERR7_InvalidEntityNodes,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetResultOptions`

Sets the Results Options for the specified model.

**Syntax**

```c
long St7SetResultOptions(long uID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..6]` — [ipResOptsBeamEnvelope] - Beam envelope results, either beLocal or bePrincipal. [ipResOptsRotationUnit] - Rotation units for model window output, either ipRadian or ipDegree. By default this setting is ignored by the Strand7 API, see St7EnableModelRotationUnit. [ipResOptsHRADisplacement] - Harmonic Response displacement results, either hrRelative or hrTotal. [ipResOptsHRAVelocity] - Harmonic Response velocity results, either hrRelative or hrTotal. [ipResOptsHRAAcceleration] - Harmonic Response acceleration results, either hrRelative or hrTotal. [ipResOptsStageDisplacement] - Stage displacement results, either sdBirthStage or sdInitial. [ipResOptsStrainUnit] - Strain unit, one of suUnit, suPercent or suMicro. By default this setting is ignored by the Strand7 API, see St7EnableModelStrainUnit.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidResOptsBeamEnvelope,
ERR7_InvalidResOptsHRASetting,
ERR7_InvalidResOptsRotationUnit,
ERR7_InvalidResOptsStageDisplacement,
ERR7_InvalidResOptsStrainUnit, ERR7_NoError
```


---

### `St7GetResultOptions`

Returns the Results Options for the specified model.

**Syntax**

```c
long St7GetResultOptions(long uID, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Integers[0..6]` — [ipResOptsBeamEnvelope] - Beam envelope results, either beLocal or bePrincipal. [ipResOptsRotationUnit] - Rotation units for model window output, either ipRadian or ipDegree. By default this setting is ignored by the Strand7 API, see St7EnableModelRotationUnit. [ipResOptsHRADisplacement] - Harmonic Response displacement results, either hrRelative or hrTotal. [ipResOptsHRAVelocity] - Harmonic Response velocity results, either hrRelative or hrTotal. [ipResOptsHRAAcceleration] - Harmonic Response acceleration results, either hrRelative or hrTotal. [ipResOptsStageDisplacement] - Stage displacement results, either sdBirthStage or sdInitial. [ipResOptsStrainUnit] - Strain unit, one of suUnit, suPercent or suMicro. By default this setting is ignored by the Strand7 API, see St7EnableModelStrainUnit.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SetToolOptions`

Sets the tool options for the specified model.

**Syntax**

```c
long St7SetToolOptions(long uID, long* Integers, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..13]` — [ipToolOptsElementTolType] - Element tolerance type, either ztAbsolute or ztRelative. [ipToolOptsGeometryAccuracyType] - Geometry accuracy type, either ztAbsolute or ztRelative. [ipToolOptsGeometryFeatureType] - Geometry feature length type, either ztAbsolute or ztRelative. [ipToolOptsZipMesh] - Mesh zipping, one of zmAsNeeded, zmOnSave or zmOnRequest. [ipToolOptsNodeCoordinate] - New node coordinates, one of ncAverage, ncLowerNode, ncHigherNode or ncSelectedNode. [ipToolOptsNodeAttributeKeep] - Attribute keep, one of naLower, naHigher or naAccumulate. [ipToolOptsAllowZeroLengthLinks] - Allow zero length links, either btTrue or btFalse. [ipToolOptsAllowZeroLengthBeams] - Allow zero length beams, either btTrue or btFalse. [ipToolOptsAllowSameProperty] - Allow duplicates of a different property, either btTrue or btFalse. [ipToolOptsCompatibleTriangle] - Compatible triangle faces, either btTrue or btFalse. [ipToolOptsSubdivideBeams] - Subdivide only normal beams, either btTrue or btFalse. [ipToolOptsPlateAxisAlign] - Axis alignment, either paCentroid or paCurvilinear. [ipToolOptsCopyMode] - Copy mode, either cmRoot or cmSibling. [ipToolOptsAutoCreateProperties] - Auto create new properties, either btTrue or btFalse.
- `Doubles[0..2]` — [ipToolOptsElementTol] - Element zip tolerance. [ipToolOptsGeometryAccuracy] - Geometry accuracy. [ipToolOptsGeometryFeatureLength] - Geometry feature length.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidToleranceType, ERR7_InvalidToolOptsCopyOptions,
ERR7_InvalidToolOptsSubdivideOptions,
ERR7_InvalidToolOptsZipOptions, ERR7_InvalidZipTolerance,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7GetToolOptions`

Returns the tool options assigned to the specified model.

**Syntax**

```c
long St7GetToolOptions(long uID, long* Integers, double*
Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Integers` — [ipToolOptsElementTolType] - Element tolerance type, either ztAbsolute or ztRelative. [ipToolOptsGeometryAccuracyType] - Geometry accuracy type, either ztAbsolute or ztRelative. [ipToolOptsGeometryFeatureType] - Geometry feature length type, either ztAbsolute or ztRelative. [ipToolOptsZipMesh] - Mesh zipping, one of zmAsNeeded, zmOnSave or zmOnRequest. [ipToolOptsNodeCoordinate] - New node coordinates, one of ncAverage, ncLowerNode, ncHigherNode or ncSelectedNode. [ipToolOptsNodeAttributeKeep] - Attribute keep, one of naLower, naHigher or naAccumulate. [ipToolOptsAllowZeroLengthLinks] - Allow zero length links, either btTrue or btFalse. [ipToolOptsAllowZeroLengthBeams] - Allow zero length beams, either btTrue or btFalse. [ipToolOptsAllowSameProperty] - Allow duplicates of a different property, either btTrue or btFalse. [ipToolOptsCompatibleTriangle] - Compatible triangle faces, either btTrue or btFalse. [ipToolOptsSubdivideBeams] - Subdivide only normal beams, either btTrue or btFalse. [ipToolOptsPlateAxisAlign] - Axis alignment, either paCentroid or paCurvilinear. [ipToolOptsCopyMode] - Copy mode, either cmRoot or cmSibling. [ipToolOptsAutoCreateProperties] - Auto create new properties, either btTrue or btFalse.
- `Doubles` — [ipToolOptsElementTol] - Element zip tolerance. [ipToolOptsGeometryAccuracy] - Geometry accuracy. [ipToolOptsGeometryFeatureLength] - Geometry feature length.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7EnableModelStrainUnit`

Allows the strain units set by St7SetResultOptions to override the report of absolute
strains, which is the API default.

**Syntax**

```c
long St7EnableModelStrainUnit(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7DisableModelStrainUnit`

Restores the API default report of absolute strains, overriding the strain units set by
St7SetResultOptions.

**Syntax**

```c
long St7DisableModelStrainUnit(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableModelRotationUnit`

Allows the rotation units set by St7SetResultOptions to override the report of
rotation in radians, which is the API default.

**Syntax**

```c
long St7EnableModelRotationUnit(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7DisableModelRotationUnit`

Restores the API default report of rotations in radians, overriding the rotation units
set by St7SetResultOptions.

**Syntax**

```c
long St7DisableModelRotationUnit(long uID)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7EnableModelRCUnit`

Allows the length and area units set by St7SetRCUnits to override the report of
plate RC results in consistent model units, which is the API default.
