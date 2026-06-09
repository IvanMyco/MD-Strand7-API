---
title: "Entities – Geometry"
source: "Strand7 R246 API Manual"
pages: 187–205
---

# Entities – Geometry

Entities – Nodes, Elements and Links
Factors for linked nodes, with the slave factor specified first.
Doubles[NumNodes] is used to specify the constant factor.
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_ExceededTotal, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_LinkNotMultiPoint, ERR7_NoError


---

### `St7GetVertexXYZ`

Returns the position of a specified vertex.

**Syntax**

```c
long St7GetVertexXYZ(long uID, long VertexNum, double* XYZ)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `VertexNum` — Vertex number.

**Output Parameters**

- `XYZ[0..2]` — The vertex position as a 3 element array, specifying the position according to the XYZ Cartesian convention in the Global Cartesian Coordinate system.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntityNumber,
ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7GetGeometryFaceOuterLoops`

Returns the outer loops in a specified geometry face, note that a geometry face
may have one or two outer loops only.

**Syntax**

```c
long St7GetGeometryFaceOuterLoops(long uID, long FaceNum,
long* OuterLoops)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — The specified face number.

**Output Parameters**

- `OuterLoops[0..1]` — [0] The loop number of the first outer loop. [1] The loop number of the second outer loop, zero if there is no such loop.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetNumGeometryFaceCavityLoops`

Returns the number of cavity loops in a specified geometry face.

**Syntax**

```c
long St7GetNumGeometryFaceCavityLoops(long uID, long
FaceNum, long* NumCavityLoops)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.

**Output Parameters**

- `NumCavityLoops` — Number of cavity loops in the specified face.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,


ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetGeometryFaceCavityLoops`

