---
title: "Entities – Load Paths"
source: "Strand7 R246 API Manual"
pages: 206–208
---

# Entities – Load Paths

[ipMeshPositionUCS] - Location of the elements on the UCS 3 axis.
Loops[..]
[0] - the total number of loops in the polygon.
[1] - the number of points in the first loop in the polygon. This loop is always
the outer loop.

[2..1+Loop[1]] - a list of point indices defining the first loop.
[2+Loop[1]] - the number of points in the second loop of the polygon.
Then recursively, where Loop[k] contains the number of points in the ith loop;

[k+1..k+Loop[k]] - contains a list of point indices defining the ith loop
[k+Loop[k]+1] contains the number of points in the (i+1)th loop.
Points[..]
A list of the XY coordinates for the polygon points, with the X and Y
coordinates stored contiguously.

[2*j-2] - the X coordinate of point j.
[2*j-1] - the Y coordinate of point j.
Mode
Controls the display of a progress bar (ieQuietRun or ieProgressRun).
Errors

ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidFileUnit, ERR7_NoError,
ERR7_ResultFileIsOpen


---

### `St7SetLoadPath`

Sets the data for a load path in the specified model. A new load path is created
if a new load path ID is specified.

**Syntax**

```c
long St7SetLoadPath(long uID, long LoadPathID, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathID` — Load path ID number.
- `Integers[0..5]` — [ipLoadPathCase] - Load case number. [ipLoadPathTemplate] - Load path template number. [ipLoadPathShape] - Load path shape, one of lpShapeStraight, lpShapeCurved, lpShapeQuadratic. [ipLoadPathSurface] - Load path surface, either lpSurfaceFlat or lpSurfaceCurved. Note that this parameter is ignored when lpShapeStraight is set in Integers[ipLoadPathShape]. [ipLoadPathTarget] - Load path target entity, one of tyBEAM, tyPLATE, tyBRICK or tyNULL to target all entities. [ipLoadPathDivisions] - Number of divisions along the load path.
- `Doubles[0..8]` — [0..2] - The start XYZ point in the definition of the load path (defined in the global coordinate system). [3..5] - The end XYZ point in the definition of the load path. [6..8] - The lateral XYZ point in the definition of the load path, used to define the plane of the load path and its curvature (for circular load paths).

**Errors**

```
ERR7_APINotInitialised, ERR7_APINotLicensed,
ERR7_FileNotOpen, ERR7_InvalidEntity, ERR7_InvalidFileUnit,
ERR7_InvalidLoadCase, ERR7_InvalidLoadPathID,
ERR7_InvalidLoadPathShape, ERR7_InvalidLoadPathSurface,
ERR7_InvalidLoadPathTemplateID, ERR7_InvalidNumPathDivs,
ERR7_InvalidPathDefinition, ERR7_NoError,
ERR7_ResultFileIsOpen
```


---

### `St7GetLoadPath`

Returns the data assigned to the specified load path.

**Syntax**

```c
long St7GetLoadPath(long uID, long LoadPathID, long*
Integers, double* Doubles)
```

**Input Parameters**

- `uID` — Strand7 model file ID number.
- `LoadPathID` — Load path ID number.

**Output Parameters**

- `Integers[0..5]` — [ipLoadPathCase] - Load case number. [ipLoadPathTemplate] - Load path template number. [ipLoadPathShape] - Load path shape, one of lpShapeStraight, lpShapeCurved, lpShapeQuadratic. [ipLoadPathSurface] - Load path surface, either lpSurfaceFlat or lpSurfaceCurved. Note that this parameter is ignored when lpShapeStraight is set in Integers[ipLoadPathShape].