Returns the cavity loop numbers for a specified geometry face. Use
St7GetNumGeometryFaceCavityLoops to determinethe number of cavity loops
in the specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceCavityLoops(long uID, long FaceNum,
long MaxCavityLoops, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `MaxCavityLoops` — Maximum amount of storage allocated for Integers, returns all loops if set greater than or equal to NumCavityLoops.

**Output Parameters**

- `Integers[0..MaxCavityLoops-1]` — An array containing the cavity loop numbers for the specified face, such that Integers[i-1] contains the ith cavity loop number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetNumGeometryFaceEdges`

Returns the number of edges in a specified geometry face.

**Syntax**

```c
long St7GetNumGeometryFaceEdges(long uID, long FaceNum,
long* NumEdges)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.

**Output Parameters**

- `NumEdges` — Number of edges in the specified face.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetGeometryFaceEdges`

Returns the edge numbers for a specified geometry face. Use
St7GetNumGeometryFaceEdges to determine the number of edges in the
specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceEdges(long uID, long FaceNum, long
MaxEdges, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.
- `MaxEdges` — Maximum amount of storage allocated for Integers, returns all edges if set greater than or equal to NumEdges.

**Output Parameters**

- `Integers[0..MaxEdges-1]` — An array containing the edge numbers for the specified face, such that Integers[i-1] contains the ith edge number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetGeometryEdgeLength`

Returns the length of a specified edge in a given geometry face.

**Syntax**

```c
long St7GetGeometryEdgeLength(long uID, long EdgeNum,
double* EdgeLength)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.

**Output Parameters**

- `EdgeLength` — Length of the specified edge.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetNumGeometryFaceVertices`

Returns the number of vertices in a given geometry face.

**Syntax**

```c
long St7GetNumGeometryFaceVertices(long uID, long FaceNum,
long* NumVertices)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.

**Output Parameters**

- `NumVertices` — Number of vertices in the specified face.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetGeometryFaceVertices`

Returns the vertex numbers for a specified geometry face. Use
St7GetNumGeometryFaceVertices to determine the number of vertices for the
specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceVertices(long uID, long FaceNum,
long MaxVertices, long* Integers)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — The specified face number.
- `MaxVertices` — Maximum amount of storage allocated for Integers, returns all vertices if set greater than or equal to NumVertices.

**Output Parameters**

- `Integers[0..MaxVertices-1]` — An array containing the vertex numbers for the specified face, such that Integers[i-1] contains the ith vertex number.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetGeometryEdgeVertices`

Returns the vertex numbers in a specified geometry edge.

**Syntax**

```c
long St7GetGeometryEdgeVertices(long uID, long EdgeNum,
long* EdgeVertices)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `EdgeNum` — Edge number.

**Output Parameters**

- `EdgeVertices[0..1]` — A 2 element array containing the start and end vertices for the specified edge.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetGeometryFaceSurface`

Returns the surface number for a specified geometry face.

**Syntax**

```c
long St7GetGeometryFaceSurface(long uID, long FaceNum,
long* SurfaceNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number.

**Output Parameters**

- `SurfaceNum` — Surface number for the specified face.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7GetGeometrySurfaceType`

Returns the type of a specified surface.

**Syntax**

```c
long St7GetGeometrySurfaceType(long uID, long SurfaceNum,
long* SurfaceType)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `SurfaceNum` — The specified surface number.

**Output Parameters**

- `SurfaceType` — Type of surface, one of suPlane, suSphere, suTorus, suCone, suBSpline, suRotSur, suPipeSur, suSumSur, suTabCyl, suRuleSur or suCubicSpline.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError
```


---

### `St7InvalidateGeometryFace`

Marks a specified geometry face as invalid for subsequent deletion using the
St7DeleteInvalidGeometryFaces function.

**Syntax**

```c
long St7InvalidateGeometryFace(long uID, long FaceNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — Face number to invalidate.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7InvalidateGeometryFaceCavityLoopID`

Marks a specified cavity loop as invalid for subsequent deletion using the
St7DeleteInvalidGeometryFaces function. This function uses the loop ID number
to identify the appropriate loop.

**Syntax**

```c
long St7InvalidateGeometryFaceCavityLoopID(long uID, long
FaceNum, long LoopNum)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — The specified face number.
- `LoopNum` — The ID number of the loop to be marked for deletion.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidGeometryCavityLoop, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7InvalidateGeometryFaceCavityLoopIndex`

Marks a specified cavity loop as invalid for subsequent deletion using the
St7DeleteInvalidGeometryFaces function. This function uses the loop index
number to identify the appropriate loop.

**Syntax**

```c
long St7InvalidateGeometryFaceCavityLoopIndex(long uID,
long FaceNum, long LoopIndex)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `FaceNum` — The specified face number.
- `LoopIndex` — The index number of the loop to be marked for deletion.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_DataNotFound, ERR7_FileNotOpen,
ERR7_InvalidEntityNumber, ERR7_InvalidFileUnit,
ERR7_InvalidGeometryCavityLoop, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7DeleteInvalidGeometryFaces`

Deletes all invalid faces in a specified model.

**Syntax**

```c
long St7DeleteInvalidGeometryFaces(long uID, long*
NumFacesDeleted, long* NumCavityLoopsDeleted)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `NumFacesDeleted` — Number of faces deleted.
- `NumCavityLoopsDeleted` — Number of cavity loops deleted.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7SetCleanGeometryData`

Specifies the settings used when performing subsequent geometry clean
operations.

**Syntax**

```c
long St7SetCleanGeometryData(long uID, long* Integers,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..4]` — [ipGeometryAccuracyType] - Tolerance type, either ztRelative or ztAbsolute. [ipGeometryFeatureType] - Feature tolerance type, either ztRelative or ztAbsolute. [ipGeometryActOnWholeModel] - Perform clean on whole model, either btTrue or btFalse. [ipGeometryFreeEdgesOnly] - Act on free edges only, either btTrue or btFalse. [ipGeometryDuplicateFaces] - Duplicate face operation, one of dfGeometryLeave, dfGeometryDeleteOne, dfGeometryDeleteBoth.
- `Doubles[0..2]` — [ipGeometryAccuracy] - Tolerance value, scaled based on Integers[ipGeometryAccuracyType]. [ipGeometryFeatureLength] - Geometry feature length. [ipGeometryEdgeMergeAngle] - Merging angle for adjacent edges.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidDuplicateFaceType,
ERR7_InvalidFileUnit, ERR7_InvalidZipTolerance,
ERR7_InvalidZipType, ERR7_NoError
```


---

### `St7GetCleanGeometryData`

Retrieves the current settings used when performing a geometry clean operation.

**Syntax**

```c
long St7GetCleanGeometryData(long uID, long* Integers,
double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Integers[0..4]` — [ipGeometryAccuracyType] - Tolerance type, either ztRelative or ztAbsolute. [ipGeometryFeatureType] - Feature tolerance type, either ztRelative or ztAbsolute. [ipGeometryActOnWholeModel] - Perform clean on whole model, either btTrue or btFalse. [ipGeometryFreeEdgesOnly] - Act on free edges only, either btTrue or btFalse. [ipGeometryDuplicateFaces] - Duplicate face operation, one of dfGeometryLeave, dfGeometryDeleteOne, dfGeometryDeleteBoth.
- `Doubles[0..2]` — [ipGeometryAccuracy] - Tolerance value, scaled based on Integers[ipGeometryAccuracyType]. [ipGeometryFeatureLength] - Geometry feature length. [ipGeometryEdgeMergeAngle] - Merging angle for adjacent edges.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7CleanGeometry`

Performs a geometry clean operation on the geometry included in the specified
Strand7 model. Cleaning the geometry can be used to improve geometry
definitions and is typically recommended before subsequent geometry or
meshing operations are conducted. The operation includes a number of different
stages including: vertex and curve zipping, duplicate face processing, curve and
surface refitting and morphing.

**Syntax**

```c
long St7CleanGeometry(long uID, long* ChangesMade, long
Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Mode` — Controls the display of a progress bar (ieQuietRun or ieProgressRun).

**Output Parameters**

- `ChangesMade` — btTrue or btFalse.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetGeometrySize`

Retrieves the relative overall size of the geometry in the specified Strand7 model.
This size measure is used when scaling the relative geometry tolerance.

**Syntax**

```c
long St7GetGeometrySize(long uID, double* Size)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.

**Output Parameters**

- `Size` — Relative overall geometry size.

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError
```


---

### `St7SurfaceMesh`

Performs a surface meshing operation based on the geometry included in the
specified Strand7 model.

**Syntax**

```c
long St7SurfaceMesh(long uID, long* Integers, double*
Doubles, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..8]` — [ipSurfaceMeshMode] - Meshing mode, either mmAuto or mmCustom. [ipSurfaceMeshSizeMode] - Mesh size option, either smPercentage or smAbsolute. [ipSurfaceMeshTargetNodes] - Number of nodes in target element, one of 3, 4, 6 or 8. [ipSurfaceMeshTargetPropertyID] - Element property definition, one of -1 to use the face property, 0 to use the face number or >0 to use a constant property. [ipSurfaceMeshAutoCreateProperties] - Create properties as needed, either btTrue or btFalse. [ipSurfaceMeshMinEdgesPerCircle] - Minimum number of edges per circular edge. [ipSurfaceMeshApplyTransitioning] - Apply edge transitioning when placing boundary nodes, either btTrue or btFalse. [ipSurfaceMeshAllowUserStop] - Allow the user to terminate the meshing process, either btTrue or btFalse. [ipSurfaceMeshConsiderNearVertex] - Allow automesher to base element size on vertices near to, but not on, a surface, either btTrue or btFalse.
- `Doubles[0..3]` — [ipSurfaceMeshSize] - Mesh size, scaled based on Integers[ipSurfaceMeshSizeMode]. [ipSurfaceMeshLengthRatio] - Maximum allowable ratio between the largest and smallest edge on each face. [ipSurfaceMeshMaximumIncrease] - Rate of increase in edge length between neighbouring elements. [ipSurfaceMeshOnEdgesLongerThan] - Minimum curve length for the Min Edges per Circle parameter to be used.
- `Mode` — Controls the display of a progress bar (ieQuietRun or ieProgressRun).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit,
ERR7_InvalidSurfaceMeshTargetType, ERR7_MeshingErrors,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7SolidTetMesh`

Performs a solid meshing operation based on the surface mesh definitions
included in the specified Strand7 model. Surface mesh definitions can be
created using the St7SurfaceMesh function, but may also be created by other
means.

**Syntax**

```c
long St7SolidTetMesh(long uID, long* Integers, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..11]` — [ipTetraMeshSize] - Mesh size control, one of msFine, msMedium or msCoarse. [ipTetraMeshProperty] - Brick property number. [ipTetraMeshInc] - Brick property number increment for separate solid parts. [ipTetraMesh10] - Mesh using Tetra10 elements, either btTrue or btFalse. [ipTetraMeshGroupsAsSolids] - Mesh groups as solids, either btTrue or btFalse. [ipTetraMeshSmooth] - Smooth elements after meshing, either btTrue or btFalse. [ipTetraMeshAutoCreateProperties] - Create brick properties as needed. [ipTetraMeshDeletePlates] - Delete surface plates after meshing. [ipTetraMeshMultiBodyOption] - action when multiple bodies are detected, one of mbCancelMeshing, mbCavity or mbSeparateSolids. [ipTetraMeshAllowUserStop] - Allow the user to terminate the meshing process, either btTrue or btFalse. [ipTetraMeshCheckSelfIntersect] - Check for initial self intersections in the surface plate mesh, either btTrue or btFalse.
- `Mode` — Controls the display of a progress bar (ieQuietRun or ieProgressRun).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_MeshingErrors,
ERR7_NoError, ERR7_ResultFileIsOpen
```


---

### `St7MeshFromLoops`

Performs a surface meshing operation on a single face. The definition of this face
is specified explicitly using the array inputs for this function.

**Syntax**

```c
long St7MeshFromLoops(long uID, long* Integers, double*
Doubles, long* Loops, double* Points, long Mode)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `Integers[0..3]` — [ipMeshTargetNodes] - Number of nodes in the target element, one of 3, 4, 6 or 8. [ipMeshTargetPropertyID] - Plate property number for new elements. [ipMeshUCSID] - UCS ID number onto which the polygon is projected. [ipMeshGroupID] - Group ID number for new elements.
  Doubles[0..0]
